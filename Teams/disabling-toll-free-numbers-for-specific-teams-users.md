---
title: Desativar números de chamada gratuita para usuários específicos do Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Saiba como controlar como os organizadores podem usar números gratuitos para suas reuniões da Ponte de Audioconferência.
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096341"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="e5f5b-103">Desativar números de chamada gratuita para usuários específicos do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5f5b-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="e5f5b-104">Se sua organização tiver números gratuitos em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="e5f5b-105">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números gratuitos, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="e5f5b-106">Se esse não for o comportamento desejado para alguns usuários em sua organização, você poderá restringir usuários específicos de usar esses números em suas reuniões por meio de um controle de habilitação de número gratuito.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="e5f5b-107">Quando os números gratuitos são desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="e5f5b-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="e5f5b-108">Um número gratuito não será mais incluído em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="e5f5b-109">Os números gratuitos não serão mais listados na página "Encontrar um número local" referenciada em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="e5f5b-110">Os participantes não poderão participar da reunião do organizador se discarem qualquer número gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="e5f5b-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido delas.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="e5f5b-112">Isso enviará todos os convites de email do organizador a todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="e5f5b-113">Os participantes podem continuar participando de reuniões do organizador usando números de telefone.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="e5f5b-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="e5f5b-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="e5f5b-115">No centro **de administração do Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="e5f5b-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e5f5b-116">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e5f5b-117">Ao lado **de Audioconferência,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="e5f5b-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="e5f5b-119">Clique **em Salvar.**</span><span class="sxs-lookup"><span data-stu-id="e5f5b-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="e5f5b-120">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e5f5b-120">**Using PowerShell**</span></span>  

<span data-ttu-id="e5f5b-121">Consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5f5b-121">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>