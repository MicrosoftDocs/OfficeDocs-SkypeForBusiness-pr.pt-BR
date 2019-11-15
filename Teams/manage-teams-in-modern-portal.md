---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Saiba como exibir ou atualizar suas equipes no centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e0e96b05aff2d1c0e54bf6f1edb33f9b91aad6d
ms.sourcegitcommit: 4060f20e8e3ce5a0464c12cfebdf8fe3473733fe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627027"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9efe5-103">Gerenciar equipes no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9efe5-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="9efe5-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="9efe5-104">Overview</span></span>

<span data-ttu-id="9efe5-105">Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9efe5-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="9efe5-106">Como administrador, talvez você precise exibir ou atualizar as equipes configuradas para colaboração ou pode precisar executar ações de correção, como a atribuição de proprietários para equipes sem proprietário.</span><span class="sxs-lookup"><span data-stu-id="9efe5-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="9efe5-107">Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9efe5-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="9efe5-108">Para obter recursos de administração plena usando esses dois conjuntos de ferramentas, você deve certificar-se de que recebeu uma das funções a seguir:</span><span class="sxs-lookup"><span data-stu-id="9efe5-108">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="9efe5-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="9efe5-109">Global Administrator</span></span>
- <span data-ttu-id="9efe5-110">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="9efe5-110">Teams Service Administrator</span></span>

<span data-ttu-id="9efe5-111">Você pode saber mais sobre as funções de administrador no Teams em [usar funções de administração do Microsoft Teams para gerenciar o Teams](using-admin-roles.md)e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9efe5-111">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="9efe5-112">Grade de visão geral do teams</span><span class="sxs-lookup"><span data-stu-id="9efe5-112">Teams overview grid</span></span>

