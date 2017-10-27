---
title: "Atribuir funções e permissões no Microsoft Teams | Suporte da Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1ccb0ff3216464aca5a17c3bebeb0e259929e798
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a><span data-ttu-id="cecb1-103">Atribuir funções e permissões no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cecb1-103">Assign roles and permissions in Microsoft Teams</span></span>
===============================================

<span data-ttu-id="cecb1-104">No Microsoft Teams, existem duas funções: **Proprietário** e **Membro**.</span><span class="sxs-lookup"><span data-stu-id="cecb1-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="cecb1-105">Por padrão, a um usuário que cria uma nova equipe, é atribuído o status de Proprietário.</span><span class="sxs-lookup"><span data-stu-id="cecb1-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="cecb1-106">Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.</span><span class="sxs-lookup"><span data-stu-id="cecb1-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="cecb1-107">A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:</span><span class="sxs-lookup"><span data-stu-id="cecb1-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="cecb1-108">Proprietário da equipe</span><span class="sxs-lookup"><span data-stu-id="cecb1-108">Team Owner</span></span>  |<span data-ttu-id="cecb1-109">Membro da equipe</span><span class="sxs-lookup"><span data-stu-id="cecb1-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cecb1-110">**Criar equipe**</span><span class="sxs-lookup"><span data-stu-id="cecb1-110">**Create team**</span></span>     |<span data-ttu-id="cecb1-111">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-111">Yes</span></span>        |<span data-ttu-id="cecb1-112">Não</span><span class="sxs-lookup"><span data-stu-id="cecb1-112">No</span></span>         |
|<span data-ttu-id="cecb1-113">**Sair da equipe**</span><span class="sxs-lookup"><span data-stu-id="cecb1-113">**Leave team**</span></span>     |<span data-ttu-id="cecb1-114">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-114">Yes</span></span>         |<span data-ttu-id="cecb1-115">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-115">Yes</span></span>         |
|<span data-ttu-id="cecb1-116">**Editar nome/descrição da equipe**</span><span class="sxs-lookup"><span data-stu-id="cecb1-116">**Edit team name/description**</span></span>      |<span data-ttu-id="cecb1-117">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-117">Yes</span></span>         |<span data-ttu-id="cecb1-118">Não</span><span class="sxs-lookup"><span data-stu-id="cecb1-118">No</span></span>         |
|<span data-ttu-id="cecb1-119">**Excluir equipe**</span><span class="sxs-lookup"><span data-stu-id="cecb1-119">**Delete team**</span></span>      |<span data-ttu-id="cecb1-120">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-120">Yes</span></span>         |<span data-ttu-id="cecb1-121">Não</span><span class="sxs-lookup"><span data-stu-id="cecb1-121">No</span></span>         |
|<span data-ttu-id="cecb1-122">**Adicionar canal**</span><span class="sxs-lookup"><span data-stu-id="cecb1-122">**Add channel**</span></span>      |<span data-ttu-id="cecb1-123">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-123">Yes</span></span>         |<span data-ttu-id="cecb1-124">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-124">Yes*</span></span>         |
|<span data-ttu-id="cecb1-125">**Editar nome/descrição do canal**</span><span class="sxs-lookup"><span data-stu-id="cecb1-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="cecb1-126">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-126">Yes</span></span>         |<span data-ttu-id="cecb1-127">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-127">Yes*</span></span>         |
|<span data-ttu-id="cecb1-128">**Excluir canal**</span><span class="sxs-lookup"><span data-stu-id="cecb1-128">**Delete channel**</span></span>      |<span data-ttu-id="cecb1-129">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-129">Yes</span></span>         |<span data-ttu-id="cecb1-130">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-130">Yes*</span></span>         |
|<span data-ttu-id="cecb1-131">**Adicionar membros**</span><span class="sxs-lookup"><span data-stu-id="cecb1-131">**Add members**</span></span>      |<span data-ttu-id="cecb1-132">Sim**</span><span class="sxs-lookup"><span data-stu-id="cecb1-132">Yes</span></span>         |<span data-ttu-id="cecb1-133">Não</span><span class="sxs-lookup"><span data-stu-id="cecb1-133">No</span></span>         |
|<span data-ttu-id="cecb1-134">**Adicionar guias**</span><span class="sxs-lookup"><span data-stu-id="cecb1-134">**Add tabs**</span></span>      |<span data-ttu-id="cecb1-135">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-135">Yes</span></span>         |<span data-ttu-id="cecb1-136">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-136">Yes*</span></span>         |
|<span data-ttu-id="cecb1-137">**Adicionar conectores**</span><span class="sxs-lookup"><span data-stu-id="cecb1-137">**Add connectors**</span></span>      |<span data-ttu-id="cecb1-138">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-138">Yes</span></span>         |<span data-ttu-id="cecb1-139">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-139">Yes*</span></span>         |
|<span data-ttu-id="cecb1-140">**Adicionar bots**</span><span class="sxs-lookup"><span data-stu-id="cecb1-140">**Add bots**</span></span>      |<span data-ttu-id="cecb1-141">Sim</span><span class="sxs-lookup"><span data-stu-id="cecb1-141">Yes</span></span>         |<span data-ttu-id="cecb1-142">Sim*</span><span class="sxs-lookup"><span data-stu-id="cecb1-142">Yes*</span></span>         |
<span data-ttu-id="cecb1-143">\* Esses itens podem ser desativados por um proprietário em nível de equipe, e nesse caso os membros não teriam acesso para tal.</span><span class="sxs-lookup"><span data-stu-id="cecb1-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to that.</span></span>

