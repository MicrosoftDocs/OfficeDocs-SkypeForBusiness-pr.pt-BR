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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Saiba como habilitar os serviços de voz do Sistema de Telefonia para seus usuários do Skype for Business.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625107"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Habilitar os usuários do Enterprise Voice online e da Caixa Postal do Sistema de Telefone
 
> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Saiba como habilitar os serviços de voz do Sistema de Telefonia para seus usuários do Skype for Business.
  
A etapa final na implantação do Sistema de Telefonia com conectividade PSTN local é habilitar seus usuários para Sistema de Telefonia e caixa postal. Para habilitar esses recursos, você deve ser um usuário com a função de Administrador Global e ser capaz de executar o PowerShell remoto. Você precisa seguir as etapas deste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business Online.
  
## <a name="enable-phone-system-voice-services"></a>Habilitar serviços de voz do Sistema de Telefonia

Para habilitar um usuário para Voz do Sistema de Telefonia e caixa postal, você precisará executar algumas etapas iniciais, como verificar se o Conector do Skype for Business Online está implantado em seus servidores e habilitar seus usuários para caixa postal hospedada.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Para habilitar seus usuários para voz e caixa postal do Sistema de Telefonia

> [!NOTE]
> O Conector do Skype for Business Online faz parte do Módulo PowerShell mais recente do Teams.
> Se você estiver usando a versão pública mais recente do PowerShell do [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não precisará instalar o Conector do Skype for Business Online.

1. Antes de começar, verifique se o módulo do PowerShell do Teams está instalado em seus Servidores Front-End. Se não estiver, instale usando as instruções na instalação do Módulo [do PowerShell do Teams.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Inicie o Windows PowerShell como administrador.
    
3. Digite o seguinte e pressione Enter:
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. Digite o seguinte e pressione Enter:
    
   ```powershell
   $cred = Get-Credential
   ```

    Depois de pressionar Enter, você deverá ver a caixa de diálogo Credencial do Windows PowerShell.
    
5. Digite o nome de usuário e a senha do administrador do locatário e clique em **OK.**
    
6. Na janela do PowerShell, digite o seguinte e pressione Enter:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importe a sessão digitando o seguinte cmdlet:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Ao executar o PowerShell em um Skype for Business Server, os cmdlets locais do Skype for Business já são carregados quando você abre o PowerShell. Você deve especificar o parâmetro -AllowClobber para permitir que os cmdlets online sobrescrevem os cmdlets locais com o mesmo nome.
    
8. Use o Set-CsUser cmdlet para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao usuário da seguinte forma:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por exemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Você também pode especificar um usuário por seu endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio \nome de usuário) e nome de exibição no Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Atualizar o URI de Linha e o plano de discagem para usuários habilitados para o Sistema de Telefonia

Esta seção descreve como atualizar o URI da Linha e o plano de discagem para usuários habilitados para o Sistema de Telefonia. 
  
### <a name="to-update-the-line-uri"></a>Para atualizar o URI da Linha

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu Iniciar ou o atalho da área de trabalho para abrir o Painel de Controle do Skype for Business Server.
    
    > [!NOTE]
    > Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 
  
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business que você deseja alterar o URI da linha.
    
6. Clique **em URI** da Linha e digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200). Em seguida, **clique em Commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Atualizar o plano de discagem usando cmdlets locais do Windows PowerShell

Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Você pode executar esse cmdlet no Skype for Business Server 2015 ou em uma sessão remota do Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para atribuir um plano de discagem por usuário a um único usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para atribuir um plano de discagem por usuário a vários usuários

- O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Você pode usar planos de discagem global ou de usuário para usuários online. Os planos de discagem de site não podem ser usados, pois se aplicam somente a usuários hospedados no local e atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para desa designar um plano de discagem por usuário

- Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desa designar qualquer plano de discagem por usuário atribuído anteriormente a Ken Myer. Depois que o plano de discagem por usuário é não atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global ou o plano de discagem de escopo de serviço atribuído ao seu Registrador ou gateway PSTN. Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Atualizar as políticas de roteamento de voz usando cmdlets locais do Windows PowerShell

Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o Sistema de Telefonia.
  
Os usuários do Sistema de Telefonia devem ter uma Política de Roteamento de Voz atribuída a eles para que as chamadas roteiem com êxito. Isso é diferente dos usuários de voz de negócios locais que exigem que uma Política de Voz seja atribuída a eles para permitir que as chamadas sejam roteadas com êxito. A Política de Roteamento de Voz deve conter usos de PSTN que definem chamadas e rotas autorizadas para usuários do Sistema de Telefonia. Você pode copiar esses usos de PSTN de Políticas de Voz existentes para novas Políticas de Roteamento de Voz. Para obter mais informações, [consulte New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos os usuários do Sistema de Telefonia são atribuídos com a mesma Política de Voz online chamada BusinessVoice, que define os recursos de chamada permitidos; por exemplo, Permitir toque simultâneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para atribuir uma política de roteamento de voz por usuário a um único usuário

- Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para atribuir uma política de roteamento de voz por usuário a vários usuários

- O próximo comando atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, [consulte Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Você pode usar políticas de roteamento de voz globais ou do usuário para usuários online. As políticas de roteamento de voz do site não podem ser usadas, pois se aplicam apenas a usuários hospedados no local e atribuídos a um site local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para desa designar uma política de roteamento de voz por usuário

- Use o Grant-CsVoiceRoutingPolicy para desa designar qualquer política de roteamento de voz por usuário atribuída anteriormente a Ken Myer. Depois que a política de roteamento de voz por usuário for não atribuída, Ken Myer será automaticamente gerenciado usando a política de roteamento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obter mais informações, [consulte Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

