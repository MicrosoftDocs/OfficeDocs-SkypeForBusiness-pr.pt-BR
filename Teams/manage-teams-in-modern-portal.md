---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar as equipes que a sua organização configurou para colaboração no centro de administração do Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3c963e88d33928add9c7f5c611f44919250b847
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583148"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="c2825-103">Gerenciar equipes no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c2825-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="c2825-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c2825-104">Overview</span></span>

<span data-ttu-id="c2825-105">Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2825-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="c2825-106">Como administrador, talvez você precise exibir ou atualizar as equipes configuradas para colaboração ou pode precisar executar ações de correção, como a atribuição de proprietários para equipes sem proprietário.</span><span class="sxs-lookup"><span data-stu-id="c2825-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="c2825-107">Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2825-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="c2825-108">Você pode acessar o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="c2825-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="c2825-109">Para obter recursos de administração plena usando esses dois conjuntos de ferramentas, você deve certificar-se de que recebeu uma das funções a seguir:</span><span class="sxs-lookup"><span data-stu-id="c2825-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="c2825-110">Administrador global</span><span class="sxs-lookup"><span data-stu-id="c2825-110">Global Administrator</span></span>
- <span data-ttu-id="c2825-111">Administrador de Serviço do Teams</span><span class="sxs-lookup"><span data-stu-id="c2825-111">Teams Service Administrator</span></span>

<span data-ttu-id="c2825-112">Você pode saber mais sobre as funções de administrador no Teams em [usar funções de administração do Microsoft Teams para gerenciar o Teams](using-admin-roles.md)e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="c2825-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="c2825-113">Grade de visão geral do teams</span><span class="sxs-lookup"><span data-stu-id="c2825-113">Teams overview grid</span></span>

<span data-ttu-id="c2825-114">As ferramentas de gerenciamento do teams estão sob o nó **Teams** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2825-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c2825-115">(No centro de administração, selecione **equipes**  >  **Gerenciar equipes**.) Cada equipe tem o suporte de um grupo do Microsoft 365, e esse nó fornece um modo de exibição de grupos que foram habilitados para o Microsoft Teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c2825-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de tela da grade de visão geral do teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="c2825-117">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c2825-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="c2825-118">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="c2825-118">**Team name**</span></span>
- <span data-ttu-id="c2825-119">**Canais** – uma contagem de todos os canais da equipe, incluindo o canal geral padrão.</span><span class="sxs-lookup"><span data-stu-id="c2825-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="c2825-120">**Membros da equipe** -uma contagem total de usuários, incluindo proprietários, convidados e membros do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c2825-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="c2825-121">**Proprietários** -uma contagem de proprietários para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="c2825-122">**Convidados** -uma contagem de usuários convidados do Azure Active Directory que são membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="c2825-123">**Privacidade** -a visibilidade/acessotype do grupo de suporte do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="c2825-124">**Status** -o status arquivado ou ativo para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="c2825-125">Saiba mais sobre o arquivamento de equipes em [arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="c2825-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="c2825-126">**Descrição** -a descrição do grupo de suporte do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="c2825-127">**Classificação** – a classificação (se usada em sua organização) atribuída ao grupo de suporte do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="c2825-128">Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c2825-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="c2825-129">**GroupId** -o GroupId exclusivo do grupo de backup do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="c2825-130">Se você não vir todas essas propriedades na grade, clique no ícone **Editar colunas** .</span><span class="sxs-lookup"><span data-stu-id="c2825-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="c2825-131">No painel **Editar colunas** , você pode usar as alternâncias para ativar ou desativar colunas na grade.</span><span class="sxs-lookup"><span data-stu-id="c2825-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="c2825-132">Quando tiver terminado, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c2825-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="c2825-133">Suplementa</span><span class="sxs-lookup"><span data-stu-id="c2825-133">Add</span></span>

<span data-ttu-id="c2825-134">Para adicionar uma nova equipe, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c2825-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="c2825-135">No painel **Adicionar uma nova equipe** , dê um nome e uma descrição para a equipe, defina se deseja torná-la uma equipe privada ou pública e definir a classificação.</span><span class="sxs-lookup"><span data-stu-id="c2825-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="c2825-136">Editar</span><span class="sxs-lookup"><span data-stu-id="c2825-136">Edit</span></span>

<span data-ttu-id="c2825-137">Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c2825-137">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="c2825-138">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="c2825-138">Archive</span></span>

<span data-ttu-id="c2825-139">Você pode arquivar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-139">You can archive a team.</span></span> <span data-ttu-id="c2825-140">Arquivar uma equipe coloca a equipe em modo somente leitura no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2825-140">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="c2825-141">Como administrador, você pode arquivar e cancelar o arquivamento de equipes em nome da sua organização no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="c2825-141">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="c2825-142">Excluir</span><span class="sxs-lookup"><span data-stu-id="c2825-142">Delete</span></span>

