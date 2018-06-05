---
title: Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Aprenda a habilitar o sistema telefônico nos serviços de voz do Office 365 para sua Skype para usuários comerciais.
ms.openlocfilehash: 7855fd7cdb2bfd30b99bf6ad17543e7aea973a6b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569558"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365
 
Aprenda a habilitar o sistema telefônico nos serviços de voz do Office 365 para sua Skype para usuários comerciais.
  
Implantar o sistema telefônico no Office 365 com conectividade PSTN de local a etapa final é habilitar os usuários para o sistema telefônico no Office 365 e caixa postal. Para isso, você precisa ter a função Administrador Global do Office 365 e estar habilitado para a execução remota do PowerShell. Siga as etapas neste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Habilitar o sistema telefônico nos serviços de voz do Office 365

Para habilitar um usuário para o sistema telefônico no Office 365 Voice e caixa postal, você precisará executar algumas etapas iniciais, como verificação vejam do Skype para Business Connector Online é implantado em seus servidores e permitir que os usuários para caixa postal hospedada.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Para habilitar os usuários para o sistema telefônico no correio de voz e voz do Office 365

1. Antes de começar, verifique se o Skype para Business Online Connector (módulo do Windows PowerShell) é implantado em seus servidores Front-End. Se não for, você pode baixá-lo no [Centro de download](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Você pode encontrar mais informações sobre como usar este módulo em [Configurando o seu computador e Skype para gerenciamento de negócios Online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Inicie o Windows PowerShell como um administrador.
    
3. Digite o seguinte e pressione Enter:
    
  ```
  Import-Module skypeonlineconnector
  ```

4. Digite o seguinte e pressione Enter:
    
  ```
  $cred = Get-Credential
  ```

    Após pressionar Enter, a caixa de diálogo Credenciais do Windows PowerShell será exibida.
    
5. Digite seu nome de usuário e sua senha de administrador de locatário e clique em **OK**.
    
6. Na janela do PowerShell, digite o seguinte e pressione Enter:
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. Importe a sessão digitando o seguinte cmdlet:
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    Ao executar o PowerShell em um Skype para Business Server, o local Skype para negócios cmdlets já estão carregados quando você abre o PowerShell. Você deve especificar o parâmetro - AllowClobber para permitir que os cmdlets on-line substituir os cmdlets no local com o mesmo nome.
    
8. Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao usuário, como a seguir:
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    Por exemplo:
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > Você também pode especificar um usuário pelo endereço SIP, nome de Usuário Principal (UPN), nome de domínio e nome e usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Atualizar o URI de linha e discagem plano para usuários habilitados para o sistema telefônico no Office 365

Esta seção descreve como atualizar o URI de linha e plano para usuários habilitados para o sistema telefônico no Office 365 de discagem. 
  
### <a name="to-update-the-line-uri"></a>Atualizar o URI da Linha

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Utilize o menu Iniciar ou o atalho na área de trabalho para abrir o Painel de Controle do Skype for Business Server.
    
    > [!NOTE]
    > Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
  
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business da qual deseja alterar o URI da linha.
    
6. Clique em **URI da Linha**, digite um número de telefone único e normalizado (por exemplo, tel:+14255550200) e, em seguida, clique em **Confirmar**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Atualizar o plano de discagem usando cmdlets do Windows PowerShell local

Você pode atribuir os planos de discagem com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para por usuário. Você pode executar esse cmdlet do Skype para Business Server 2015 ou de uma sessão remota do Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Atribuir um plano de discagem por usuário a um único usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Atribuir um plano de discagem por usuário a vários usuários

- Esse comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usada nesse comando, consulte a documentação para o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Você pode usar planos de discagem globais ou do usuário para usuários online. Planos de discagem locais não podem ser usados, pois se aplicam somente a usuários hospedados no local e são atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Retirar a atribuição de uma plano de discagem por usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para retirar a atribuição de qualquer plano de discagem por usuário previamente atribuído a Ken Myer. Depois que a atribuição do plano de discagem por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso do plano de discagem global ou do plano de discagem de escopo de serviço atribuído ao seu Registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local

Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema telefônico no Office 365.
  
O sistema telefônico em usuários do Office 365 deve ter uma política de roteamento de voz atribuída a eles para chamadas rotear com êxito. É diferente dos usuários de voz de negócios locais, que exigem que uma política de voz seja atribuída a eles para permitir o roteamento bem-sucedido das chamadas. A política de roteamento de voz deve conter os usos de PSTN que definem chamadas autorizadas e rotas para o sistema telefônico no usuários do Office 365. Você pode copiar esses usos de PSTN de Políticas de voz existentes para as novas Políticas de roteamento de voz. Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos os sistema telefônico no Office 365 usuários recebem a mesma política de voz online chamado BusinessVoice que define os recursos de chamada permitidos; Por exemplo, permitir que o toque simultâneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para atribuir uma política de roteamento de voz por usuário a um único usuário

- Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz RedmondVoiceRoutingPolicy por usuário ao usuário Ken Myer:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para atribuir uma política de roteamento de voz por usuário a vários usuários

- O comando a seguir atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usada nesse comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Você pode usar políticas de roteamento de voz globais ou do usuário para usuários online. Políticas de roteamento de voz locais não podem ser usadas, pois se aplicam somente a usuários hospedados no local e são atribuídas a um site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para retirar a atribuição de uma política de roteamento de voz por usuário

- Use o Grant-CsVoiceRoutingPolicy para retirar a atribuição de qualquer política roteamento de voz por usuário previamente atribuída a Ken Myer. Depois que a atribuição da política de roteamento de voz por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso da política de roteamento de voz global.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

