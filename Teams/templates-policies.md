---
title: Gerenciar modelos do Teams no centro de administração
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
description: Saiba como gerenciar modelos do Teams no centro de administração
ms.openlocfilehash: 27cf2d2d80f0e715e5ee9e9390ca86d81bd39d70
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875131"
---
# <a name="manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="c7ac4-103">Gerenciar modelos do Teams no centro de administração</span><span class="sxs-lookup"><span data-stu-id="c7ac4-103">Manage Teams templates in the admin center</span></span>

<span data-ttu-id="c7ac4-104">Gerencie os modelos do Teams que os usuários finais veem criando políticas de modelos no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="c7ac4-105">Em cada política de modelo, você pode designar quais modelos são mostrados ou ocultos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="c7ac4-106">Atribua usuários diferentes a políticas de modelo diferentes para que seus usuários visualizam apenas o subconjunto de modelos do Teams especificados.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-106">Assign different users to different template policies so that your users view only the subset of Teams templates specified.</span></span>

<span data-ttu-id="c7ac4-107">Assista a este breve vídeo para saber como gerenciar políticas de modelo.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="c7ac4-108">Criar políticas de modelo e atribuir modelos disponíveis</span><span class="sxs-lookup"><span data-stu-id="c7ac4-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="c7ac4-109">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="c7ac4-110">Expanda **políticas**  >  **de Modelos do** Teams.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="c7ac4-111">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-111">Select **Add**.</span></span>

    ![As políticas de modelo são selecionadas e Add é realçada](media/template-policies-1.png)

1. <span data-ttu-id="c7ac4-113">Na seção **Configurações de Políticas de Modelos,** conclua os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c7ac4-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="c7ac4-114">Nome da Política de Modelos</span><span class="sxs-lookup"><span data-stu-id="c7ac4-114">Templates Policy name</span></span>

    - <span data-ttu-id="c7ac4-115">Descrição curta da Política de Modelos</span><span class="sxs-lookup"><span data-stu-id="c7ac4-115">Templates Policy short description</span></span>

2. <span data-ttu-id="c7ac4-116">Na tabela **Modelos Exibiveis,** selecione os modelos que você deseja ocultar e selecione **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Os modelos selecionados com ocultação realçada](media/template-policies-2.png)

    <span data-ttu-id="c7ac4-118">Você pode ver os modelos selecionados para ocultar na tabela **Modelos Ocultos.**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="c7ac4-119">Para desaconsule determinados modelos, role até **a tabela Modelos ocultos.**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

2. <span data-ttu-id="c7ac4-120">Selecione os modelos a ser desaconsudidados e selecione **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![Os modelos selecionados que não estão ocultos](media/template-policies-3.png)

   <span data-ttu-id="c7ac4-122">Os modelos selecionados serão exibidos na tabela **Modelos Exibiveis.**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="c7ac4-123">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-123">Select **Save**.</span></span>

   <span data-ttu-id="c7ac4-124">Sua nova política de modelo é exibida na lista **Políticas de** Modelos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="c7ac4-125">Atribuir usuários às políticas de modelo</span><span class="sxs-lookup"><span data-stu-id="c7ac4-125">Assign users to the template policies</span></span>

<span data-ttu-id="c7ac4-126">Os usuários atribuídos a uma política só poderão exibir os modelos que podem ser visualizados nessa política.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="c7ac4-127">Em **Políticas de Modelos,** selecione uma política e selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="c7ac4-128">Digite os usuários a atribuir a essa política.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-128">Type the users to assign to this policy.</span></span>

   ![atribuir usuários a uma política de modelo](media/template-policies-4.png)

3. <span data-ttu-id="c7ac4-130">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="c7ac4-131">Pode levar até 24 horas para que sua nova política entre em vigor para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="c7ac4-132">Limites de tamanho para políticas de modelo</span><span class="sxs-lookup"><span data-stu-id="c7ac4-132">Size limits for Template policies</span></span>

