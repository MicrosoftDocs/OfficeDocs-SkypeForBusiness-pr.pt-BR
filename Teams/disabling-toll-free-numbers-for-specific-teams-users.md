---
title: Desativar números gratuitos para usuários específicos do Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podme usar os números gratuitos para suas reuniões.
ms.openlocfilehash: 158a4b31b0aaf65414af0d2119b3b6931a1f74ac
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014689"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="27fd0-103">Desativar números gratuitos para usuários específicos do Teams</span><span class="sxs-lookup"><span data-stu-id="27fd0-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="27fd0-104">Se a sua organização tem números gratuitos na Ponte de Audioconferência da Microsoft, é possível permitir ou impedir o uso deles em reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="27fd0-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="27fd0-105">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="27fd0-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="27fd0-106">Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="27fd0-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="27fd0-107">Quando os números gratuitos são desativados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="27fd0-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="27fd0-108">Seus convites de reunião não conterão mais um número gratuito.</span><span class="sxs-lookup"><span data-stu-id="27fd0-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="27fd0-109">Os números gratuitos não serão mais listados na página “Encontrar um número local” que é mencionada em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="27fd0-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="27fd0-110">Os participantes não conseguirão entrar na reunião desse organizador se discarem para algum número gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="27fd0-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="27fd0-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido.</span><span class="sxs-lookup"><span data-stu-id="27fd0-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="27fd0-112">O convite do organizador será reenviado por e-mail para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="27fd0-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="27fd0-113">Os participantes podem continuar participando das reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="27fd0-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="27fd0-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="27fd0-114">Disabling toll-free numbers for specific users</span></span> 

1. <span data-ttu-id="27fd0-115">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="27fd0-115">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="27fd0-116">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="27fd0-116">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="27fd0-117">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="27fd0-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="27fd0-118">Desative **Incluir números gratuitos em solicitações de reunião deste usuário**.</span><span class="sxs-lookup"><span data-stu-id="27fd0-118">Turn off **Include toll-free numbers in meeting requests from this user**.</span></span> 

5. <span data-ttu-id="27fd0-119">Clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="27fd0-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="27fd0-120">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27fd0-120">**Using PowerShell**</span></span>  

<span data-ttu-id="27fd0-121">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="27fd0-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
