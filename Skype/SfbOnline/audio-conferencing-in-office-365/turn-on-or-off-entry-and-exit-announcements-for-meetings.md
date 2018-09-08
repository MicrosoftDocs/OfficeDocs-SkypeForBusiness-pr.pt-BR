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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar e desativar anúncios de entrada ou saída em reuniões no Skype for Business Online usando o centro de administração do Skype for Business. '
ms.openlocfilehash: b00c52d905fb031c7f0eaebc57f9fbb88549daa0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884048"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online

> [!Note]
> Para obter informações sobre anúncios de entrada e saída no Microsoft Teams, consulte [Ativar ou desativar anúncios de entrada e saída em reuniões no Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

Quando você estiver configurando a Audioconferência no Office 365, obterá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para uma reunião com o Skype for Business Online. 
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone. A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático de conferência e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN. Um PIN é fornecido para o organizador da reunião no Skype for Business e permite que ele inicie uma reunião se não puder iniciar a reunião usando o aplicativo do Skype for Business. Você pode, no entanto, defini-lo para que não é necessário um PIN para iniciar uma reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Definir as opções de participação da reunião
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
2. Sob a **experiência de participação da reunião**, marque ou desmarque **Habilitar a entrada da reunião e sair notificações para ser ativado**. Esta opção é selecionada por padrão. Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
3. Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.
    
4. Marque ou desmarque **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
-  No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
