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
description: Saiba como usar modelos do Teams para criar estruturas de equipe projetadas para necessidades do revendedor, fornecendo configurações, canais e aplicativos pré-instalados predefinidos.
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
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="3264f-103">Introdução aos modelos do Teams no varejo</span><span class="sxs-lookup"><span data-stu-id="3264f-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="3264f-104">Os modelos do Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="3264f-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3264f-105">Os modelos do Teams têm definições predefinida de estruturas de equipe projetadas em torno das necessidades do varejista.</span><span class="sxs-lookup"><span data-stu-id="3264f-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="3264f-106">Você pode usar modelos do Teams para criar rapidamente os tipos de equipes que funcionam bem para revendedores e implantá-los em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="3264f-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="3264f-107">Você também pode estender os modelos do Teams para criar equipes adaptadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="3264f-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3264f-108">Neste artigo, apresentaremos cada um dos modelos do Teams e recomendaremos como usá-los.</span><span class="sxs-lookup"><span data-stu-id="3264f-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="3264f-109">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em sua organização de varejo.</span><span class="sxs-lookup"><span data-stu-id="3264f-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="3264f-110">Você já implantou o serviço do Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3264f-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="3264f-111">Se você ainda não tiver lançado o Teams, comece lendo o livro Como [lançar o Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3264f-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="3264f-112">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos do Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="3264f-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="3264f-113">Modelo da Loja</span><span class="sxs-lookup"><span data-stu-id="3264f-113">Store template</span></span>

<span data-ttu-id="3264f-114">O modelo da Store é ideal para criar uma equipe para representar um local de loja de varejo individual.</span><span class="sxs-lookup"><span data-stu-id="3264f-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="3264f-115">Usando o modelo da Store, você pode criar uma equipe para cada local da loja de varejo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3264f-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="3264f-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="3264f-116">Base template type</span></span> | <span data-ttu-id="3264f-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3264f-117">baseTemplateId</span></span> | <span data-ttu-id="3264f-118">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="3264f-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="3264f-119">Varejo –</span><span class="sxs-lookup"><span data-stu-id="3264f-119">Retail -</span></span> <br><span data-ttu-id="3264f-120">Repositório</span><span class="sxs-lookup"><span data-stu-id="3264f-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="3264f-121">Canais</span><span class="sxs-lookup"><span data-stu-id="3264f-121">Channels</span></span> <ul><li><span data-ttu-id="3264f-122">Entrega de turnos\*</span><span class="sxs-lookup"><span data-stu-id="3264f-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="3264f-123">Aprendizagem\*</span><span class="sxs-lookup"><span data-stu-id="3264f-123">Learning\*</span></span></li></ul><span data-ttu-id="3264f-124">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="3264f-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="3264f-125">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="3264f-125">Team properties</span></span> <ul><li><span data-ttu-id="3264f-126">Visibilidade da equipe definida como Pública</span><span class="sxs-lookup"><span data-stu-id="3264f-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="3264f-127">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="3264f-127">Member permissions</span></span> <ul><li><span data-ttu-id="3264f-128">Não é possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="3264f-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="3264f-129">Não é possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="3264f-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="3264f-130">Não é possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="3264f-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="3264f-131">Não é possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="3264f-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="3264f-132">Maneiras recomendadas de personalizar o modelo da Store para sua organização:</span><span class="sxs-lookup"><span data-stu-id="3264f-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="3264f-133">Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="3264f-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="3264f-134">Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.</span><span class="sxs-lookup"><span data-stu-id="3264f-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="3264f-135">Se sua organização tiver qualquer site interno (por exemplo, um site do SharePoint), considere fixá-los como guias no canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="3264f-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="3264f-136">Consulte Instruções [sobre como começar a usar modelos do Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="3264f-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="3264f-137">Modelo de Colaboração do Gerente</span><span class="sxs-lookup"><span data-stu-id="3264f-137">Manager Collaboration template</span></span>

<span data-ttu-id="3264f-138">O modelo colaboração do Gerente é outro dos modelos do Teams projetados em torno das necessidades do varejista.</span><span class="sxs-lookup"><span data-stu-id="3264f-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="3264f-139">O modelo colaboração do Gerente é ideal para criar uma equipe para um conjunto de gerentes colaborarem entre lojas/regiões e muito mais.</span><span class="sxs-lookup"><span data-stu-id="3264f-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="3264f-140">Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a Região da Califórnia e incluir todos os gerentes de loja nessa região, bem como o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="3264f-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="3264f-141">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="3264f-141">Base template type</span></span> | <span data-ttu-id="3264f-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3264f-142">baseTemplateId</span></span> | <span data-ttu-id="3264f-143">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="3264f-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="3264f-144">Varejo –</span><span class="sxs-lookup"><span data-stu-id="3264f-144">Retail -</span></span> <br><span data-ttu-id="3264f-145">Repositório</span><span class="sxs-lookup"><span data-stu-id="3264f-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="3264f-146">Canais</span><span class="sxs-lookup"><span data-stu-id="3264f-146">Channels</span></span> <ul><li><span data-ttu-id="3264f-147">Operações\*</span><span class="sxs-lookup"><span data-stu-id="3264f-147">Operations\*</span></span></li><li><span data-ttu-id="3264f-148">Aprendizagem\*</span><span class="sxs-lookup"><span data-stu-id="3264f-148">Learning\*</span></span></li></ul><span data-ttu-id="3264f-149">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="3264f-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="3264f-150">Propriedades da equipe</span><span class="sxs-lookup"><span data-stu-id="3264f-150">Team properties</span></span> <ul><li><span data-ttu-id="3264f-151">Visibilidade da equipe definida como Particular</span><span class="sxs-lookup"><span data-stu-id="3264f-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="3264f-152">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="3264f-152">Member permissions</span></span> <ul><li><span data-ttu-id="3264f-153">Pode criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="3264f-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="3264f-154">Pode adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="3264f-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="3264f-155">Pode criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="3264f-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="3264f-156">Pode criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="3264f-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="3264f-157">Maneiras recomendadas de personalizar o modelo de Colaboração do Gerente para sua organização:</span><span class="sxs-lookup"><span data-stu-id="3264f-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="3264f-158">Se sua organização tiver sites internos, como um site do SharePoint, relevantes para os gerentes, considere fixá-los como guias em um canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="3264f-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="3264f-159">Você pode dar uma olhada na documentação do [Modelo do Microsoft Teams para](get-started-with-teams-templates.md) obter instruções.</span><span class="sxs-lookup"><span data-stu-id="3264f-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="3264f-160">Como usar modelos de primeira parte</span><span class="sxs-lookup"><span data-stu-id="3264f-160">How to use first party templates</span></span>

<span data-ttu-id="3264f-161">Para usar esses modelos, altere a propriedade 'template@odata.bind' no corpo da solicitação de 'padrão' para as IDs modelo acima.</span><span class="sxs-lookup"><span data-stu-id="3264f-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="3264f-162">Para obter mais informações sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph sobre como [criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="3264f-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="3264f-163">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="3264f-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="3264f-164">Exemplo: Script de extensão de modelo da Store</span><span class="sxs-lookup"><span data-stu-id="3264f-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="3264f-165">Relacionar tópico</span><span class="sxs-lookup"><span data-stu-id="3264f-165">Relate topic</span></span>

[<span data-ttu-id="3264f-166">Começar a usar modelos do Teams no Centro de administração</span><span class="sxs-lookup"><span data-stu-id="3264f-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
