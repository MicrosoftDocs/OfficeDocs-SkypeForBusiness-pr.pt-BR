---
title: Implantar aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015. O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604218"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implantar aparência de linha compartilhada no Skype for Business Server 2015

Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015. O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.

Para obter mais informações sobre esse recurso, consulte [Plan for Shared line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

A aparência de linha compartilhada (SLA) é um novo recurso no Skype for Business Server, atualização cumulativa de novembro de 2015. Para habilitar esse recurso, primeiro você deve implantar esta atualização cumulativa.

### <a name="install-shared-line-appearance"></a>Instalar a aparência da linha compartilhada

1. Após o Skype for Business Server, a atualização cumulativa de novembro de 2015 é `SkypeServerUpdateInstaller.exe` implantada, execute o patch em cada servidor de front-end no pool.

2. O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão. Ele é habilitado seguindo as etapas descritas abaixo:

    a. Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   em que% FQDN% é o nome de domínio totalmente qualificado do pool.

    b. Execute o seguinte comando para atualizar as funções RBAC para os cmdlets de SLA:

   ```powershell
   Update-CsAdminRole
   ```

    c. Reinicie todos os servidores front-end (serviço RTCSRV) em todos os pools em que o SLA foi instalado e habilitado:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Criar um grupo de SLA e adicionar usuários a ele

1. Crie o grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    O cmdlet Set-CsSlaConfiguration marca a conta do Enterprise Voice SLAGroup1 como uma entidade SLA e o número de SLAGroup1 se torna o número do grupo SLA. Todas as chamadas para o SLAGroup1 tocarão todo o grupo de SLA.

    O exemplo a seguir cria um grupo de SLA para um usuário existente do Enterprise Voice, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número principal de SLA.

    O comando define o número máximo de chamadas simultâneas para o novo grupo de SLA como 3 e para as chamadas que excedem o sinal de ocupado:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Você pode usar set-CsSlaConfiguration para criar um novo grupo de SLA ou modificar um existente.

    > [!NOTE]
    > Observe que o que você especificar `-Identity` para deve ser uma conta de usuário válida habilitada para Enterprise Voice.

2. Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    O exemplo a seguir adiciona um usuário ao grupo SLA. Cada usuário adicionado ao grupo deve ser um usuário habilitado para Enterprise Voice válido:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários só podem pertencer a um único grupo de SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configurar a opção ocupado do grupo de SLA

- Configure a opção ocupado do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234. O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe da pessoa que receberá as chamadas encaminhadas será o mesmo que quando você especificar um representante: `sip:<NameofDelegate@domain>`. O outro parâmetro possível para `BusyOption` é `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configurar a opção de chamada perdida do grupo de SLA

1. Configure a opção de chamada perdida do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o `sla_forward_number`usuário chamado. As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`. Se escolher `Forward`, você também deve incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Remover um representante de um grupo

- Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por exemplo:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Excluir um grupo de SLA

- Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por exemplo:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