<span data-ttu-id="9efe5-113">As ferramentas de gerenciamento do teams estão sob o nó **Teams** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9efe5-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9efe5-114">(No centro de administração, selecione **Teams** > **Manage Teams**.) Cada equipe tem o suporte de um grupo do Office 365, e esse nó fornece um modo de exibição de grupos que foram habilitados para o Microsoft Teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="9efe5-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de tela da grade de visão geral do teams](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="9efe5-116">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="9efe5-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="9efe5-117">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="9efe5-117">**Team name**</span></span>
- <span data-ttu-id="9efe5-118">**Canais** – uma contagem de todos os canais da equipe, incluindo o canal geral padrão.</span><span class="sxs-lookup"><span data-stu-id="9efe5-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="9efe5-119">**Membros da equipe** -uma contagem total de usuários, incluindo proprietários, convidados e membros do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9efe5-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="9efe5-120">**Proprietários** -uma contagem de proprietários para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="9efe5-121">**Convidados** -uma contagem de usuários convidados do Azure Active Directory que são membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="9efe5-122">**Privacidade** -a visibilidade/acessotype do grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="9efe5-123">**Status** -o status arquivado ou ativo para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="9efe5-124">Saiba mais sobre o arquivamento de equipes em [arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="9efe5-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="9efe5-125">**Descrição** -a descrição do grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="9efe5-126">**Classificação** – a classificação (se usada em sua organização) atribuída ao grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="9efe5-127">Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9efe5-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="9efe5-128">**GroupId** -o GroupId exclusivo do grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="9efe5-129">Se você não vir todas essas propriedades na grade, clique no ícone **Editar colunas** .</span><span class="sxs-lookup"><span data-stu-id="9efe5-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="9efe5-130">No painel **Editar colunas** , você pode usar as alternâncias para ativar ou desativar colunas na grade.</span><span class="sxs-lookup"><span data-stu-id="9efe5-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="9efe5-131">Quando tiver terminado, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9efe5-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="9efe5-132">Suplementa</span><span class="sxs-lookup"><span data-stu-id="9efe5-132">Add</span></span>

<span data-ttu-id="9efe5-133">Para adicionar uma nova equipe, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9efe5-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="9efe5-134">No painel **Adicionar uma nova equipe** , dê um nome e uma descrição para a equipe, defina se deseja torná-la uma equipe privada ou pública e definir a classificação.</span><span class="sxs-lookup"><span data-stu-id="9efe5-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="9efe5-135">Editar</span><span class="sxs-lookup"><span data-stu-id="9efe5-135">Edit</span></span>

<span data-ttu-id="9efe5-136">Para editar configurações específicas do grupo e da equipe, selecione a equipe clicando à esquerda do nome da equipe e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9efe5-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="9efe5-137">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="9efe5-137">Archive</span></span>

<span data-ttu-id="9efe5-138">Você pode arquivar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-138">You can archive a team.</span></span> <span data-ttu-id="9efe5-139">Arquivar uma equipe coloca a equipe em modo somente leitura no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9efe5-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="9efe5-140">Como administrador, você pode arquivar e cancelar o arquivamento de equipes em nome da sua organização no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="9efe5-140">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="9efe5-141">Excluir</span><span class="sxs-lookup"><span data-stu-id="9efe5-141">Delete</span></span>

<span data-ttu-id="9efe5-142">A exclusão de uma equipe é uma exclusão suave da equipe e do grupo correspondente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="9efe5-143">Para restaurar uma equipe excluída incorretamente, siga as instruções em [restaurar um grupo excluído do Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9efe5-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="9efe5-144">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="9efe5-144">Search</span></span>

<span data-ttu-id="9efe5-145">A pesquisa atualmente oferece suporte à cadeia de caracteres "começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="9efe5-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="9efe5-146">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="9efe5-146">Team profile</span></span>

<span data-ttu-id="9efe5-147">Você pode navegar até a página perfil da equipe de qualquer equipe na grade principal do teams Overview clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="9efe5-148">A página perfil da equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu grupo de suporte do Office 365), bem como os canais e as configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="9efe5-149">Na página perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="9efe5-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="9efe5-150">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="9efe5-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="9efe5-151">Adicionar ou remover canais (Observe que você não pode remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="9efe5-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="9efe5-152">Alterar configurações de equipe e grupo.</span><span class="sxs-lookup"><span data-stu-id="9efe5-152">Change team and group settings.</span></span>
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="9efe5-154">Como fazer alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="9efe5-154">Making changes to teams</span></span>

<span data-ttu-id="9efe5-155">Na página de perfil da equipe, você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="9efe5-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="9efe5-156">**Membros** : Adicionar ou remover membros e promover ou rebaixar proprietários.</span><span class="sxs-lookup"><span data-stu-id="9efe5-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="9efe5-157">**Canais** – adicionar novos canais e editar ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="9efe5-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="9efe5-158">Lembre-se de que não é possível excluir o canal geral padrão.</span><span class="sxs-lookup"><span data-stu-id="9efe5-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="9efe5-159">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="9efe5-159">**Team name**</span></span>
- <span data-ttu-id="9efe5-160">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9efe5-160">**Description**</span></span>
- <span data-ttu-id="9efe5-161">**Privacidade** -defina se a equipe é pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="9efe5-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="9efe5-162">**Classificação** : apoiado por suas classificações de grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9efe5-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="9efe5-163">Escolha **confidencial**, **altamente confidencial**ou **geral**.</span><span class="sxs-lookup"><span data-stu-id="9efe5-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="9efe5-164">**Configurações de conversas** -defina se os membros podem editar e excluir mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="9efe5-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="9efe5-165">**Configurações de canais** -defina se os membros poderão criar novos canais e editar os existentes e adicionar, editar e remover guias, conectores e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9efe5-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="9efe5-166">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="9efe5-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="9efe5-167">Se você estiver modificando as configurações do grupo (alterando o nome, a descrição, a foto, a classificação, a classificação ou os membros da equipe), as alterações serão atribuídas a você pelo pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="9efe5-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="9efe5-168">Se você estiver executando ações em configurações específicas de equipes, suas alterações serão controladas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9efe5-169">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="9efe5-169">Troubleshooting</span></span>

<span data-ttu-id="9efe5-170">**Problema: equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="9efe5-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="9efe5-171">Algumas de suas equipes estão ausentes da lista de equipes na grade de visão geral do teams.</span><span class="sxs-lookup"><span data-stu-id="9efe5-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="9efe5-172">**Causa**: esse problema ocorre quando a equipe era incorretamente (ou ainda não) Profile pelo sistema, que pode levar a uma propriedade ausente para ser reconhecida.</span><span class="sxs-lookup"><span data-stu-id="9efe5-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="9efe5-173">**Resolução: definir manualmente a propriedade como o valor correto via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="9efe5-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="9efe5-174">Substitua **{GroupId}** na consulta para o GroupId em questão real, que você pode obter por meio do PowerShell do Exchange Online, com o cmdlet **"[Get-unificado](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="9efe5-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="9efe5-175">[Gerenciador de gráficos](https://developer.microsoft.com/graph/graph-explorer)do Access.</span><span class="sxs-lookup"><span data-stu-id="9efe5-175">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="9efe5-176">Conecte-se ao Graph Explorer no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="9efe5-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="9efe5-177">Altere a linha de consulta para: PATCH > v 1.0 https://graph.microsoft.com/v1.0/groups/{groupid}>.</span><span class="sxs-lookup"><span data-stu-id="9efe5-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="9efe5-178">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}.</span><span class="sxs-lookup"><span data-stu-id="9efe5-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="9efe5-179">Execute a consulta no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="9efe5-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="9efe5-180">Confirme que a equipe é exibida corretamente no centro de administração do Microsoft Teams-visão geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="9efe5-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="9efe5-181">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="9efe5-181">Learn more</span></span>

- [<span data-ttu-id="9efe5-182">Referência do cmdlet do teams</span><span class="sxs-lookup"><span data-stu-id="9efe5-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="9efe5-183">Usar funções de administrador do teams para gerenciar equipes</span><span class="sxs-lookup"><span data-stu-id="9efe5-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="9efe5-184">Planejar o gerenciamento do ciclo de vida no Teams</span><span class="sxs-lookup"><span data-stu-id="9efe5-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
