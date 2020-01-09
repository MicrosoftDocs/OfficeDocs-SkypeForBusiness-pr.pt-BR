---
title: Gerencie o aplicativo Turnos para sua organização no Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como configurar e gerenciar o aplicativo turnos no Microsoft Teams para trabalhadores de primeira mão em sua organização.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ed7f4bc282686c31f2f9c2239fbe6326e5151f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992538"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="f610e-103">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f610e-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f610e-104">A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="f610e-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="f610e-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f610e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f610e-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="f610e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f610e-107">O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019.</span><span class="sxs-lookup"><span data-stu-id="f610e-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="f610e-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="f610e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="f610e-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="f610e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="f610e-110">Visão geral de turnos</span><span class="sxs-lookup"><span data-stu-id="f610e-110">Overview of Shifts</span></span>
<span data-ttu-id="f610e-111">O aplicativo turnos no Microsoft Teams mantém os trabalhadores de primeiro lugar conectados e em sincronização. Ele foi criado para o seu celular primeiro para gerenciamento e comunicação de tempo rápido e eficiente para equipes.</span><span class="sxs-lookup"><span data-stu-id="f610e-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="f610e-112">Os turnos permitem que os funcionários de primeira mão e seus gerentes usem seus dispositivos móveis para gerenciar os cronogramas e manter contato.</span><span class="sxs-lookup"><span data-stu-id="f610e-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="f610e-113">Gerentes criam, atualizam e gerenciam os cronogramas de turnos do teams.</span><span class="sxs-lookup"><span data-stu-id="f610e-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="f610e-114">Eles podem enviar mensagens para uma pessoa ("há um derramamento na base") ou toda a equipe ("a GM regional é chegando em 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="f610e-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="f610e-115">Eles também podem enviar documentos de política, boletins de notícias e vídeos.</span><span class="sxs-lookup"><span data-stu-id="f610e-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="f610e-116">Os funcionários visualizam seus próximos turnos, podem ver quem mais está agendado para o dia, solicitar a troca ou oferecer um turno e solicitar folga.</span><span class="sxs-lookup"><span data-stu-id="f610e-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="f610e-117">É importante saber que os turnos atualmente não dão suporte a usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="f610e-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="f610e-118">Isso significa que os convidados de uma equipe não podem ser adicionados ou usar as agendas de turnos quando o acesso de convidado está ativado no Teams.</span><span class="sxs-lookup"><span data-stu-id="f610e-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="f610e-119">Disponibilidade de turnos</span><span class="sxs-lookup"><span data-stu-id="f610e-119">Availability of Shifts</span></span>

<span data-ttu-id="f610e-120">Os turnos estão disponíveis em todos os SKUs corporativos nos quais o Microsoft Teams está disponível.</span><span class="sxs-lookup"><span data-stu-id="f610e-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="f610e-121">Local dos dados de turnos</span><span class="sxs-lookup"><span data-stu-id="f610e-121">Location of Shifts data</span></span>

<span data-ttu-id="f610e-122">Os dados de turnos atualmente estão armazenados no Azure em data centers na América do Norte, Europa Ocidental e Pacífico Asiático.</span><span class="sxs-lookup"><span data-stu-id="f610e-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="f610e-123">Para obter mais informações sobre onde os dados são armazenados, confira [onde estão os meus dados](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="f610e-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="f610e-124">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="f610e-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="f610e-125">Habilitar ou desabilitar turnos em sua organização</span><span class="sxs-lookup"><span data-stu-id="f610e-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="f610e-126">Os turnos são habilitados por padrão para todos os usuários do teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="f610e-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="f610e-127">Você pode desativar ou ativar o aplicativo em toda a organização usando as configurações de toda a organização nas políticas de permissão do aplicativo no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f610e-127">You can turn off or turn on the app org-wide by using org-wide settings in app permission policies in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f610e-128">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para > **políticas de permissão** de **aplicativos do teams**.</span><span class="sxs-lookup"><span data-stu-id="f610e-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies** .</span></span>
2. <span data-ttu-id="f610e-129">Clique em **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="f610e-129">Click **Org-wide settings**.</span></span>
3. <span data-ttu-id="f610e-130">No painel **configurações de toda a organização** , em **aplicativos bloqueados**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f610e-130">In the **Org-wide settings** panel, under **Blocked apps**, do one of the following:</span></span>

    - <span data-ttu-id="f610e-131">Para desativar os turnos da sua organização, procure o aplicativo turnos e clique em **Adicionar** para adicioná-lo à lista de aplicativos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f610e-131">To turn off Shifts for your organization, search for the Shifts app, and click **Add** to add it to the blocked apps list.</span></span>
    - <span data-ttu-id="f610e-132">Para ativar turnos para sua organização, remova o aplicativo turnos da lista de aplicativos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f610e-132">To turn on Shifts for your organization, remove the Shifts app from the blocked apps list.</span></span>
