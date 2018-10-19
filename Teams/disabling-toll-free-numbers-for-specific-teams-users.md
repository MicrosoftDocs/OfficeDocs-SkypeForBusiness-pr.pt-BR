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
ms.openlocfilehash: cc179ff20d3bd523952ce57a79553025092532a9
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678334"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="4296e-103">Desativar números gratuitos para usuários específicos do Teams</span><span class="sxs-lookup"><span data-stu-id="4296e-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="4296e-104">Se a sua organização tem números gratuitos na Ponte de Audioconferência da Microsoft, é possível permitir ou impedir o uso deles em reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="4296e-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="4296e-105">Por padrão, todos os usuários da sua organização estão habilitados para usar números gratuitos, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para participar de suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="4296e-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="4296e-106">Se esse não for o comportamento desejado para alguns usuários da sua organização, será possível restringir o uso desses números por usuários específicos em reuniões através de um controle de ativação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="4296e-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="4296e-107">Quando os números gratuitos são desativados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="4296e-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="4296e-108">Seus convites de reunião não conterão mais um número gratuito.</span><span class="sxs-lookup"><span data-stu-id="4296e-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4296e-109">Os números gratuitos não serão mais listados na página “Encontrar um número local” que é mencionada em seus convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="4296e-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4296e-110">Os participantes não conseguirão entrar na reunião desse organizador se discarem para algum número gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="4296e-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="4296e-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido.</span><span class="sxs-lookup"><span data-stu-id="4296e-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="4296e-112">O convite do organizador será reenviado por e-mail para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="4296e-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="4296e-113">Os participantes podem continuar participando das reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="4296e-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="4296e-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="4296e-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="4296e-115">Das **equipes da Microsoft & Skype para Business Admin Center**:</span><span class="sxs-lookup"><span data-stu-id="4296e-115">From the **Microsoft Teams & Skype for Business Admin Center**:</span></span>

1. <span data-ttu-id="4296e-116">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4296e-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4296e-117">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4296e-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="4296e-118">Defina a **incluir números para ligações gratuitas nas solicitações deste usuário de reunião** para **Off**.</span><span class="sxs-lookup"><span data-stu-id="4296e-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="4296e-119">Clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="4296e-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="4296e-120">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4296e-120">**Using PowerShell**</span></span>  

<span data-ttu-id="4296e-121">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4296e-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
