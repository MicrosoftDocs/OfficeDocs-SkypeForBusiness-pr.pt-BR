---
title: Atribuir proprietários de equipe e membros no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569953"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="f7f03-103">Atribuir proprietários de equipe e membros no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7f03-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f7f03-104">Em Microsoft Teams, existem duas funções de usuário: **proprietário** e do **membro**.</span><span class="sxs-lookup"><span data-stu-id="f7f03-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="f7f03-105">Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário.</span><span class="sxs-lookup"><span data-stu-id="f7f03-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="f7f03-106">Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.</span><span class="sxs-lookup"><span data-stu-id="f7f03-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="f7f03-107">A tabela abaixo mostra a diferença em permissões entre um proprietário e um membro.</span><span class="sxs-lookup"><span data-stu-id="f7f03-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="f7f03-108">Proprietário da equipe</span><span class="sxs-lookup"><span data-stu-id="f7f03-108">Team Owner</span></span> | <span data-ttu-id="f7f03-109">Membro da equipe</span><span class="sxs-lookup"><span data-stu-id="f7f03-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="f7f03-110">**Criar equipe**</span><span class="sxs-lookup"><span data-stu-id="f7f03-110">**Create team**</span></span>          |    <span data-ttu-id="f7f03-111">Sim<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="f7f03-112">Não</span><span class="sxs-lookup"><span data-stu-id="f7f03-112">No</span></span>      |
|          <span data-ttu-id="f7f03-113">**Sair da equipe**</span><span class="sxs-lookup"><span data-stu-id="f7f03-113">**Leave team**</span></span>           |    <span data-ttu-id="f7f03-114">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-114">Yes</span></span>     |     <span data-ttu-id="f7f03-115">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-115">Yes</span></span>     |
|  <span data-ttu-id="f7f03-116">**Editar nome/descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="f7f03-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="f7f03-117">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-117">Yes</span></span>     |     <span data-ttu-id="f7f03-118">Não</span><span class="sxs-lookup"><span data-stu-id="f7f03-118">No</span></span>      |
|          <span data-ttu-id="f7f03-119">**Excluir equipe**</span><span class="sxs-lookup"><span data-stu-id="f7f03-119">**Delete team**</span></span>          |    <span data-ttu-id="f7f03-120">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-120">Yes</span></span>     |     <span data-ttu-id="f7f03-121">Não</span><span class="sxs-lookup"><span data-stu-id="f7f03-121">No</span></span>      |
|          <span data-ttu-id="f7f03-122">**Adicionar canal**</span><span class="sxs-lookup"><span data-stu-id="f7f03-122">**Add channel**</span></span>          |    <span data-ttu-id="f7f03-123">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-123">Yes</span></span>     |    <span data-ttu-id="f7f03-124">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="f7f03-125">**Editar nome/descrição do canal**</span><span class="sxs-lookup"><span data-stu-id="f7f03-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="f7f03-126">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-126">Yes</span></span>     |    <span data-ttu-id="f7f03-127">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="f7f03-128">**Excluir canal**</span><span class="sxs-lookup"><span data-stu-id="f7f03-128">**Delete channel**</span></span>         |    <span data-ttu-id="f7f03-129">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-129">Yes</span></span>     |    <span data-ttu-id="f7f03-130">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="f7f03-131">**Adicionar membros**</span><span class="sxs-lookup"><span data-stu-id="f7f03-131">**Add members**</span></span>          |  <span data-ttu-id="f7f03-132">Sim<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="f7f03-133">Nenhum<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="f7f03-134">**Solicitação para adicionar membros**</span><span class="sxs-lookup"><span data-stu-id="f7f03-134">**Request to add members**</span></span>          |  <span data-ttu-id="f7f03-135">N/D</span><span class="sxs-lookup"><span data-stu-id="f7f03-135">N/A</span></span>   |     <span data-ttu-id="f7f03-136">Sim<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="f7f03-137">**Adicionar guias**</span><span class="sxs-lookup"><span data-stu-id="f7f03-137">**Add tabs**</span></span>            |    <span data-ttu-id="f7f03-138">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-138">Yes</span></span>     |    <span data-ttu-id="f7f03-139">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="f7f03-140">**Adicionar conectores**</span><span class="sxs-lookup"><span data-stu-id="f7f03-140">**Add connectors**</span></span>         |    <span data-ttu-id="f7f03-141">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-141">Yes</span></span>     |    <span data-ttu-id="f7f03-142">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="f7f03-143">**Adicionar bots**</span><span class="sxs-lookup"><span data-stu-id="f7f03-143">**Add bots**</span></span>            |    <span data-ttu-id="f7f03-144">Sim</span><span class="sxs-lookup"><span data-stu-id="f7f03-144">Yes</span></span>     |    <span data-ttu-id="f7f03-145">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f7f03-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="f7f03-146"><sup>1</sup> proprietários de equipe possam criar equipes, a menos que eles tenham sido impedidos de fazer isso.</span><span class="sxs-lookup"><span data-stu-id="f7f03-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="f7f03-147">Consulte "Permissões para criar equipes" abaixo.</span><span class="sxs-lookup"><span data-stu-id="f7f03-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="f7f03-148"><sup>2</sup> desses itens podem ser desativados por um proprietário em um nível de equipe, caso em que os membros não terá acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="f7f03-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="f7f03-149"><sup>3</sup> depois de adicionar um membro para uma equipe, um proprietário também pode promover um membro ao status de proprietário.</span><span class="sxs-lookup"><span data-stu-id="f7f03-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="f7f03-150">Também é possível para um proprietário a serem rebaixados suas próprias status do membro.</span><span class="sxs-lookup"><span data-stu-id="f7f03-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="f7f03-151"><sup>4</sup> membros da equipe podem adicionar outros membros para uma equipe pública.</span><span class="sxs-lookup"><span data-stu-id="f7f03-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="f7f03-152"><sup>5</sup> enquanto um membro da equipe não pode adicionar membros diretamente para uma equipe privada, eles podem solicitar uma pessoa a ser adicionado a uma equipe que elas já membro do.</span><span class="sxs-lookup"><span data-stu-id="f7f03-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="f7f03-153">Quando um membro solicita uma pessoa a ser adicionado a uma equipe, os proprietários de equipe recebem um alerta que têm uma solicitação pendente que eles podem aceitar ou recusar.</span><span class="sxs-lookup"><span data-stu-id="f7f03-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="f7f03-154">Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes.</span><span class="sxs-lookup"><span data-stu-id="f7f03-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="f7f03-155">Uma equipe pode ter até 100 proprietários.</span><span class="sxs-lookup"><span data-stu-id="f7f03-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="f7f03-156">É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização.</span><span class="sxs-lookup"><span data-stu-id="f7f03-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="f7f03-157">Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="f7f03-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="f7f03-158">Permissões para criar equipes</span><span class="sxs-lookup"><span data-stu-id="f7f03-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="f7f03-159">Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f7f03-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="f7f03-160">Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="f7f03-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="f7f03-161">Para obter instruções, consulte [Manage quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="f7f03-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="f7f03-163">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="f7f03-163">Decision Point</span></span>         |<span data-ttu-id="f7f03-164">Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="f7f03-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="f7f03-166">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="f7f03-166">Next Steps</span></span>         |<span data-ttu-id="f7f03-167">Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes</span><span class="sxs-lookup"><span data-stu-id="f7f03-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
