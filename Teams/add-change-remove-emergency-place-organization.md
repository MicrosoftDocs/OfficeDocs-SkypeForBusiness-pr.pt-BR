---
title: Adicionar, alterar, remover locais para locais de emergência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba como adicionar, alterar ou remover um local para um local de emergência de sua organização no centro de administração do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c3ff180848d12ad3fb00d048bbb1910bf13c00d6
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232492"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="01b15-103">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="01b15-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="01b15-104">Dependendo do número de locais físicos da sua organização, você pode adicionar locais para prédios, andares e escritórios para criar um local de emergência mais específico.</span><span class="sxs-lookup"><span data-stu-id="01b15-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="01b15-105">Consulte [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="01b15-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="01b15-106">Para saber como obter um plano de chamadas e quanto eles custam, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="01b15-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="01b15-107">Você gerencia locais de emergência para sua organização no centro de administração do Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01b15-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="01b15-108">Adicionar um local a um local de emergência</span><span class="sxs-lookup"><span data-stu-id="01b15-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01b15-109">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01b15-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="01b15-110">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="01b15-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="01b15-111">Na lista, clique no nome do local ao qual você deseja adicionar um local.</span><span class="sxs-lookup"><span data-stu-id="01b15-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="01b15-112">Na guia **locais** , clique em **Adicionar local**.</span><span class="sxs-lookup"><span data-stu-id="01b15-112">On the **Places** tab, click **Add place**.</span></span>
4. <span data-ttu-id="01b15-113">Digite um nome para o local e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="01b15-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="01b15-114">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01b15-114">Using PowerShell</span></span>

<span data-ttu-id="01b15-115">Veja [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="01b15-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="01b15-116">Alterar um local para um local de emergência</span><span class="sxs-lookup"><span data-stu-id="01b15-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01b15-117">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01b15-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="01b15-118">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="01b15-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="01b15-119">Na lista, clique no nome do local para o qual você deseja alterar um local.</span><span class="sxs-lookup"><span data-stu-id="01b15-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="01b15-120">Na guia **locais** , selecione o local que você deseja alterar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="01b15-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="01b15-121">Atualize as informações do local e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="01b15-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="01b15-122">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01b15-122">Using PowerShell</span></span>

<span data-ttu-id="01b15-123">Consulte [set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="01b15-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="01b15-124">Remover um local de um local de emergência</span><span class="sxs-lookup"><span data-stu-id="01b15-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="01b15-125">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01b15-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="01b15-126">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **locais**  >  **endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="01b15-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="01b15-127">Na lista, clique no nome do local para o qual você deseja remover um local.</span><span class="sxs-lookup"><span data-stu-id="01b15-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="01b15-128">Na guia **locais** , selecione o local que você deseja remover e clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="01b15-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="01b15-129">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01b15-129">Using PowerShell</span></span>

<span data-ttu-id="01b15-130">Consulte [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="01b15-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="01b15-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="01b15-131">Related topics</span></span>

- [<span data-ttu-id="01b15-132">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="01b15-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="01b15-133">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="01b15-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="01b15-134">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="01b15-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
