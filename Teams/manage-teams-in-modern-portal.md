---
title: Gerenciar equipes em Centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes no Centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202724"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8cfd7-103">Gerenciar equipes em Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cfd7-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="8cfd7-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="8cfd7-104">Overview</span></span>

<span data-ttu-id="8cfd7-105">Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="8cfd7-106">Você pode gerenciar as equipes usadas na sua organização por meio do módulo de PowerShell de equipes da Microsoft e o Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="8cfd7-107">Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="8cfd7-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="8cfd7-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="8cfd7-108">Global Administrator</span></span>
- <span data-ttu-id="8cfd7-109">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="8cfd7-109">Teams Service Administrator</span></span>

<span data-ttu-id="8cfd7-110">Você pode aprender mais sobre as funções de administrador em equipes nas [funções de administração de usar equipes da Microsoft para gerenciar equipes](using-admin-roles.md)e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="8cfd7-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="8cfd7-111">Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="8cfd7-112">Grade de visão geral de equipes</span><span class="sxs-lookup"><span data-stu-id="8cfd7-112">Teams overview grid</span></span>

<span data-ttu-id="8cfd7-113">Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8cfd7-114">(No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição dos grupos que foram habilitados para equipes em sua organização do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="8cfd7-116">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="8cfd7-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="8cfd7-117">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="8cfd7-117">**Team name**</span></span>
- <span data-ttu-id="8cfd7-118">**Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="8cfd7-119">**Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="8cfd7-120">**Proprietários** - uma contagem de proprietários para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="8cfd7-121">**Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="8cfd7-122">**Privacidade** - a visibilidade/AccessType do grupo apoio Office 365.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="8cfd7-123">**Status** - o status ativo para essa equipe ou arquivado.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="8cfd7-124">Saiba mais sobre as equipes no [arquivo morto ou restauração uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="8cfd7-125">**GroupID** - ID exclusivo do grupo do grupo apoio Office 365</span><span class="sxs-lookup"><span data-stu-id="8cfd7-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="8cfd7-126">**Classificação** - a classificação (se utilizados na organização) atribuída ao grupo do Office 365 de backup.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="8cfd7-127">Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="8cfd7-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="8cfd7-128">**Descrição** - a descrição definidas para o grupo de apoio Office 365</span><span class="sxs-lookup"><span data-stu-id="8cfd7-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="8cfd7-129">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="8cfd7-129">Search</span></span>

<span data-ttu-id="8cfd7-130">Pesquisa atualmente suporta a cadeia de caracteres "Começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="8cfd7-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="8cfd7-131">Editar</span><span class="sxs-lookup"><span data-stu-id="8cfd7-131">Edit</span></span>

<span data-ttu-id="8cfd7-132">Você pode editar o grupo e as configurações específicas do team selecionando uma equipe da grade e, em seguida, selecionando o botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="8cfd7-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar a equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="8cfd7-134">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="8cfd7-134">Team profile</span></span>

<span data-ttu-id="8cfd7-135">Você pode navegar para a página de perfil de equipe de qualquer equipe da grade de visão geral de equipes principal clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="8cfd7-136">A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu fazendo O365 grupo), bem como os canais e configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="8cfd7-137">Na página de perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="8cfd7-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="8cfd7-138">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="8cfd7-139">Adicionar ou remover canais (Observe que não é possível remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="8cfd7-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="8cfd7-140">Atualize a equipe e configurações de grupo.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-140">Update team and group settings.</span></span>
 
![Perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="8cfd7-142">Fazendo alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="8cfd7-142">Making changes to teams</span></span>

<span data-ttu-id="8cfd7-143">Você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="8cfd7-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="8cfd7-144">**Os usuários na equipe de** - você pode adicionar ou remover membros e promover ou rebaixar proprietários</span><span class="sxs-lookup"><span data-stu-id="8cfd7-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="8cfd7-145">**Canais** - você pode adicionar novos canais ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="8cfd7-146">Você não pode excluir o canal de "General" padrão e uma vez criada você só pode editar o nome de canal, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="8cfd7-147">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="8cfd7-147">**Team name**</span></span>
- <span data-ttu-id="8cfd7-148">**Descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="8cfd7-148">**Team description**</span></span>
- <span data-ttu-id="8cfd7-149">**Privacidade de equipe** - pública ou privada</span><span class="sxs-lookup"><span data-stu-id="8cfd7-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="8cfd7-150">**Classificação de equipe** - feito pelo seus classificações de grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="8cfd7-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="8cfd7-151">**Configurações de membro de equipe** - configurações de membro da equipe select</span><span class="sxs-lookup"><span data-stu-id="8cfd7-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="8cfd7-152">Outras alterações com suporte para equipes</span><span class="sxs-lookup"><span data-stu-id="8cfd7-152">Other supported changes to teams</span></span>

- <span data-ttu-id="8cfd7-153">**Exclua** - a exclusão de uma equipe é uma exclusão de soft da equipe e grupo correspondente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="8cfd7-154">Para restaurar uma equipe excluída por engano, siga as instruções em [Restaurar de um grupo de 365 excluído do Office](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8cfd7-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="8cfd7-155">**Archive** - o arquivamento de uma equipe coloca a equipe em modo somente leitura no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="8cfd7-156">Como um administrador, você pode arquivar e unarchive equipes em nome de sua organização através do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="8cfd7-157">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="8cfd7-158">Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="8cfd7-159">Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8cfd7-160">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="8cfd7-160">Troubleshooting</span></span>

<span data-ttu-id="8cfd7-161">**Problema: As equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="8cfd7-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="8cfd7-162">Quando você insere o Centro de administração do Microsoft Teams, sob a opção de **equipes** algumas das suas equipes estão ausentes da listagem na grade de visão geral de equipes.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="8cfd7-163">**Causa**: esse problema ocorre quando a equipe foi atribuída incorretamente (ou ainda não) pelo sistema que pode resultar em uma propriedade ausente para que ele seja reconhecida.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="8cfd7-164">**Resolução: Definir a propriedade manualmente o valor correto via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="8cfd7-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="8cfd7-165">Substitua **{groupid}** na consulta referente a GroupId real em questão, que você pode obter via o powershell do Exchange Online, o cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="8cfd7-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="8cfd7-166">Acesso do [Explorer do gráfico](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="8cfd7-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="8cfd7-167">Entrar no Explorer do gráfico no menu à esquerda</span><span class="sxs-lookup"><span data-stu-id="8cfd7-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="8cfd7-168">Altere a linha de consulta para: gt _ do PATCH gt _ v 1.0https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="8cfd7-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="8cfd7-169">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}</span><span class="sxs-lookup"><span data-stu-id="8cfd7-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="8cfd7-170">Execute a consulta na parte superior direita.</span><span class="sxs-lookup"><span data-stu-id="8cfd7-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="8cfd7-171">Confirmar que a equipe seja exibido corretamente no Centro de administração do Microsoft Teams - visão geral da equipe</span><span class="sxs-lookup"><span data-stu-id="8cfd7-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="8cfd7-172">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="8cfd7-172">Learn more</span></span>

[<span data-ttu-id="8cfd7-173">Referência do cmdlet Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8cfd7-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="8cfd7-174">Funções de administrador no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cfd7-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

