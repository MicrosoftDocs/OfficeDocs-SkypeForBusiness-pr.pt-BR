---
title: Permitir que usuários gravem o nome ao entrar em uma reunião no Microsoft Teams
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Saiba como ativar ou desativar se seus usuários podem ou não gravar o nome ao entrarem em uma reunião no Microsoft Teams.
ms.openlocfilehash: 20888f206e3ffbca72227ff1b9cd5d5f624101f3
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573047"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="90fa3-103">Permitir que usuários gravem o nome ao entrar em uma reunião no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90fa3-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="90fa3-104">Ao configurar a audioconferência discada no Office 365, você receberá números de telefone e o que chamamos de ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="90fa3-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="90fa3-105">Uma ponte de conferência pode conter um ou mais números de telefone, que podem ser um número de telefone exclusivo ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="90fa3-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="90fa3-106">A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone.</span><span class="sxs-lookup"><span data-stu-id="90fa3-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="90fa3-107">A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático e, dependendo das configurações dele, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN para os organizadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="90fa3-107">The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers.</span></span> <span data-ttu-id="90fa3-108">Os organizadores de reunião recebem PINs que os permitem iniciar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="90fa3-108">PINs are given to meeting organizers to allow them to start a meeting.</span></span> <span data-ttu-id="90fa3-109">Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.</span><span class="sxs-lookup"><span data-stu-id="90fa3-109">However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="90fa3-110">Definir se os chamadores devem gravar o nome</span><span class="sxs-lookup"><span data-stu-id="90fa3-110">Set whether callers should record their name</span></span>

<span data-ttu-id="90fa3-111">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="90fa3-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90fa3-112">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="90fa3-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90fa3-113">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="90fa3-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90fa3-114">Habilite ou desabilite as **notificações de entrada e saída da reunião**.</span><span class="sxs-lookup"><span data-stu-id="90fa3-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="90fa3-115">Se habilitar notificações, escolha **nomes ou números de telefone** em **tipo de anúncio de entrada/saída**e ative **solicitar aos chamadores gravarem o nome antes de ingressar em uma reunião.**</span><span class="sxs-lookup"><span data-stu-id="90fa3-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="90fa3-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90fa3-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="90fa3-117">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="90fa3-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="90fa3-p103">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="90fa3-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="90fa3-121">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="90fa3-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="90fa3-122">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90fa3-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="90fa3-123">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="90fa3-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="90fa3-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="90fa3-124">Related topics</span></span>

[<span data-ttu-id="90fa3-125">Experimentar ou comprar audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="90fa3-125">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
