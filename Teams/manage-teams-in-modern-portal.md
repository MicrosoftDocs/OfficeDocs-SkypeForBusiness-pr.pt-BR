---
title: Gerenciar equipes no Centro de administração do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar as equipes que sua organização definiu para colaboração no Centro de administração do Microsoft Teams.
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
ms.openlocfilehash: c736cf17d263f097e97b32f856bc83cf2fe42a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814550"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0403d-103">Gerenciar equipes no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="0403d-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0403d-104">Overview</span></span>

<span data-ttu-id="0403d-105">Este artigo fornece uma visão geral das ferramentas de gerenciamento do Teams no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="0403d-106">Como administrador, talvez seja necessário exibir ou atualizar as equipes que sua organização definiu para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário.</span><span class="sxs-lookup"><span data-stu-id="0403d-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="0403d-107">Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="0403d-108">Você pode acessar o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="0403d-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="0403d-109">Para recursos completos de administração usando essas duas ferramentas, certifique-se de que você tenha atribuído uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="0403d-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="0403d-110">Administrador Global</span><span class="sxs-lookup"><span data-stu-id="0403d-110">Global Administrator</span></span>
- <span data-ttu-id="0403d-111">Administrador de Serviço do Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-111">Teams Service Administrator</span></span>

<span data-ttu-id="0403d-112">Você pode saber mais sobre as funções de administrador do Teams em Usar funções de administrador do [Microsoft Teams](using-admin-roles.md)para gerenciar o Teams e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na referência [de cmdlet](https://docs.microsoft.com/powershell/teams/?view=teams-ps)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="0403d-113">Grade de visão geral do Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-113">Teams overview grid</span></span>

<span data-ttu-id="0403d-114">As ferramentas de gerenciamento para equipes estão sob o nó **do Teams** no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0403d-115">(No centro de administração, selecione **Teams**  >  **Gerenciar equipes**.) Cada equipe tem o suporte de um Grupo do Microsoft 365, e esse nó fornece uma exibição dos grupos que foram habilitados para o Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0403d-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de tela da grade de visão geral do Teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="0403d-117">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="0403d-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="0403d-118">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="0403d-118">**Team name**</span></span>
- <span data-ttu-id="0403d-119">**Canais** - uma contagem de todos os canais da equipe, incluindo o canal Geral padrão.</span><span class="sxs-lookup"><span data-stu-id="0403d-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="0403d-120">**Membros da** equipe – uma contagem total de usuários, incluindo proprietários, convidados e membros de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0403d-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="0403d-121">**Proprietários** – uma contagem de proprietários para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="0403d-122">**Convidados** – uma contagem de usuários convidados do Azure Active Directory B2B que são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="0403d-123">**Privacidade** – a Visibilidade/AccessType do grupo de backing do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="0403d-124">**Status** – o status Arquivado ou Ativo desta equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="0403d-125">Saiba mais sobre como arquivar equipes no [Arquivo Morto ou restaurar uma equipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)</span><span class="sxs-lookup"><span data-stu-id="0403d-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="0403d-126">**Descrição** : a descrição do grupo de backing do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="0403d-127">**Classificação** : a classificação (se usada em sua organização) atribuída ao grupo de backing do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="0403d-128">Saiba mais sobre classificações em [Criar classificações para grupos do Office em sua organização.](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0403d-128">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="0403d-129">**GroupID** - o GroupID exclusivo do grupo de apoio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="0403d-130">Se você não vir todas essas propriedades na grade, clique no **ícone Editar colunas.**</span><span class="sxs-lookup"><span data-stu-id="0403d-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="0403d-131">No painel **Editar colunas,** você pode usar os botões para ativar ou desativar colunas na grade.</span><span class="sxs-lookup"><span data-stu-id="0403d-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="0403d-132">Quando terminar, clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="0403d-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="0403d-133">Adicionar</span><span class="sxs-lookup"><span data-stu-id="0403d-133">Add</span></span>

<span data-ttu-id="0403d-134">Para adicionar uma nova equipe, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="0403d-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="0403d-135">No painel **Adicionar uma** nova equipe, dê um nome e uma descrição à equipe, desmarque se deseja torná-la uma equipe pública ou privada e desmarque a classificação.</span><span class="sxs-lookup"><span data-stu-id="0403d-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="0403d-136">As equipes recém-criadas podem ser gerenciadas imediatamente no Centro de administração do Teams, diferentemente da experiência em outros clientes, como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="0403d-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="0403d-137">Editar</span><span class="sxs-lookup"><span data-stu-id="0403d-137">Edit</span></span>

<span data-ttu-id="0403d-138">Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e, em seguida, selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="0403d-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="0403d-139">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="0403d-139">Archive</span></span>

<span data-ttu-id="0403d-140">Você pode arquivar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-140">You can archive a team.</span></span> <span data-ttu-id="0403d-141">O arquivamento de uma equipe coloca a equipe no modo somente leitura no Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="0403d-142">Como administrador, você pode arquivar e des arquivar equipes em nome de sua organização no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="0403d-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="0403d-143">Excluir</span><span class="sxs-lookup"><span data-stu-id="0403d-143">Delete</span></span>

<span data-ttu-id="0403d-144">Excluir uma equipe é uma exclusão suave da equipe e o grupo correspondente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="0403d-145">Para restaurar uma equipe excluída por engano, siga as instruções em [Restaurar um Grupo excluído.](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)</span><span class="sxs-lookup"><span data-stu-id="0403d-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="0403d-146">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="0403d-146">Search</span></span>

<span data-ttu-id="0403d-147">A pesquisa atualmente dá suporte à cadeia de caracteres "Começa com" e pesquisa o **campo nome da** equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="0403d-148">Perfil da equipe</span><span class="sxs-lookup"><span data-stu-id="0403d-148">Team profile</span></span>

<span data-ttu-id="0403d-149">Você pode navegar até a página de perfil da equipe de qualquer equipe na grade de visão geral das equipes principais clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="0403d-150">A página de perfil da equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de apoio do Microsoft 365), bem como os canais e configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="0403d-151">Na página de perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="0403d-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="0403d-152">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="0403d-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="0403d-153">Adicionar ou remover canais (observe que não é possível remover o canal Geral).</span><span class="sxs-lookup"><span data-stu-id="0403d-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="0403d-154">Altere as configurações de equipe e grupo.</span><span class="sxs-lookup"><span data-stu-id="0403d-154">Change team and group settings.</span></span>
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="0403d-156">Fazer alterações nas equipes</span><span class="sxs-lookup"><span data-stu-id="0403d-156">Making changes to teams</span></span>

<span data-ttu-id="0403d-157">Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="0403d-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="0403d-158">**Membros** - adicionar ou remover membros e promover ou rebaixar proprietários.</span><span class="sxs-lookup"><span data-stu-id="0403d-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="0403d-159">**Canais** – adicione novos canais e edite ou remova canais existentes.</span><span class="sxs-lookup"><span data-stu-id="0403d-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="0403d-160">Lembre-se de que não é possível excluir o canal Geral padrão.</span><span class="sxs-lookup"><span data-stu-id="0403d-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="0403d-161">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="0403d-161">**Team name**</span></span>
- <span data-ttu-id="0403d-162">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0403d-162">**Description**</span></span>
- <span data-ttu-id="0403d-163">**Privacidade** : definir se a equipe é pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="0403d-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="0403d-164">**Classificação** : isso é respaldado pelas classificações de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0403d-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="0403d-165">Escolha **Confidencial,** **Altamente Confidencial** ou **Geral.**</span><span class="sxs-lookup"><span data-stu-id="0403d-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="0403d-166">**Configurações de conversas** - de definir se os membros podem editar e excluir mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="0403d-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="0403d-167">**Configurações de canais** : de definir se os membros podem criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0403d-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="0403d-168">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="0403d-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="0403d-169">Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a privacidade, a classificação ou os membros da equipe), as alterações serão atribuídas a você por meio do pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="0403d-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="0403d-170">Se você estiver executando ações em relação às configurações específicas do Teams, suas alterações serão controladas e atribuídas a você no canal Geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0403d-171">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="0403d-171">Troubleshooting</span></span>

