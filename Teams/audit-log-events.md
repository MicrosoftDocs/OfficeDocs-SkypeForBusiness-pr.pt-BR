---
title: Pesquisar o log de auditoria para eventos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/22/2018
ms.topic: article
ms.service: msteams
description: Saiba como recuperar dados do Microsoft Teams a partir do log de auditoria do Office 365.
ms.openlocfilehash: 229ddc5fb1e8a775524564c27ffeecce96483fe1
ms.sourcegitcommit: 9f185be910855f6312344ea906e96e5e6449cf4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2018
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="e7a76-103">Pesquisar o registro de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7a76-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="e7a76-104">O log de auditoria pode ajudar na investigação de atividades específicas em todos os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7a76-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="e7a76-105">Para o Microsoft Teams, estas são algumas das atividades auditadas:</span><span class="sxs-lookup"><span data-stu-id="e7a76-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="e7a76-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="e7a76-106">Team Creation</span></span>

-   <span data-ttu-id="e7a76-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="e7a76-107">Team Deletion</span></span>

-   <span data-ttu-id="e7a76-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="e7a76-108">Added Channel</span></span>

-   <span data-ttu-id="e7a76-109">Configuração alterada</span><span class="sxs-lookup"><span data-stu-id="e7a76-109">Changed Setting</span></span>

<span data-ttu-id="e7a76-110">Para ver a lista completa de atividades que são auditadas no Office 365, consulte [Pesquisar no log de auditoria no Centro de Conformidade e Segurança do Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span><span class="sxs-lookup"><span data-stu-id="e7a76-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c?=&PickTab=Activities&ad=US#PickTab=Activities).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="e7a76-111">Ativar a auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7a76-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="e7a76-112">Para examinar os dados de auditoria, você precisa ativar a auditoria no **Centro de Conformidade e Segurança** (https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e7a76-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="e7a76-113">Para obter ajuda para ativar a auditoria, consulte [Ativar ou desativar a pesquisa no log de auditoria do Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="e7a76-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e7a76-114">Os dados de auditoria estão disponíveis apenas a partir do momento em que a auditoria foi ativada.</span><span class="sxs-lookup"><span data-stu-id="e7a76-114">Audit data is only available from the point at which Auditing was enabled.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="e7a76-115">Recuperar dados do Microsoft Teams a partir do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="e7a76-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="e7a76-116">Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="e7a76-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="e7a76-117">Em **Pesquisa e Investigação**, selecione **Pesquisa de log de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="e7a76-117">Under **Search & Investigation**, select **Audit log search.**</span></span>

![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="e7a76-119">Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.</span><span class="sxs-lookup"><span data-stu-id="e7a76-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="e7a76-120">Exporte os resultados para o Excel para analisá-los melhor.</span><span class="sxs-lookup"><span data-stu-id="e7a76-120">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e7a76-121">Os dados de auditoria estarão visíveis no Log de Auditoria somente se a auditoria estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="e7a76-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="e7a76-122">Vídeo: Dicas de tecnologia: Como usar a pesquisa de log de auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7a76-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="e7a76-123">Conheça Ansuman Acharya, gerente de programas do Microsoft Teams, que demonstra como realizar uma pesquisa de Log de Auditoria do Microsoft Teams no Centro de Conformidade e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7a76-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






