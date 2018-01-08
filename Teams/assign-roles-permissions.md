---
title: "Atribuir funções e permissões no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: ec15844064a88cf1e6aa8af9e510107e342dd369
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="b2592-103">Atribuir funções e permissões no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2592-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="b2592-104">No Microsoft Teams, existem duas funções: **Proprietário** e **Membro**.</span><span class="sxs-lookup"><span data-stu-id="b2592-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="b2592-105">Por padrão, a um usuário que cria uma nova equipe, é atribuído o status de Proprietário.</span><span class="sxs-lookup"><span data-stu-id="b2592-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="b2592-106">Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.</span><span class="sxs-lookup"><span data-stu-id="b2592-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="b2592-107">A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:</span><span class="sxs-lookup"><span data-stu-id="b2592-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="b2592-108">Proprietário da equipe</span><span class="sxs-lookup"><span data-stu-id="b2592-108">Team Owner</span></span>  |<span data-ttu-id="b2592-109">Membro da equipe</span><span class="sxs-lookup"><span data-stu-id="b2592-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b2592-110">**Criar equipe**</span><span class="sxs-lookup"><span data-stu-id="b2592-110">**Create team**</span></span>     |<span data-ttu-id="b2592-111">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-111">Yes</span></span>        |<span data-ttu-id="b2592-112">Não</span><span class="sxs-lookup"><span data-stu-id="b2592-112">No</span></span>         |
|<span data-ttu-id="b2592-113">**Sair da equipe**</span><span class="sxs-lookup"><span data-stu-id="b2592-113">**Leave team**</span></span>     |<span data-ttu-id="b2592-114">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-114">Yes</span></span>         |<span data-ttu-id="b2592-115">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-115">Yes</span></span>         |
|<span data-ttu-id="b2592-116">**Editar nome/descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="b2592-116">**Edit team name/description**</span></span>      |<span data-ttu-id="b2592-117">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-117">Yes</span></span>         |<span data-ttu-id="b2592-118">Não</span><span class="sxs-lookup"><span data-stu-id="b2592-118">No</span></span>         |
|<span data-ttu-id="b2592-119">**Excluir equipe**</span><span class="sxs-lookup"><span data-stu-id="b2592-119">**Delete team**</span></span>      |<span data-ttu-id="b2592-120">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-120">Yes</span></span>         |<span data-ttu-id="b2592-121">Não</span><span class="sxs-lookup"><span data-stu-id="b2592-121">No</span></span>         |
|<span data-ttu-id="b2592-122">**Adicionar canal**</span><span class="sxs-lookup"><span data-stu-id="b2592-122">**Add channel**</span></span>      |<span data-ttu-id="b2592-123">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-123">Yes</span></span>         |<span data-ttu-id="b2592-124">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-124">Yes*</span></span>         |
|<span data-ttu-id="b2592-125">**Editar nome/descrição do canal**</span><span class="sxs-lookup"><span data-stu-id="b2592-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="b2592-126">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-126">Yes</span></span>         |<span data-ttu-id="b2592-127">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-127">Yes*</span></span>         |
|<span data-ttu-id="b2592-128">**Excluir canal**</span><span class="sxs-lookup"><span data-stu-id="b2592-128">**Delete channel**</span></span>      |<span data-ttu-id="b2592-129">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-129">Yes</span></span>         |<span data-ttu-id="b2592-130">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-130">Yes*</span></span>         |
|<span data-ttu-id="b2592-131">**Adicionar membros**</span><span class="sxs-lookup"><span data-stu-id="b2592-131">**Add members**</span></span>      |<span data-ttu-id="b2592-132">Sim**</span><span class="sxs-lookup"><span data-stu-id="b2592-132">Yes**</span></span>         |<span data-ttu-id="b2592-133">Não</span><span class="sxs-lookup"><span data-stu-id="b2592-133">No</span></span>         |
|<span data-ttu-id="b2592-134">**Adicionar guias**</span><span class="sxs-lookup"><span data-stu-id="b2592-134">**Add tabs**</span></span>      |<span data-ttu-id="b2592-135">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-135">Yes</span></span>         |<span data-ttu-id="b2592-136">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-136">Yes*</span></span>         |
|<span data-ttu-id="b2592-137">**Adicionar conectores**</span><span class="sxs-lookup"><span data-stu-id="b2592-137">**Add connectors**</span></span>      |<span data-ttu-id="b2592-138">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-138">Yes</span></span>         |<span data-ttu-id="b2592-139">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-139">Yes*</span></span>         |
|<span data-ttu-id="b2592-140">**Adicionar bots**</span><span class="sxs-lookup"><span data-stu-id="b2592-140">**Add bots**</span></span>      |<span data-ttu-id="b2592-141">Sim</span><span class="sxs-lookup"><span data-stu-id="b2592-141">Yes</span></span>         |<span data-ttu-id="b2592-142">Sim*</span><span class="sxs-lookup"><span data-stu-id="b2592-142">Yes*</span></span>         |
<span data-ttu-id="b2592-143">\* Esses itens podem ser desativados por um proprietário em nível de equipe, e nesse caso os membros não teriam acesso para tal.</span><span class="sxs-lookup"><span data-stu-id="b2592-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="b2592-144">\*\*Após adicionar um membro a uma equipe, o Proprietário também pode promover um Membro para o status de Proprietário.</span><span class="sxs-lookup"><span data-stu-id="b2592-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="b2592-145">Também é possível para um Proprietário rebaixar seu próprio status para o status de Membro.</span><span class="sxs-lookup"><span data-stu-id="b2592-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="b2592-146">Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes.</span><span class="sxs-lookup"><span data-stu-id="b2592-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="b2592-147">Uma equipe pode ter até 100 proprietários.</span><span class="sxs-lookup"><span data-stu-id="b2592-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="b2592-148">É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização.</span><span class="sxs-lookup"><span data-stu-id="b2592-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="b2592-149">Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span><span class="sxs-lookup"><span data-stu-id="b2592-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="b2592-150">Permissões para criar equipes</span><span class="sxs-lookup"><span data-stu-id="b2592-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="b2592-151">Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2592-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="b2592-152">Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="b2592-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="b2592-153">Se a sua organização tiver interesse em proceder dessa forma, as instruções abaixo descrevem as tarefas necessárias para tal.</span><span class="sxs-lookup"><span data-stu-id="b2592-153">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="b2592-154">Identifique ou crie um grupo de segurança (SG) de usuários que tenham permissões atribuídas para criar grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b2592-154">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="b2592-155">a.</span><span class="sxs-lookup"><span data-stu-id="b2592-155">a.</span></span>  <span data-ttu-id="b2592-156">**Ação:** Estabeleça um grupo de segurança no Office 365 para que você possa incluir os usuários que podem criar grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b2592-156">**Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="b2592-157">b.</span><span class="sxs-lookup"><span data-stu-id="b2592-157">b.</span></span>  <span data-ttu-id="b2592-158">Para obter mais informações, consulte [Criar, editar ou excluir um grupo de segurança no centro de administração do Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="b2592-158">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="b2592-159">Verifique se o controle na empresa para que usuários criem grupos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b2592-159">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="b2592-160">a.</span><span class="sxs-lookup"><span data-stu-id="b2592-160">a.</span></span>  <span data-ttu-id="b2592-161">**Ação:** Execute o seguinte script no PowerShell e verifique se o parâmetro UsersPermissiontoCreateGroupsEnabled está definido como **True.**</span><span class="sxs-lookup"><span data-stu-id="b2592-161">**Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="b2592-162">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="b2592-162">Connect-MsolService</span></span>

    <span data-ttu-id="b2592-163">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="b2592-163">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="b2592-164">b.</span><span class="sxs-lookup"><span data-stu-id="b2592-164">b.</span></span>  <span data-ttu-id="b2592-165">Se não estiver como true, execute o cmdlet Set-MsolCompanySettings **para defini-lo como True**.</span><span class="sxs-lookup"><span data-stu-id="b2592-165">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="b2592-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="b2592-166">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="b2592-167">c.</span><span class="sxs-lookup"><span data-stu-id="b2592-167">c.</span></span> <span data-ttu-id="b2592-168">Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="b2592-168">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="b2592-169">Configurar as configurações de Grupo do Office 365 para permitir que apenas grupos de segurança identificados tenham permissões para criar grupos</span><span class="sxs-lookup"><span data-stu-id="b2592-169">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="b2592-170">a.</span><span class="sxs-lookup"><span data-stu-id="b2592-170">a.</span></span>  <span data-ttu-id="b2592-171">**Ação:** Crie um objeto de configuração de grupos que contenha as configurações de grupo que receberão permissões atribuídas para a criação de grupos.</span><span class="sxs-lookup"><span data-stu-id="b2592-171">**Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="b2592-172">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="b2592-172">Connect-AzureAD</span></span>

    <span data-ttu-id="b2592-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="b2592-173">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="b2592-174">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="b2592-174">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="b2592-175">$setting[“EnableGroupCreation”] = “false”</span><span class="sxs-lookup"><span data-stu-id="b2592-175">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="b2592-176">$setting[“GroupCreationAllowedGroupId”] = “&lt;ObjectId of Group Allowed to Create Groups>”</span><span class="sxs-lookup"><span data-stu-id="b2592-176">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="b2592-177">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="b2592-177">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="b2592-178">b.</span><span class="sxs-lookup"><span data-stu-id="b2592-178">b.</span></span> <span data-ttu-id="b2592-179">Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="b2592-179">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="b2592-181">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="b2592-181">Decision Point</span></span>         |<span data-ttu-id="b2592-182">Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="b2592-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="b2592-184">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="b2592-184">Next Steps</span></span>         |<span data-ttu-id="b2592-185">Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes</span><span class="sxs-lookup"><span data-stu-id="b2592-185">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
