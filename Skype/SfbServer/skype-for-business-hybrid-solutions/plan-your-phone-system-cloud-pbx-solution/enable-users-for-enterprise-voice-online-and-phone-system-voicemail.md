---
title: Habilitar os usuários do Enterprise Voice online e do Sistema de Telefone na Caixa Postal do Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Saiba como habilitar o sistema telefônico nos serviços de voz do Office 365 para seus usuários do Skype for Business.
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003461"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Habilitar os usuários do Enterprise Voice online e do Sistema de Telefone na Caixa Postal do Office 365
 
Saiba como habilitar o sistema telefônico nos serviços de voz do Office 365 para seus usuários do Skype for Business.
  
A etapa final em Implantando o sistema telefônico no Office 365 com conectividade PSTN local é habilitar seus usuários para o sistema telefônico no Office 365 e correio de voz. Para isso, você precisa ter a função Administrador Global do Office 365 e estar habilitado para a execução remota do PowerShell. Siga as etapas neste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Habilitar o sistema telefônico nos serviços de voz do Office 365

Para habilitar um usuário para o sistema telefônico no Office 365 voz e correio de voz, você precisará realizar algumas etapas iniciais, como verificar se o conector do Skype for Business online está implantado em seus servidores e habilitar os usuários do correio de voz hospedado.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Para habilitar os usuários do sistema telefônico no Office 365 voz e correio de voz

1. Antes de começar, verifique se o conector do Skype for Business online (módulo do Windows PowerShell) está implantado em seus servidores front-end. Se não for, você pode baixá-lo [a partir do centro de download](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Você pode encontrar mais informações sobre como usar este módulo em [configurando seu computador para gerenciamento do Skype for Business online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Inicie o Windows PowerShell como um administrador.
    
3. Digite o seguinte e pressione Enter:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Digite o seguinte e pressione Enter:
    
   ```powershell
   $cred = Get-Credential
   ```

    Após pressionar Enter, a caixa de diálogo Credenciais do Windows PowerShell será exibida.
    
5. Digite seu nome de usuário e sua senha de administrador de locatário e clique em **OK**.
    
6. Na janela do PowerShell, digite o seguinte e pressione Enter:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importe a sessão digitando o seguinte cmdlet:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Ao executar o PowerShell em um servidor do Skype for Business, os cmdlets locais do Skype for Business já são carregados quando você abre o PowerShell. Você deve especificar o parâmetro-AllowClobber para permitir que os cmdlets online substituam os cmdlets locais com o mesmo nome.
    
8. Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao usuário, como a seguir:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por exemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Você também pode especificar um usuário pelo endereço SIP, nome de Usuário Principal (UPN), nome de domínio e nome e usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Atualizar o URI de linha e o plano de discagem para usuários habilitados para o sistema telefônico no Office 365

Esta seção descreve como atualizar o URI de linha e o plano de discagem para usuários habilitados para o sistema telefônico no Office 365. 
  
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

Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Você pode executar esse cmdlet a partir do Skype for Business Server 2015 ou de uma sessão remota do Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Atribuir um plano de discagem por usuário a um único usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Atribuir um plano de discagem por usuário a vários usuários

- Esse comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Você pode usar planos de discagem globais ou do usuário para usuários online. Planos de discagem locais não podem ser usados, pois se aplicam somente a usuários hospedados no local e são atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Retirar a atribuição de uma plano de discagem por usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar a atribuição de qualquer plano de discagem por usuário atribuído anteriormente a Ken Myer. Depois que a atribuição do plano de discagem por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso do plano de discagem global ou do plano de discagem de escopo de serviço atribuído ao seu Registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local

Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema telefônico no Office 365.
  
O sistema telefônico nos usuários do Office 365 deve ter uma política de roteamento de voz atribuída a eles para que as chamadas sejam roteadas com êxito. É diferente dos usuários de voz de negócios locais, que exigem que uma política de voz seja atribuída a eles para permitir o roteamento bem-sucedido das chamadas. A política de roteamento de voz deve conter usos de PSTN que definem chamadas e rotas autorizadas para o sistema telefônico nos usuários do Office 365. Você pode copiar esses usos de PSTN de Políticas de voz existentes para as novas Políticas de roteamento de voz. Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos os sistemas telefônicos dos usuários do Office 365 recebem a mesma política de voz online chamada BusinessVoice, que define os recursos de chamada permitidos; por exemplo, permitir toque simultâneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para atribuir uma política de roteamento de voz por usuário a um único usuário

- Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para atribuir uma política de roteamento de voz por usuário a vários usuários

- O comando a seguir atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Você pode usar políticas de roteamento de voz globais ou do usuário para usuários online. Políticas de roteamento de voz locais não podem ser usadas, pois se aplicam somente a usuários hospedados no local e são atribuídas a um site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para retirar a atribuição de uma política de roteamento de voz por usuário

- Use o Grant-CsVoiceRoutingPolicy para cancelar a atribuição de qualquer política de roteamento de voz por usuário atribuída anteriormente a Ken Myer. Depois que a atribuição da política de roteamento de voz por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso da política de roteamento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

