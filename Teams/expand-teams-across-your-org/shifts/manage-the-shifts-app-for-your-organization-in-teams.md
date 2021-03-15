---
title: Gerenciar o aplicativo Turnos para sua organização
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
description: Saiba como configurar e gerenciar o aplicativo Turnos no Teams para Funcionários da Linha de Frente em sua organização.
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
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909085"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="ecd91-103">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ecd91-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecd91-104">A partir de 30 de junho de 2020, o Microsoft StaffHub foi desativado.</span><span class="sxs-lookup"><span data-stu-id="ecd91-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="ecd91-105">Estamos criando recursos StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ecd91-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="ecd91-106">Hoje, o Teams inclui o aplicativo Shifts para o gerenciamento de cronogramas e recursos adicionais serão implantados com o tempo.</span><span class="sxs-lookup"><span data-stu-id="ecd91-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="ecd91-107">O StaffHub parou de funcionar para todos os usuários em 30 de junho de 2020.</span><span class="sxs-lookup"><span data-stu-id="ecd91-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="ecd91-108">Todas as pessoas que tentarem abrir o StaffHub receberão uma mensagem direcionando-as para o download do Teams.</span><span class="sxs-lookup"><span data-stu-id="ecd91-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="ecd91-109">Para saber mais, confira [O Microsoft StaffHub foi desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="ecd91-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="ecd91-110">Visão geral do Turnos</span><span class="sxs-lookup"><span data-stu-id="ecd91-110">Overview of Shifts</span></span>

<span data-ttu-id="ecd91-111">O aplicativo Turnos no Microsoft Teams mantém os Funcionários da Linha de Frente conectados e em sincronia. Ele foi criado nos dispositivos móveis para a gestão rápida e eficaz do tempo e da comunicação para as equipes.</span><span class="sxs-lookup"><span data-stu-id="ecd91-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="ecd91-112">O Turnos permite que Funcionários da Linha de Frente e seus gerentes usem seus dispositivos móveis para gerenciar cronogramas e manter contato.</span><span class="sxs-lookup"><span data-stu-id="ecd91-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="ecd91-113">Os gerentes criam, atualizam e gerenciam cronogramas de turnos da equipe.</span><span class="sxs-lookup"><span data-stu-id="ecd91-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="ecd91-114">Eles também podem enviar mensagens para uma pessoa ("há um derramamento no chão") ou para toda a equipe ("o gerente regional chega em 20 minutos").</span><span class="sxs-lookup"><span data-stu-id="ecd91-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="ecd91-115">Eles podem enviar documentos de política, boletins de notícias e vídeos.</span><span class="sxs-lookup"><span data-stu-id="ecd91-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="ecd91-116">Os funcionários visualizam os próximos turnos rapidamente, podem ver quem mais está agendado para o dia, solicitar uma troca de turno, oferecer um turno e solicitar folgas.</span><span class="sxs-lookup"><span data-stu-id="ecd91-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="ecd91-117">É importante saber que o Turnos atualmente não suporta usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="ecd91-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="ecd91-118">Isso significa que os convidados em uma equipe não podem ser adicionados ou usar escalas de turnos quando o acesso de Convidado estiver ativado no Teams.</span><span class="sxs-lookup"><span data-stu-id="ecd91-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="ecd91-119">Para obter detalhes sobre os recursos do Turnos em diferentes plataformas, confira [Recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="ecd91-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="ecd91-120">Disponibilidade de Turnos</span><span class="sxs-lookup"><span data-stu-id="ecd91-120">Availability of Shifts</span></span>

<span data-ttu-id="ecd91-121">O Turnos está disponível em todas as SKUs corporativas onde o Teams está disponível.</span><span class="sxs-lookup"><span data-stu-id="ecd91-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="ecd91-122">Local dos dados de Turnos</span><span class="sxs-lookup"><span data-stu-id="ecd91-122">Location of Shifts data</span></span>

<span data-ttu-id="ecd91-123">Atualmente, os dados do Turnos estão armazenados no Azure, em datacenters na América do Norte, na Europa Ocidental e Ásia-Pacífico.</span><span class="sxs-lookup"><span data-stu-id="ecd91-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="ecd91-124">Confira mais informações sobre onde os dados são armazenados em [Onde estão meus dados?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="ecd91-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="ecd91-125">Configurar Turnos</span><span class="sxs-lookup"><span data-stu-id="ecd91-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="ecd91-126">Habilitar ou desabilitar o Turnos em sua organização</span><span class="sxs-lookup"><span data-stu-id="ecd91-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="ecd91-127">O Turnos é habilitado por padrão para todos os usuários do Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ecd91-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="ecd91-128">Você pode desativar ou ativar o aplicativo no nível da organização na página [Gerenciar aplicativos](../../manage-apps.md) no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ecd91-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ecd91-129">Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="ecd91-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="ecd91-130">Na lista de aplicativos, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ecd91-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="ecd91-131">Para desativar o Turnos para sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="ecd91-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="ecd91-132">Para ativar o Turnos para sua organização, pesquise o aplicativo Turnos, selecione-o e clique em **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="ecd91-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="ecd91-133">Habilite ou desabilite o Turnos para usuários específicos em sua organização</span><span class="sxs-lookup"><span data-stu-id="ecd91-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="ecd91-134">Para permitir ou bloquear usuários específicos de usarem o Turnos em sua organização, certifique-se de que o Turnos esteja ativado para sua organização na página [Gerenciar aplicativos](../../manage-apps.md) e, em seguida, crie uma política de permissão de aplicativo personalizada e atribua a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="ecd91-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="ecd91-135">Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ecd91-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="ecd91-136">Use uma política de configuração de aplicativo para fixar o Turnos ao Teams</span><span class="sxs-lookup"><span data-stu-id="ecd91-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="ecd91-137">As políticas de configuração de aplicativos permitem que você personalize o Teams para destacar os aplicativos que são mais importantes para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ecd91-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="ecd91-138">Os aplicativos definidos em uma política são fixados na barra do aplicativo&mdash;na barra na lateral do cliente de área de trabalho do Teams e na parte inferior dos clientes móveis do Teams&mdash;onde os usuários podem acessá-los de forma rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="ecd91-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="ecd91-139">O Teams inclui uma política interna de configuração de aplicativo Frontlineworker que você pode atribuir aos Funcionários na Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ecd91-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="ecd91-140">Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada.</span><span class="sxs-lookup"><span data-stu-id="ecd91-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="ecd91-141">Para exibir a política do FrontlineWorker, na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Políticas de configuração de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="ecd91-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="ecd91-142">![Captura de tela da política de configuração do aplicativo FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de tela da política de configuração do aplicativo FrontlineWorker no Centro de Administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="ecd91-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="ecd91-143">Atribua a política de configuração do aplicativo FrontlineWorker aos usuários</span><span class="sxs-lookup"><span data-stu-id="ecd91-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="ecd91-144">Pesquisar o registro de auditoria para eventos do Turnos</span><span class="sxs-lookup"><span data-stu-id="ecd91-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="ecd91-145">**(em visualização)**</span><span class="sxs-lookup"><span data-stu-id="ecd91-145">**(in preview)**</span></span>

<span data-ttu-id="ecd91-146">Você pode pesquisar no log de auditoria para exibir as atividades de Turnos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="ecd91-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="ecd91-147">Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de [atividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que são registradas no log de auditoria, consulte [Pesquisar no log de auditoria por eventos no Teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="ecd91-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="ecd91-148">Antes de poder pesquisar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="ecd91-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ecd91-149">Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="ecd91-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="ecd91-150">Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.</span><span class="sxs-lookup"><span data-stu-id="ecd91-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ecd91-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ecd91-151">Related topics</span></span>

- [<span data-ttu-id="ecd91-152">Ajuda do Turnos para Funcionários de Linha de Frente</span><span class="sxs-lookup"><span data-stu-id="ecd91-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="ecd91-153">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="ecd91-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
