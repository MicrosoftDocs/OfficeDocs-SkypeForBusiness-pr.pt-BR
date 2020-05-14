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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de identificação de chamadas no Microsoft Teams para alterar ou bloquear a identificação de chamadas de usuários do teams em sua organização.
ms.openlocfilehash: a4dbdbac0922bb475f47447a3cf8b2d0f001909c
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224245"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="1b0d6-103">Gerenciar políticas de identificação de chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b0d6-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="1b0d6-104">Como administrador, você pode usar as políticas de identificação de chamada no Microsoft Teams para alterar ou bloquear a identificação de chamadas (também conhecida como identificação da linha de chamada).</span><span class="sxs-lookup"><span data-stu-id="1b0d6-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="1b0d6-105">Por padrão, o número de telefone dos usuários do teams pode ser visto ao fazer uma chamada para um telefone PSTN, e o número de telefone PSTN pode ser visto quando ele chama um usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="1b0d6-106">Você pode usar as políticas de identificação de chamadas para exibir um número de telefone alternativo para usuários do teams em sua organização ou impedir que um número recebido seja exibido.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="1b0d6-107">Por exemplo, quando os usuários fazem uma chamada, você pode alterar a identificação de chamadas para exibir o número de telefone principal da sua organização, em vez de números de telefone dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="1b0d6-108">Você gerencia as políticas de identificação de chamadas **Voice**indo para  >  **políticas de identificação de chamadas** de voz no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1b0d6-109">Você pode usar a política global (padrão para toda a organização) ou criar políticas personalizadas e atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="1b0d6-110">Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="1b0d6-111">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="1b0d6-112">Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="1b0d6-113">Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="1b0d6-114">Criar uma política de identificação de chamadas personalizada</span><span class="sxs-lookup"><span data-stu-id="1b0d6-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="1b0d6-115">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1b0d6-116">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-116">Click **Add**.</span></span> <br>
<span data-ttu-id="1b0d6-117">![Captura de tela da página nova política de identificação de chamadas no centro de administração](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="1b0d6-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="1b0d6-118">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1b0d6-119">Aqui, escolha as configurações desejadas:</span><span class="sxs-lookup"><span data-stu-id="1b0d6-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="1b0d6-120">**Bloquear a identificação**de chamadas de entrada: Ative essa configuração para impedir que a identificação de chamadas de chamadas de entrada seja exibida.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="1b0d6-121">**Substituir a política de identificação de chamadas**: Ative essa configuração para permitir que os usuários substituam as configurações na política para exibir seu número para chamar ou não.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="1b0d6-122">Isso significa que os usuários podem escolher se desejam exibir a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="1b0d6-123">Para obter mais informações, consulte [controle do usuário final da identificação de chamadas de saída](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="1b0d6-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="1b0d6-124">**Substituir a identificação de chamadas**por: definir a identificação de chamadas a ser exibida para os usuários selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1b0d6-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="1b0d6-125">**Número do usuário**: exibe o número do usuário.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="1b0d6-126">**Número do serviço**: permite que você defina um número de telefone de serviço para ser exibido como a identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="1b0d6-127">**Anônimo**: EXIBE a identificação de chamadas como anônima.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="1b0d6-128">**Substituir a identificação de chamadas por este número de serviço**: escolha um número de serviço para substituir a identificação de chamadas dos usuários.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="1b0d6-129">Essa opção estará disponível se você tiver selecionado **número de serviço** em **substituir a identificação de chamadas por**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="1b0d6-130">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="1b0d6-131">Editar uma política de identificação de chamadas</span><span class="sxs-lookup"><span data-stu-id="1b0d6-131">Edit a caller ID policy</span></span>

<span data-ttu-id="1b0d6-132">Você pode editar a política global ou qualquer política personalizada criada.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="1b0d6-133">Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de identificação de chamadas**de voz.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1b0d6-134">Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1b0d6-135">Altere as configurações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="1b0d6-136">Atribuir uma política de identificação de chamadas personalizada a usuários</span><span class="sxs-lookup"><span data-stu-id="1b0d6-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="1b0d6-137">Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a um ou mais usuários ou ao módulo do PowerShell do Skype for Business para atribuir uma política personalizada a grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="1b0d6-138">Atribuir uma política de ID de linha de chamador personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="1b0d6-138">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="1b0d6-139">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-139">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1b0d6-140">Clique em **políticas**e, em seguida, ao lado de **políticas atribuídas**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-140">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="1b0d6-141">Em **política de identificação de chamadas**, selecione a política que você deseja atribuir e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-141">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="1b0d6-142">Atribuir uma política de ID de linha de chamada personalizada a vários usuários de uma vez</span><span class="sxs-lookup"><span data-stu-id="1b0d6-142">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="1b0d6-143">Para atribuir uma política de ID de linha de chamada personalizada a vários usuários de uma só vez, consulte [Editar configurações de usuários do teams em massa](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="1b0d6-143">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="1b0d6-144">Ou, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1b0d6-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1b0d6-145">Vá para políticas de identificação de chamadas de voz **do centro de administração do Microsoft Teams**  >  **Voice**  >  **Caller ID policies**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-145">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1b0d6-146">Escolha a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1b0d6-147">Escolha **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="1b0d6-148">No painel **Gerenciar usuários**, procure o usuário pelo nome de exibição ou pelo nome de usuário, escolha o nome e marque **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1b0d6-149">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1b0d6-150">Quando tiver terminado de adicionar usuários, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-150">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="1b0d6-151">Atribuir uma política de identificação de chamadas personalizada a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="1b0d6-151">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="1b0d6-152">Você pode querer atribuir uma política personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-152">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="1b0d6-153">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-153">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="1b0d6-154">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-154">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="1b0d6-155">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1b0d6-155">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1b0d6-156">Neste exemplo, atribuímos uma política de limite de chamadas personalizada chamada política de identificação de chamadas para todos os usuários no grupo de suporte da contoso.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-156">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="1b0d6-157">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="1b0d6-157">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="1b0d6-158">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-158">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="1b0d6-159">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-159">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="1b0d6-160">Atribua todos os usuários do grupo a uma política específica de identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-160">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="1b0d6-161">Neste exemplo, ele é compatível com a política de identificação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-161">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="1b0d6-162">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="1b0d6-162">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="1b0d6-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1b0d6-163">Related topics</span></span>

- [<span data-ttu-id="1b0d6-164">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="1b0d6-164">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