<span data-ttu-id="c2825-143">A exclusão de uma equipe é uma exclusão suave da equipe e do grupo correspondente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-143">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="c2825-144">Para restaurar uma equipe excluída incorretamente, siga as instruções em [restaurar um grupo excluído](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span><span class="sxs-lookup"><span data-stu-id="c2825-144">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="c2825-145">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="c2825-145">Search</span></span>

<span data-ttu-id="c2825-146">A pesquisa atualmente oferece suporte à cadeia de caracteres "começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="c2825-146">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="c2825-147">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="c2825-147">Team profile</span></span>

<span data-ttu-id="c2825-148">Você pode navegar até a página perfil da equipe de qualquer equipe na grade principal do teams Overview clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-148">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="c2825-149">A página perfil da equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de suporte do Microsoft 365), bem como os canais e as configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-149">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="c2825-150">Na página perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="c2825-150">From the team profile page, you can:</span></span>

- <span data-ttu-id="c2825-151">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="c2825-151">Add or remove members and owners.</span></span>
- <span data-ttu-id="c2825-152">Adicionar ou remover canais (Observe que você não pode remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="c2825-152">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="c2825-153">Alterar configurações de equipe e grupo.</span><span class="sxs-lookup"><span data-stu-id="c2825-153">Change team and group settings.</span></span>
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="c2825-155">Como fazer alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="c2825-155">Making changes to teams</span></span>

<span data-ttu-id="c2825-156">Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="c2825-156">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="c2825-157">**Membros** : Adicionar ou remover membros e promover ou rebaixar proprietários.</span><span class="sxs-lookup"><span data-stu-id="c2825-157">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="c2825-158">**Canais** – adicionar novos canais e editar ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="c2825-158">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="c2825-159">Lembre-se de que não é possível excluir o canal geral padrão.</span><span class="sxs-lookup"><span data-stu-id="c2825-159">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="c2825-160">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="c2825-160">**Team name**</span></span>
- <span data-ttu-id="c2825-161">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c2825-161">**Description**</span></span>
- <span data-ttu-id="c2825-162">**Privacidade** -defina se a equipe é pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="c2825-162">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="c2825-163">**Classificação** : apoiado por suas classificações de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2825-163">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="c2825-164">Escolha **confidencial**, **altamente confidencial**ou **geral**.</span><span class="sxs-lookup"><span data-stu-id="c2825-164">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="c2825-165">**Configurações de conversas** -defina se os membros podem editar e excluir mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="c2825-165">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="c2825-166">**Configurações de canais** -defina se os membros poderão criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c2825-166">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="c2825-167">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="c2825-167">The changes that you make to a team are logged.</span></span> <span data-ttu-id="c2825-168">Se você estiver modificando as configurações do grupo (alterando o nome, a descrição, a foto, a classificação, a classificação ou os membros da equipe), as alterações serão atribuídas a você pelo pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="c2825-168">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="c2825-169">Se você estiver executando ações em configurações específicas de equipes, suas alterações serão controladas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-169">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c2825-170">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="c2825-170">Troubleshooting</span></span>

<span data-ttu-id="c2825-171">**Problema: equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="c2825-171">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="c2825-172">Algumas de suas equipes estão ausentes da lista de equipes na grade de visão geral do teams.</span><span class="sxs-lookup"><span data-stu-id="c2825-172">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="c2825-173">**Causa**: esse problema ocorre quando a equipe era incorretamente (ou ainda não) Profile pelo sistema, que pode levar a uma propriedade ausente para ser reconhecida.</span><span class="sxs-lookup"><span data-stu-id="c2825-173">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="c2825-174">**Resolução: definir manualmente a propriedade como o valor correto via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="c2825-174">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="c2825-175">Substitua **{GroupId}** na consulta para o GroupId em questão real, que você pode obter por meio do PowerShell do Exchange Online, com o cmdlet **"[Get-unificado](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="c2825-175">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="c2825-176">[Gerenciador de gráficos](https://developer.microsoft.com/graph/graph-explorer)do Access.</span><span class="sxs-lookup"><span data-stu-id="c2825-176">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="c2825-177">Conecte-se ao Graph Explorer no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c2825-177">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="c2825-178">Altere a linha de consulta para: PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} .</span><span class="sxs-lookup"><span data-stu-id="c2825-178">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="c2825-179">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}.</span><span class="sxs-lookup"><span data-stu-id="c2825-179">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="c2825-180">Execute a consulta no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="c2825-180">Run the query on the top-right.</span></span>

6. <span data-ttu-id="c2825-181">Confirme que a equipe é exibida corretamente no centro de administração do Microsoft Teams-visão geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="c2825-181">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="c2825-182">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="c2825-182">Learn more</span></span>

- [<span data-ttu-id="c2825-183">Referência do cmdlet do teams</span><span class="sxs-lookup"><span data-stu-id="c2825-183">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="c2825-184">Usar funções de administrador do teams para gerenciar equipes</span><span class="sxs-lookup"><span data-stu-id="c2825-184">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="c2825-185">Planejar o gerenciamento do ciclo de vida no Teams</span><span class="sxs-lookup"><span data-stu-id="c2825-185">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
