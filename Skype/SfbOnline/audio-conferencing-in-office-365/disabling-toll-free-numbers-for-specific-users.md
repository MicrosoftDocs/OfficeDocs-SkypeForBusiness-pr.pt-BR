---
title: Desabilitando números gratuitos para usuários Skype for Business Online específicos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Os administradores podem controlar como os organizadores podem usar números gratuitos para suas reuniões.
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238506"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="95826-103">Desabilitando números gratuitos para usuários Skype for Business Online específicos</span><span class="sxs-lookup"><span data-stu-id="95826-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="95826-104">Para obter informações sobre como desabilitar números sem ferramentas para usuários Teams, consulte Desabilitando números gratuitos para usuários Teams [específicos.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)</span><span class="sxs-lookup"><span data-stu-id="95826-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="95826-105">Se sua organização tiver números gratuitos em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="95826-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="95826-106">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números gratuitos, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="95826-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="95826-107">Se esse não for o comportamento desejado para alguns usuários em sua organização, você poderá restringir usuários específicos de usar esses números em suas reuniões por meio de um controle de habilitação de número gratuito.</span><span class="sxs-lookup"><span data-stu-id="95826-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="95826-108">Quando os números gratuitos são desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="95826-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="95826-109">Um número gratuito não será mais incluído em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="95826-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="95826-110">Os números gratuitos não serão mais listados na página "Encontrar um número local" referenciada em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="95826-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="95826-111">Os participantes não poderão participar da reunião do organizador se discarem qualquer número gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="95826-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="95826-112">Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido delas.</span><span class="sxs-lookup"><span data-stu-id="95826-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="95826-113">Isso enviará todos os convites de email do organizador a todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="95826-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="95826-114">Os participantes podem continuar participando de reuniões do organizador usando números de telefone.</span><span class="sxs-lookup"><span data-stu-id="95826-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="95826-115">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="95826-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="95826-116">No centro **de Microsoft Teams de administração**:</span><span class="sxs-lookup"><span data-stu-id="95826-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="95826-117">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="95826-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="95826-118">Ao lado **de Audioconferência,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="95826-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="95826-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span><span class="sxs-lookup"><span data-stu-id="95826-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="95826-120">Clique **em Salvar.**</span><span class="sxs-lookup"><span data-stu-id="95826-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="95826-121">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="95826-121">**Using PowerShell**</span></span>  

<span data-ttu-id="95826-122">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="95826-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="95826-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95826-123">For example:</span></span> 

- <span data-ttu-id="95826-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="95826-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
