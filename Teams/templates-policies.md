---
title: Gerenciar modelos de equipe no centro de administração
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar modelos de equipe no centro de administração
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125858"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="e2778-103">Criar e gerenciar modelos de equipe no centro de administração</span><span class="sxs-lookup"><span data-stu-id="e2778-103">Create and manage Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="e2778-104">Gerencie os modelos do teams que são mostrados para seus usuários finais criando políticas de modelos no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="e2778-104">Manage the Teams templates that are shown to your end users by creating templates policies in the admin center.</span></span> <span data-ttu-id="e2778-105">Em cada política de modelo, você pode designar quais modelos são mostrados ou ocultos.</span><span class="sxs-lookup"><span data-stu-id="e2778-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="e2778-106">Atribua diferentes usuários a políticas de modelos diferentes para que seus usuários exibam somente o subconjunto de modelos de equipes especificado.</span><span class="sxs-lookup"><span data-stu-id="e2778-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="e2778-107">Criar políticas de modelo e atribuir modelos disponíveis</span><span class="sxs-lookup"><span data-stu-id="e2778-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="e2778-108">Entre no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2778-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="e2778-109">Expanda políticas de modelos do **Teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="e2778-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="e2778-110">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-110">Select **Add**.</span></span>

    ![As políticas de modelo são selecionadas e a adição é realçada](media/template-policies-1.png)

1. <span data-ttu-id="e2778-112">Na seção **configurações de políticas de modelos** , preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="e2778-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="e2778-113">Nome da política de modelos</span><span class="sxs-lookup"><span data-stu-id="e2778-113">Templates Policy name</span></span>

    - <span data-ttu-id="e2778-114">Descrição resumida da política modelos</span><span class="sxs-lookup"><span data-stu-id="e2778-114">Templates Policy short description</span></span>

2. <span data-ttu-id="e2778-115">Na tabela **modelos exibíveis** , selecione os modelos que você deseja ocultar e selecione **ocultar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Os modelos selecionados com ocultar realçado](media/template-policies-2.png)

    <span data-ttu-id="e2778-117">Você pode ver os modelos que selecionou para ocultar na tabela **modelos ocultos** .</span><span class="sxs-lookup"><span data-stu-id="e2778-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="e2778-118">Para reexibir determinados modelos, role até a tabela **modelos ocultos** .</span><span class="sxs-lookup"><span data-stu-id="e2778-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="e2778-119">Selecione os modelos para reexibir e selecione **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Os modelos selecionados com ocultar realçado](media/template-policies-3.png)

   <span data-ttu-id="e2778-121">Os modelos selecionados aparecerão na tabela **modelos exibíveis** .</span><span class="sxs-lookup"><span data-stu-id="e2778-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="e2778-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-122">Select **Save**.</span></span>

   <span data-ttu-id="e2778-123">Sua nova política de modelo é exibida na lista **políticas de modelos** .</span><span class="sxs-lookup"><span data-stu-id="e2778-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="e2778-124">Atribuir usuários às políticas de modelo</span><span class="sxs-lookup"><span data-stu-id="e2778-124">Assign users to the template policies</span></span>

<span data-ttu-id="e2778-125">Os usuários atribuídos a uma política só poderão ver os modelos visíveis dentro dessa política.</span><span class="sxs-lookup"><span data-stu-id="e2778-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="e2778-126">Em **políticas de modelos**, selecione uma política e, em seguida, selecione **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="e2778-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="e2778-127">Digite os usuários que deseja atribuir a essa política.</span><span class="sxs-lookup"><span data-stu-id="e2778-127">Type the users to assign to this policy.</span></span>

   ![Os modelos selecionados com ocultar realçado](media/template-policies-4.png)

3. <span data-ttu-id="e2778-129">Selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="e2778-130">Pode levar até 24 horas para que sua nova política entre em vigor para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="e2778-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="e2778-131">Limites de tamanho para políticas de modelo</span><span class="sxs-lookup"><span data-stu-id="e2778-131">Size limits for Template policies</span></span>

<span data-ttu-id="e2778-132">Você pode ocultar um máximo de modelos do 100 por política.</span><span class="sxs-lookup"><span data-stu-id="e2778-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="e2778-133">O botão **ocultar** estará desabilitado se a política fornecida já tiver modelos do 100 ocultos.</span><span class="sxs-lookup"><span data-stu-id="e2778-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="e2778-134">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e2778-134">Frequently asked questions</span></span>

