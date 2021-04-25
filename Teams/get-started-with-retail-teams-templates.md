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
description: Aprenda a usar os modelos do Teams para criar estruturas de equipe projetadas para as necessidades do varejista, fornecendo configurações predefinidas, canais e aplicativos pré-instalados.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995139"
---
# <a name="create-a-team-using-teams-retail-templates"></a><span data-ttu-id="da76d-103">Criar uma equipe usando modelos de varejo do Teams</span><span class="sxs-lookup"><span data-stu-id="da76d-103">Create a team using Teams retail templates</span></span>

<span data-ttu-id="da76d-104">Os modelos do Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="da76d-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="da76d-105">Os modelos do Teams têm definições previamente criadas de estruturas de equipe projetadas em torno das necessidades dos varejistas.</span><span class="sxs-lookup"><span data-stu-id="da76d-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="da76d-106">Você pode usar modelos do Teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-los em sua organização.</span><span class="sxs-lookup"><span data-stu-id="da76d-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="da76d-107">Você também pode estender os modelos do Teams para criar equipes adaptadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="da76d-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="da76d-108">Neste artigo, apresentaremos cada um dos modelos do Teams e como recomendamos usá-los.</span><span class="sxs-lookup"><span data-stu-id="da76d-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="da76d-109">Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de varejo.</span><span class="sxs-lookup"><span data-stu-id="da76d-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="da76d-110">Você já implantou o serviço Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="da76d-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="da76d-111">Se você ainda não implementou o Teams, comece lendo [Como implementar o Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da76d-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="da76d-112">Para saber mais sobre os modelos de equipe em geral, confira [Primeiros passos com os modelos do Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="da76d-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="da76d-113">Quem</span><span class="sxs-lookup"><span data-stu-id="da76d-113">Who</span></span> | <span data-ttu-id="da76d-114">Método a ser usado:</span><span class="sxs-lookup"><span data-stu-id="da76d-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="da76d-115">Administradores e profissionais de TI</span><span class="sxs-lookup"><span data-stu-id="da76d-115">Admins and IT Professionals</span></span> | <span data-ttu-id="da76d-116">[Use o centro de administração do Teams](#use-the-teams-templates-in-the-teams-admin-center) para criar equipes com base nos modelos do Teams de revenda.</span><span class="sxs-lookup"><span data-stu-id="da76d-116">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the retail Teams templates.</span></span>|
| <span data-ttu-id="da76d-117">Os desenvolvedores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="da76d-117">Developers and systems integrators</span></span> | <span data-ttu-id="da76d-118">[Use o Microsoft Graph para](#use-the-teams-templates-with-the-microsoft-graph) criar equipes com base nos modelos do Teams de revenda.</span><span class="sxs-lookup"><span data-stu-id="da76d-118">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the retail Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="da76d-119">Usar os modelos do Teams no Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="da76d-119">Use the Teams templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="da76d-120">Organizar uma store</span><span class="sxs-lookup"><span data-stu-id="da76d-120">Organize a store</span></span>

<span data-ttu-id="da76d-121">Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e resolver problemas de clientes.</span><span class="sxs-lookup"><span data-stu-id="da76d-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="da76d-122">Integre aplicativos adicionais para simplificar os processos de início e fim de turno.</span><span class="sxs-lookup"><span data-stu-id="da76d-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="da76d-123">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-123">Base template type</span></span> |<span data-ttu-id="da76d-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="da76d-124">baseTemplateId</span></span> | <span data-ttu-id="da76d-125">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="da76d-126">Organizar uma store</span><span class="sxs-lookup"><span data-stu-id="da76d-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="da76d-127">Canais:</span><span class="sxs-lookup"><span data-stu-id="da76d-127">Channels:</span></span> <ul><li><span data-ttu-id="da76d-128">Geral</span><span class="sxs-lookup"><span data-stu-id="da76d-128">General</span></span><li><span data-ttu-id="da76d-129">Mudança de entrega</span><span class="sxs-lookup"><span data-stu-id="da76d-129">Shift handoff</span></span></li><li><span data-ttu-id="da76d-130">Aprendizado</span><span class="sxs-lookup"><span data-stu-id="da76d-130">Learning</span></span></li></ul> <span data-ttu-id="da76d-131">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="da76d-131">Apps:</span></span> <ul><li><span data-ttu-id="da76d-132">Wiki</span><span class="sxs-lookup"><span data-stu-id="da76d-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="da76d-133">Colaboração do Gerente</span><span class="sxs-lookup"><span data-stu-id="da76d-133">Manager Collaboration</span></span>

<span data-ttu-id="da76d-134">O modelo de Colaboração do Gerente é ideal para criar uma equipe para um conjunto de gerentes colaborarem entre lojas/regiões, etc. Por exemplo, se sua organização tiver regiões, você poderá criar uma equipe de Colaboração do Gerente para a Região da Califórnia e incluir todos os gerentes de loja nessa região, juntamente com o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="da76d-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="da76d-135">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-135">Base template type</span></span>| <span data-ttu-id="da76d-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="da76d-136">baseTemplateId</span></span> | <span data-ttu-id="da76d-137">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="da76d-138">Varejo - colaboração do gerente</span><span class="sxs-lookup"><span data-stu-id="da76d-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="da76d-139">Canais:</span><span class="sxs-lookup"><span data-stu-id="da76d-139">Channels:</span></span> <ul><li><span data-ttu-id="da76d-140">Geral</span><span class="sxs-lookup"><span data-stu-id="da76d-140">General</span></span><li><span data-ttu-id="da76d-141">Operações</span><span class="sxs-lookup"><span data-stu-id="da76d-141">Operations</span></span></li><li><span data-ttu-id="da76d-142">Aprendizado</span><span class="sxs-lookup"><span data-stu-id="da76d-142">Learning</span></span></li></ul> <span data-ttu-id="da76d-143">Aplicativos:</span><span class="sxs-lookup"><span data-stu-id="da76d-143">Apps:</span></span> <ul><li><span data-ttu-id="da76d-144">Wiki</span><span class="sxs-lookup"><span data-stu-id="da76d-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="da76d-145">Usar os modelos do Teams com o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="da76d-145">Use the Teams templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="da76d-146">Modelo de Loja</span><span class="sxs-lookup"><span data-stu-id="da76d-146">Store template</span></span>

<span data-ttu-id="da76d-147">O modelo de Loja é ideal para criar uma equipe para representar um local de loja individual.</span><span class="sxs-lookup"><span data-stu-id="da76d-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="da76d-148">Usando o modelo de Loja, você pode criar uma equipe para cada local de loja de varejo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="da76d-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="da76d-149">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-149">Base template type</span></span> | <span data-ttu-id="da76d-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="da76d-150">baseTemplateId</span></span> | <span data-ttu-id="da76d-151">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="da76d-152">Varejo -</span><span class="sxs-lookup"><span data-stu-id="da76d-152">Retail -</span></span> <br><span data-ttu-id="da76d-153">Loja</span><span class="sxs-lookup"><span data-stu-id="da76d-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="da76d-154">Canais</span><span class="sxs-lookup"><span data-stu-id="da76d-154">Channels</span></span> <ul><li><span data-ttu-id="da76d-155">Entrega dos turnos\*</span><span class="sxs-lookup"><span data-stu-id="da76d-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="da76d-156">Aprendizado\*</span><span class="sxs-lookup"><span data-stu-id="da76d-156">Learning\*</span></span></li></ul><span data-ttu-id="da76d-157">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="da76d-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="da76d-158">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="da76d-158">Team properties</span></span> <ul><li><span data-ttu-id="da76d-159">Visibilidade da equipe definida como Pública</span><span class="sxs-lookup"><span data-stu-id="da76d-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="da76d-160">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="da76d-160">Member permissions</span></span> <ul><li><span data-ttu-id="da76d-161">Não é possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="da76d-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="da76d-162">Não é possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="da76d-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="da76d-163">Não é possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="da76d-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="da76d-164">Não é possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="da76d-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="da76d-165">Maneiras recomendadas de personalizar o modelo de Loja para sua organização:</span><span class="sxs-lookup"><span data-stu-id="da76d-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="da76d-166">Se sua organização tiver departamentos dentro de cada loja, adicione um canal para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="da76d-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="da76d-167">Adicionar um canal facilita a comunicação e a colaboração dentro do departamento.</span><span class="sxs-lookup"><span data-stu-id="da76d-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="da76d-168">Se sua organização tiver sites internos (por exemplo, um site do Microsoft Office SharePoint Online), considere fixá-los como guias no canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="da76d-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="da76d-169">Confira [Introdução aos modelos do Teams para varejo](get-started-with-teams-templates.md) para instruções.</span><span class="sxs-lookup"><span data-stu-id="da76d-169">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="da76d-170">Modelo Colaboração de Gerente</span><span class="sxs-lookup"><span data-stu-id="da76d-170">Manager Collaboration template</span></span>

<span data-ttu-id="da76d-171">O modelo Colaboração de Gerente é outro dos modelos do Teams desenvolvidos em torno das necessidades dos varejistas.</span><span class="sxs-lookup"><span data-stu-id="da76d-171">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="da76d-172">O modelo Colaboração de Gerente é ideal para criar uma equipe para um conjunto de gerentes para colaborar em lojas/regiões e muito mais.</span><span class="sxs-lookup"><span data-stu-id="da76d-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="da76d-173">Por exemplo, se sua organização tem regiões, você pode criar uma equipe de Colaboração de Gerente para a Região da Califórnia e incluir todos os gerentes de loja dessa região, bem como o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="da76d-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="da76d-174">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-174">Base template type</span></span> | <span data-ttu-id="da76d-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="da76d-175">baseTemplateId</span></span> | <span data-ttu-id="da76d-176">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="da76d-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="da76d-177">Varejo -</span><span class="sxs-lookup"><span data-stu-id="da76d-177">Retail -</span></span> <br><span data-ttu-id="da76d-178">Loja</span><span class="sxs-lookup"><span data-stu-id="da76d-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="da76d-179">Canais</span><span class="sxs-lookup"><span data-stu-id="da76d-179">Channels</span></span> <ul><li><span data-ttu-id="da76d-180">Operações\*</span><span class="sxs-lookup"><span data-stu-id="da76d-180">Operations\*</span></span></li><li><span data-ttu-id="da76d-181">Aprendizado\*</span><span class="sxs-lookup"><span data-stu-id="da76d-181">Learning\*</span></span></li></ul><span data-ttu-id="da76d-182">\*Canais favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="da76d-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="da76d-183">Propriedades de equipe</span><span class="sxs-lookup"><span data-stu-id="da76d-183">Team properties</span></span> <ul><li><span data-ttu-id="da76d-184">Visibilidade da equipe definida como Privada</span><span class="sxs-lookup"><span data-stu-id="da76d-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="da76d-185">Permissões de membro</span><span class="sxs-lookup"><span data-stu-id="da76d-185">Member permissions</span></span> <ul><li><span data-ttu-id="da76d-186">É possível criar/atualizar/excluir canais</span><span class="sxs-lookup"><span data-stu-id="da76d-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="da76d-187">É possível adicionar/remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="da76d-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="da76d-188">É possível criar/atualizar/remover guias</span><span class="sxs-lookup"><span data-stu-id="da76d-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="da76d-189">É possível criar/atualizar/remover conectores</span><span class="sxs-lookup"><span data-stu-id="da76d-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="da76d-190">Maneiras recomendadas de personalizar o modelo Colaboração de Gerente para sua organização:</span><span class="sxs-lookup"><span data-stu-id="da76d-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="da76d-191">Se sua organização tiver sites internos, como um site do Microsoft Office SharePoint Online, que são relevantes para gerentes, considere fixá-los como guias em um canal de equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="da76d-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="da76d-192">Você pode dar uma olhada na [documentação do modelo do Microsoft Teams](get-started-with-teams-templates.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="da76d-192">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="da76d-193">Como usar modelos de primeiros</span><span class="sxs-lookup"><span data-stu-id="da76d-193">How to use first party templates</span></span>

<span data-ttu-id="da76d-194">Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="da76d-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="da76d-195">Para saber mais sobre como implantar modelos do Teams, confira o artigo do Microsoft Graph sobre como [criar um Team](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="da76d-195">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="da76d-196">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="da76d-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="da76d-197">Exemplo: Script de extensão de modelo de Loja</span><span class="sxs-lookup"><span data-stu-id="da76d-197">Example: Store template extension script</span></span>

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
