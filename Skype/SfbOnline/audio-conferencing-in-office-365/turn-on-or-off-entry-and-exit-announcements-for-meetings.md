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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como ativar e desativar anúncios de entrada ou saída em reuniões no Skype for Business Online usando o centro de administração do Skype for Business. '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237567"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="57572-103">Ativar ou desativar anúncios de entrada ou saída em reuniões no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57572-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="57572-104">Para obter informações sobre anúncios de entrada e saída no Microsoft Teams, consulte [Ativar ou desativar anúncios de entrada e saída em reuniões no Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span><span class="sxs-lookup"><span data-stu-id="57572-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="57572-105">Ao configurar a Audioconferência em Microsoft 365 ou Office 365, você receberá uma ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="57572-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="57572-106">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para uma reunião com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="57572-106">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="57572-107">A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="57572-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="57572-108">A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático de conferência e, dependendo das suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN.</span><span class="sxs-lookup"><span data-stu-id="57572-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="57572-109">Um PIN é fornecido para o organizador da reunião no Skype for Business e permite que ele inicie uma reunião se não puder iniciar a reunião usando o aplicativo do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="57572-109">A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app.</span></span> <span data-ttu-id="57572-110">No entanto, você pode fazer a configuração de modo que o PIN não seja obrigatório para iniciar a reunião.</span><span class="sxs-lookup"><span data-stu-id="57572-110">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="57572-111">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="57572-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="57572-112">No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  </span><span class="sxs-lookup"><span data-stu-id="57572-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="57572-113">Em **Experiência de ingresso na reunião,** selecione ou desempure Habilitar as notificações de entrada e saída da reunião a serem **ativadas.**</span><span class="sxs-lookup"><span data-stu-id="57572-113">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="57572-114">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="57572-114">This is selected by default.</span></span> <span data-ttu-id="57572-115">Entretanto, se você a desmarcar, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="57572-115">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="57572-116">Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.</span><span class="sxs-lookup"><span data-stu-id="57572-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="57572-117">Verificar ou desmarcar Peça que **os chamadores gravem seu nome antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="57572-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="57572-118">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="57572-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="57572-119">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="57572-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="57572-120">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="57572-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="57572-121">No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="57572-121">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="57572-122">Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="57572-122">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="57572-123">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="57572-123">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="57572-124">Por que você precisa usar Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="57572-124">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="57572-125">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="57572-125">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="57572-126">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="57572-126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="57572-127">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="57572-127">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="57572-128">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57572-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="57572-129">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57572-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="57572-130">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="57572-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="57572-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="57572-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="57572-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="57572-133">Related topics</span></span>

[<span data-ttu-id="57572-134">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="57572-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
