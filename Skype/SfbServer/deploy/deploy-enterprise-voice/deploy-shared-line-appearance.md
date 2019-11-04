---
title: Implantar Aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leia este tópico para aprender como implantar a Aparência de linha compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.
ms.openlocfilehash: 040801c08490edb103fa195098ef8aa3483fc2e0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924852"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Implantar Aparência de linha compartilhada no Skype for Business Server 2015

Leia este tópico para aprender como implantar a Aparência de linha compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.

Para obter mais informações sobre esse recurso, consulte [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

A aparência da linha compartilhada (SLA) é um novo recurso no Skype for Business Server, atualização cumulativa de novembro de 2015. Para habilitar este recurso, você deve primeiro ter implantado essa atualização cumulativa.

### <a name="install-shared-line-appearance"></a>Instalar Aparência de Linha Compartilhada

1. Após o Skype for Business Server, a atualização cumulativa de novembro de 2015 é `SkypeServerUpdateInstaller.exe` implementada, executa o patch em cada servidor front-end do pool.

2. O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão. Ele será habilitado quando as etapas descritas abaixo forem seguidas:

    a. Registrar SLA como um aplicativo de servidor executando o seguinte comando para cada pool:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   onde %FQDN% é o nome de domínio totalmente qualificado do pool.

    b. Execute o seguinte comando para atualizar as funções do RBAC para cmdlets de SLA:

   ```
   Update-CsAdminRole
   ```

    c. Reiniciar todos os Servidores Front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e ativado:

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Criar um grupo SLA e adicionar usuários a ele

1. Criar o grupo SLA utilizando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    O cmdlet Set-Cs SlaConfiguration marca a conta SLAGroup1 da conta do Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 transforma-se no número para o grupo SLA. Todas as chamadas para SLAGroup1 tocarão no grupo SLA inteiro.

    O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1 e usa o número atribuído para SLAGroup1 como número principal de SLA.

    O comando define o número máximo de chamadas simultâneas para o novo grupo SLA em 3, e chamadas além desse número ouvirão um sinal de ocupado:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Você pode usar Set-Cs SlaConfiguration para criar um novo grupo SLA ou modificar um existente.

    > [!NOTE]
    > Observe que o que você especificar `-Identity` para deve ser uma conta de usuário válida habilitada para Enterprise Voice.

2. Adicionar representantes ao grupo utilizando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps):

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    O exemplo a seguir adiciona um usuário ao grupo SLA. Cada usuário adicionado ao grupo deve ser um usuário habilitado para o Enterprise Voice habilitado:

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários podem somente pertencer a um único grupo SLA.

### <a name="configure-the-sla-group-busy-option"></a>Configuração da Opção Ocupado do grupo SLA

- Configurar a Opção Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    O exemplo a seguir define que as chamadas excedendo o número máximo de chamadas simultâneas serão encaminhadas ao número de telefone 202-555-1234. O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe para a pessoa que receber as chamadas encaminhadas é a mesma que quando você especifica um representante: `sip:<NameofDelegate@domain>`. O outro parâmetro possível para `BusyOption` é `Voicemail`:

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Configuração da Opção de Chamada perdida do grupo SLA

1. Configurar a Opção de Chamada Perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. O exemplo a seguir especifica que as chamadas perdidas serão encaminhadas para o usuário `sla_forward_number`chamado. As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`. Se você escolher `Forward`, também deverá incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Remover um representante de um grupo

- Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps):

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Por exemplo:

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Excluir um grupo SLA

- Excluir um grupo SLA utilizando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Por exemplo:

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


