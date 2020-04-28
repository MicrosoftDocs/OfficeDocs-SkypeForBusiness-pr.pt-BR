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
description: Saiba como controlar como os organizadores podem usar números de chamada gratuita para suas reuniões de ponte de áudio da conferência.
ms.openlocfilehash: 517ffea6a15cd625320f33e3eb4911f4a250d51d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904566"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="335df-103">Desativar números de chamada gratuita para usuários específicos do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="335df-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="335df-104">Se sua organização tiver números de chamada gratuita em sua ponte de conferência de áudio da Microsoft, você poderá permitir ou impedir o uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="335df-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="335df-105">Por padrão, todos os usuários de sua organização estão habilitados para usar números de chamada gratuita, o que significa que esses números, se estiverem disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="335df-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="335df-106">Se esse não for o comportamento desejado para alguns usuários da sua organização, você poderá impedir que usuários específicos usem esses números em suas reuniões por meio de um controle de habilitação de número de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="335df-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="335df-107">Quando números de chamada gratuita são desativados para um organizador específico:</span><span class="sxs-lookup"><span data-stu-id="335df-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="335df-108">Um número de chamada gratuita não será mais incluído em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="335df-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="335df-109">Os números de chamada gratuita não serão mais listados na página "encontrar um número local" que é referenciado em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="335df-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="335df-110">Os participantes não poderão participar da reunião do organizador específico se discarem qualquer número de chamada gratuita da organização.</span><span class="sxs-lookup"><span data-stu-id="335df-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="335df-111">Todas as reuniões do organizador serão automaticamente reagendadas e o número de chamada gratuita será removido delas.</span><span class="sxs-lookup"><span data-stu-id="335df-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="335df-112">Isso reenviará todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="335df-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="335df-113">Os participantes podem continuar a ingressar em reuniões do organizador usando números de chamada tarifada.</span><span class="sxs-lookup"><span data-stu-id="335df-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="335df-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="335df-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="335df-115">No **centro de administração do Microsoft Teams**:</span><span class="sxs-lookup"><span data-stu-id="335df-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="335df-116">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="335df-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="335df-117">Ao lado de **conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="335df-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="335df-118">Defina **incluir números de chamada gratuita em solicitações de reunião desse usuário** para **desativar**.</span><span class="sxs-lookup"><span data-stu-id="335df-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="335df-119">Clique em **salvar.**</span><span class="sxs-lookup"><span data-stu-id="335df-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="335df-120">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="335df-120">**Using PowerShell**</span></span>  

<span data-ttu-id="335df-121">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="335df-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
