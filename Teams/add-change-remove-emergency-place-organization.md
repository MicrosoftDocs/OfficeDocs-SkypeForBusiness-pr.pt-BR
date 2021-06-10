---
title: Adicionar, alterar, remover locais para locais de emergência
author: cichur
ms.author: v-cichur
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
description: Saiba como adicionar, alterar ou remover um local de emergência para sua organização no Microsoft Teams de administração.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50343fbd1d16694e46afafe53114f2dde4b7b150
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121499"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="b7c52-103">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="b7c52-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="b7c52-104">Dependendo do número de locais físicos em sua organização, você pode adicionar locais para edifícios, pisos e escritórios para criar um local de emergência mais específico.</span><span class="sxs-lookup"><span data-stu-id="b7c52-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="b7c52-105">Consulte [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b7c52-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="b7c52-106">Para saber como obter um Plano de Chamada e quanto eles custam, [consulte Teams licenciamento de complemento.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="b7c52-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="b7c52-107">Você gerencia locais de emergência para sua organização no centro de administração Microsoft Teams ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7c52-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="b7c52-108">Adicionar um local a um local de emergência</span><span class="sxs-lookup"><span data-stu-id="b7c52-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7c52-109">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7c52-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b7c52-110">Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b7c52-111">Na lista, clique no nome do local para o qual você deseja adicionar um lugar.</span><span class="sxs-lookup"><span data-stu-id="b7c52-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="b7c52-112">Na guia **Locais,** clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="b7c52-113">Insira um nome de local e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7c52-114">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c52-114">Using PowerShell</span></span>

<span data-ttu-id="b7c52-115">Consulte [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="b7c52-115">See [New-CsOnlineLisLocation](/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="b7c52-116">Alterar um local para um local de emergência</span><span class="sxs-lookup"><span data-stu-id="b7c52-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7c52-117">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7c52-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b7c52-118">Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b7c52-119">Na lista, clique no nome do local para o qual você deseja alterar um local.</span><span class="sxs-lookup"><span data-stu-id="b7c52-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="b7c52-120">Na guia **Locais,** selecione o local que você deseja alterar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="b7c52-121">Atualize as informações do local e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7c52-122">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c52-122">Using PowerShell</span></span>

<span data-ttu-id="b7c52-123">Consulte [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="b7c52-123">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="b7c52-124">Remover um local de emergência</span><span class="sxs-lookup"><span data-stu-id="b7c52-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b7c52-125">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7c52-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b7c52-126">Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Locais**  >  **Endereços de emergência**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="b7c52-127">Na lista, clique no nome do local para o qual você deseja remover um local.</span><span class="sxs-lookup"><span data-stu-id="b7c52-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="b7c52-128">Na guia **Locais,** selecione o local que você deseja remover e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b7c52-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7c52-129">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7c52-129">Using PowerShell</span></span>

<span data-ttu-id="b7c52-130">Consulte [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span><span class="sxs-lookup"><span data-stu-id="b7c52-130">See [Remove-CsOnlineLisLocation](/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b7c52-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b7c52-131">Related topics</span></span>

- [<span data-ttu-id="b7c52-132">Adicionar, alterar ou remover um endereço de um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="b7c52-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="b7c52-133">Gerenciar os números de telefone de sua organização</span><span class="sxs-lookup"><span data-stu-id="b7c52-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="b7c52-134">Termos e condições das Chamadas de Emergência</span><span class="sxs-lookup"><span data-stu-id="b7c52-134">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)