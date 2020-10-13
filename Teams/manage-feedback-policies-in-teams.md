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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar políticas de comentários para controlar se os usuários de equipes em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: 0bece4515825a0d7ddf7e547f1607fbd6cf205cc
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433034"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="eb8e2-103">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb8e2-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="eb8e2-104">Os usuários em sua organização podem enviar comentários sobre as equipes para a Microsoft nos informar como estamos fazendo, diretamente dentro dos clientes da área de trabalho e da Web do teams.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="eb8e2-105">Estamos melhorando continuamente a experiência do Teams e usamos esses comentários para melhorar a equipe.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="eb8e2-106">Políticas de feedback não estão disponíveis em implantações GCC, GCC High ou DOD.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="eb8e2-107">**O recurso fornecer comentários**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-107">**The Give feedback feature**</span></span>

<span data-ttu-id="eb8e2-108">Os usuários podem enviar comentários e sugestões sobre equipes para nós indo para **ajudar**a enviar comentários sobre o Microsoft  >  **Give feedback** Teams.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="eb8e2-109">Os dados enviados por meio de **comentários** são considerados como "dados de suporte" em seu contrato do Microsoft 365 ou do Office 365, incluindo informações que, de outra forma, seriam consideradas "dados do cliente" ou "dados pessoais".</span><span class="sxs-lookup"><span data-stu-id="eb8e2-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de tela da opção fornecer comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="eb8e2-111">**Formulários**</span><span class="sxs-lookup"><span data-stu-id="eb8e2-111">**Surveys**</span></span>

<span data-ttu-id="eb8e2-112">Os usuários também podem classificar sua experiência com o Microsoft Teams e nos enviar detalhes sobre a classificação que elas oferecem.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="eb8e2-113">Esta pesquisa instantânea é exibida para os usuários de tempos em tempos no Teams.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="eb8e2-114">Quando um usuário clica em **fornecer comentários** na notificação, a pesquisa é exibida para que elas sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de tela da notificação de pesquisa e do formulário no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="eb8e2-116">Definir se os usuários podem enviar comentários sobre o Microsoft Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="eb8e2-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="eb8e2-117">Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de **comentários** e se eles recebem a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="eb8e2-118">Por padrão, todos os usuários de sua organização recebem automaticamente a atribuição da política global (padrão da organização), e o recurso **fornecer comentários** e a pesquisa são habilitados na política.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="eb8e2-119">A exceção é o Teams for Education, em que os recursos são habilitados para professores e desabilitado para estudantes.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="eb8e2-120">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="eb8e2-121">Depois de editar a política global ou atribuir uma política personalizada, pode demorar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="eb8e2-122">Digamos, por exemplo, permitir que todos os usuários em sua organização enviem comentários por meio de **comentários** e recebam pesquisas, exceto para novas contratações no treinamento.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="eb8e2-123">Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-lo a novas contratações.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="eb8e2-124">Todos os outros usuários da sua organização obtêm a política global com os recursos ativados.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="eb8e2-125">Você gerencia políticas de comentários usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="eb8e2-126">Use o cmdlet **New-CsTeamsFeedbackPolicy** , *que pode ser [encontrado aqui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="eb8e2-127">Para desativar e ativar os recursos, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="eb8e2-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="eb8e2-128">**Enviar comentários**: defina o parâmetro **useriniciad** como **Enabled** para permitir que os usuários atribuídos à política forneçam comentários.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="eb8e2-129">Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos à política não têm a opção de enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="eb8e2-130">**Pesquisas**: defina o parâmetro **receiveSurveysMode** como **Enabled** para permitir que os usuários atribuídos à política recebam a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="eb8e2-131">Para que os usuários recebam a pesquisa e permitam que eles se recusem, defina o parâmetro como **enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="eb8e2-132">No Teams, os usuários podem ir até a privacidade **das configurações**  >  **Privacy** e escolher se desejam participar de pesquisas.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="eb8e2-133">Definir o parâmetro como **desativado** desativa o recurso e os usuários atribuídos a política não receberão a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="eb8e2-134">Criar uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="eb8e2-134">Create a custom feedback policy</span></span>

<span data-ttu-id="eb8e2-135">Neste exemplo, criamos uma política de comentários chamada nova política de feedback de contratar e desativamos a capacidade de enviar comentários por meio de **comentários** e a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="eb8e2-136">Atribuir uma política de comentários personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="eb8e2-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="eb8e2-137">Neste exemplo, atribuímos uma política personalizada chamada nova política de feedback de contratação a um usuário chamado Usuário1.</span><span class="sxs-lookup"><span data-stu-id="eb8e2-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="eb8e2-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="eb8e2-138">Related topics</span></span>

- [<span data-ttu-id="eb8e2-139">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="eb8e2-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="eb8e2-140">Atribuir políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="eb8e2-140">Assign policies to your users in Teams</span></span>](assign-policies.md)