---
title: Gerenciar equipes no centro de administração do Microsoft Teams
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
ms.openlocfilehash: d5ba19fac66ef4e12e2734948a6695894b52dd3b
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494033"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="29336-103">Gerenciar equipes no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29336-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="29336-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="29336-104">Overview</span></span>

<span data-ttu-id="29336-105">Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários.</span><span class="sxs-lookup"><span data-stu-id="29336-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="29336-106">Você pode gerenciar as equipes usadas na sua organização por meio do módulo de PowerShell de equipes da Microsoft e o Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="29336-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="29336-107">Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="29336-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="29336-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="29336-108">Global Administrator</span></span>
- <span data-ttu-id="29336-109">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="29336-109">Teams Service Administrator</span></span>

<span data-ttu-id="29336-110">Você também deve garantir que sua conta tenha sido atribuída uma licença de equipes não seja de avaliação para o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="29336-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="29336-111">Como parte de um problema conhecido, você deve garantir que sua conta tem apenas **uma** função de administrador atribuída.</span><span class="sxs-lookup"><span data-stu-id="29336-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="29336-112">Você pode aprender mais sobre as funções de administrador no Microsoft Teams em [equipes da Microsoft usar funções de administrador para gerenciar equipes](using-admin-roles.md)e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="29336-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="29336-113">Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="29336-113">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="29336-114">Grade de visão geral de equipes</span><span class="sxs-lookup"><span data-stu-id="29336-114">Teams overview grid</span></span>

<span data-ttu-id="29336-115">Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="29336-115">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="29336-116">(No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição dos grupos que foram habilitados para equipes em sua organização do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29336-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="29336-117">Estamos no processo backfilling criado anteriormente equipes para garantir que eles serão exibidas nesse modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="29336-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="29336-119">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="29336-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="29336-120">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="29336-120">**Team name**</span></span>
- <span data-ttu-id="29336-121">**Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.</span><span class="sxs-lookup"><span data-stu-id="29336-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="29336-122">**Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="29336-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="29336-123">**Proprietários** - uma contagem de proprietários para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="29336-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="29336-124">**Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="29336-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="29336-125">**Privacidade** - o AccessType do grupo apoio Office 365.</span><span class="sxs-lookup"><span data-stu-id="29336-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="29336-126">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="29336-126">Search</span></span>

<span data-ttu-id="29336-127">Pesquisa atualmente suporta a cadeia de caracteres "Começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="29336-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="29336-128">Editar</span><span class="sxs-lookup"><span data-stu-id="29336-128">Edit</span></span>

<span data-ttu-id="29336-129">Você pode editar o grupo e as configurações específicas do team selecionando uma equipe da grade e, em seguida, selecionando o botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="29336-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar a equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="29336-131">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="29336-131">Team profile</span></span>

<span data-ttu-id="29336-132">Você pode navegar para a página de perfil de equipe de qualquer equipe da grade de visão geral de equipes principal clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="29336-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="29336-133">A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu fazendo O365 grupo), bem como os canais e configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="29336-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="29336-134">Na página de perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="29336-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="29336-135">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="29336-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="29336-136">Adicionar ou remover canais (Observe que não é possível remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="29336-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="29336-137">Atualize a equipe e configurações de grupo.</span><span class="sxs-lookup"><span data-stu-id="29336-137">Update team and group settings.</span></span>
 
![Perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="29336-139">Fazendo alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="29336-139">Making changes to teams</span></span>

<span data-ttu-id="29336-140">Você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="29336-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="29336-141">**Os usuários na equipe de** - você pode adicionar ou remover membros e promover ou rebaixar proprietários</span><span class="sxs-lookup"><span data-stu-id="29336-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="29336-142">**Canais** - você pode adicionar novos canais ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="29336-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="29336-143">Você não pode excluir o canal de "General" padrão e uma vez criada você só pode editar o nome de canal, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="29336-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="29336-144">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="29336-144">**Team name**</span></span>
- <span data-ttu-id="29336-145">**Descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="29336-145">**Team description**</span></span>
- <span data-ttu-id="29336-146">**Privacidade de equipe** - pública ou privada</span><span class="sxs-lookup"><span data-stu-id="29336-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="29336-147">**Classificação de equipe** - feito pelo seus classificações de grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="29336-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="29336-148">**Configurações de membro de equipe** - configurações de membro da equipe select</span><span class="sxs-lookup"><span data-stu-id="29336-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="29336-149">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="29336-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="29336-150">Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="29336-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="29336-151">Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="29336-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="29336-152">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="29336-152">Troubleshooting</span></span>

<span data-ttu-id="29336-153">**Problema: As equipes ausentes da grade de visão geral da equipe**</span><span class="sxs-lookup"><span data-stu-id="29336-153">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="29336-154">Quando você insere o Centro de administração do Microsoft Teams, sob a opção de **equipes** algumas das suas equipes estão ausentes da listagem na grade de visão geral de equipes.</span><span class="sxs-lookup"><span data-stu-id="29336-154">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="29336-155">**Causa**: esse problema ocorre quando a equipe foi atribuída incorretamente (ou ainda não) pelo sistema que pode resultar em uma propriedade ausente para que ele seja reconhecida.</span><span class="sxs-lookup"><span data-stu-id="29336-155">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="29336-156">**Resolução: Definir a propriedade manualmente o valor correto via MS Graph**</span><span class="sxs-lookup"><span data-stu-id="29336-156">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="29336-157">Substitua **{groupid}** na consulta referente a GroupId real em questão, que você pode obter via o powershell do Exchange Online, o cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como o atributo "**ExternalDirectoryObjectId**".</span><span class="sxs-lookup"><span data-stu-id="29336-157">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="29336-158">Acesso do [Explorer do gráfico](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="29336-158">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="29336-159">Entrar no Explorer do gráfico no menu à esquerda</span><span class="sxs-lookup"><span data-stu-id="29336-159">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="29336-160">Altere a linha de consulta para: gt _ do PATCH gt _ v 1.0https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="29336-160">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="29336-161">Adicione o seguinte valor no corpo da solicitação: {"resourceProvisioningOptions": ["equipe"]}</span><span class="sxs-lookup"><span data-stu-id="29336-161">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="29336-162">Execute a consulta na parte superior direita.</span><span class="sxs-lookup"><span data-stu-id="29336-162">Run the query on the top-right.</span></span>

6. <span data-ttu-id="29336-163">Confirmar que a equipe seja exibido corretamente no Centro de administração do Microsoft Teams - visão geral da equipe</span><span class="sxs-lookup"><span data-stu-id="29336-163">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="29336-164">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="29336-164">Learn more</span></span>

[<span data-ttu-id="29336-165">Referência do cmdlet Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="29336-165">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="29336-166">Funções de administrador no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29336-166">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

