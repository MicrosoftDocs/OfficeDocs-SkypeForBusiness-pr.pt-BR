---
title: Desabilitando números de chamada gratuita para usuários específicos do Skype for Business Online
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
description: Os administradores podem controlar como os organizadores podem usar números de tarifa gratuita para suas reuniões.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695676"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="23eac-103">Desabilitando números de chamada gratuita para usuários específicos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="23eac-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="23eac-104">Para obter informações sobre como desabilitar números sem ferramentas para usuários do Teams, consulte Desabilitar números de tarifa gratuita [para usuários específicos do Teams.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)</span><span class="sxs-lookup"><span data-stu-id="23eac-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="23eac-105">Se sua organização tiver números de tarifa gratuita em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir o uso deles nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="23eac-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="23eac-106">Por padrão, todos os usuários em sua organização estão habilitados para usar números de tarifa gratuita, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="23eac-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="23eac-107">Se esse não for o comportamento desejado para alguns usuários em sua organização, você pode restringir usuários específicos de usar esses números em suas reuniões por meio de um controle de habilitação de número de ligação gratuita.</span><span class="sxs-lookup"><span data-stu-id="23eac-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="23eac-108">Quando os números de tarifa gratuita são desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="23eac-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="23eac-109">Um número de ligação gratuita não será mais incluído em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="23eac-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="23eac-110">Os números de tarifa gratuita não serão mais listados na página "Encontrar um número local" referenciada em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="23eac-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="23eac-111">Os participantes não poderão ingressar na reunião do organizador se discarem para qualquer número de tarifa gratuita da organização.</span><span class="sxs-lookup"><span data-stu-id="23eac-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="23eac-112">Todas as reuniões do organizador serão reagenddas automaticamente, e o número da tarifa gratuita será removido delas.</span><span class="sxs-lookup"><span data-stu-id="23eac-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="23eac-113">Isso resende todos os convites por email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="23eac-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="23eac-114">Os participantes podem continuar in joining meetings of the organizer using toll numbers.</span><span class="sxs-lookup"><span data-stu-id="23eac-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="23eac-115">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="23eac-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="23eac-116">No Centro **de administração do Microsoft Teams:**</span><span class="sxs-lookup"><span data-stu-id="23eac-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="23eac-117">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="23eac-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="23eac-118">Ao lado **de Audioconferência,** clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="23eac-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="23eac-119">Definir **Incluir números de tarifa gratuita em solicitações de reunião deste usuário** para **Desligado.**</span><span class="sxs-lookup"><span data-stu-id="23eac-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="23eac-120">Clique **em Salvar.**</span><span class="sxs-lookup"><span data-stu-id="23eac-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="23eac-121">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="23eac-121">**Using PowerShell**</span></span>  

<span data-ttu-id="23eac-122">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="23eac-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="23eac-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="23eac-123">For example:</span></span> 

- <span data-ttu-id="23eac-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="23eac-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
