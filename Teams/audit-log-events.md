---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Saiba como recuperar dados do Microsoft Teams do log de auditoria.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778887"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="178a0-103">Pesquisar o log de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="178a0-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="178a0-104">O log de auditoria pode ajudar na investigação de atividades específicas em todos os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="178a0-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="178a0-105">Para o Microsoft Teams, estas são algumas das atividades auditadas:</span><span class="sxs-lookup"><span data-stu-id="178a0-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="178a0-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="178a0-106">Team creation</span></span>

- <span data-ttu-id="178a0-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="178a0-107">Team deletion</span></span>

- <span data-ttu-id="178a0-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="178a0-108">Added channel</span></span>

- <span data-ttu-id="178a0-109">Configuração alterada</span><span class="sxs-lookup"><span data-stu-id="178a0-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="178a0-110">Os eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.</span><span class="sxs-lookup"><span data-stu-id="178a0-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="178a0-111">Para ver a lista completa de atividades auditadas no Microsoft 365, leia [Pesquisar o log de auditoria no centro de conformidade do microsoft 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="178a0-111">To see the complete list of activities that are audited in Microsoft 365, read [Search the audit log in the Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="178a0-112">Ativar a auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="178a0-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="178a0-113">Antes de poder ver os dados de auditoria, você deve primeiro ativar a auditoria no centro de [conformidade do & de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="178a0-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="178a0-114">Para obter ajuda para ativar a auditoria, leia [Ativar ou desativar a pesquisa ativar log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="178a0-114">For help turning on auditing, read [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="178a0-115">Os dados de auditoria estão disponíveis apenas a partir do momento em que a auditoria foi ativada.</span><span class="sxs-lookup"><span data-stu-id="178a0-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="178a0-116">Recuperar dados do Microsoft Teams a partir do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="178a0-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="178a0-117">Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="178a0-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="178a0-118">Em **Pesquisar**, selecione **pesquisa de log de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="178a0-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="178a0-119">Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.</span><span class="sxs-lookup"><span data-stu-id="178a0-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="178a0-120">Exporte os resultados para o Excel para analisá-los melhor.</span><span class="sxs-lookup"><span data-stu-id="178a0-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="178a0-121">Os dados de auditoria estarão visíveis no Log de Auditoria somente se a auditoria estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="178a0-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="178a0-122">Cenário de usuário externo</span><span class="sxs-lookup"><span data-stu-id="178a0-122">External user scenario</span></span>

<span data-ttu-id="178a0-123">Um cenário do qual você pode querer ficar atento, do ponto de vista dos negócios, é a adição de usuários externos ao seu ambiente de equipe.</span><span class="sxs-lookup"><span data-stu-id="178a0-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="178a0-124">Se usuários externos estiverem habilitados, então a monitoração da presença será uma boa ideia.</span><span class="sxs-lookup"><span data-stu-id="178a0-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="178a0-126">A captura de tela desta política para monitorar o usuário externo permite que você nomeie a política, defina a severidade de acordo com suas necessidades comerciais, defina-a como (neste caso) uma única atividade e, em seguida, estabeleça os parâmetros que monitorarão especificamente apenas a adição de usuários não internos e limitarão essa atividade ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="178a0-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="178a0-127">Em seguida, os resultados dessa política poderão ser visualizados no log de atividades:</span><span class="sxs-lookup"><span data-stu-id="178a0-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserList.png)

<span data-ttu-id="178a0-129">Aqui você pode revisar as correspondências da política que definiu e fazer os ajustes necessários ou exportar os resultados para usar em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="178a0-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="178a0-130">Cenário de exclusão em massa</span><span class="sxs-lookup"><span data-stu-id="178a0-130">Mass delete scenario</span></span>

<span data-ttu-id="178a0-131">Conforme mencionado acima, você pode monitorar cenários de exclusão.</span><span class="sxs-lookup"><span data-stu-id="178a0-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="178a0-132">É possível criar uma política que monitoria a exclusão em massa de sites de equipe:</span><span class="sxs-lookup"><span data-stu-id="178a0-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Captura de tela da página Criar política mostrando a configuração de uma política para a detecção de exclusão da equipe em massa](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="178a0-134">Conforme mostrado na captura de tela, você pode definir vários parâmetros diferentes para essa política para monitorar as exclusões do Teams, incluindo gravidade, ação única ou repetida e parâmetros que limitam isso a equipes e exclusão de sites.</span><span class="sxs-lookup"><span data-stu-id="178a0-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="178a0-135">Isso pode ser feito independentemente de um modelo, ou você pode ter um modelo criado para basear essa política, dependendo das suas necessidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="178a0-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="178a0-136">Depois de estabelecer uma política que funcionará para a sua empresa, você pode revisar os resultados no registro de atividades à medida que os eventos são disparados:</span><span class="sxs-lookup"><span data-stu-id="178a0-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsMassDeleteList.png)

<span data-ttu-id="178a0-138">Você pode filtrar para baixo até a política definida para ver os resultados dessa política.</span><span class="sxs-lookup"><span data-stu-id="178a0-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="178a0-139">Se os resultados que você está recebendo no registro de atividades não forem satisfatórios (talvez você esteja vendo muitos resultados ou nada), isso pode ajudá-lo a ajustar a consulta para torná-la mais relevante para o que você precisa.</span><span class="sxs-lookup"><span data-stu-id="178a0-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="178a0-140">Vídeo: Dicas de tecnologia: Como usar a pesquisa de log de auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="178a0-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="178a0-141">Conheça Ansuman Acharya, gerente de programas do Microsoft Teams, que demonstra como realizar uma pesquisa de Log de Auditoria do Microsoft Teams no Centro de Conformidade e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="178a0-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
