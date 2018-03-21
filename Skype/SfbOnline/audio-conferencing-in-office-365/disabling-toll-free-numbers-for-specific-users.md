---
title: "Desabilitando números para ligações gratuitas para usuários específicos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões."
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="3a9ee-103">Desabilitando números para ligações gratuitas para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="3a9ee-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="3a9ee-104">Se sua organização tiver números para ligações gratuitas no seu Microsoft Audio Conferencing Bridge, você pode permitir ou impedir que o seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="3a9ee-105">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="3a9ee-106">Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="3a9ee-107">Quando os números para ligações gratuitas estão desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="3a9ee-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="3a9ee-108">Não é mais um número de chamada gratuito será incluído em seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="3a9ee-109">Não há mais números para ligações gratuitas serão listados na página "Localizar um número local" que é referenciada no seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="3a9ee-110">Os participantes não conseguirá ingressar na reunião do organizador determinado se eles discarem qualquer número de chamada gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="3a9ee-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número de chamada gratuito será removido do-los.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="3a9ee-112">Isso irá Reenviar todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="3a9ee-113">Os participantes podem continuar a ingressar em reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a><span data-ttu-id="3a9ee-114">Desabilitando números para ligações gratuitas para usuários específicos usando o Skype para o Centro de administração de negócios</span><span class="sxs-lookup"><span data-stu-id="3a9ee-114">Disabling toll-free numbers for specific users using the Skype for Business admin center</span></span> 
 1. <span data-ttu-id="3a9ee-115">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span> 
 2. <span data-ttu-id="3a9ee-116">No Skype para o Centro de administração de negócios, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-116">In the Skype for Business admin center, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 
 3. <span data-ttu-id="3a9ee-117">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-117">In the Action pane, click **Edit**.</span></span> 
 4. <span data-ttu-id="3a9ee-118">Marque ou desmarque **Permitir usando números de discagem gratuita para participar de reuniões deste usuário**.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-118">Check or clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 5. <span data-ttu-id="3a9ee-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-119">Click **Save**.</span></span> 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a><span data-ttu-id="3a9ee-120">Desabilitando números para ligações gratuitas para usuários específicos usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a9ee-120">Disabling toll-free numbers for specific users using PowerShell</span></span>  

<span data-ttu-id="3a9ee-121">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="3a9ee-121">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="3a9ee-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a9ee-122">For example:</span></span> 

 - <span data-ttu-id="3a9ee-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="3a9ee-123">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
