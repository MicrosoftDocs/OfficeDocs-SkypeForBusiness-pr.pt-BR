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
description: Saiba como recuperar dados do Microsoft Teams a partir do log de auditoria do Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c1f82a7688e3fdde7be85004c717293cc5777fa
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826269"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="f9fb4-103">Pesquisar o log de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9fb4-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f9fb4-104">O log de auditoria pode ajudar na investigação de atividades específicas em todos os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="f9fb4-105">Para o Microsoft Teams, estas são algumas das atividades auditadas:</span><span class="sxs-lookup"><span data-stu-id="f9fb4-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="f9fb4-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="f9fb4-106">Team creation</span></span>

- <span data-ttu-id="f9fb4-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="f9fb4-107">Team deletion</span></span>

- <span data-ttu-id="f9fb4-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="f9fb4-108">Added channel</span></span>

- <span data-ttu-id="f9fb4-109">Configuração alterada</span><span class="sxs-lookup"><span data-stu-id="f9fb4-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="f9fb4-110">Os eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="f9fb4-111">Para ver a lista completa de atividades que são auditadas no Office 365, consulte [Pesquisar no log de auditoria no Centro de Conformidade e Segurança do Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="f9fb4-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="f9fb4-112">Ativar a auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9fb4-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="f9fb4-113">Antes de poder ver os dados de auditoria, você deve primeiro ativar a auditoria no centro de [conformidade do & de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="f9fb4-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="f9fb4-114">Para obter ajuda para ativar a auditoria, consulte [Ativar ou desativar a pesquisa no log de auditoria do Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="f9fb4-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9fb4-115">Os dados de auditoria estão disponíveis apenas a partir do momento em que a auditoria foi ativada.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="f9fb4-116">Recuperar dados do Microsoft Teams a partir do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="f9fb4-116">Retrieve Teams data from the audit log</span></span>


1.  <span data-ttu-id="f9fb4-117">Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="f9fb4-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="f9fb4-118">Em **Pesquisar**, selecione **pesquisa de log de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-118">Under **Search**, select **Audit log search**.</span></span>



2. <span data-ttu-id="f9fb4-119">Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="f9fb4-120">Exporte os resultados para o Excel para analisá-los melhor.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9fb4-121">Os dados de auditoria estarão visíveis no Log de Auditoria somente se a auditoria estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="f9fb4-122">Vídeo: Dicas de tecnologia: Como usar a pesquisa de log de auditoria no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9fb4-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="f9fb4-123">Conheça Ansuman Acharya, gerente de programas do Microsoft Teams, que demonstra como realizar uma pesquisa de Log de Auditoria do Microsoft Teams no Centro de Conformidade e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9fb4-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
