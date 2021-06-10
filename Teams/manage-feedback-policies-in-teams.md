---
title: Gerenciar políticas de comentários em Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: Saiba como usar políticas de comentários para controlar se Teams usuários em sua organização podem enviar comentários sobre Teams para a Microsoft.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656717"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="57c58-103">Gerenciar políticas de comentários em Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57c58-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="57c58-104">Os usuários em sua organização podem enviar comentários sobre Teams para a Microsoft para nos dizer como estamos fazendo, diretamente de dentro da área de trabalho Teams clientes Web e da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="57c58-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="57c58-105">Estamos melhorando continuamente a experiência Teams e usamos esse feedback para melhorar Teams.</span><span class="sxs-lookup"><span data-stu-id="57c58-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="57c58-106">As políticas de feedback não estão disponíveis em implantações GCC, GCC High ou DOD.</span><span class="sxs-lookup"><span data-stu-id="57c58-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="57c58-107">**O recurso Dar comentários**</span><span class="sxs-lookup"><span data-stu-id="57c58-107">**The Give feedback feature**</span></span>

<span data-ttu-id="57c58-108">Os usuários podem enviar comentários e sugestões sobre Teams para nós, indo para **Ajudar** a dar  >  **comentários** em Teams.</span><span class="sxs-lookup"><span data-stu-id="57c58-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="57c58-109">Os dados  enviados por meio de Feedback são considerados como "Dados de Suporte" em seu contrato Microsoft 365 ou Office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".</span><span class="sxs-lookup"><span data-stu-id="57c58-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de tela da opção Dar comentários em Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="57c58-111">**Pesquisas**</span><span class="sxs-lookup"><span data-stu-id="57c58-111">**Surveys**</span></span>

<span data-ttu-id="57c58-112">Os usuários também podem taxar sua experiência com Teams e nos enviar detalhes sobre a classificação que eles dão.</span><span class="sxs-lookup"><span data-stu-id="57c58-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="57c58-113">Essa pesquisa pop-up é exibida para os usuários de tempos em tempos Teams.</span><span class="sxs-lookup"><span data-stu-id="57c58-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="57c58-114">Quando um usuário seleciona **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.</span><span class="sxs-lookup"><span data-stu-id="57c58-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![a notificação e o formulário de pesquisa Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="57c58-116">Definir se os usuários podem enviar comentários sobre Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="57c58-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="57c58-117">Como administrador, você pode controlar se os usuários em sua organização  podem enviar comentários sobre o Teams para a Microsoft por meio de Comentários e se eles receberão a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="57c58-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="57c58-118">Por padrão, todos os usuários em sua organização são atribuídos automaticamente à política global (padrão em toda a organização), e o recurso Dar **comentários** e a pesquisa estão habilitados na política.</span><span class="sxs-lookup"><span data-stu-id="57c58-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="57c58-119">A exceção é Teams educação, onde os recursos são habilitados para professores e desabilitados para alunos.</span><span class="sxs-lookup"><span data-stu-id="57c58-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="57c58-120">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="57c58-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="57c58-121">Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="57c58-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="57c58-122">Digamos, por exemplo, que você deseja permitir que  todos os usuários em sua organização enviem comentários por meio de Comentários e recebam pesquisas, exceto para novos contratados em treinamento.</span><span class="sxs-lookup"><span data-stu-id="57c58-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="57c58-123">Nesse cenário, você cria uma política personalizada para desativar ambos os recursos e atribuí-la a novos contratados.</span><span class="sxs-lookup"><span data-stu-id="57c58-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="57c58-124">Todos os outros usuários em sua organização obterão a política global com os recursos ativos.</span><span class="sxs-lookup"><span data-stu-id="57c58-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="57c58-125">Você gerencia políticas de comentários usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57c58-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="57c58-126">Use o cmdlet **New-CsTeamsFeedbackPolicy,** que pode ser encontrado aqui *, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="57c58-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="57c58-127">Use o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="57c58-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="57c58-128">Use **Set-CsTeamsFeedbackPolicy** para definir sinalizadores específicos.</span><span class="sxs-lookup"><span data-stu-id="57c58-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="57c58-129">Para desativar e ativar os recursos, de definir os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="57c58-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="57c58-130">**Comentários**: de definir o parâmetro  **userInitiatedMode** como habilitado para permitir que os usuários atribuídos à política deem feedback.</span><span class="sxs-lookup"><span data-stu-id="57c58-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="57c58-131">A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários que são atribuídos à política não têm a opção de dar comentários.</span><span class="sxs-lookup"><span data-stu-id="57c58-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="57c58-132">Pesquisas : de definir o parâmetro  **receiveSurveysMode** como habilitado para permitir que os usuários **atribuídos** à política recebam a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="57c58-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="57c58-133">Para que os usuários recebam a pesquisa e permitam que eles optem por não fazer isso, de definir o parâmetro **como enabledUserOverride**.</span><span class="sxs-lookup"><span data-stu-id="57c58-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="57c58-134">Em Teams, os usuários podem, em seguida, ir **Configurações** Privacidade e escolher se eles  >   querem participar de pesquisas.</span><span class="sxs-lookup"><span data-stu-id="57c58-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="57c58-135">A configuração do parâmetro como **desabilitado** desativa o recurso e os usuários atribuídos à política não receberão a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="57c58-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="57c58-136">**Email**: Use o **sinalizador AllowEmailCollection** para adicionar um campo de email.</span><span class="sxs-lookup"><span data-stu-id="57c58-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="57c58-137">Criar uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="57c58-137">Create a custom feedback policy</span></span>

<span data-ttu-id="57c58-138">Neste exemplo, criamos uma política de comentários chamada New Hire Feedback Policy e desativaremos a capacidade de dar comentários por meio de Comentários **e** da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="57c58-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="57c58-139">Atribuir uma política de feedback personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="57c58-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="57c58-140">Neste exemplo, atribuímos uma política personalizada chamada New Hire Feedback Policy a um usuário chamado user1.</span><span class="sxs-lookup"><span data-stu-id="57c58-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="57c58-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="57c58-141">Related topics</span></span>

- [<span data-ttu-id="57c58-142">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="57c58-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="57c58-143">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="57c58-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
