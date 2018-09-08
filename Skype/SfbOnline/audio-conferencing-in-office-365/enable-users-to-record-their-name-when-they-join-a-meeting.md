---
title: Permitir que os usuários registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Aprenda a habilitar ou desabilitar se seus usuários podem registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online.
ms.openlocfilehash: 0e330d5efdd7325a8db48aa679d6ecbb9264c345
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884717"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="e2e1c-103">Permitir que os usuários registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="e2e1c-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e2e1c-104">Se você quiser permitir que os usuários registrem seus nomes no Teams, consulte [Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="e2e1c-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="e2e1c-105">Quando você estiver configurando a conferência de áudio no Office 365, você receberá números de telefone e o que é chamado uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-105">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="e2e1c-106">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="e2e1c-107">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="e2e1c-108">A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN para organizadores de reunião.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-108">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="e2e1c-109">PINs são fornecidas aos organizadores de reuniões para permitir que eles iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-109">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="e2e1c-110">Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-110">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="e2e1c-111">Definir se os chamadores devem gravar o nome</span><span class="sxs-lookup"><span data-stu-id="e2e1c-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="e2e1c-112">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="e2e1c-113">Em **Experiência de participação da reunião**, veja a caixa de seleção **Habilitar a ativação de notificações de entrada e saída na reunião**.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="e2e1c-114">**Selecionado** Os chamadores serão solicitados a registrar seu nome antes que eles entrem na reunião.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-114">**Selected** Callers will be asked to record their name before they enter the meeting.</span></span> <span data-ttu-id="e2e1c-115">Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-115">This is selected by default.</span></span>
    
  - <span data-ttu-id="e2e1c-116">**Desmarcada** Os chamadores não ser solicitados a registrar seus nomes antes que eles entrem na reunião.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="e2e1c-117">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e2e1c-118">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e2e1c-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e2e1c-119">Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="e2e1c-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="e2e1c-120">Windows PowerShell é tudo sobre o gerenciamento de usuários e quais usuários têm permissão para fazer.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="e2e1c-121">Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-121">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e2e1c-122">Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e2e1c-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2e1c-123">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="e2e1c-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e2e1c-124">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e1c-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e2e1c-125">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="e2e1c-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e2e1c-126">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e2e1c-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e2e1c-127">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2e1c-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e2e1c-128">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2e1c-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e2e1c-129">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2e1c-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e2e1c-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="e2e1c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2e1c-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2e1c-132">Related topics</span></span>

[<span data-ttu-id="e2e1c-133">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="e2e1c-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