<span data-ttu-id="0403d-172">**Problema: Equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="0403d-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="0403d-173">Algumas de suas equipes estão ausentes na lista de equipes na grade de visão geral do Teams.</span><span class="sxs-lookup"><span data-stu-id="0403d-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="0403d-174">**Causa:** esse problema ocorre quando a equipe foi perfilada incorretamente (ou ainda não) pelo sistema, o que pode levar a uma propriedade ausente para que ela seja reconhecida.</span><span class="sxs-lookup"><span data-stu-id="0403d-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="0403d-175">**Resolução: definir manualmente a propriedade como o valor correto por meio do MS Graph**</span><span class="sxs-lookup"><span data-stu-id="0403d-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="0403d-176">Substitua **{groupid}** na Consulta para o GroupId real em questão, que você pode obter por meio do powershell do Exchange Online, pelo cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)",** como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="0403d-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="0403d-177">Access [Graph Explorer.](https://developer.microsoft.com/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="0403d-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="0403d-178">Entre no Graph Explorer no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="0403d-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="0403d-179">Altere a linha da consulta para: PATCH > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >.</span><span class="sxs-lookup"><span data-stu-id="0403d-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="0403d-180">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["Equipe"]}.</span><span class="sxs-lookup"><span data-stu-id="0403d-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="0403d-181">Execute a consulta no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="0403d-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="0403d-182">Confirme se a equipe aparece corretamente no Centro de administração do Microsoft Teams – Visão geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="0403d-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="0403d-183">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="0403d-183">Learn more</span></span>

- [<span data-ttu-id="0403d-184">Referência de cmdlet do Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-184">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="0403d-185">Usar funções de administrador do Teams para gerenciar o Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="0403d-186">Planejar o gerenciamento do ciclo de vida no Teams</span><span class="sxs-lookup"><span data-stu-id="0403d-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