4. <span data-ttu-id="f610e-133">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f610e-133">Click **Save**.</span></span> 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="f610e-134">Habilitar ou desabilitar turnos para usuários específicos em sua organização</span><span class="sxs-lookup"><span data-stu-id="f610e-134">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="f610e-135">Para permitir ou bloquear usuários específicos em sua organização usando turnos, certifique-se de que o recurso turnos esteja ativado para sua organização em configurações de toda a organização e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="f610e-135">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization in org-wide settings, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="f610e-136">Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f610e-136">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="f610e-137">Usar a política de configuração do aplicativo FirstlineWorker para fixar mudanças em equipes</span><span class="sxs-lookup"><span data-stu-id="f610e-137">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="f610e-138">As políticas de configuração do aplicativo permitem que você personalize o Microsoft Teams para realçar os aplicativos que são mais importantes para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f610e-138">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="f610e-139">Os aplicativos definidos em uma política são fixados na barra&mdash;do aplicativo na barra do cliente da área de trabalho do Teams e na parte inferior dos clientes&mdash;móveis do Teams, nos quais os usuários podem acessá-los de forma rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="f610e-139">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="f610e-140">O Teams inclui uma política interna de configuração de aplicativos FirstlineWorker que você pode atribuir a trabalhos de primeiros a sua organização.</span><span class="sxs-lookup"><span data-stu-id="f610e-140">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="f610e-141">Por padrão, a política inclui os aplicativos atividade, turnos, chat e chamadas.</span><span class="sxs-lookup"><span data-stu-id="f610e-141">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="f610e-142">Para exibir a política FirstlineWorker, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para**políticas de configuração do aplicativo** **Teams app** > .</span><span class="sxs-lookup"><span data-stu-id="f610e-142">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="f610e-143">![Captura de tela da política de configuração do aplicativo FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FirstlineWorker no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="f610e-143">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="f610e-144">Atribuir a política FirstlineWorker a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="f610e-144">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="f610e-145">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="f610e-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f610e-146">Ao lado de **políticas atribuídas**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f610e-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="f610e-147">Em **política de configuração do aplicativo Teams**, selecione **FirstlineWorker**e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f610e-147">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="f610e-148">Atribuir a política de configuração do aplicativo FirstlineWorker a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="f610e-148">Assign the FirstlineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="f610e-149">Você pode atribuir a política de configuração do aplicativo FirstlineWorker a usuários em um grupo, como um grupo de segurança, conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f610e-149">You can assign the FirstlineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="f610e-150">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f610e-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="f610e-151">Neste exemplo, atribuímos a política de configuração do aplicativo FirstlineWorker a todos os usuários no grupo de equipe do primeiro grupo da contoso.</span><span class="sxs-lookup"><span data-stu-id="f610e-151">In this example, we assign the FirstlineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="f610e-152">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="f610e-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="f610e-153">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="f610e-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="f610e-154">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="f610e-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="f610e-155">Atribua todos os usuários do grupo à política de configuração do aplicativo FirstlineWorker.</span><span class="sxs-lookup"><span data-stu-id="f610e-155">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="f610e-156">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="f610e-156">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f610e-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f610e-157">Related topics</span></span>
- [<span data-ttu-id="f610e-158">Ajuda de turnos para trabalhadores de primeira mão</span><span class="sxs-lookup"><span data-stu-id="f610e-158">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
