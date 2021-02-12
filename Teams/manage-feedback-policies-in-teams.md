---
title: Gerenciar políticas de comentários no Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como usar políticas de comentários para controlar se os usuários do Teams em sua organização podem enviar comentários sobre o Teams para a Microsoft.
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804691"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="55ba0-103">Gerenciar políticas de comentários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55ba0-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="55ba0-104">Os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft para nos dizer como estamos fazendo, diretamente na área de trabalho do Teams e em clientes Web.</span><span class="sxs-lookup"><span data-stu-id="55ba0-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="55ba0-105">Estamos melhorando continuamente a experiência do Teams e usamos esse comentário para melhorar o Teams.</span><span class="sxs-lookup"><span data-stu-id="55ba0-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="55ba0-106">As políticas de comentários não estão disponíveis nas implantações GCC, GCC High ou DOD.</span><span class="sxs-lookup"><span data-stu-id="55ba0-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="55ba0-107">**O recurso Dar comentários**</span><span class="sxs-lookup"><span data-stu-id="55ba0-107">**The Give feedback feature**</span></span>

<span data-ttu-id="55ba0-108">Os usuários podem enviar comentários e sugestões sobre o Teams para nós, indo para **Ajudar**  >  **a enviar comentários** no Teams.</span><span class="sxs-lookup"><span data-stu-id="55ba0-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="55ba0-109">Os dados enviados por meio de Enviar **comentários** são considerados como "Dados de Suporte" sob seu contrato do Microsoft 365 ou do Office 365, incluindo informações que, de outra forma, seriam consideradas "Dados do Cliente" ou "Dados Pessoais".</span><span class="sxs-lookup"><span data-stu-id="55ba0-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Captura de tela da opção Dar comentários no Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="55ba0-111">**Pesquisas**</span><span class="sxs-lookup"><span data-stu-id="55ba0-111">**Surveys**</span></span>

<span data-ttu-id="55ba0-112">Os usuários também podem taxar sua experiência com o Teams e nos enviar detalhes sobre a classificação que eles dão.</span><span class="sxs-lookup"><span data-stu-id="55ba0-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="55ba0-113">Esta pesquisa pop-up é exibida para os usuários de tempos em tempos no Teams.</span><span class="sxs-lookup"><span data-stu-id="55ba0-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="55ba0-114">Quando um usuário clica em **Fornecer comentários** na notificação, a pesquisa é exibida para que ele seja concluído.</span><span class="sxs-lookup"><span data-stu-id="55ba0-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Captura de tela da notificação e formulário da pesquisa no Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="55ba0-116">Definir se os usuários podem enviar comentários sobre o Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="55ba0-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="55ba0-117">Como administrador, você pode controlar se os usuários em sua organização podem enviar comentários sobre o Teams para a Microsoft por meio de Enviar **comentários** e se eles recebem a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="55ba0-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="55ba0-118">Por padrão, todos os usuários em sua organização são atribuídos automaticamente à política global (padrão de toda a organização), e o recurso Enviar **comentários** e a pesquisa são habilitados na política.</span><span class="sxs-lookup"><span data-stu-id="55ba0-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="55ba0-119">A exceção é o Teams for Education, onde os recursos são habilitados para professores e desabilitados para alunos.</span><span class="sxs-lookup"><span data-stu-id="55ba0-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="55ba0-120">Você pode editar a política global ou criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="55ba0-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="55ba0-121">Depois de editar a política global ou atribuir uma política personalizada, pode levar algumas horas para que as alterações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="55ba0-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="55ba0-122">Por exemplo, você deseja permitir que todos os usuários em sua organização enviem comentários por meio de Enviar **comentários** e receber pesquisas, exceto para novos contratados no treinamento.</span><span class="sxs-lookup"><span data-stu-id="55ba0-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="55ba0-123">Nesse cenário, você cria uma política personalizada para desativar os dois recursos e atribuí-la a novas contratações.</span><span class="sxs-lookup"><span data-stu-id="55ba0-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="55ba0-124">Todos os outros usuários em sua organização ficam com a política global com os recursos ativos.</span><span class="sxs-lookup"><span data-stu-id="55ba0-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="55ba0-125">Você gerencia políticas de comentários usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55ba0-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="55ba0-126">Use o cmdlet **New-CsTeamsFeedbackPolicy,** que pode ser encontrado *aqui, [](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* para criar uma política personalizada e o cmdlet **Grant-CsTeamsFeedbackPolicy** para atribuí-lo a um ou mais usuários ou grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="55ba0-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="55ba0-127">Para desativar e ativar os recursos, de definir os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="55ba0-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="55ba0-128">**Fazer comentários:** De definir o parâmetro  **userInitiatedMode** para habilitado para permitir que os usuários que têm a política sejam atribuídos a fazer comentários.</span><span class="sxs-lookup"><span data-stu-id="55ba0-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="55ba0-129">Definir o parâmetro para **desabilitar** desativa o recurso, e os usuários que têm a política atribuída não têm a opção de fazer comentários.</span><span class="sxs-lookup"><span data-stu-id="55ba0-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="55ba0-130">**Pesquisas:** De definir o **parâmetro receiveSurveysMode** para habilitado para permitir que os usuários que receberam a política recebam a pesquisa. </span><span class="sxs-lookup"><span data-stu-id="55ba0-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="55ba0-131">Para que os usuários recebam a pesquisa e permitam que eles optem por não fazer isso, de definir o parâmetro para **habilitar oUserOverride.**</span><span class="sxs-lookup"><span data-stu-id="55ba0-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="55ba0-132">No Teams, os usuários podem ir para **Configurações de** Privacidade e escolher se  >   querem participar de pesquisas.</span><span class="sxs-lookup"><span data-stu-id="55ba0-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="55ba0-133">Definir o parâmetro para **desabilitar** desativa o recurso, e os usuários que receberam a política não receberão a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="55ba0-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="55ba0-134">Criar uma política de comentários personalizada</span><span class="sxs-lookup"><span data-stu-id="55ba0-134">Create a custom feedback policy</span></span>

<span data-ttu-id="55ba0-135">Neste exemplo, criamos uma política de comentários chamada Política de Comentários de Nova Contratação e desligamos a capacidade de fazer comentários por meio de Dar **comentários** e da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="55ba0-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="55ba0-136">Atribuir uma política de comentários personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="55ba0-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="55ba0-137">Neste exemplo, atribuímos uma política personalizada chamada Política de Comentários de Nova Contratação a um usuário chamado usuário1.</span><span class="sxs-lookup"><span data-stu-id="55ba0-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="55ba0-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="55ba0-138">Related topics</span></span>

- [<span data-ttu-id="55ba0-139">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="55ba0-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="55ba0-140">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="55ba0-140">Assign policies to your users in Teams</span></span>](assign-policies.md)