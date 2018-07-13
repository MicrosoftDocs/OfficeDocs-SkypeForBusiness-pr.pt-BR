---
title: Desativar números gratuitos para usuários específicos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números para ligações gratuitas para suas reuniões.
ms.openlocfilehash: 2f506163ce815f71d18935040dbf13bf4af4f04c
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20324137"
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="85beb-103">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="85beb-103">Disabling toll-free numbers for specific users</span></span>

<span data-ttu-id="85beb-104">Se sua organização tiver números para ligações gratuitas no seu Microsoft Audio Conferencing Bridge, você pode permitir ou impedir que o seu uso nas reuniões de organizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="85beb-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="85beb-105">Por padrão, todos os usuários em sua organização estão habilitados para o uso de números para ligações gratuitas, que significa que esses números, se estiver disponível, podem ser usados pelos participantes ingressem em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="85beb-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="85beb-106">Se isso não for o comportamento desejado para alguns usuários em sua organização, você pode impedir usuários específicos usando esses números em suas reuniões por meio de um controle de habilitação de números gratuitos.</span><span class="sxs-lookup"><span data-stu-id="85beb-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="85beb-107">Quando os números para ligações gratuitas estão desabilitados para um determinado organizador:</span><span class="sxs-lookup"><span data-stu-id="85beb-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="85beb-108">Não é mais um número de chamada gratuito será incluído em seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="85beb-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="85beb-109">Não há mais números para ligações gratuitas serão listados na página "Localizar um número local" que é referenciada no seu ou convida sua reunião.</span><span class="sxs-lookup"><span data-stu-id="85beb-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="85beb-110">Os participantes não conseguirá ingressar na reunião do organizador determinado se eles discarem qualquer número de chamada gratuito da organização.</span><span class="sxs-lookup"><span data-stu-id="85beb-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="85beb-111">Todas as reuniões do organizador serão reagendadas automaticamente e o número de chamada gratuito será removido do-los.</span><span class="sxs-lookup"><span data-stu-id="85beb-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="85beb-112">Isso irá Reenviar todos os convites de email do organizador para todos os participantes dessas reuniões.</span><span class="sxs-lookup"><span data-stu-id="85beb-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="85beb-113">Os participantes podem continuar a ingressar em reuniões do organizador usando números tarifados.</span><span class="sxs-lookup"><span data-stu-id="85beb-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="85beb-114">Desativar números gratuitos para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="85beb-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="85beb-115">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="85beb-115">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="85beb-116">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="85beb-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="85beb-117">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85beb-117">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="85beb-118">Clique no menu ao lado de **Pontes de conferência**e clique em **Editar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="85beb-118">Click the menu next to **Conference Bridges**, and then click **Edit** in the drop-down list.</span></span>

4. <span data-ttu-id="85beb-119">No painel de tarefas do **provedor de ponte de conferência** , desative **Permitir usando números para ligações gratuitas na ponte de conferência da sua organização para participar de reuniões deste usuário**.</span><span class="sxs-lookup"><span data-stu-id="85beb-119">In the **Conference bridge provider** pane, turn off **Allow using toll-free numbers in the Conferencing bridge of your organization to join the meetings of this user**.</span></span> 

5. <span data-ttu-id="85beb-120">Clique em **se aplicam.**</span><span class="sxs-lookup"><span data-stu-id="85beb-120">Click **Apply.**</span></span> 

<span data-ttu-id="85beb-121">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="85beb-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="85beb-122">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="85beb-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span> 

2. <span data-ttu-id="85beb-123">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="85beb-123">In the Action pane, click **Edit**.</span></span> 

3. <span data-ttu-id="85beb-124">Desmarque **Permitir usando números de discagem gratuita para participar de reuniões deste usuário**.</span><span class="sxs-lookup"><span data-stu-id="85beb-124">Clear **Allow using toll-free numbers to join the meetings of this user**.</span></span> 
 
4. <span data-ttu-id="85beb-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="85beb-125">Click **Save**.</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="85beb-126">**Usando o PowerShell**</span><span class="sxs-lookup"><span data-stu-id="85beb-126">**Using PowerShell**</span></span>  

<span data-ttu-id="85beb-127">Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle.</span><span class="sxs-lookup"><span data-stu-id="85beb-127">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="85beb-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="85beb-128">For example:</span></span> 

 - <span data-ttu-id="85beb-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="85beb-129">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
