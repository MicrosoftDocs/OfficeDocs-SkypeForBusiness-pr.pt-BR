---
title: Gerenciar o aplicativo turnos para a sua organização
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Saiba como configurar e gerenciar o aplicativo turnos no Microsoft Teams para trabalhadores do Frontline em sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909085"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="d8a96-103">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8a96-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8a96-104">A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado.</span><span class="sxs-lookup"><span data-stu-id="d8a96-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="d8a96-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8a96-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d8a96-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="d8a96-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d8a96-107">StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020.</span><span class="sxs-lookup"><span data-stu-id="d8a96-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="d8a96-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="d8a96-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="d8a96-109">Para saber mais, confira [o Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="d8a96-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="d8a96-110">Visão geral de turnos</span><span class="sxs-lookup"><span data-stu-id="d8a96-110">Overview of Shifts</span></span>

<span data-ttu-id="d8a96-111">O aplicativo turnos no Microsoft Teams mantém os funcionários do Frontline conectados e em sincronização. Ele foi criado para o seu celular primeiro para gerenciamento e comunicação de tempo rápido e eficiente para equipes.</span><span class="sxs-lookup"><span data-stu-id="d8a96-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="d8a96-112">Turnos permite que os funcionários do Frontline e seus gerentes usem seus dispositivos móveis para gerenciar os cronogramas e manter contato.</span><span class="sxs-lookup"><span data-stu-id="d8a96-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="d8a96-113">Gerentes criam, atualizam e gerenciam os cronogramas de turnos do teams.</span><span class="sxs-lookup"><span data-stu-id="d8a96-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="d8a96-114">Eles podem enviar mensagens para uma pessoa ("há um derramamento na base") ou toda a equipe ("a GM regional é chegando em 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="d8a96-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="d8a96-115">Eles também podem enviar documentos de política, boletins de notícias e vídeos.</span><span class="sxs-lookup"><span data-stu-id="d8a96-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="d8a96-116">Os funcionários visualizam seus próximos turnos, ver quem mais está agendado para o dia, solicitar a troca ou oferecer um turno e solicitar folga.</span><span class="sxs-lookup"><span data-stu-id="d8a96-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="d8a96-117">É importante saber que os turnos atualmente não dão suporte a usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="d8a96-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="d8a96-118">Isso significa que os convidados de uma equipe não podem ser adicionados ou usar as agendas de turnos quando o acesso de convidado está ativado no Teams.</span><span class="sxs-lookup"><span data-stu-id="d8a96-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="d8a96-119">Para obter detalhes sobre os recursos de turnos em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="d8a96-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="d8a96-120">Disponibilidade de turnos</span><span class="sxs-lookup"><span data-stu-id="d8a96-120">Availability of Shifts</span></span>

<span data-ttu-id="d8a96-121">Os turnos estão disponíveis em todos os SKUs corporativos nos quais o Microsoft Teams está disponível.</span><span class="sxs-lookup"><span data-stu-id="d8a96-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="d8a96-122">Local dos dados de turnos</span><span class="sxs-lookup"><span data-stu-id="d8a96-122">Location of Shifts data</span></span>

<span data-ttu-id="d8a96-123">Os dados de turnos atualmente estão armazenados no Azure em data centers na América do Norte, Europa Ocidental e Pacífico Asiático.</span><span class="sxs-lookup"><span data-stu-id="d8a96-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="d8a96-124">Para obter mais informações sobre onde os dados são armazenados, confira [onde estão os meus dados](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="d8a96-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="d8a96-125">Configurar turnos</span><span class="sxs-lookup"><span data-stu-id="d8a96-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="d8a96-126">Habilitar ou desabilitar turnos em sua organização</span><span class="sxs-lookup"><span data-stu-id="d8a96-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="d8a96-127">Os turnos são habilitados por padrão para todos os usuários do teams na sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8a96-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="d8a96-128">Você pode desativar ou ativar o aplicativo no nível da organização na página [gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8a96-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="d8a96-129">Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="d8a96-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="d8a96-130">Na lista de aplicativos, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d8a96-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="d8a96-131">Para desativar os turnos da sua organização, procure o aplicativo turnos, selecione-o e, em seguida, selecione **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="d8a96-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="d8a96-132">Para ativar turnos para sua organização, procure o aplicativo turnos, selecione-o e, em seguida, selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="d8a96-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="d8a96-133">Habilitar ou desabilitar turnos para usuários específicos em sua organização</span><span class="sxs-lookup"><span data-stu-id="d8a96-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="d8a96-134">Para permitir ou bloquear usuários específicos em sua organização usando turnos, certifique-se de que os turnos estejam ativados para sua organização na página [gerenciar aplicativos](../../manage-apps.md) e crie uma política de permissão de aplicativo personalizada e atribua-a a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="d8a96-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="d8a96-135">Para saber mais, consulte [gerenciar políticas de permissão do aplicativo no Microsoft Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d8a96-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="d8a96-136">Usar a política de configuração do aplicativo FrontlineWorker para fixar mudanças em equipes</span><span class="sxs-lookup"><span data-stu-id="d8a96-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="d8a96-137">As políticas de configuração do aplicativo permitem que você personalize o Microsoft Teams para realçar os aplicativos que são mais importantes para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8a96-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="d8a96-138">Os aplicativos definidos em uma política são fixados na barra do aplicativo na &mdash; barra do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, &mdash; nos quais os usuários podem acessá-los de forma rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="d8a96-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="d8a96-139">O Teams inclui uma política interna de configuração de aplicativos do FrontlineWorker que você pode atribuir a trabalhadores do Frontline em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8a96-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="d8a96-140">Por padrão, a política inclui os aplicativos atividade, turnos, chat e chamadas.</span><span class="sxs-lookup"><span data-stu-id="d8a96-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="d8a96-141">Para exibir a política FrontlineWorker, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para políticas de configuração do aplicativo **Teams app**  >  .</span><span class="sxs-lookup"><span data-stu-id="d8a96-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="d8a96-142">![Captura de tela da política de configuração do aplicativo FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FrontlineWorker no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="d8a96-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="d8a96-143">Atribuir a política de configuração do aplicativo FrontlineWorker aos usuários</span><span class="sxs-lookup"><span data-stu-id="d8a96-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="d8a96-144">Pesquisar eventos Shift do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="d8a96-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="d8a96-145">**(em visualização)**</span><span class="sxs-lookup"><span data-stu-id="d8a96-145">**(in preview)**</span></span>

<span data-ttu-id="d8a96-146">Você pode pesquisar o log de auditoria para exibir a atividade de turnos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8a96-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="d8a96-147">Para saber mais sobre como Pesquisar no log de auditoria e ver uma lista de [atividades de turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar o log de auditoria para eventos no Teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="d8a96-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="d8a96-148">Para que você possa Pesquisar no log de auditoria, primeiro ative a auditoria no [centro de conformidade do & de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="d8a96-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d8a96-149">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="d8a96-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="d8a96-150">Lembre-se de que os dados de auditoria estão disponíveis apenas no ponto em que você ativou a auditoria.</span><span class="sxs-lookup"><span data-stu-id="d8a96-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8a96-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8a96-151">Related topics</span></span>

- [<span data-ttu-id="d8a96-152">Ajuda de turnos para trabalhadores do Frontline</span><span class="sxs-lookup"><span data-stu-id="d8a96-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="d8a96-153">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8a96-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
