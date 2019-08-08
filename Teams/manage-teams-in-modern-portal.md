---
title: Gerenciar equipes no centro de administração do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes no centro de administração do Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f495a9cc5b3bfb1fd270e85b2a1fb17bd5f11e68
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233347"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="274bc-103">Gerenciar equipes no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="274bc-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="274bc-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="274bc-104">Overview</span></span>

<span data-ttu-id="274bc-105">Como um administrador de ti, talvez seja necessário exibir ou atualizar as equipes que a sua organização configurou para colaboração, ou talvez seja necessário executar ações de correção, como a atribuição de proprietários para equipes sem proprietário.</span><span class="sxs-lookup"><span data-stu-id="274bc-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="274bc-106">Você pode gerenciar as equipes usadas em sua organização por meio do módulo do Microsoft Teams PowerShell e do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="274bc-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="274bc-107">Para obter recursos de administração plena usando esses dois conjuntos de ferramentas, você deve certificar-se de que recebeu uma das funções a seguir:</span><span class="sxs-lookup"><span data-stu-id="274bc-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="274bc-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="274bc-108">Global Administrator</span></span>
- <span data-ttu-id="274bc-109">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="274bc-109">Teams Service Administrator</span></span>

<span data-ttu-id="274bc-110">Você pode saber mais sobre as funções de administrador no Teams em [usar funções de administração do Microsoft Teams para gerenciar o Teams](using-admin-roles.md)e ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="274bc-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="274bc-111">Este artigo fornece uma visão geral das ferramentas de gerenciamento para Teams no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="274bc-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="274bc-112">Grade de visão geral do teams</span><span class="sxs-lookup"><span data-stu-id="274bc-112">Teams overview grid</span></span>

