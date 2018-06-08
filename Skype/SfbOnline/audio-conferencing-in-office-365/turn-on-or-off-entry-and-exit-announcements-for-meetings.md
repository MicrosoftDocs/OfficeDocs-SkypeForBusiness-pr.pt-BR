---
title: Ativar ou desativar anúncios de entrada e de saída para reuniões
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: 18b22e5491b67b6f4ec3f089803bcfb5e486eb14
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703450"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="7fe67-103">Ativar ou desativar anúncios de entrada e de saída para reuniões</span><span class="sxs-lookup"><span data-stu-id="7fe67-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="7fe67-104">Quando você estiver configurando a conferência de áudio no Office 365, você receberá uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="7fe67-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="7fe67-105">Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para um Skype para reunião de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fe67-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="7fe67-106">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="7fe67-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="7fe67-107">A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático de conferência e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN.</span><span class="sxs-lookup"><span data-stu-id="7fe67-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="7fe67-108">Um PIN é fornecido para um Skype para negócios ou Microsoft Teams organizador da reunião e permite que eles iniciar uma reunião se eles não é possível iniciar a reunião usando um Skype para aplicativo de negócios ou Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fe67-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="7fe67-109">Você pode, no entanto, defini-lo para que não é necessário um PIN para iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="7fe67-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="7fe67-110">Definir as opções de participação da reunião</span><span class="sxs-lookup"><span data-stu-id="7fe67-110">Setting meeting join options</span></span>

<span data-ttu-id="7fe67-111">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="7fe67-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7fe67-112">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="7fe67-113">Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="7fe67-114">No painel de **configurações de ponte** , habilitar ou desabilitar a **Habilitar a entrada da reunião e sair notificações para ser ativado**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="7fe67-115">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fe67-115">This is selected by default.</span></span> <span data-ttu-id="7fe67-116">Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="7fe67-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="7fe67-117">Em **tipo de anúncio de entrada/saída**, selecione **nomes ou números de telefone** ou **tons**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="7fe67-118">Habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="7fe67-119">Depois de fazer as alterações, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="7fe67-120">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="7fe67-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="7fe67-121">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="7fe67-122">Sob a **experiência de participação da reunião**, marque ou desmarque **Habilitar a entrada da reunião e sair notificações para ser ativado**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="7fe67-123">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="7fe67-123">This is selected by default.</span></span> <span data-ttu-id="7fe67-124">Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="7fe67-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="7fe67-125">Em **tipo de anúncio de entrada/saída**, selecione **nomes ou números de telefone** ou **tons**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="7fe67-126">Marque ou desmarque **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="7fe67-127">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7fe67-127">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7fe67-128">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7fe67-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7fe67-129">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).</span><span class="sxs-lookup"><span data-stu-id="7fe67-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="7fe67-p105">No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7fe67-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7fe67-133">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="7fe67-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7fe67-134">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fe67-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7fe67-135">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="7fe67-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="7fe67-136">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7fe67-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7fe67-137">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fe67-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7fe67-138">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fe67-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7fe67-139">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fe67-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="7fe67-p107">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="7fe67-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7fe67-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7fe67-142">Related topics</span></span>

[<span data-ttu-id="7fe67-143">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7fe67-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
