---
title: Introdução aos modelos do Teams no varejo
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar modelos de equipe para criar estruturas de equipe projetadas para as necessidades do revendedor fornecendo configurações, canais e aplicativos pré-instalados predefinidos.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424631"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="ad206-103">Introdução aos modelos do Teams no varejo</span><span class="sxs-lookup"><span data-stu-id="ad206-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="ad206-104">Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="ad206-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ad206-105">Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base nas necessidades do revendedor.</span><span class="sxs-lookup"><span data-stu-id="ad206-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="ad206-106">Você pode usar modelos do teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-las em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="ad206-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="ad206-107">Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="ad206-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="ad206-108">Neste artigo, apresentaremos cada um dos modelos de equipe e recomendaremos como usá-los.</span><span class="sxs-lookup"><span data-stu-id="ad206-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="ad206-109">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de varejo.</span><span class="sxs-lookup"><span data-stu-id="ad206-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="ad206-110">Você já implantou o serviço Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad206-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="ad206-111">Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ad206-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="ad206-112">Para saber mais sobre os modelos de equipe em geral, confira [introdução aos modelos](get-started-with-teams-templates.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad206-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="ad206-113">Modelo da loja</span><span class="sxs-lookup"><span data-stu-id="ad206-113">Store template</span></span>

<span data-ttu-id="ad206-114">O modelo da loja é ideal para criar uma equipe para representar um local individual da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="ad206-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="ad206-115">Usando o modelo da loja, você pode criar uma equipe para cada local da loja de varejo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ad206-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="ad206-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="ad206-116">Base template type</span></span> | <span data-ttu-id="ad206-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ad206-117">baseTemplateId</span></span> | <span data-ttu-id="ad206-118">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="ad206-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="ad206-119">Varejo</span><span class="sxs-lookup"><span data-stu-id="ad206-119">Retail -</span></span> <br><span data-ttu-id="ad206-120">Repositório</span><span class="sxs-lookup"><span data-stu-id="ad206-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="ad206-121">Canais</span><span class="sxs-lookup"><span data-stu-id="ad206-121">Channels</span></span> <ul><li><span data-ttu-id="ad206-122">Entrega de turnos\*</span><span class="sxs-lookup"><span data-stu-id="ad206-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="ad206-123">Aprendizagem\*</span><span class="sxs-lookup"><span data-stu-id="ad206-123">Learning\*</span></span></li></ul><span data-ttu-id="ad206-124">\*Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="ad206-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="ad206-125">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="ad206-125">Team properties</span></span> <ul><li><span data-ttu-id="ad206-126">Visibilidade da equipe definida como Public</span><span class="sxs-lookup"><span data-stu-id="ad206-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="ad206-127">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="ad206-127">Member permissions</span></span> <ul><li><span data-ttu-id="ad206-128">Não é possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="ad206-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="ad206-129">Não é possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="ad206-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="ad206-130">Não é possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="ad206-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="ad206-131">Não é possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="ad206-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="ad206-132">Maneiras recomendadas de personalizar o modelo de loja para sua organização:</span><span class="sxs-lookup"><span data-stu-id="ad206-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="ad206-133">Se a sua organização tiver departamentos em cada loja, adicione um canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="ad206-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="ad206-134">Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.</span><span class="sxs-lookup"><span data-stu-id="ad206-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="ad206-135">Se sua organização tiver sites internos (por exemplo, um site do SharePoint), considere fixar como guias no canal da equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="ad206-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="ad206-136">Confira o introdução ao [Teams templates](get-started-with-teams-templates.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ad206-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="ad206-137">Modelo de colaboração do gerente</span><span class="sxs-lookup"><span data-stu-id="ad206-137">Manager Collaboration template</span></span>

<span data-ttu-id="ad206-138">O modelo de colaboração do gerente é outro um dos modelos de equipe projetados em torno das necessidades do revendedor.</span><span class="sxs-lookup"><span data-stu-id="ad206-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="ad206-139">O modelo de colaboração do gerente é ideal para criar uma equipe para um conjunto de gerentes colaborar em lojas/regiões e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ad206-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="ad206-140">Por exemplo, se a sua organização tiver regiões, você pode criar uma equipe de colaboração do gerente para a região da Califórnia e incluir todos os gerentes da loja nessa região, bem como o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="ad206-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="ad206-141">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="ad206-141">Base template type</span></span> | <span data-ttu-id="ad206-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ad206-142">baseTemplateId</span></span> | <span data-ttu-id="ad206-143">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="ad206-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="ad206-144">Varejo</span><span class="sxs-lookup"><span data-stu-id="ad206-144">Retail -</span></span> <br><span data-ttu-id="ad206-145">Repositório</span><span class="sxs-lookup"><span data-stu-id="ad206-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="ad206-146">Canais</span><span class="sxs-lookup"><span data-stu-id="ad206-146">Channels</span></span> <ul><li><span data-ttu-id="ad206-147">Operações\*</span><span class="sxs-lookup"><span data-stu-id="ad206-147">Operations\*</span></span></li><li><span data-ttu-id="ad206-148">Aprendizagem\*</span><span class="sxs-lookup"><span data-stu-id="ad206-148">Learning\*</span></span></li></ul><span data-ttu-id="ad206-149">\*Canais de favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="ad206-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="ad206-150">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="ad206-150">Team properties</span></span> <ul><li><span data-ttu-id="ad206-151">Visibilidade da equipe definida como particular</span><span class="sxs-lookup"><span data-stu-id="ad206-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="ad206-152">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="ad206-152">Member permissions</span></span> <ul><li><span data-ttu-id="ad206-153">Pode criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="ad206-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="ad206-154">Pode adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="ad206-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="ad206-155">Pode criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="ad206-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="ad206-156">Pode criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="ad206-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="ad206-157">Maneiras recomendadas de personalizar o modelo de colaboração do gerente para sua organização:</span><span class="sxs-lookup"><span data-stu-id="ad206-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="ad206-158">Se a sua organização tiver qualquer site interno, como um site do SharePoint, que seja relevante para gerentes, considere fixar as guias em um canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="ad206-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="ad206-159">Você pode dar uma olhada na [documentação do modelo do Microsoft Teams](get-started-with-teams-templates.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ad206-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="ad206-160">Como usar modelos de primeira empresa</span><span class="sxs-lookup"><span data-stu-id="ad206-160">How to use first party templates</span></span>

<span data-ttu-id="ad206-161">Para usar esses modelos, altere a propriedade ' template@odata. BIND ' no corpo da solicitação de ' Standard ' para a TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="ad206-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="ad206-162">Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph sobre como [criar uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="ad206-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="ad206-163">Os canais no modelo serão automaticamente criados na guia geral.</span><span class="sxs-lookup"><span data-stu-id="ad206-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="ad206-164">Exemplo: armazenar script de extensão de modelo</span><span class="sxs-lookup"><span data-stu-id="ad206-164">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a><span data-ttu-id="ad206-165">Tópico de relação</span><span class="sxs-lookup"><span data-stu-id="ad206-165">Relate topic</span></span>

[<span data-ttu-id="ad206-166">Introdução aos modelos do Microsoft Teams no centro de administração</span><span class="sxs-lookup"><span data-stu-id="ad206-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
