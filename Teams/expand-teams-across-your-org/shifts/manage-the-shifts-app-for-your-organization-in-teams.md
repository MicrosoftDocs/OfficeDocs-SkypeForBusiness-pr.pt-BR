---
title: Gerenciar o aplicativo turnos para a sua organização
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como configurar e gerenciar o aplicativo turnos no Microsoft Teams para trabalhadores de primeira mão em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 745644c7a6cf2207412faacd78e7b5a26d7b754d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349655"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="88d81-103">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="88d81-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d81-104">A partir de 30 de junho de 2020, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="88d81-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="88d81-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="88d81-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="88d81-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="88d81-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="88d81-107">O StaffHub deixará de funcionar para todos os usuários em 30 de junho de 2020.</span><span class="sxs-lookup"><span data-stu-id="88d81-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="88d81-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="88d81-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="88d81-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="88d81-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="88d81-110">Visão geral de turnos</span><span class="sxs-lookup"><span data-stu-id="88d81-110">Overview of Shifts</span></span>

<span data-ttu-id="88d81-111">O aplicativo turnos no Microsoft Teams mantém os trabalhadores de primeiro lugar conectados e em sincronização. Ele foi criado para o seu celular primeiro para gerenciamento e comunicação de tempo rápido e eficiente para equipes.</span><span class="sxs-lookup"><span data-stu-id="88d81-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="88d81-112">Os turnos permitem que os funcionários de primeira mão e seus gerentes usem seus dispositivos móveis para gerenciar os cronogramas e manter contato.</span><span class="sxs-lookup"><span data-stu-id="88d81-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="88d81-113">Gerentes criam, atualizam e gerenciam os cronogramas de turnos do teams.</span><span class="sxs-lookup"><span data-stu-id="88d81-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="88d81-114">Eles podem enviar mensagens para uma pessoa ("há um derramamento na base") ou toda a equipe ("a GM regional é chegando em 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="88d81-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="88d81-115">Eles também podem enviar documentos de política, boletins de notícias e vídeos.</span><span class="sxs-lookup"><span data-stu-id="88d81-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="88d81-116">Os funcionários visualizam seus próximos turnos, podem ver quem mais está agendado para o dia, solicitar a troca ou oferecer um turno e solicitar folga.</span><span class="sxs-lookup"><span data-stu-id="88d81-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="88d81-117">É importante saber que os turnos atualmente não dão suporte a usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="88d81-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="88d81-118">Isso significa que os convidados de uma equipe não podem ser adicionados ou usar as agendas de turnos quando o acesso de convidado está ativado no Teams.</span><span class="sxs-lookup"><span data-stu-id="88d81-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="88d81-119">Disponibilidade de turnos</span><span class="sxs-lookup"><span data-stu-id="88d81-119">Availability of Shifts</span></span>

<span data-ttu-id="88d81-120">Os turnos estão disponíveis em todos os SKUs corporativos nos quais o Microsoft Teams está disponível.</span><span class="sxs-lookup"><span data-stu-id="88d81-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="88d81-121">Local dos dados de turnos</span><span class="sxs-lookup"><span data-stu-id="88d81-121">Location of Shifts data</span></span>

<span data-ttu-id="88d81-122">Os dados de turnos atualmente estão armazenados no Azure em data centers na América do Norte, Europa Ocidental e Pacífico Asiático.</span><span class="sxs-lookup"><span data-stu-id="88d81-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="88d81-123">Para obter mais informações sobre onde os dados são armazenados, confira [onde estão os meus dados](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="88d81-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="88d81-124">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="88d81-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="88d81-125">Habilitar ou desabilitar turnos em sua organização</span><span class="sxs-lookup"><span data-stu-id="88d81-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="88d81-126">Os turnos são habilitados por padrão para todos os usuários do teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="88d81-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="88d81-127">Você pode desativar ou ativar o aplicativo no nível da organização na página [gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="88d81-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="88d81-128">Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="88d81-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="88d81-129">Na lista de aplicativos, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="88d81-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="88d81-130">Para desativar os turnos da sua organização, procure o aplicativo turnos, selecione-o e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="88d81-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="88d81-131">Para ativar turnos para sua organização, procure o aplicativo turnos, selecione-o e clique em **permitir**.</span><span class="sxs-lookup"><span data-stu-id="88d81-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="88d81-132">Habilitar ou desabilitar turnos para usuários específicos em sua organização</span><span class="sxs-lookup"><span data-stu-id="88d81-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="88d81-133">Para permitir ou bloquear usuários específicos em sua organização usando turnos, certifique-se de que os turnos estejam ativados para sua organização na página [gerenciar aplicativos](../../manage-apps.md) e crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="88d81-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="88d81-134">Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="88d81-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="88d81-135">Usar a política de configuração do aplicativo FirstlineWorker para fixar mudanças em equipes</span><span class="sxs-lookup"><span data-stu-id="88d81-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="88d81-136">As políticas de configuração do aplicativo permitem que você personalize o Microsoft Teams para realçar os aplicativos que são mais importantes para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="88d81-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="88d81-137">Os aplicativos definidos em uma política são fixados na barra do aplicativo na &mdash; barra do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, &mdash; nos quais os usuários podem acessá-los de forma rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="88d81-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="88d81-138">O Teams inclui uma política interna de configuração de aplicativos FirstlineWorker que você pode atribuir a trabalhos de primeiros a sua organização.</span><span class="sxs-lookup"><span data-stu-id="88d81-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="88d81-139">Por padrão, a política inclui os aplicativos atividade, turnos, chat e chamadas.</span><span class="sxs-lookup"><span data-stu-id="88d81-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="88d81-140">Para exibir a política FirstlineWorker, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para políticas de configuração do aplicativo **Teams app**  >  **App setup policies**.</span><span class="sxs-lookup"><span data-stu-id="88d81-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="88d81-141">![Captura de tela da política de configuração do aplicativo FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FirstlineWorker no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="88d81-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="88d81-142">Atribuir a política FirstlineWorker a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="88d81-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="88d81-143">Na barra de navegação à esquerda do centro de administração do Microsoft Teams, vá para **Usuários** e clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="88d81-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="88d81-144">Ao lado de **Políticas atribuídas**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="88d81-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="88d81-145">Em **política de configuração do aplicativo Teams**, selecione **FirstlineWorker**e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="88d81-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="88d81-146">Atribuir a política de configuração do aplicativo FirstlineWorker a membros do grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="88d81-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="88d81-147">Você pode atribuir a política de configuração do aplicativo FirstlineWorker a membros do grupo, como um grupo de segurança, conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="88d81-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="88d81-148">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="88d81-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="88d81-149">Neste exemplo, atribuímos a política de configuração do aplicativo FirstlineWorker a todos os membros do grupo de equipe do contoso First.</span><span class="sxs-lookup"><span data-stu-id="88d81-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="88d81-150">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="88d81-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="88d81-151">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="88d81-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="88d81-152">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="88d81-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="88d81-153">Atribua a política de configuração do aplicativo FirstlineWorker a todos os membros de usuário do grupo.</span><span class="sxs-lookup"><span data-stu-id="88d81-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="88d81-154">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="88d81-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="88d81-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="88d81-155">Related topics</span></span>
- [<span data-ttu-id="88d81-156">Ajuda de turnos para trabalhadores de primeira mão</span><span class="sxs-lookup"><span data-stu-id="88d81-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
