---
title: Permitir que os usuários registrar seus nomes quando ingressarem em uma reunião em Teams da Microsoft
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Aprenda a habilitar ou desabilitar se seus usuários podem registrar seus nomes quando ingressarem em uma reunião em Microsoft Teams.
ms.openlocfilehash: 55aa14f53e71bb13c7219e3730cf91388b566047
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850789"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="62d85-103">Permitir que os usuários registrar seus nomes quando ingressarem em uma reunião em Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="62d85-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="62d85-104">Quando você estiver configurando a conferência de áudio no Office 365, você receberá números de telefone e o que é chamado uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="62d85-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="62d85-105">Uma ponte de conferência pode conter um ou mais números de telefone.</span><span class="sxs-lookup"><span data-stu-id="62d85-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="62d85-106">A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="62d85-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="62d85-107">A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN para organizadores de reunião.</span><span class="sxs-lookup"><span data-stu-id="62d85-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="62d85-108">PINs são fornecidas aos organizadores de reuniões para permitir que eles iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="62d85-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="62d85-109">Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.</span><span class="sxs-lookup"><span data-stu-id="62d85-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="62d85-110">Definir se os chamadores devem gravar o nome</span><span class="sxs-lookup"><span data-stu-id="62d85-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="62d85-111">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="62d85-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="62d85-112">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="62d85-112">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="62d85-113">Habilitar ou desabilitar a **entrada de reunião e sair de notificações**.</span><span class="sxs-lookup"><span data-stu-id="62d85-113">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="62d85-114">Se Ativar notificações, escolha **nomes ou números de telefone** em **tipo de anúncio de entrada/saída**e, em seguida, ativar **será feita aos chamadores registrar seus nomes antes de ingressar em uma reunião.**</span><span class="sxs-lookup"><span data-stu-id="62d85-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="62d85-115">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="62d85-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="62d85-116">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="62d85-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="62d85-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="62d85-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="62d85-120">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="62d85-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="62d85-121">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="62d85-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="62d85-122">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="62d85-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="62d85-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="62d85-123">Related topics</span></span>

[<span data-ttu-id="62d85-124">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="62d85-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
