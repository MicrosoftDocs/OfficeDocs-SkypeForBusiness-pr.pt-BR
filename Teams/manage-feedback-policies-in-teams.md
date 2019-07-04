---
title: Gerenciar políticas de comentários no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar políticas de comentários para controlar se os usuários de equipes em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540949"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="a8121-103">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8121-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="a8121-104">Os usuários podem enviar comentários e sugestões sobre o Microsoft Teams para a Microsoft para **ajudar** > a**fornecer comentários** sobre os clientes do teams.</span><span class="sxs-lookup"><span data-stu-id="a8121-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="a8121-105">Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.</span><span class="sxs-lookup"><span data-stu-id="a8121-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="a8121-107">Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".</span><span class="sxs-lookup"><span data-stu-id="a8121-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="a8121-108">Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8121-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="a8121-109">Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8121-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="a8121-110">Por padrão, todos os usuários de sua organização recebem automaticamente a política global (padrão para toda a organização) e o recurso é habilitado na política.</span><span class="sxs-lookup"><span data-stu-id="a8121-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="a8121-111">A exceção é o Teams for Education, em que o recurso está habilitado para professores e desabilitado para estudantes.</span><span class="sxs-lookup"><span data-stu-id="a8121-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="a8121-112">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="a8121-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="a8121-113">Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a8121-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="a8121-114">Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a8121-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="a8121-115">Depois de editar a política global ou atribuir uma política, pode levar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="a8121-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="a8121-116">Digamos, por exemplo, que você queira permitir que todos os usuários da sua organização enviem comentários, exceto para novas contratações no treinamento.</span><span class="sxs-lookup"><span data-stu-id="a8121-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="a8121-117">Nesse cenário, você cria uma política personalizada para desativar o recurso e atribuí-lo a novas contratações.</span><span class="sxs-lookup"><span data-stu-id="a8121-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="a8121-118">Todos os outros usuários da sua organização obtêm a política global com o recurso ativado.</span><span class="sxs-lookup"><span data-stu-id="a8121-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="a8121-119">Use o cmdlet **New-CsTeamsFeedbackPolicy** para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="a8121-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="a8121-120">Defina o \*\*\*\* parâmetro userinicioumode como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários.</span><span class="sxs-lookup"><span data-stu-id="a8121-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="a8121-121">Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="a8121-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="a8121-122">Criar uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="a8121-122">Create a custom feedback policy</span></span>

<span data-ttu-id="a8121-123">Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="a8121-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="a8121-124">Atribuir uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="a8121-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="a8121-125">Atribuir uma política de comentários personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="a8121-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="a8121-126">Neste exemplo, atribuímos uma política personalizada chamada nova política de feedback de contratação a um usuário chamado Usuário1.</span><span class="sxs-lookup"><span data-stu-id="a8121-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="a8121-127">Atribuir uma política de comentários personalizada aos usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="a8121-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="a8121-128">Você pode querer atribuir uma política de comentários personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="a8121-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="a8121-129">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="a8121-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="a8121-130">Neste exemplo, atribuímos uma política de comentários personalizada chamada nova política de feedback de contratação a todos os usuários no novo grupo contoso contratações.</span><span class="sxs-lookup"><span data-stu-id="a8121-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="a8121-131">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="a8121-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="a8121-132">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="a8121-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="a8121-133">Atribua todos os usuários do grupo a uma política de comentários específica.</span><span class="sxs-lookup"><span data-stu-id="a8121-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="a8121-134">Neste exemplo, a nova política de feedback para contratação.</span><span class="sxs-lookup"><span data-stu-id="a8121-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="a8121-135">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="a8121-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8121-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a8121-136">Related topics</span></span>

- [<span data-ttu-id="a8121-137">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="a8121-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)