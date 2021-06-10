---
title: Permitir que os usuários gravem seu nome para uma reunião
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba como habilitar ou desabilitar se os usuários podem gravar seus nomes quando ingressarem em uma reunião Microsoft Teams.
ms.openlocfilehash: 8b92e0d4a73cc18ceaf374f1a05102e51752c083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092689"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="2ec43-103">Permitir que usuários gravem seu nome ao entrar em uma reunião no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ec43-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="2ec43-104">Ao configurar a Audioconferência em Microsoft 365 ou Office 365, você receberá números de telefone e o que é chamado de ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2ec43-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="2ec43-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="2ec43-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="2ec43-106">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="2ec43-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="2ec43-107">A ponte de conferência atende o chamador com prompts de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações, solicitar que os chamadores gravem seus nomes e configurar a segurança de PIN para organizadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="2ec43-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="2ec43-108">Os PINs são dados aos organizadores da reunião para permitir que eles iniciem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="2ec43-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="2ec43-109">Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.</span><span class="sxs-lookup"><span data-stu-id="2ec43-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="2ec43-110">Definir se os chamadores devem gravar o nome</span><span class="sxs-lookup"><span data-stu-id="2ec43-110">Set whether callers should record their name</span></span>

<span data-ttu-id="2ec43-111">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="2ec43-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2ec43-112">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="2ec43-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="2ec43-113">Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.**</span><span class="sxs-lookup"><span data-stu-id="2ec43-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="2ec43-114">Habilitar ou **desabilitar notificações de entrada e saída de reunião.**</span><span class="sxs-lookup"><span data-stu-id="2ec43-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="2ec43-115">Se estiver habilitando notificações, escolha **Nomes** ou números de telefone em Tipo de comunicado de **entrada/saída** e, em seguida, ative Solicitar que os chamadores gravem seus nomes antes de ingressar em **uma reunião.**</span><span class="sxs-lookup"><span data-stu-id="2ec43-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="2ec43-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2ec43-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="2ec43-117">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="2ec43-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="2ec43-118">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="2ec43-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="2ec43-119">Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="2ec43-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="2ec43-120">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="2ec43-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2ec43-121">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="2ec43-121">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="2ec43-122">[Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="2ec43-122">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="2ec43-123">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2ec43-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2ec43-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2ec43-124">Related topics</span></span>

[<span data-ttu-id="2ec43-125">Experimente ou compre Audioconferência</span><span class="sxs-lookup"><span data-stu-id="2ec43-125">Try or purchase Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)