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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões.
ms.openlocfilehash: 6fd415575110f9c6ae1dcf7b4fc006213a23cedd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232623"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="34664-103">Desativar números de chamada gratuita para usuários específicos do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34664-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="34664-104">Se sua organização tiver números para ligações gratuitas no seu Microsoft Audio Conferencing Bridge, você pode permitir ou impedir que o seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="34664-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="34664-105">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="34664-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="34664-106">Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="34664-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="34664-107">Quando os números para ligações gratuitas estão desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="34664-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="34664-108">Não é mais um número de chamada gratuito será incluído em seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="34664-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="34664-109">Não há mais números para ligações gratuitas serão listados na página "Localizar um número local" que é referenciada no seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="34664-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="34664-110">Os participantes não conseguirá ingressar na reunião do organizador determinado se eles discarem qualquer número de chamada gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="34664-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="34664-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número de chamada gratuito será removido do-los.</span><span class="sxs-lookup"><span data-stu-id="34664-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="34664-112">Isso irá Reenviar todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="34664-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="34664-113">Os participantes podem continuar a ingressar em reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="34664-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="34664-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="34664-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="34664-115">Partir do **Centro de administração de equipes da Microsoft**:</span><span class="sxs-lookup"><span data-stu-id="34664-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="34664-116">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="34664-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="34664-117">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="34664-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="34664-118">Defina a **incluir números para ligações gratuitas nas solicitações deste usuário de reunião** para **Off**.</span><span class="sxs-lookup"><span data-stu-id="34664-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="34664-119">Clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="34664-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="34664-120">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="34664-120">**Using PowerShell**</span></span>  

<span data-ttu-id="34664-121">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="34664-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