<span data-ttu-id="e2778-135">**P: posso atribuir usuários a políticas de modelos de equipe a um lote?**</span><span class="sxs-lookup"><span data-stu-id="e2778-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="e2778-136">R: Sim, oferecemos suporte à atribuição em lote para a política de modelo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2778-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="e2778-137">O tipo de política para esta ação é TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="e2778-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="e2778-138">Saiba Mais</span><span class="sxs-lookup"><span data-stu-id="e2778-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="e2778-139">**P: os grupos podem ser atribuídos a políticas de modelos de equipe?**</span><span class="sxs-lookup"><span data-stu-id="e2778-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="e2778-140">R: no momento.</span><span class="sxs-lookup"><span data-stu-id="e2778-140">A: Currently no.</span></span> <span data-ttu-id="e2778-141">Esta funcionalidade estará disponível no futuro.</span><span class="sxs-lookup"><span data-stu-id="e2778-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="e2778-142">**P: se um novo modelo for criado, o modelo será incluído em minhas políticas?**</span><span class="sxs-lookup"><span data-stu-id="e2778-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="e2778-143">R: os modelos novos ficarão visíveis por padrão.</span><span class="sxs-lookup"><span data-stu-id="e2778-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="e2778-144">Você pode optar por ocultar o modelo no centro de administração na seção políticas de modelos.</span><span class="sxs-lookup"><span data-stu-id="e2778-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="e2778-145">**P: o que acontece se um modelo é excluído?**</span><span class="sxs-lookup"><span data-stu-id="e2778-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="e2778-146">R: todos os modelos excluídos não estarão mais presentes em políticas de modelos.</span><span class="sxs-lookup"><span data-stu-id="e2778-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="e2778-147">**P: posso atribuir vários usuários a uma política de modelo no centro de administração do teams?**</span><span class="sxs-lookup"><span data-stu-id="e2778-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="e2778-148">R: Sim.</span><span class="sxs-lookup"><span data-stu-id="e2778-148">A: Yes.</span></span>

1. <span data-ttu-id="e2778-149">No centro de administração, vá para **usuários**.</span><span class="sxs-lookup"><span data-stu-id="e2778-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="e2778-150">Na tabela lista de usuários, selecione os usuários que você deseja atribuir a determinada política de modelos.</span><span class="sxs-lookup"><span data-stu-id="e2778-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="e2778-151">Selecione Editar configurações e altere o campo políticas de modelos.</span><span class="sxs-lookup"><span data-stu-id="e2778-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="e2778-152">Selecione aplicar.</span><span class="sxs-lookup"><span data-stu-id="e2778-152">Select apply.</span></span>
   <span data-ttu-id="e2778-153">Saiba mais [atribuir políticas a seus usuários no Microsoft Teams-Microsoft Teams \| Microsoft docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="e2778-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="e2778-154">**P: como exibir todos os usuários atribuídos a uma política específica?**</span><span class="sxs-lookup"><span data-stu-id="e2778-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="e2778-155">R: no centro de administração:</span><span class="sxs-lookup"><span data-stu-id="e2778-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="e2778-156">Vá para a seção **usuários** .</span><span class="sxs-lookup"><span data-stu-id="e2778-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="e2778-157">Selecione o filtro na tabela da lista usuários e o filtro para a política de modelo do teams.</span><span class="sxs-lookup"><span data-stu-id="e2778-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="e2778-158">Selecione **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e2778-158">Select **Apply**.</span></span>

![Os modelos selecionados com ocultar realçado](media/template-policies-5.png)

<span data-ttu-id="e2778-160">**P: é possível gerenciar políticas de modelos pelo PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="e2778-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="e2778-161">R: não, isso não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="e2778-161">A: No, this isn't supported.</span></span>

<span data-ttu-id="e2778-162">**P: as políticas de modelos se aplicam ao EDU?**</span><span class="sxs-lookup"><span data-stu-id="e2778-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="e2778-163">R: não, isso não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="e2778-163">A: No, this isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e2778-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2778-164">Related topics</span></span>

- [<span data-ttu-id="e2778-165">Introdução aos modelos de equipe no centro de administração</span><span class="sxs-lookup"><span data-stu-id="e2778-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="e2778-166">Criar um modelo de equipe personalizado</span><span class="sxs-lookup"><span data-stu-id="e2778-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="e2778-167">Criar um modelo a partir de uma equipe existente</span><span class="sxs-lookup"><span data-stu-id="e2778-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="e2778-168">Criar um modelo de equipe a partir de um modelo de equipe existente</span><span class="sxs-lookup"><span data-stu-id="e2778-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="e2778-169">Atribuir políticas a seus usuários no Microsoft Teams-Microsoft Teams \| Microsoft docs</span><span class="sxs-lookup"><span data-stu-id="e2778-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="e2778-170">TeamsTemplatePermissionPolicy</span><span class="sxs-lookup"><span data-stu-id="e2778-170">TeamsTemplatePermissionPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)