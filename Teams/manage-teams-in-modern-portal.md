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
ms.openlocfilehash: 14ab474289e5a677e1125df7146ba7c5a6fc2ca1
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539053"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="ac50e-103">Gerenciar equipes na Microsoft Teams & Skype para Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="ac50e-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="ac50e-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="ac50e-104">Overview</span></span>

<span data-ttu-id="ac50e-105">Como um administrador de TI, você pode precisar exibir ou atualizar as equipes que sua organização tiver configurado para colaboração, ou você podem precisar efetuar as ações de remediação como atribuir proprietários para equipes sem proprietários.</span><span class="sxs-lookup"><span data-stu-id="ac50e-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="ac50e-106">Você pode gerenciar as equipes usadas na sua organização por meio de tanto o módulo de PowerShell de equipes da Microsoft e o Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ac50e-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="ac50e-107">Para os recursos de administração completos usando esses dois conjuntos de ferramentas, verifique se você recebem uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="ac50e-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="ac50e-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ac50e-108">Global Administrator</span></span>
- <span data-ttu-id="ac50e-109">Administrador de Serviço de Equipes</span><span class="sxs-lookup"><span data-stu-id="ac50e-109">Teams Service Administrator</span></span>

<span data-ttu-id="ac50e-110">Você também deve garantir que sua conta tenha sido atribuída uma licença de equipes não seja de avaliação para o gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ac50e-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="ac50e-111">Como parte de um problema conhecido, você deve garantir que sua conta tem apenas **uma** função de administrador atribuída.</span><span class="sxs-lookup"><span data-stu-id="ac50e-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="ac50e-112">Você pode aprender mais sobre as funções de administrador no Microsoft Teams em [equipes da Microsoft usar funções de administrador para gerenciar equipes](using-admin-roles.md)e você pode ler mais sobre como usar os cmdlets do PowerShell para gerenciar equipes na [referência do cmdlet equipes da Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="ac50e-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="ac50e-113">Este artigo fornece uma visão geral das ferramentas de gerenciamento para equipes na Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ac50e-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="ac50e-114">Grade de visão geral de equipes</span><span class="sxs-lookup"><span data-stu-id="ac50e-114">Teams overview grid</span></span>

<span data-ttu-id="ac50e-115">Ferramentas de gerenciamento para equipes estão sob o nó de **equipes** na Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ac50e-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="ac50e-116">(No Centro de administração, selecione **equipes** > **gerenciar equipes**.) Cada equipe é feito por um grupo do Office 365 e este nó fornece um modo de exibição dos grupos que foram habilitados para equipes em sua organização do Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac50e-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="ac50e-117">Estamos no processo backfilling criado anteriormente equipes para garantir que eles serão exibidas nesse modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="ac50e-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![Grade de visão geral de equipes](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="ac50e-119">A grade exibe as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="ac50e-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="ac50e-120">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="ac50e-120">**Team name**</span></span>
- <span data-ttu-id="ac50e-121">**Canais** - uma contagem de todos os canais da equipe, incluindo o canal gerais do padrão.</span><span class="sxs-lookup"><span data-stu-id="ac50e-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="ac50e-122">**Os usuários** - uma contagem do total de usuários, incluindo proprietários, convidados e membros de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ac50e-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="ac50e-123">**Proprietários** - uma contagem de proprietários para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="ac50e-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="ac50e-124">**Convidados** - uma contagem de usuários de convidado B2B do Azure Active Directory que são membros dessa equipe.</span><span class="sxs-lookup"><span data-stu-id="ac50e-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="ac50e-125">**Privacidade** - o AccessType do grupo apoio Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac50e-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="ac50e-126">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="ac50e-126">Search</span></span>

<span data-ttu-id="ac50e-127">Pesquisa atualmente suporta a cadeia de caracteres "Começa com" e pesquisa o campo **nome da equipe** .</span><span class="sxs-lookup"><span data-stu-id="ac50e-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="ac50e-128">Editar</span><span class="sxs-lookup"><span data-stu-id="ac50e-128">Edit</span></span>

