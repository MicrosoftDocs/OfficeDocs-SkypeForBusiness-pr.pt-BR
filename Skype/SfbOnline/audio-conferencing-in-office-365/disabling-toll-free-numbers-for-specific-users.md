---
title: Desativando números de chamada gratuita para usuários específicos do Skype for Business Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números de chamada gratuita para suas reuniões.
ms.openlocfilehash: 541398a760f41effc37e802cafde1141acca2d57
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306085"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="c5055-103">Desativando números de chamada gratuita para usuários específicos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c5055-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="c5055-104">Para obter informações sobre como desabilitar os números de ferramenta livre para usuários do Teams, consulte [desabilitando números de chamada gratuita para usuários específicos do teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="c5055-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="c5055-105">Se sua organização tiver números de chamada gratuita em sua ponte de conferência de áudio da Microsoft, você poderá permitir ou impedir o uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="c5055-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="c5055-106">Por padrão, todos os usuários de sua organização estão habilitados para usar números de chamada gratuita, o que significa que esses números, se estiverem disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="c5055-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="c5055-107">Se esse não for o comportamento desejado para alguns usuários da sua organização, você poderá impedir que usuários específicos usem esses números em suas reuniões por meio de um controle de habilitação de número de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="c5055-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="c5055-108">Quando números de chamada gratuita são desativados para um organizador específico:</span><span class="sxs-lookup"><span data-stu-id="c5055-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="c5055-109">Um número de chamada gratuita não será mais incluído em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="c5055-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c5055-110">Os números de chamada gratuita não serão mais listados na página "encontrar um número local" que é referenciado em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="c5055-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="c5055-111">Os participantes não poderão participar da reunião do organizador específico se discarem qualquer número de chamada gratuita da organização.</span><span class="sxs-lookup"><span data-stu-id="c5055-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="c5055-112">Todas as reuniões do organizador serão automaticamente reagendadas e o número de chamada gratuita será removido delas.</span><span class="sxs-lookup"><span data-stu-id="c5055-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="c5055-113">Isso reenviará todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="c5055-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="c5055-114">Os participantes podem continuar a ingressar em reuniões do organizador usando números de chamada tarifada.</span><span class="sxs-lookup"><span data-stu-id="c5055-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="c5055-115">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="c5055-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="c5055-116">No **centro de administração do Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="c5055-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="c5055-117">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c5055-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c5055-118">Ao lado de **conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c5055-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="c5055-119">Defina **incluir números de chamada gratuita em solicitações de reunião desse usuário** para **desativar**.</span><span class="sxs-lookup"><span data-stu-id="c5055-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="c5055-120">Clique em **salvar.**</span><span class="sxs-lookup"><span data-stu-id="c5055-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="c5055-121">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c5055-121">**Using PowerShell**</span></span>  

<span data-ttu-id="c5055-122">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="c5055-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="c5055-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c5055-123">For example:</span></span> 

- <span data-ttu-id="c5055-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="c5055-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
