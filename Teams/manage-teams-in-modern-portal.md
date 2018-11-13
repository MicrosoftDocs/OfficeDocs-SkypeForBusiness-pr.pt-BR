---
title: Gerenciar equipes na Microsoft Teams & Skype para Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Saiba como exibir ou atualizar suas equipes na Microsoft Teams & Skype para Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8d517ce7f2fb614a22c45fcf63d59a7d46b606f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295019"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="090ae-103">Gerenciar equipes na Microsoft Teams & Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="090ae-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="090ae-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="090ae-104">Overview</span></span>

<span data-ttu-id="090ae-105">Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários.</span><span class="sxs-lookup"><span data-stu-id="090ae-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="090ae-106">Você pode gerenciar as equipes usadas na sua organização por meio de tanto o módulo de PowerShell de equipes da Microsoft e o Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="090ae-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="090ae-107">Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="090ae-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="090ae-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="090ae-108">Global Administrator</span></span>
- <span data-ttu-id="090ae-109">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="090ae-109">Teams Service Administrator</span></span>

<span data-ttu-id="090ae-110">Você pode aprender mais sobre as funções de administrador no Microsoft Teams [aqui](using-admin-roles.md), e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="090ae-110">You can learn more about admin roles in Microsoft Teams [here](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="090ae-111">Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes na Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="090ae-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="090ae-112">Grade de visão geral de equipes</span><span class="sxs-lookup"><span data-stu-id="090ae-112">Teams overview grid</span></span>

<span data-ttu-id="090ae-113">Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** na Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="090ae-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="090ae-114">(No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição de todos os grupos que foram habilitados para equipes em sua organização do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="090ae-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of all groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="090ae-116">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="090ae-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="090ae-117">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="090ae-117">**Team name**</span></span>
- <span data-ttu-id="090ae-118">**Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.</span><span class="sxs-lookup"><span data-stu-id="090ae-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="090ae-119">**Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="090ae-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="090ae-120">**Proprietários** - uma contagem de proprietários para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="090ae-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="090ae-121">**Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="090ae-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="090ae-122">**Privacidade** - o AccessType do grupo apoio Office 365.</span><span class="sxs-lookup"><span data-stu-id="090ae-122">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="090ae-123">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="090ae-123">Search</span></span>

<span data-ttu-id="090ae-124">Pesquisa atualmente suporta a cadeia de caracteres "Começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="090ae-124">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="090ae-125">Editar</span><span class="sxs-lookup"><span data-stu-id="090ae-125">Edit</span></span>

<span data-ttu-id="090ae-126">Você pode editar o grupo e as configurações específicas do team selecionando uma equipe da grade e, em seguida, selecionando o botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="090ae-126">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar a equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="090ae-128">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="090ae-128">Team profile</span></span>

<span data-ttu-id="090ae-129">Você pode navegar para a página de perfil de equipe de qualquer equipe da grade de visão geral de equipes principal clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="090ae-129">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="090ae-130">A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu fazendo O365 grupo), bem como os canais e configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="090ae-130">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="090ae-131">Na página de perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="090ae-131">From the team profile page, you can:</span></span>

- <span data-ttu-id="090ae-132">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="090ae-132">Add or remove members and owners.</span></span>
- <span data-ttu-id="090ae-133">Adicionar ou remover canais (Observe que não é possível remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="090ae-133">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="090ae-134">Atualize a equipe e configurações de grupo.</span><span class="sxs-lookup"><span data-stu-id="090ae-134">Update team and group settings.</span></span>
 
![Perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="090ae-136">Fazendo alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="090ae-136">Making changes to teams</span></span>

<span data-ttu-id="090ae-137">Você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="090ae-137">You can change the following elements of a team:</span></span>
- <span data-ttu-id="090ae-138">**Os usuários na equipe de** - você pode adicionar ou remover membros e promover ou rebaixar proprietários</span><span class="sxs-lookup"><span data-stu-id="090ae-138">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="090ae-139">**Canais** - você pode adicionar novos canais ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="090ae-139">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="090ae-140">Você não pode excluir o canal de "General" padrão e uma vez criada você só pode editar o nome de canal, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="090ae-140">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="090ae-141">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="090ae-141">**Team name**</span></span>
- <span data-ttu-id="090ae-142">**Descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="090ae-142">**Team description**</span></span>
- <span data-ttu-id="090ae-143">**Foto de equipe**</span><span class="sxs-lookup"><span data-stu-id="090ae-143">**Team photo**</span></span>
- <span data-ttu-id="090ae-144">**Privacidade de equipe** - pública ou privada</span><span class="sxs-lookup"><span data-stu-id="090ae-144">**Team privacy** - public or private</span></span>
- <span data-ttu-id="090ae-145">**Classificação de equipe** - feito pelo seus classificações de grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="090ae-145">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="090ae-146">**Configurações de membro de equipe** - configurações de membro da equipe select</span><span class="sxs-lookup"><span data-stu-id="090ae-146">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="090ae-147">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="090ae-147">The changes that you make to a team are logged.</span></span> <span data-ttu-id="090ae-148">Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="090ae-148">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="090ae-149">Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="090ae-149">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="090ae-150">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="090ae-150">Learn more</span></span>

[<span data-ttu-id="090ae-151">Referência do cmdlet Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="090ae-151">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="090ae-152">Funções de administrador no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="090ae-152">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

