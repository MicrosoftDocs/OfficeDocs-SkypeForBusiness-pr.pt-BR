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
ms.openlocfilehash: 148ba1dc19eecba4e447dd7049ae580c920a7bdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242145"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="9b0b8-103">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b0b8-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9b0b8-104">Os usuários em sua organização podem enviar comentários sobre as equipes para a Microsoft nos informar como estamos fazendo, diretamente dentro dos clientes da área de trabalho e da Web do teams.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="9b0b8-105">Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="9b0b8-106">**O recurso fornecer comentários**</span><span class="sxs-lookup"><span data-stu-id="9b0b8-106">**The Give feedback feature**</span></span>

<span data-ttu-id="9b0b8-107">Os usuários podem enviar comentários e sugestões sobre equipes para nós indo para **ajudar** > a enviar**comentários** sobre o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="9b0b8-108">Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".</span><span class="sxs-lookup"><span data-stu-id="9b0b8-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="9b0b8-110">**Formulários**</span><span class="sxs-lookup"><span data-stu-id="9b0b8-110">**Surveys**</span></span>

<span data-ttu-id="9b0b8-111">Os usuários também podem classificar sua experiência com o Microsoft Teams e nos enviar detalhes sobre a classificação que elas oferecem.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="9b0b8-112">Esta pesquisa instantânea é exibida para os usuários de tempos em tempos no Teams.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="9b0b8-113">Quando um usuário clica em **fornecer comentários** na notificação, a pesquisa é exibida para que elas sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de tela da notificação de pesquisa e do formulário no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="9b0b8-115">Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9b0b8-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="9b0b8-116">Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de **comentários** e se eles recebem a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="9b0b8-117">Por padrão, todos os usuários de sua organização recebem automaticamente a atribuição da política global (padrão da organização), e o recurso **fornecer comentários** e a pesquisa são habilitados na política.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="9b0b8-118">A exceção é o Teams for Education, em que os recursos são habilitados para professores e desabilitado para estudantes.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="9b0b8-119">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="9b0b8-120">Se for atribuída uma política personalizada a um usuário, essa política se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="9b0b8-121">Se um usuário não estiver atribuído a uma política personalizada, a política global se aplicará ao usuário.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="9b0b8-122">Depois de editar a política global ou atribuir uma política, pode levar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-122">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="9b0b8-123">Digamos, por exemplo, permitir que todos os usuários em sua organização enviem comentários por meio de **comentários** e recebam pesquisas, exceto para novas contratações no treinamento.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="9b0b8-124">Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-lo a novas contratações.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="9b0b8-125">Todos os outros usuários da sua organização obtêm a política global com os recursos ativados.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="9b0b8-126">Use o cmdlet **New-CsTeamsFeedbackPolicy** para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="9b0b8-127">Para desativar e ativar os recursos, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9b0b8-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="9b0b8-128">**Enviar comentários**: defina o \*\*\*\* parâmetro useriniciad como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="9b0b8-129">Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="9b0b8-130">**Pesquisas**: defina o parâmetro **receiveSurveysMode** como **Enabled** para permitir que os usuários atribuídos à política recebam a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="9b0b8-131">Para que os usuários recebam a pesquisa e permitam que eles se recusem, defina o parâmetro como **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="9b0b8-132">No Teams, os usuários podem ir até a**privacidade** **das configurações** > e escolher se desejam participar de pesquisas.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="9b0b8-133">Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos a política não receberão a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="9b0b8-134">Criar uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="9b0b8-134">Create a custom feedback policy</span></span>

<span data-ttu-id="9b0b8-135">Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários por meio de **comentários** e a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="9b0b8-136">Atribuir uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="9b0b8-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="9b0b8-137">Atribuir uma política de comentários personalizada a um usuário</span><span class="sxs-lookup"><span data-stu-id="9b0b8-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="9b0b8-138">Neste exemplo, atribuímos uma política personalizada chamada nova política de feedback de contratação a um usuário chamado Usuário1.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="9b0b8-139">Atribuir uma política de comentários personalizada aos usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="9b0b8-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="9b0b8-140">Você pode querer atribuir uma política de comentários personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-140">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="9b0b8-141">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="9b0b8-142">Neste exemplo, atribuímos uma política de comentários personalizada chamada nova política de feedback de contratação a todos os usuários no novo grupo contoso contratações.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="9b0b8-143">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-143">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="9b0b8-144">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-144">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9b0b8-145">Atribua todos os usuários do grupo a uma política de comentários específica.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="9b0b8-146">Neste exemplo, a nova política de feedback para contratação.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-146">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9b0b8-147">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="9b0b8-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b0b8-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9b0b8-148">Related topics</span></span>

- [<span data-ttu-id="9b0b8-149">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9b0b8-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)