<span data-ttu-id="ac50e-129">Você pode editar o grupo e as configurações específicas do team selecionando uma equipe da grade e, em seguida, selecionando o botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ac50e-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![Editar a equipe](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="ac50e-131">Perfil de equipe</span><span class="sxs-lookup"><span data-stu-id="ac50e-131">Team profile</span></span>

<span data-ttu-id="ac50e-132">Você pode navegar para a página de perfil de equipe de qualquer equipe da grade de visão geral de equipes principal clicando no nome da equipe.</span><span class="sxs-lookup"><span data-stu-id="ac50e-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="ac50e-133">A página de perfil de equipe mostra os membros, proprietários e convidados que pertencem à equipe (e seu fazendo O365 grupo), bem como os canais e configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="ac50e-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="ac50e-134">Na página de perfil da equipe, você pode:</span><span class="sxs-lookup"><span data-stu-id="ac50e-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="ac50e-135">Adicionar ou remover membros e proprietários.</span><span class="sxs-lookup"><span data-stu-id="ac50e-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="ac50e-136">Adicionar ou remover canais (Observe que não é possível remover o canal geral).</span><span class="sxs-lookup"><span data-stu-id="ac50e-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="ac50e-137">Atualize a equipe e configurações de grupo.</span><span class="sxs-lookup"><span data-stu-id="ac50e-137">Update team and group settings.</span></span>
 
![Perfil de equipe](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="ac50e-139">Fazendo alterações em equipes</span><span class="sxs-lookup"><span data-stu-id="ac50e-139">Making changes to teams</span></span>

<span data-ttu-id="ac50e-140">Você pode alterar os seguintes elementos de uma equipe:</span><span class="sxs-lookup"><span data-stu-id="ac50e-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="ac50e-141">**Os usuários na equipe de** - você pode adicionar ou remover membros e promover ou rebaixar proprietários</span><span class="sxs-lookup"><span data-stu-id="ac50e-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="ac50e-142">**Canais** - você pode adicionar novos canais ou remover canais existentes.</span><span class="sxs-lookup"><span data-stu-id="ac50e-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="ac50e-143">Você não pode excluir o canal de "General" padrão e uma vez criada você só pode editar o nome de canal, não a descrição.</span><span class="sxs-lookup"><span data-stu-id="ac50e-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="ac50e-144">**Nome da equipe**</span><span class="sxs-lookup"><span data-stu-id="ac50e-144">**Team name**</span></span>
- <span data-ttu-id="ac50e-145">**Descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="ac50e-145">**Team description**</span></span>
- <span data-ttu-id="ac50e-146">**Privacidade de equipe** - pública ou privada</span><span class="sxs-lookup"><span data-stu-id="ac50e-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="ac50e-147">**Classificação de equipe** - feito pelo seus classificações de grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="ac50e-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="ac50e-148">**Configurações de membro de equipe** - configurações de membro da equipe select</span><span class="sxs-lookup"><span data-stu-id="ac50e-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="ac50e-149">As alterações feitas em uma equipe são registradas.</span><span class="sxs-lookup"><span data-stu-id="ac50e-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="ac50e-150">Se você estiver modificando configurações de grupo (alterando o nome, descrição, foto, privacidade, classificação ou membros da equipe), essas alterações serão atribuídas a você através do pipeline de auditoria.</span><span class="sxs-lookup"><span data-stu-id="ac50e-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="ac50e-151">Se você estiver realizando ações contra as configurações específicas de equipes, suas alterações serão rastreadas e atribuídas a você no canal geral da equipe.</span><span class="sxs-lookup"><span data-stu-id="ac50e-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="ac50e-152">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="ac50e-152">Learn more</span></span>

[<span data-ttu-id="ac50e-153">Referência do cmdlet Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ac50e-153">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="ac50e-154">Funções de administrador no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ac50e-154">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