<span data-ttu-id="cecb1-144">\*\*Após adicionar um membro a uma equipe, o Proprietário também pode promover um Membro para o status de Proprietário.</span><span class="sxs-lookup"><span data-stu-id="cecb1-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="cecb1-145">Também é possível para um Proprietário rebaixar seu próprio status para o status de Membro.</span><span class="sxs-lookup"><span data-stu-id="cecb1-145">It is also possible for an Owner to demote their own status to a Member.</span></span>

| | |
|---------|---------|
|![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br><span data-ttu-id="cecb1-146">Nota</span><span class="sxs-lookup"><span data-stu-id="cecb1-146">Note:</span></span>     |<span data-ttu-id="cecb1-147">Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes.</span><span class="sxs-lookup"><span data-stu-id="cecb1-147">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="cecb1-148">Uma equipe pode ter até 10 proprietários.</span><span class="sxs-lookup"><span data-stu-id="cecb1-148">A team can have up to 10 owners.</span></span>         |

<a name="permissions-to-create-teams"></a><span data-ttu-id="cecb1-149">Permissões para criar equipes</span><span class="sxs-lookup"><span data-stu-id="cecb1-149">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="cecb1-150">Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cecb1-150">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="cecb1-151">Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="cecb1-151">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span>

<span data-ttu-id="cecb1-152">Se a sua organização tiver interesse em proceder dessa forma, as instruções abaixo descrevem as tarefas necessárias para tal.</span><span class="sxs-lookup"><span data-stu-id="cecb1-152">If your organization is interested in doing this, the instructions below outlines the tasks required to do so.</span></span>

1.  <span data-ttu-id="cecb1-153">Identifique ou crie um grupo de segurança (SG) de usuários que tenham permissões atribuídas para criar grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cecb1-153">Identify or create a security group (SG) of users who will have delegated permissions to create Office 365 groups.</span></span>

    <span data-ttu-id="cecb1-154">a.</span><span class="sxs-lookup"><span data-stu-id="cecb1-154">A</span></span>  <span data-ttu-id="cecb1-155">**Ação:** Estabeleça um grupo de segurança no Office 365 para que você possa incluir os usuários que podem criar grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cecb1-155">**Action:** Set up a security group in Office 365 so you can add your users who can create Office 365 groups.</span></span>

    <span data-ttu-id="cecb1-156">b.</span><span class="sxs-lookup"><span data-stu-id="cecb1-156">B</span></span>  <span data-ttu-id="cecb1-157">Para obter mais informações, consulte [Criar, editar ou excluir um grupo de segurança no centro de administração do Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span><span class="sxs-lookup"><span data-stu-id="cecb1-157">For more information, see [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).</span></span>

2.  <span data-ttu-id="cecb1-158">Verifique se o controle na empresa para que usuários criem grupos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="cecb1-158">Verify that the company-wide control for users to create groups is enabled.</span></span>

    <span data-ttu-id="cecb1-159">a.</span><span class="sxs-lookup"><span data-stu-id="cecb1-159">A</span></span>  <span data-ttu-id="cecb1-160">**Ação:** Execute o seguinte script no PowerShell e verifique se o parâmetro UsersPermissiontoCreateGroupsEnabled está definido como **True.**</span><span class="sxs-lookup"><span data-stu-id="cecb1-160">**Action:** Run the following PowerShell script and verify UsersPermissiontoCreateGroupsEnabled parameter is set to **True.**</span></span>

    <span data-ttu-id="cecb1-161">Connect-MsolService</span><span class="sxs-lookup"><span data-stu-id="cecb1-161">Connect-MsolService</span></span>

    <span data-ttu-id="cecb1-162">Get-MsolCompanyInformation</span><span class="sxs-lookup"><span data-stu-id="cecb1-162">Get-MsolCompanyInformation</span></span>

    <span data-ttu-id="cecb1-163">b.</span><span class="sxs-lookup"><span data-stu-id="cecb1-163">B</span></span>  <span data-ttu-id="cecb1-164">Se não estiver como true, execute o cmdlet Set-MsolCompanySettings **para defini-lo como True**.</span><span class="sxs-lookup"><span data-stu-id="cecb1-164">If this is not true, run the Set-MsolCompanySettings  cmdlet **to set it to True**.</span></span>
<span data-ttu-id="cecb1-165">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span><span class="sxs-lookup"><span data-stu-id="cecb1-165">Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True</span></span>

    <span data-ttu-id="cecb1-166">c.</span><span class="sxs-lookup"><span data-stu-id="cecb1-166">C</span></span> <span data-ttu-id="cecb1-167">Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span><span class="sxs-lookup"><span data-stu-id="cecb1-167">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).</span></span>

3.  <span data-ttu-id="cecb1-168">Configurar as configurações de Grupo do Office 365 para permitir que apenas grupos de segurança identificados tenham permissões para criar grupos</span><span class="sxs-lookup"><span data-stu-id="cecb1-168">Configure Office 365 Group settings to allow only identified security group has permissions to create groups</span></span>

    <span data-ttu-id="cecb1-169">a.</span><span class="sxs-lookup"><span data-stu-id="cecb1-169">A</span></span>  <span data-ttu-id="cecb1-170">**Ação:** Crie um objeto de configuração de grupos que contenha as configurações de grupo que receberão permissões atribuídas para a criação de grupos.</span><span class="sxs-lookup"><span data-stu-id="cecb1-170">**Action:** Create a group settings object that contains the configuration settings of the group that will be assigned delegated permissions to create groups.</span></span> 

    <span data-ttu-id="cecb1-171">Connect-AzureAD</span><span class="sxs-lookup"><span data-stu-id="cecb1-171">Connect-AzureAD</span></span>

    <span data-ttu-id="cecb1-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span><span class="sxs-lookup"><span data-stu-id="cecb1-172">$Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b</span></span>

    <span data-ttu-id="cecb1-173">$Setting = $template.CreateDirectorySetting()</span><span class="sxs-lookup"><span data-stu-id="cecb1-173">$Setting = $template.CreateDirectorySetting()</span></span>

    <span data-ttu-id="cecb1-174">$setting[“EnableGroupCreation”] = “false”</span><span class="sxs-lookup"><span data-stu-id="cecb1-174">$setting["EnableGroupCreation"] = "false"</span></span>

    <span data-ttu-id="cecb1-175">$setting[“GroupCreationAllowedGroupId”] = “&lt;ObjectId of Group Allowed to Create Groups>”</span><span class="sxs-lookup"><span data-stu-id="cecb1-175">$setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"</span></span>

    <span data-ttu-id="cecb1-176">New-AzureADDirectorySetting -DirectorySetting $settings</span><span class="sxs-lookup"><span data-stu-id="cecb1-176">New-AzureADDirectorySetting -DirectorySetting $settings</span></span>

    <span data-ttu-id="cecb1-177">b.</span><span class="sxs-lookup"><span data-stu-id="cecb1-177">B</span></span> <span data-ttu-id="cecb1-178">Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span><span class="sxs-lookup"><span data-stu-id="cecb1-178">For more information, see: [Manage Office 365 Group Creation](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)</span></span>


||||
|---------|---------|---------|
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="cecb1-179">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="cecb1-179">Policy Decision Point</span></span>         |<span data-ttu-id="cecb1-180">Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?</span><span class="sxs-lookup"><span data-stu-id="cecb1-180">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="cecb1-181">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="cecb1-181">Next Steps</span></span>         |<span data-ttu-id="cecb1-182">Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes</span><span class="sxs-lookup"><span data-stu-id="cecb1-182">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