<span data-ttu-id="c7ac4-133">Você pode ocultar um máximo de 100 modelos por política.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="c7ac4-134">O **botão Ocultar** será desabilitado se a política determinada já tiver 100 modelos ocultos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c7ac4-135">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="c7ac4-135">Frequently asked questions</span></span>

<span data-ttu-id="c7ac4-136">**P: Posso atribuir usuários em lote a políticas de modelos de equipe?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="c7ac4-137">R: Sim, suportamos a atribuição em lote para a política de modelo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="c7ac4-138">O tipo de política dessa ação é TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="c7ac4-139">Saiba Mais</span><span class="sxs-lookup"><span data-stu-id="c7ac4-139">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="c7ac4-140">**P: Os grupos podem ser atribuídos às políticas de modelos de equipe?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="c7ac4-141">R: Atualmente não.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-141">A: Currently no.</span></span> <span data-ttu-id="c7ac4-142">Essa funcionalidade estará disponível no futuro.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="c7ac4-143">**P: Se um novo modelo for criado, o modelo será incluído em minhas políticas?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="c7ac4-144">R: Todos os novos modelos estarão visíveis por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="c7ac4-145">Você pode optar por ocultar o modelo no centro de administração na seção Políticas de Modelos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="c7ac4-146">**P: O que acontece se um modelo for excluído?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="c7ac4-147">R: Quaisquer modelos excluídos não estarão mais presentes em nenhuma política de modelos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="c7ac4-148">**P: Posso atribuir vários usuários a uma política de modelo no Centro de Administração do Teams?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="c7ac4-149">R: Sim.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-149">A: Yes.</span></span>

1. <span data-ttu-id="c7ac4-150">No Centro de administração, vá para **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="c7ac4-151">Na tabela de lista Usuários, selecione os usuários que você deseja atribuir a uma determinada política de modelos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="c7ac4-152">Selecione Editar configurações e altere o campo Políticas de modelos.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="c7ac4-153">Selecione aplicar.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-153">Select apply.</span></span>
   <span data-ttu-id="c7ac4-154">Saiba mais [Atribuir políticas aos seus usuários no Microsoft Teams - Microsoft Teams Microsoft \| Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="c7ac4-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="c7ac4-155">**P: Como vejo todos os usuários atribuídos a uma política específica?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="c7ac4-156">R: No Centro de administração:</span><span class="sxs-lookup"><span data-stu-id="c7ac4-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="c7ac4-157">Vá para a **seção Usuários.**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="c7ac4-158">Selecione o filtro na tabela de lista Usuários e filtre a política de modelo de equipes.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-158">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="c7ac4-159">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-159">Select **Apply**.</span></span>

![A política de modelo selecionada e exibir usuários](media/template-policies-5.png)

<span data-ttu-id="c7ac4-161">**P: Posso gerenciar políticas de modelos por meio do PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="c7ac4-162">R: Não há suporte para gerenciar modelos no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="c7ac4-163">**P: As políticas de modelos são aplicáveis ao EDU?**</span><span class="sxs-lookup"><span data-stu-id="c7ac4-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="c7ac4-164">R: Não, não há suporte para políticas de modelo para EDU.</span><span class="sxs-lookup"><span data-stu-id="c7ac4-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7ac4-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c7ac4-165">Related topics</span></span>

- [<span data-ttu-id="c7ac4-166">Começar a usar modelos de equipe no centro de administração</span><span class="sxs-lookup"><span data-stu-id="c7ac4-166">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="c7ac4-167">Criar um modelo de equipe personalizado</span><span class="sxs-lookup"><span data-stu-id="c7ac4-167">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="c7ac4-168">Criar um modelo de uma equipe existente</span><span class="sxs-lookup"><span data-stu-id="c7ac4-168">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="c7ac4-169">Criar um modelo de equipe a partir de um modelo de equipe existente</span><span class="sxs-lookup"><span data-stu-id="c7ac4-169">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="c7ac4-170">Atribuir políticas aos seus usuários no Microsoft Teams - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c7ac4-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="c7ac4-171">Atribuir em lotes usuários a uma política</span><span class="sxs-lookup"><span data-stu-id="c7ac4-171">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
