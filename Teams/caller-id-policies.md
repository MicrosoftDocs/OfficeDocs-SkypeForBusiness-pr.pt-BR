---
title: Gerenciar políticas de identificação de chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de identificação de chamadas no Microsoft Teams para alterar ou bloquear a identificação de chamadas de usuários do teams em sua organização.
ms.openlocfilehash: b30f2f8650d1d875c56254d99efddb2f5fdbb5d0
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919365"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="f984a-103">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f984a-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="f984a-104">Como administrador, você pode usar as políticas de identificação de chamada no Microsoft Teams para alterar ou bloquear a identificação de chamadas (também conhecida como identificação da linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="f984a-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="f984a-105">Por padrão, o número de telefone dos usuários do teams pode ser visto ao fazer uma chamada para um telefone PSTN, e o número de telefone PSTN pode ser visto quando ele chama um usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="f984a-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="f984a-106">Você pode usar as políticas de identificação de chamadas para exibir um número de telefone alternativo para usuários do teams em sua organização ou impedir que um número recebido seja exibido.</span><span class="sxs-lookup"><span data-stu-id="f984a-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="f984a-107">Por exemplo, quando os usuários fazem uma chamada, você pode alterar a identificação de chamadas para exibir o número de telefone principal da sua organização, em vez de números de telefone dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f984a-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="f984a-108">Você gerencia as políticas de identificação de chamadas indo para**políticas de identificação de chamadas** de **voz** > no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f984a-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f984a-109">Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f984a-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="f984a-110">Os usuários em sua organização receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="f984a-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="f984a-111">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="f984a-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="f984a-112">Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f984a-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="f984a-113">Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f984a-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="f984a-114">Criar uma política de identificação de chamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="f984a-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="f984a-115">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de identificação de chamadas**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="f984a-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="f984a-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-116">Click **Add**.</span></span>
<span data-ttu-id="f984a-117">![Captura de tela da página nova política de identificação de chamadas no centro de administração](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="f984a-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="f984a-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="f984a-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="f984a-119">Aqui, escolha as configurações desejadas:</span><span class="sxs-lookup"><span data-stu-id="f984a-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="f984a-120">**Bloquear a identificação**de chamadas de entrada: Ative essa configuração para impedir que a identificação de chamadas de chamadas de entrada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="f984a-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="f984a-121">**Os usuários podem substituir a política de identificação de chamadas**: Ative essa configuração para permitir que os usuários substituam as configurações na política para exibir seu número para chamar ou não.</span><span class="sxs-lookup"><span data-stu-id="f984a-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="f984a-122">Isso significa que os usuários podem escolher se desejam exibir a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f984a-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="f984a-123">**Substituir identificação de chamadas**: defina a identificação de chamadas a ser exibida para os usuários selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f984a-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="f984a-124">**Número do usuário**: exibe o número do usuário.</span><span class="sxs-lookup"><span data-stu-id="f984a-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="f984a-125">**Número do serviço**: permite que você defina um número de telefone de serviço para ser exibido como a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f984a-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="f984a-126">**Anônimo**: EXIBE a identificação de chamadas como anônima.</span><span class="sxs-lookup"><span data-stu-id="f984a-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="f984a-127">**Número de serviço a ser usado para substituir a identificação de chamadas**: escolha um número de serviço para substituir a identificação de chamadas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f984a-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="f984a-128">Essa opção estará disponível se você tiver selecionado **número de serviço** em **substituir identificação de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="f984a-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="f984a-129">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="f984a-130">Editar uma política de identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="f984a-130">Edit a caller ID policy</span></span>

<span data-ttu-id="f984a-131">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="f984a-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="f984a-132">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de identificação de chamadas**de **voz** > .</span><span class="sxs-lookup"><span data-stu-id="f984a-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="f984a-133">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f984a-134">Altere as configurações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="f984a-135">Atribuir uma política de identificação de chamadas personalizada a usuários</span><span class="sxs-lookup"><span data-stu-id="f984a-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="f984a-136">Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a um ou mais usuários ou ao módulo do PowerShell do Skype for Business para atribuir uma política personalizada a grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="f984a-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="f984a-137">Atribuir uma política de ID de linha de chamador personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="f984a-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="f984a-138">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="f984a-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f984a-139">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="f984a-140">Em **política de identificação de chamadas**, selecione a política que você deseja atribuir e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="f984a-141">Atribuir uma política de ID de linha de chamada personalizada a vários usuários de uma vez</span><span class="sxs-lookup"><span data-stu-id="f984a-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="f984a-142">Para atribuir uma política de ID de linha de chamada personalizada a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="f984a-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="f984a-143">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f984a-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="f984a-144">Vá para**políticas de identificação de chamadas**de**voz** > do centro > de **Administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f984a-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="f984a-145">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="f984a-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="f984a-146">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="f984a-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="f984a-147">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="f984a-148">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="f984a-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="f984a-149">Quando tiver terminado de adicionar usuários, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f984a-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="f984a-150">Atribuir uma política de identificação de chamadas personalizada a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="f984a-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="f984a-151">Você pode querer atribuir uma política personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="f984a-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="f984a-152">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="f984a-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="f984a-153">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f984a-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="f984a-154">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f984a-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="f984a-155">Neste exemplo, atribuímos uma política de limite de chamadas personalizada chamada política de identificação de chamadas para todos os usuários no grupo de suporte da contoso.</span><span class="sxs-lookup"><span data-stu-id="f984a-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="f984a-156">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="f984a-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="f984a-157">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="f984a-157">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="f984a-158">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="f984a-158">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="f984a-159">Atribua todos os usuários do grupo a uma política específica de identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f984a-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="f984a-160">Neste exemplo, ele é compatível com a política de identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f984a-160">In this example, it's Support Caller ID Policy.</span></span>
```
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="f984a-161">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="f984a-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="f984a-162">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f984a-162">Related topics</span></span>

- [<span data-ttu-id="f984a-163">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="f984a-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

