---
title: Habilitar usuários para o Enterprise Voice online e a caixa postal do sistema de telefonia
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Saiba como habilitar os serviços de voz do sistema de telefonia para seus usuários do Skype for Business.
ms.openlocfilehash: 522da56969f851280812670692a27d94e4df09a8
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221101"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Habilitar usuários para o Enterprise Voice online e a caixa postal do sistema de telefonia
 
Saiba como habilitar os serviços de voz do sistema de telefonia para seus usuários do Skype for Business.
  
A etapa final na implantação do sistema de telefonia com conectividade PSTN local é habilitar os usuários para o sistema de telefonia e caixa postal. Para habilitar esses recursos, você deve ser um usuário com a função de administrador global e poder executar o PowerShell remoto. Você precisa seguir as etapas deste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business online.
  
## <a name="enable-phone-system-voice-services"></a>Habilitar serviços de voz do sistema de telefonia

Para habilitar um usuário para voz e caixa postal do sistema de telefonia, você precisará executar algumas etapas iniciais, como verificar se o conector do Skype for Business online está implantado nos seus servidores e habilitar os usuários para caixa postal hospedada.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Para habilitar os usuários para voz e caixa postal do sistema de telefonia

1. Antes de começar, verifique se o conector do Skype for Business online (módulo do Windows PowerShell) está implantado em seus servidores front-end. Caso contrário, você pode baixá-lo do [centro de download](https://www.microsoft.com/download/details.aspx?id=39366). Você pode encontrar mais informações sobre como usar esse módulo em [Configurando o computador para o gerenciamento do Skype for Business online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).
    
2. Inicie o Windows PowerShell como administrador.
    
3. Digite o seguinte e pressione ENTER:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Digite o seguinte e pressione ENTER:
    
   ```powershell
   $cred = Get-Credential
   ```

    Após pressionar Enter, você deverá ver a caixa de diálogo de credenciais do Windows PowerShell.
    
5. Digite o nome de usuário e a senha do administrador do locatário e clique em **OK**.
    
6. Na janela do PowerShell, digite o seguinte e pressione ENTER:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importe a sessão digitando o seguinte cmdlet:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Ao executar o PowerShell em um Skype for Business Server, os cmdlets locais do Skype for Business já estão carregados quando você abre o PowerShell. Você deve especificar o parâmetro-AllowClobber para permitir que os cmdlets online substituam os cmdlets locais com o mesmo nome.
    
8. Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao seu usuário da seguinte maneira:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por exemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Você também pode especificar um usuário pelo endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio \ nomedeusuário) e nome de exibição no Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia

Esta seção descreve como atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia. 
  
### <a name="to-update-the-line-uri"></a>Para atualizar o URI da linha

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu iniciar ou o atalho da área de trabalho para abrir o painel de controle do Skype for Business Server.
    
    > [!NOTE]
    > Você também pode abrir uma janela do navegador e, em seguida, inserir a URL do administrador para abrir o painel de controle do Skype for Business Server. 
  
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business que você deseja alterar o URI da linha.
    
6. Clique em **URI de linha**e digite um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200). Em seguida, clique em **confirmar**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Atualizar o plano de discagem usando cmdlets do Windows PowerShell no local

Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Você pode executar esse cmdlet do Skype for Business Server 2015 ou de uma sessão remota do Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para atribuir um plano de discagem por usuário a um único usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para atribuir um plano de discagem por usuário a vários usuários

- O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Você pode usar planos de discagem globais ou de usuário para usuários online. Os planos de discagem de site não podem ser usados, pois eles se aplicam a usuários que estão hospedados no local e são atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para cancelar a atribuição de um plano de discagem por usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar a atribuição de qualquer plano de discagem por usuário anteriormente atribuído a Ken Myer. Após o plano de discagem por usuário não ser atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global ou o plano de discagem de escopo de serviço atribuído ao seu registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local

Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema de telefonia.
  
Os usuários do sistema de telefonia precisam ter uma política de roteamento de voz atribuída a eles para que as chamadas sejam roteadas com êxito. Isso difere dos usuários do Business Voice no local que exigem que uma política de voz seja atribuída a eles para permitir que as chamadas sejam roteadas com êxito. A política de roteamento de voz deve conter usos de PSTN que definem chamadas e rotas autorizadas para usuários de sistema de telefonia. Você pode copiar esses usos de PSTN de políticas de voz existentes para novas políticas de roteamento de voz. Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos os usuários do sistema telefônico recebem a mesma política de voz online chamada Businessvoice,, que define os recursos de chamada permitidos; por exemplo, permita o toque simultâneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para atribuir uma política de roteamento de voz por usuário a um único usuário

- Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para atribuir uma política de roteamento de voz por usuário a vários usuários

- O próximo comando atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Você pode usar políticas globais ou de roteamento de voz do usuário para usuários online. As políticas de roteamento de voz do site não podem ser usadas, pois elas só se aplicam a usuários hospedados no local e são atribuídas a um site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para cancelar a atribuição de uma política de roteamento de voz por usuário

- Use o Grant-CsVoiceRoutingPolicy para cancelar a atribuição de qualquer política de roteamento de voz por usuário anteriormente atribuída a Ken Myer. Depois que a política de roteamento de voz por usuário é desatribuída, Ken Myer será automaticamente gerenciado usando a política de roteamento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

