---
title: Implantar a aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leia este tópico para saber como implantar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. SLA é um recurso para lidar com várias chamadas em um número específico chamado número compartilhado.
ms.openlocfilehash: 5adf5934e93bd93fe9f50c0a8e4dd790c695da57
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397481"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implantar a aparência de linha compartilhada no Skype for Business Server 2015

Leia este tópico para saber como implantar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. SLA é um recurso para lidar com várias chamadas em um número específico chamado número compartilhado.

Para obter mais informações sobre esse recurso, consulte [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Aparência de linha compartilhada (SLA) é um novo recurso Skype for Business Server atualização cumulativa de novembro de 2015. Para habilitar esse recurso, você deve ter implantado primeiro essa atualização cumulativa.

### <a name="install-shared-line-appearance"></a>Instalar a aparência de linha compartilhada

1. Após Skype for Business Server, a Atualização Cumulativa de novembro de 2015 é implantada, `SkypeServerUpdateInstaller.exe` execute o patch em cada Servidor Front-End no pool.

2. O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão. Ele é habilitado seguindo as etapas descritas abaixo:

    a. Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   onde %FQDN% é o nome de domínio totalmente qualificado do pool.

    b. Execute o seguinte comando para atualizar as funções RBAC dos cmdlets SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Reinicie todos os Servidores front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e habilitado:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Criar um grupo SLA e adicionar usuários a ele

1. Crie o grupo SLA usando o cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    O cmdlet Set-CsSlaConfiguration marca o SLAGroup1 da conta Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 se torna o número do grupo SLA. Todas as chamadas para SLAGroup1 tocarão todo o grupo SLA.

    O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número de linha principal do SLA.

    O comando define o número máximo de chamadas simultâneas para o novo grupo SLA como 3 e para chamadas em excesso ouvirem um sinal de ocupado:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Você pode usar Set-CsSlaConfiguration para criar um novo grupo SLA ou modificar um existente.

    > [!NOTE]
    > Observe que o que você especificar deve `-Identity` ser uma conta de usuário Enterprise Voice habilitada para uso.

2. Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    O exemplo a seguir adiciona um usuário ao grupo SLA. Cada usuário adicionado ao grupo deve ser um usuário Enterprise Voice habilitado para uso válido:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários só podem pertencer a um único grupo SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurar a opção de ocupado do grupo SLA

- Configure a Opção de Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234. O destino pode ser um usuário em sua organização em vez de um número de telefone; nesse caso, a sintaxe para a pessoa receber as chamadas encaminhadas é a mesma que quando você especifica um representante:  `sip:<NameofDelegate@domain>`. O outro parâmetro possível para  `BusyOption` é `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurar a opção de chamada perdida do grupo SLA

1. Configure a opção de chamada perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o usuário chamado  `sla_forward_number`. As opções válidas para o  `-MissedCallOption` parâmetro são `Forward`,  `BusySignal`ou  `Disconnect`. Se você escolher  `Forward`, também deverá incluir o  `-MissedCallForwardTarget` parâmetro, com um usuário ou número de telefone como o destino:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Remover um representante de um grupo

- Remova um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por exemplo:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Excluir um grupo SLA

- Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por exemplo:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```