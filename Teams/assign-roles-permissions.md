---
title: Atribuir membros em Microsoft Teams e proprietários de equipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d5b3f52caf7de455d2b579a3360d17e18602450
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014287"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="71e88-103">Atribuir membros em Microsoft Teams e proprietários de equipe</span><span class="sxs-lookup"><span data-stu-id="71e88-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="71e88-104">Em Microsoft Teams, existem duas funções de usuário: **proprietário** e do **membro**.</span><span class="sxs-lookup"><span data-stu-id="71e88-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="71e88-105">Por padrão, um usuário que cria uma nova equipe recebe o status de proprietário.</span><span class="sxs-lookup"><span data-stu-id="71e88-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="71e88-106">Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.</span><span class="sxs-lookup"><span data-stu-id="71e88-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="71e88-107">A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:</span><span class="sxs-lookup"><span data-stu-id="71e88-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="71e88-108">Proprietário da equipe</span><span class="sxs-lookup"><span data-stu-id="71e88-108">Team Owner</span></span>  |<span data-ttu-id="71e88-109">Membro da equipe</span><span class="sxs-lookup"><span data-stu-id="71e88-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="71e88-110">**Criar equipe**</span><span class="sxs-lookup"><span data-stu-id="71e88-110">**Create team**</span></span>     |<span data-ttu-id="71e88-111">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-111">Yes</span></span>        |<span data-ttu-id="71e88-112">Não</span><span class="sxs-lookup"><span data-stu-id="71e88-112">No</span></span>         |
|<span data-ttu-id="71e88-113">**Sair da equipe**</span><span class="sxs-lookup"><span data-stu-id="71e88-113">**Leave team**</span></span>     |<span data-ttu-id="71e88-114">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-114">Yes</span></span>         |<span data-ttu-id="71e88-115">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-115">Yes</span></span>         |
|<span data-ttu-id="71e88-116">**Editar nome/descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="71e88-116">**Edit team name/description**</span></span>      |<span data-ttu-id="71e88-117">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-117">Yes</span></span>         |<span data-ttu-id="71e88-118">Não</span><span class="sxs-lookup"><span data-stu-id="71e88-118">No</span></span>         |
|<span data-ttu-id="71e88-119">**Excluir equipe**</span><span class="sxs-lookup"><span data-stu-id="71e88-119">**Delete team**</span></span>      |<span data-ttu-id="71e88-120">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-120">Yes</span></span>         |<span data-ttu-id="71e88-121">Não</span><span class="sxs-lookup"><span data-stu-id="71e88-121">No</span></span>         |
|<span data-ttu-id="71e88-122">**Adicionar canal**</span><span class="sxs-lookup"><span data-stu-id="71e88-122">**Add channel**</span></span>      |<span data-ttu-id="71e88-123">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-123">Yes</span></span>         |<span data-ttu-id="71e88-124">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-124">Yes\*</span></span>         |
|<span data-ttu-id="71e88-125">**Editar nome/descrição do canal**</span><span class="sxs-lookup"><span data-stu-id="71e88-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="71e88-126">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-126">Yes</span></span>         |<span data-ttu-id="71e88-127">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-127">Yes\*</span></span>         |
|<span data-ttu-id="71e88-128">**Excluir canal**</span><span class="sxs-lookup"><span data-stu-id="71e88-128">**Delete channel**</span></span>      |<span data-ttu-id="71e88-129">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-129">Yes</span></span>         |<span data-ttu-id="71e88-130">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-130">Yes\*</span></span>         |
|<span data-ttu-id="71e88-131">**Adicionar membros**</span><span class="sxs-lookup"><span data-stu-id="71e88-131">**Add members**</span></span>      |<span data-ttu-id="71e88-132">Sim\*\*</span><span class="sxs-lookup"><span data-stu-id="71e88-132">Yes\*\*</span></span>         |<span data-ttu-id="71e88-133">Não</span><span class="sxs-lookup"><span data-stu-id="71e88-133">No</span></span>         |
|<span data-ttu-id="71e88-134">**Adicionar guias**</span><span class="sxs-lookup"><span data-stu-id="71e88-134">**Add tabs**</span></span>      |<span data-ttu-id="71e88-135">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-135">Yes</span></span>         |<span data-ttu-id="71e88-136">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-136">Yes\*</span></span>         |
|<span data-ttu-id="71e88-137">**Adicionar conectores**</span><span class="sxs-lookup"><span data-stu-id="71e88-137">**Add connectors**</span></span>      |<span data-ttu-id="71e88-138">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-138">Yes</span></span>         |<span data-ttu-id="71e88-139">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-139">Yes\*</span></span>         |
|<span data-ttu-id="71e88-140">**Adicionar bots**</span><span class="sxs-lookup"><span data-stu-id="71e88-140">**Add bots**</span></span>      |<span data-ttu-id="71e88-141">Sim</span><span class="sxs-lookup"><span data-stu-id="71e88-141">Yes</span></span>         |<span data-ttu-id="71e88-142">Sim\*</span><span class="sxs-lookup"><span data-stu-id="71e88-142">Yes\*</span></span>         |
<span data-ttu-id="71e88-143">\*Esses itens podem ser desativados por um proprietário em um nível de equipe, caso em que os membros não terá acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="71e88-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="71e88-144">\*\*Após adicionar um membro a uma equipe, o Proprietário também pode promover um Membro para o status de Proprietário.</span><span class="sxs-lookup"><span data-stu-id="71e88-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="71e88-145">Também é possível para um Proprietário rebaixar seu próprio status para o status de Membro.</span><span class="sxs-lookup"><span data-stu-id="71e88-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="71e88-146">Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes.</span><span class="sxs-lookup"><span data-stu-id="71e88-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="71e88-147">Uma equipe pode ter até 100 proprietários.</span><span class="sxs-lookup"><span data-stu-id="71e88-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="71e88-148">É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização.</span><span class="sxs-lookup"><span data-stu-id="71e88-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="71e88-149">Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="71e88-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="71e88-150">Permissões para criar equipes</span><span class="sxs-lookup"><span data-stu-id="71e88-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="71e88-151">Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="71e88-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="71e88-152">Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="71e88-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="71e88-153">Para obter instruções, consulte [Manage quem pode criar grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="71e88-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="71e88-155">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="71e88-155">Decision Point</span></span>         |<span data-ttu-id="71e88-156">Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="71e88-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="71e88-158">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="71e88-158">Next Steps</span></span>         |<span data-ttu-id="71e88-159">Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes</span><span class="sxs-lookup"><span data-stu-id="71e88-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
