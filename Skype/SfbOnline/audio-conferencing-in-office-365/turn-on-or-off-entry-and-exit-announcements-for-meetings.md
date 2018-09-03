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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar e desativar anúncios de entrada ou saída em reuniões no Skype for Business Online usando o centro de administração do Skype for Business. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779031"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="85526-103">Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85526-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="85526-104">Para obter informações sobre anúncios de entrada e saída no Microsoft Teams, consulte [Ativar ou desativar anúncios de entrada e saída em reuniões no Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="85526-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="85526-105">Quando você estiver configurando a Audioconferência no Office 365, obterá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="85526-105">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="85526-106">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para uma reunião com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="85526-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="85526-107">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="85526-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="85526-108">A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN.</span><span class="sxs-lookup"><span data-stu-id="85526-108">The conferencing bridge answers the caller with voice prompts from an auto attendant and then depending on your settings can play notifications, ask callers to record their name and sets up the PIN security.</span></span> <span data-ttu-id="85526-109">Um PIN é fornecido para o organizador da reunião no Skype for Business e permite que ele inicie uma reunião se não puder iniciar a reunião usando o aplicativo do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="85526-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="85526-110">No entanto, você pode configurar para que não seja necessário um PIN para começar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="85526-110">You can however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="85526-111">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="85526-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="85526-112">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="85526-112">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="85526-113">Em **Experiência de participação da reunião**, marque ou desmarque a opção **Habilitar a ativação de notificações de entrada e saída na reunião**.</span><span class="sxs-lookup"><span data-stu-id="85526-113">Under ** Meeting join experience** > check or uncheck Enable meeting entry and exit notifications to be turned on This is selected by default.</span></span> <span data-ttu-id="85526-114">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="85526-114">This is selected by default.</span></span> <span data-ttu-id="85526-115">Se você desmarcá-la, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="85526-115">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="85526-116">Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.</span><span class="sxs-lookup"><span data-stu-id="85526-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="85526-117">Marque ou desmarque a opção **Peça para os chamadores gravarem seus nomes antes de ingressarem na reunião**.</span><span class="sxs-lookup"><span data-stu-id="85526-117">Ask callers to record their name before joining the meeting</span></span>
    
5. <span data-ttu-id="85526-118">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="85526-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="85526-119">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="85526-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="85526-120">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="85526-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="85526-p104">No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="85526-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="85526-124">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="85526-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="85526-125">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="85526-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="85526-126">O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação com o centro de administração do Office 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="85526-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="85526-127">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="85526-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="85526-128">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85526-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="85526-129">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85526-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="85526-130">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85526-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="85526-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="85526-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="85526-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="85526-133">Related topics</span></span>

[<span data-ttu-id="85526-134">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="85526-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