<span data-ttu-id="274bc-113">As ferramentas de gerenciamento do teams \*\*\*\* estão sob o nó Teams no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="274bc-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="274bc-114">(No centro de administração, selecione **Teams** > **Manage Teams**.) Cada equipe tem o suporte de um grupo do Office 365, e esse nó fornece um modo de exibição de grupos que foram habilitados para o Microsoft Teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="274bc-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Captura de tela da grade de visão geral do teams](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="274bc-116">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="274bc-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="274bc-117">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="274bc-117">**Team name**</span></span>
- <span data-ttu-id="274bc-118">**Canais** – uma contagem de todos os canais da equipe, incluindo o canal geral padrão.</span><span class="sxs-lookup"><span data-stu-id="274bc-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="274bc-119">**Usuários** – uma contagem do total de usuários, incluindo proprietários, convidados e membros do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="274bc-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="274bc-120">**Proprietários** -uma contagem de proprietários para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="274bc-121">**Convidados** -uma contagem de usuários convidados do Azure Active Directory que são membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="274bc-122">**Privacidade** -a visibilidade/acessotype do grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="274bc-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="274bc-123">**Status** -o status arquivado ou ativo para esta equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="274bc-124">Saiba mais sobre o arquivamento de equipes no [arquivamento ou restauração de uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span><span class="sxs-lookup"><span data-stu-id="274bc-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="274bc-125">**GroupId** -o GroupId exclusivo do grupo de backup do Office 365</span><span class="sxs-lookup"><span data-stu-id="274bc-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="274bc-126">**Classificação** – a classificação (se usada em sua organização) atribuída ao grupo de backup do Office 365.</span><span class="sxs-lookup"><span data-stu-id="274bc-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="274bc-127">Saiba mais sobre classificações em [criar classificações para grupos do Office em sua organização](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="274bc-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="274bc-128">**Descrição** -a descrição definida para o grupo de backup do Office 365</span><span class="sxs-lookup"><span data-stu-id="274bc-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="274bc-129">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="274bc-129">Search</span></span>

<span data-ttu-id="274bc-130">A pesquisa atualmente oferece suporte à cadeia de caracteres "começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="274bc-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="274bc-131">Editar</span><span class="sxs-lookup"><span data-stu-id="274bc-131">Edit</span></span>

<span data-ttu-id="274bc-132">Você pode editar as configurações específicas do grupo e da equipe selecionando uma equipe na grade e, em seguida, selecionando o botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="274bc-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Captura de tela das opções de editar equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="274bc-134">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="274bc-134">Team profile</span></span>

<span data-ttu-id="274bc-135">Você pode navegar até a página perfil da equipe de qualquer equipe na grade principal do teams Overview clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="274bc-136">A página perfil da equipe mostra os membros, os proprietários e os convidados que pertencem à equipe (e seu grupo de O365 de apoio), bem como os canais e as configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="274bc-137">Na página perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="274bc-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="274bc-138">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="274bc-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="274bc-139">Adicionar ou remover canais (Observe que não é possível remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="274bc-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="274bc-140">Atualizar configurações de equipe e grupo.</span><span class="sxs-lookup"><span data-stu-id="274bc-140">Update team and group settings.</span></span>
 
![Captura de tela de um exemplo de perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="274bc-142">Como fazer alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="274bc-142">Making changes to teams</span></span>

<span data-ttu-id="274bc-143">Você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="274bc-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="274bc-144">**Usuários na equipe** -você pode adicionar ou remover membros e promover ou rebaixar proprietários</span><span class="sxs-lookup"><span data-stu-id="274bc-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="274bc-145">**Canais** – você pode adicionar novos canais ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="274bc-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="274bc-146">Não é possível excluir o canal "geral" padrão e, depois de criado, você só pode editar o nome do canal e não a descrição.</span><span class="sxs-lookup"><span data-stu-id="274bc-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="274bc-147">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="274bc-147">**Team name**</span></span>
- <span data-ttu-id="274bc-148">**Descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="274bc-148">**Team description**</span></span>
- <span data-ttu-id="274bc-149">**Privacidade da equipe** -público ou privado</span><span class="sxs-lookup"><span data-stu-id="274bc-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="274bc-150">**Classificação da equipe** -apoiada pelas suas classificações de grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="274bc-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="274bc-151">**Configurações de membro da equipe** – selecionar configurações de membro da equipe</span><span class="sxs-lookup"><span data-stu-id="274bc-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="274bc-152">Outras alterações com suporte no Teams</span><span class="sxs-lookup"><span data-stu-id="274bc-152">Other supported changes to teams</span></span>

- <span data-ttu-id="274bc-153">**Excluir** – excluir uma equipe é uma exclusão suave da equipe e do grupo correspondente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="274bc-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="274bc-154">Para restaurar uma equipe excluída incorretamente, siga as instruções em [restaurar um grupo do Office 365 excluído](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="274bc-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="274bc-155">**Arquivo morto** : o arquivamento de uma equipe coloca a equipe em modo somente leitura no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="274bc-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="274bc-156">Como administrador, você pode arquivar e Desarquivar equipes em nome de sua organização por meio do portal de administração.</span><span class="sxs-lookup"><span data-stu-id="274bc-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="274bc-157">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="274bc-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="274bc-158">Se você estiver modificando as configurações de grupo (alterando o nome, a descrição, a foto, a classificação, a classificação ou os membros da equipe), essas alterações serão atribuídas a você pelo pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="274bc-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="274bc-159">Se você estiver executando ações em configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="274bc-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="274bc-160">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="274bc-160">Troubleshooting</span></span>

<span data-ttu-id="274bc-161">**Problema: equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="274bc-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="274bc-162">Quando você insere o centro de administração do Microsoft Teams, na opção **equipes** algumas de suas equipes estão ausentes da listagem na grade de visão geral do teams.</span><span class="sxs-lookup"><span data-stu-id="274bc-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="274bc-163">**Causa**: esse problema ocorre quando a equipe era incorretamente (ou ainda não) Profile pelo sistema, que pode levar a uma propriedade ausente para ser reconhecida.</span><span class="sxs-lookup"><span data-stu-id="274bc-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="274bc-164">**Resolução: definir manualmente a propriedade como o valor correto via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="274bc-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="274bc-165">Substitua **{GroupId}** na consulta para o GroupId em questão real, que você pode obter por meio do PowerShell do Exchange Online, com o cmdlet **"[Get-](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)unificado"** , como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="274bc-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="274bc-166">[Gerenciador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer) do Access</span><span class="sxs-lookup"><span data-stu-id="274bc-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="274bc-167">Entrar no explorador de gráficos no menu à esquerda</span><span class="sxs-lookup"><span data-stu-id="274bc-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="274bc-168">Alterar a linha da consulta para: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="274bc-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="274bc-169">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}</span><span class="sxs-lookup"><span data-stu-id="274bc-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="274bc-170">Execute a consulta no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="274bc-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="274bc-171">Confirmar que a equipe é exibida corretamente no centro de administração do Microsoft Teams-visão geral da equipe</span><span class="sxs-lookup"><span data-stu-id="274bc-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="274bc-172">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="274bc-172">Learn more</span></span>

[<span data-ttu-id="274bc-173">Referência do cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="274bc-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="274bc-174">Funções de administrador no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="274bc-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

