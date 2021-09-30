---
title: Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar e desativar anúncios de entrada ou saída em reuniões no Skype for Business Online usando o centro de administração do Skype for Business. '
ms.openlocfilehash: ed4e94359f6d85ffbc02cd37445c400d2eb348ec
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012745"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre anúncios de entrada e saída no Microsoft Teams, consulte [Ativar ou desativar anúncios de entrada e saída em reuniões no Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Ao configurar a Audioconferência em Microsoft 365 ou Office 365, você receberá uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para uma reunião com o Skype for Business Online. 
  
A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone. A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático de conferência e, dependendo das suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN. Um PIN é fornecido para o organizador da reunião no Skype for Business e permite que ele inicie uma reunião se não puder iniciar a reunião usando o aplicativo do Skype for Business. No entanto, você pode fazer a configuração de modo que o PIN não seja obrigatório para iniciar a reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Definir as opções de participação da reunião
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  
    
2. Em **Experiência de ingresso na reunião,** selecione ou desempure Habilitar as notificações de entrada e saída da reunião a serem **ativadas.** Esta opção é selecionada por padrão. Entretanto, se você a desmarcar, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.
    
3. Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.
    
4. Verificar ou desmarcar Peça que **os chamadores gravem seu nome antes de ingressar na reunião**.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
- No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
