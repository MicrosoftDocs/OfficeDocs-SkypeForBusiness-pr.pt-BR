---
title: Habilitar os usuários do Enterprise Voice online e da Caixa Postal do Sistema de Telefone
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Saiba como habilitar Sistema de Telefonia de voz para seus Skype for Business usuários.
ms.openlocfilehash: 9c9123b79a1fd5557d0d31db7b4b150bcda80af3
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563434"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Habilitar os usuários do Enterprise Voice online e da Caixa Postal do Sistema de Telefone
 
> [!Important]
> O Skype for Business Online foi retirado em 31 de julho de 2021 e a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não tem mais suporte.  Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba como habilitar Sistema de Telefonia de voz para seus Skype for Business usuários.
  
A etapa final na implantação Sistema de Telefonia com conectividade PSTN local é habilitar seus usuários para Sistema de Telefonia e caixa postal. Para habilitar esses recursos, você deve ser um usuário com a função Administrador Global e poder executar o PowerShell remoto. Você precisa seguir as etapas deste tópico para todas as contas de usuário que ainda não Enterprise Voice habilitadas para Skype for Business Online.
  
## <a name="enable-phone-system-voice-services"></a>Habilitar Sistema de Telefonia serviços de voz

Para habilitar um usuário para Sistema de Telefonia Voz e caixa postal, você precisará executar algumas etapas iniciais, como verificar se o conector online do Skype for Business está implantado em seus servidores e habilitar seus usuários para a caixa postal hospedada.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Para habilitar seus usuários para Sistema de Telefonia voz e caixa postal

> [!NOTE]
> Skype for Business Conector Online atualmente faz parte do módulo Teams PowerShell mais recente.
> Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.

1. Antes de começar, verifique se o módulo Teams PowerShell está instalado em seus Servidores Front-End. Se não estiver, instale usando as instruções em Teams [Instalação do Módulo do PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Inicie Windows PowerShell como administrador.
    
3. Digite o seguinte e pressione Enter:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao usuário da seguinte forma:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por exemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Você também pode especificar um usuário por seu endereço SIP, nome da Entidade de Usuário (UPN), nome de domínio e nome de usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Atualize o URI de linha e o plano de discagem para usuários habilitados para Sistema de Telefonia

Esta seção descreve como atualizar o URI de linha e o plano de discagem para usuários habilitados para Sistema de Telefonia. 
  
### <a name="to-update-the-line-uri"></a>Para atualizar o URI de linha

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu Iniciar ou o atalho da área de trabalho para abrir o painel Skype for Business Server Controle.
    
    > [!NOTE]
    > Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o painel Skype for Business Server Controle. 
  
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na Skype for Business de usuário que você deseja alterar o URI de linha.
    
6. Clique **em URI** de linha e digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200). Em seguida, **clique em Commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Atualizar o plano de discagem usando cmdlets locais Windows PowerShell cmdlets

Você pode atribuir planos de discagem por usuário com Windows PowerShell e o cmdlet [Grant-CsDialPlan.](/powershell/module/skype/grant-csdialplan?view=skype-ps) Você pode executar esse cmdlet no Skype for Business Server 2015 ou em uma sessão remota de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para atribuir um plano de discagem por usuário a um único usuário

- Use o cmdlet [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para atribuir um plano de discagem por usuário a vários usuários

- O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser:](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Você pode usar planos de discagem global ou de usuário para usuários online. Os planos de discagem de site não podem ser usados, pois eles só se aplicam aos usuários hospedados no local e são atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para desaignar um plano de discagem por usuário

- Use o cmdlet [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) para desemplacar qualquer plano de discagem por usuário atribuído anteriormente a Ken Myer. Depois que o plano de discagem por usuário não for atribuído, Ken Myer será gerenciado automaticamente usando o plano de discagem global ou o plano de discagem de escopo de serviço atribuído ao seu Registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Atualizar as políticas de roteamento de voz usando cmdlets locais Windows PowerShell cmdlets

Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para Sistema de Telefonia.
  
Sistema de Telefonia usuários devem ter uma Política de Roteamento de Voz atribuída a eles para que as chamadas roteem com êxito. Isso difere dos usuários de voz comerciais locais que exigem que uma Política de Voz seja atribuída a eles para permitir que as chamadas sejam roteadas com êxito. A Política de Roteamento de Voz deve conter usos PSTN que definem chamadas e rotas autorizadas para Sistema de Telefonia usuários. Você pode copiar esses usos PSTN de Políticas de Voz existentes para novas Políticas de Roteamento de Voz. Para obter mais informações, [consulte New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos Sistema de Telefonia usuários são atribuídos à mesma Política de Voz online chamada BusinessVoice, que define os recursos de chamada permitidos; por exemplo, Permitir Toque Simultâneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para atribuir uma política de roteamento de voz por usuário a um único usuário

- Use o cmdlet [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para atribuir uma política de roteamento de voz por usuário a vários usuários

- O próximo comando atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Você pode usar políticas de roteamento de voz global ou de usuário para usuários online. As políticas de roteamento de voz do site não podem ser usadas, pois elas só se aplicam a usuários hospedados no local e são atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para desaignar uma política de roteamento de voz por usuário

- Use o Grant-CsVoiceRoutingPolicy para desaignar qualquer política de roteamento de voz por usuário atribuída anteriormente a Ken Myer. Depois que a política de roteamento de voz por usuário não for atribuída, Ken Myer será gerenciado automaticamente usando a política de roteamento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obter mais informações, [consulte Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
