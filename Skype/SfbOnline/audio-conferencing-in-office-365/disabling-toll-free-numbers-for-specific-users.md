---
title: Desabilitando números para ligações gratuitas para Skype específico para usuários corporativos Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões.
ms.openlocfilehash: b438ee16135485a79458869858c52dd35bafa560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885167"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="70679-103">Desabilitando números para ligações gratuitas para Skype específico para usuários corporativos Online</span><span class="sxs-lookup"><span data-stu-id="70679-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

> [!Note]
> <span data-ttu-id="70679-104">Para obter informações sobre como desabilitar números livre de ferramenta para usuários de equipes, consulte [Desabilitando números para ligações gratuitas para usuários específicos de equipes](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span><span class="sxs-lookup"><span data-stu-id="70679-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="70679-105">Se sua organização tiver números para ligações gratuitas no seu Microsoft Audio Conferencing Bridge, você pode permitir ou impedir que o seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="70679-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="70679-106">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="70679-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="70679-107">Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="70679-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="70679-108">Quando os números para ligações gratuitas estão desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="70679-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="70679-109">Não é mais um número de chamada gratuito será incluído em seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="70679-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="70679-110">Não há mais números para ligações gratuitas serão listados na página "Localizar um número local" que é referenciada no seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="70679-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="70679-111">Os participantes não conseguirá ingressar na reunião do organizador determinado se eles discarem qualquer número de chamada gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="70679-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="70679-112">Todas as reuniões do organizador serão reagendadas automaticamente e o número de chamada gratuito será removido do-los.</span><span class="sxs-lookup"><span data-stu-id="70679-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="70679-113">Isso irá Reenviar todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="70679-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="70679-114">Os participantes podem continuar a ingressar em reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="70679-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="70679-115">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="70679-115">Disabling toll-free numbers for specific users</span></span> 


1. <span data-ttu-id="70679-116">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="70679-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="70679-117">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="70679-117">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="70679-118">Desmarque **Permitir usando números de discagem gratuita para participar de reuniões deste usuário**.</span><span class="sxs-lookup"><span data-stu-id="70679-118">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="70679-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="70679-119">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="70679-120">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="70679-120">**Using PowerShell**</span></span>  

<span data-ttu-id="70679-121">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="70679-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="70679-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="70679-122">For example:</span></span> 

 - <span data-ttu-id="70679-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="70679-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
