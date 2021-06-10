---
title: Começar com um modelo de equipe no varejo
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
description: Saiba como usar modelos de equipe para criar estruturas de equipe projetadas para necessidades do varejista fornecendo configurações, canais e aplicativos pré-instalados predefinidos.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684549"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="d02b9-103">Criar uma equipe usando modelos de equipe de varejo</span><span class="sxs-lookup"><span data-stu-id="d02b9-103">Create a team using retail team templates</span></span>

<span data-ttu-id="d02b9-104">Os modelos de equipe da Microsoft permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="d02b9-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d02b9-105">Os modelos de equipe têm definições pré-criadas de estruturas de equipe projetadas em torno das necessidades do varejista.</span><span class="sxs-lookup"><span data-stu-id="d02b9-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="d02b9-106">Você pode usar modelos de equipe para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-los em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d02b9-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="d02b9-107">Você também pode estender os modelos de equipe para criar equipes adaptadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="d02b9-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="d02b9-108">Neste artigo, apresentaremos cada um dos modelos de equipe e recomendaremos como usá-los.</span><span class="sxs-lookup"><span data-stu-id="d02b9-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="d02b9-109">Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de varejo.</span><span class="sxs-lookup"><span data-stu-id="d02b9-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="d02b9-110">Você já implantou o serviço Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d02b9-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="d02b9-111">Se você ainda não implementou o Teams, comece lendo [Como implementar o Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d02b9-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="d02b9-112">Para saber mais sobre modelos de equipe em geral, consulte [Get started with team templates](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d02b9-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="d02b9-113">Quem</span><span class="sxs-lookup"><span data-stu-id="d02b9-113">Who</span></span> | <span data-ttu-id="d02b9-114">Método a ser usado:</span><span class="sxs-lookup"><span data-stu-id="d02b9-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="d02b9-115">Administradores e profissionais de TI</span><span class="sxs-lookup"><span data-stu-id="d02b9-115">Admins and IT Professionals</span></span> | <span data-ttu-id="d02b9-116">[Use o Teams de administração](#use-the-team-templates-in-the-teams-admin-center) para criar equipes com base nos modelos de equipe de varejo.</span><span class="sxs-lookup"><span data-stu-id="d02b9-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="d02b9-117">Os desenvolvedores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="d02b9-117">Developers and systems integrators</span></span> | <span data-ttu-id="d02b9-118">[Use o microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) para criar equipes com base nos modelos de equipe de varejo.</span><span class="sxs-lookup"><span data-stu-id="d02b9-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="d02b9-119">Usar os modelos de equipe no Teams de administração</span><span class="sxs-lookup"><span data-stu-id="d02b9-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="d02b9-120">Organizar uma store</span><span class="sxs-lookup"><span data-stu-id="d02b9-120">Organize a store</span></span>

<span data-ttu-id="d02b9-121">Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e resolver problemas de clientes.</span><span class="sxs-lookup"><span data-stu-id="d02b9-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="d02b9-122">Integre aplicativos adicionais para simplificar os processos de início e fim de turno.</span><span class="sxs-lookup"><span data-stu-id="d02b9-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="d02b9-123">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-123">Base template type</span></span> |<span data-ttu-id="d02b9-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d02b9-124">baseTemplateId</span></span> | <span data-ttu-id="d02b9-125">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="d02b9-126">Organizar uma store</span><span class="sxs-lookup"><span data-stu-id="d02b9-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="d02b9-127">Canais:</span><span class="sxs-lookup"><span data-stu-id="d02b9-127">Channels:</span></span> <ul><li><span data-ttu-id="d02b9-128">Geral</span><span class="sxs-lookup"><span data-stu-id="d02b9-128">General</span></span><li><span data-ttu-id="d02b9-129">Mudança de entrega</span><span class="sxs-lookup"><span data-stu-id="d02b9-129">Shift handoff</span></span></li><li><span data-ttu-id="d02b9-130">Aprendizado</span><span class="sxs-lookup"><span data-stu-id="d02b9-130">Learning</span></span></li></ul> <span data-ttu-id="d02b9-131">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="d02b9-131">Apps:</span></span> <ul><li><span data-ttu-id="d02b9-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="d02b9-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="d02b9-133">Colaboração do Gerente</span><span class="sxs-lookup"><span data-stu-id="d02b9-133">Manager Collaboration</span></span>

<span data-ttu-id="d02b9-134">O modelo de Colaboração do Gerente é ideal para criar uma equipe para um conjunto de gerentes colaborarem entre lojas/regiões, etc. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a Região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="d02b9-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="d02b9-135">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-135">Base template type</span></span>| <span data-ttu-id="d02b9-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d02b9-136">baseTemplateId</span></span> | <span data-ttu-id="d02b9-137">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="d02b9-138">Varejo - colaboração do gerente</span><span class="sxs-lookup"><span data-stu-id="d02b9-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="d02b9-139">Canais:</span><span class="sxs-lookup"><span data-stu-id="d02b9-139">Channels:</span></span> <ul><li><span data-ttu-id="d02b9-140">Geral</span><span class="sxs-lookup"><span data-stu-id="d02b9-140">General</span></span><li><span data-ttu-id="d02b9-141">Operações</span><span class="sxs-lookup"><span data-stu-id="d02b9-141">Operations</span></span></li><li><span data-ttu-id="d02b9-142">Aprendizado</span><span class="sxs-lookup"><span data-stu-id="d02b9-142">Learning</span></span></li></ul> <span data-ttu-id="d02b9-143">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="d02b9-143">Apps:</span></span> <ul><li><span data-ttu-id="d02b9-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="d02b9-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="d02b9-145">Use os modelos de equipe com o microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d02b9-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="d02b9-146">Modelo de Loja</span><span class="sxs-lookup"><span data-stu-id="d02b9-146">Store template</span></span>

<span data-ttu-id="d02b9-147">O modelo de Loja é ideal para criar uma equipe para representar um local de loja individual.</span><span class="sxs-lookup"><span data-stu-id="d02b9-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="d02b9-148">Usando o modelo de Loja, você pode criar uma equipe para cada local de loja de varejo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d02b9-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="d02b9-149">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-149">Base template type</span></span> | <span data-ttu-id="d02b9-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d02b9-150">baseTemplateId</span></span> | <span data-ttu-id="d02b9-151">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d02b9-152">Varejo -</span><span class="sxs-lookup"><span data-stu-id="d02b9-152">Retail -</span></span> <br><span data-ttu-id="d02b9-153">Loja</span><span class="sxs-lookup"><span data-stu-id="d02b9-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="d02b9-154">Canais</span><span class="sxs-lookup"><span data-stu-id="d02b9-154">Channels</span></span> <ul><li><span data-ttu-id="d02b9-155">Entrega dos turnos\*</span><span class="sxs-lookup"><span data-stu-id="d02b9-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="d02b9-156">Aprendizado\*</span><span class="sxs-lookup"><span data-stu-id="d02b9-156">Learning\*</span></span></li></ul><span data-ttu-id="d02b9-157">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="d02b9-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d02b9-158">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="d02b9-158">Team properties</span></span> <ul><li><span data-ttu-id="d02b9-159">Visibilidade da equipe definida como Pública</span><span class="sxs-lookup"><span data-stu-id="d02b9-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="d02b9-160">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="d02b9-160">Member permissions</span></span> <ul><li><span data-ttu-id="d02b9-161">Não é possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="d02b9-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="d02b9-162">Não é possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="d02b9-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="d02b9-163">Não é possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="d02b9-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="d02b9-164">Não é possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="d02b9-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d02b9-165">Maneiras recomendadas de personalizar o modelo de Loja para sua organização:</span><span class="sxs-lookup"><span data-stu-id="d02b9-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="d02b9-166">Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="d02b9-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="d02b9-167">Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.</span><span class="sxs-lookup"><span data-stu-id="d02b9-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="d02b9-168">Se sua organização tiver sites internos (por exemplo, um site do Microsoft Office SharePoint Online), considere fixá-los como guias no canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="d02b9-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="d02b9-169">Consulte [Começar a usar modelos de equipe para](get-started-with-teams-templates.md) obter instruções.</span><span class="sxs-lookup"><span data-stu-id="d02b9-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="d02b9-170">Modelo Colaboração de Gerente</span><span class="sxs-lookup"><span data-stu-id="d02b9-170">Manager Collaboration template</span></span>

<span data-ttu-id="d02b9-171">O modelo de Colaboração do Gerente é outro dos modelos de equipe projetados em torno das necessidades do varejista.</span><span class="sxs-lookup"><span data-stu-id="d02b9-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="d02b9-172">O modelo Colaboração de Gerente é ideal para criar uma equipe para um conjunto de gerentes para colaborar em lojas/regiões e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d02b9-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="d02b9-173">Por exemplo, se sua organização tem regiões, você pode criar uma equipe de Colaboração de Gerente para a Região da Califórnia e incluir todos os gerentes de loja dessa região, bem como o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="d02b9-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="d02b9-174">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-174">Base template type</span></span> | <span data-ttu-id="d02b9-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d02b9-175">baseTemplateId</span></span> | <span data-ttu-id="d02b9-176">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="d02b9-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d02b9-177">Varejo -</span><span class="sxs-lookup"><span data-stu-id="d02b9-177">Retail -</span></span> <br><span data-ttu-id="d02b9-178">Loja</span><span class="sxs-lookup"><span data-stu-id="d02b9-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="d02b9-179">Canais</span><span class="sxs-lookup"><span data-stu-id="d02b9-179">Channels</span></span> <ul><li><span data-ttu-id="d02b9-180">Operações\*</span><span class="sxs-lookup"><span data-stu-id="d02b9-180">Operations\*</span></span></li><li><span data-ttu-id="d02b9-181">Aprendizado\*</span><span class="sxs-lookup"><span data-stu-id="d02b9-181">Learning\*</span></span></li></ul><span data-ttu-id="d02b9-182">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="d02b9-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d02b9-183">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="d02b9-183">Team properties</span></span> <ul><li><span data-ttu-id="d02b9-184">Visibilidade da equipe definida como Privada</span><span class="sxs-lookup"><span data-stu-id="d02b9-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="d02b9-185">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="d02b9-185">Member permissions</span></span> <ul><li><span data-ttu-id="d02b9-186">É possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="d02b9-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="d02b9-187">É possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="d02b9-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="d02b9-188">É possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="d02b9-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="d02b9-189">É possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="d02b9-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d02b9-190">Maneiras recomendadas de personalizar o modelo Colaboração de Gerente para sua organização:</span><span class="sxs-lookup"><span data-stu-id="d02b9-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="d02b9-191">Se sua organização tiver sites internos, como um site do Microsoft Office SharePoint Online, que são relevantes para gerentes, considere fixá-los como guias em um canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="d02b9-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="d02b9-192">Você pode dar uma olhada na documentação modelo de [equipe da Microsoft](get-started-with-teams-templates.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="d02b9-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="d02b9-193">Como usar modelos de terceiros</span><span class="sxs-lookup"><span data-stu-id="d02b9-193">How to use first-party templates</span></span>

<span data-ttu-id="d02b9-194">Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="d02b9-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="d02b9-195">Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph sobre como [criar uma equipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="d02b9-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="d02b9-196">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="d02b9-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="d02b9-197">Exemplo: Script de extensão de modelo de Loja</span><span class="sxs-lookup"><span data-stu-id="d02b9-197">Example: Store template extension script</span></span>

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
