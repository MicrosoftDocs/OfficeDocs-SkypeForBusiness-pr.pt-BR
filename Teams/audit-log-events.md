---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Saiba como recuperar dados do Microsoft Teams a partir do log de auditoria do Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 028d01a2ed05f3596cfe7cca299a1b8e35a15721
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194988"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="5fecd-103">Pesquisar o log de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fecd-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5fecd-104">O log de auditoria pode ajudar na investigação de atividades específicas em todos os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fecd-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="5fecd-105">Para o Microsoft Teams, estas são algumas das atividades auditadas:</span><span class="sxs-lookup"><span data-stu-id="5fecd-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="5fecd-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="5fecd-106">Team creation</span></span>

-   <span data-ttu-id="5fecd-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="5fecd-107">Team deletion</span></span>

-   <span data-ttu-id="5fecd-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="5fecd-108">Added channel</span></span>

-   <span data-ttu-id="5fecd-109">Configuração alterada</span><span class="sxs-lookup"><span data-stu-id="5fecd-109">Changed setting</span></span>

<span data-ttu-id="5fecd-110">Para ver a lista completa de atividades que são auditadas no Office 365, consulte [Pesquisar no log de auditoria no Centro de Conformidade e Segurança do Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="5fecd-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="5fecd-111">Ativar a auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fecd-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="5fecd-112">Antes de você pode analisar dados de auditoria, você deve primeiro ativar a auditoria de **segurança & Centro de conformidade**(https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="5fecd-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="5fecd-113">Para obter ajuda para ativar a auditoria, consulte [Ativar ou desativar a pesquisa no log de auditoria do Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="5fecd-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5fecd-114">Os dados de auditoria estão disponíveis apenas a partir do momento em que a auditoria foi ativada.</span><span class="sxs-lookup"><span data-stu-id="5fecd-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="5fecd-115">Recuperar dados do Microsoft Teams a partir do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5fecd-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="5fecd-116">Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="5fecd-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="5fecd-117">Em **Search & Investigation** (Pesquisa e Investigação), selecione **Audit log search** (Pesquisa do log de auditoria).![Captura de tela da página de pesquisa do log de auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="5fecd-117">Under **Search & Investigation**, select **Audit log search**.![Screenshot of the Audit log search page of the Security & Compliance Center.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)</span></span>

2.  <span data-ttu-id="5fecd-118">Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.</span><span class="sxs-lookup"><span data-stu-id="5fecd-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="5fecd-119">Exporte os resultados para o Excel para analisá-los melhor.</span><span class="sxs-lookup"><span data-stu-id="5fecd-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5fecd-120">Os dados de auditoria estarão visíveis no Log de Auditoria somente se a auditoria estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="5fecd-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="5fecd-121">Vídeo: Dicas de tecnologia: Como usar a pesquisa de log de auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fecd-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="5fecd-122">Conheça Ansuman Acharya, gerente de programas do Microsoft Teams, que demonstra como realizar uma pesquisa de Log de Auditoria do Microsoft Teams no Centro de Conformidade e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fecd-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






