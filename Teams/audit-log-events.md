---
title: Pesquisar o registro de auditoria de eventos no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como recuperar dados do Microsoft Teams a partir do registro de auditoria.
ms.openlocfilehash: bea1a808fd92d3b43caf8ee61152a999ca3af8a3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="8fa4d-103">Pesquisar o registro de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8fa4d-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="8fa4d-104">O registro de auditoria oferece recursos de pesquisa ad-hoc de eventos notáveis nos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-104">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services.</span></span> <span data-ttu-id="8fa4d-105">Especificamente para o Microsoft Teams, seguem abaixo alguns exemplos de eventos capturados:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-105">For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="8fa4d-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="8fa4d-106">Team Creation</span></span>

-   <span data-ttu-id="8fa4d-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="8fa4d-107">Team Deletion</span></span>

-   <span data-ttu-id="8fa4d-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="8fa4d-108">Added Channel</span></span>

-   <span data-ttu-id="8fa4d-109">Configuração de canal</span><span class="sxs-lookup"><span data-stu-id="8fa4d-109">Changed Setting</span></span>

<span data-ttu-id="8fa4d-110">A lista completa de eventos do Office 365 é bastante extensa e pode ser encontrada [aqui](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="8fa4d-111">Antes que você possa se aprofundar em insights de auditoria, a auditoria precisa primeiro ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-111">Before you can dig into audit insights, auditing must first be enabled.</span></span> <span data-ttu-id="8fa4d-112">Para habilitar a auditoria, vá até o Centro de Administração de *Segurança e Conformidade*.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-112">To enable Auditing, navigate to the *Security & Compliance* Admin Center.</span></span> <span data-ttu-id="8fa4d-113">Em *Pesquisa por atividade*, clique em **Iniciar registro agora**.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-113">Under *Search for activity*, click on **Start recording now**.</span></span> <span data-ttu-id="8fa4d-114">Depois de 24 horas, os dados de auditoria estarão disponíveis via *Pesquisa de Log de Auditoria*, localizada na guia *Pesquisa e Investigação*.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-114">After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8fa4d-115">Os dados de auditoria estão disponíveis apenas a partir do ponto em que a auditoria foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-115">Audit data is only available from the point at which Auditing was enabled.</span></span>



![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="8fa4d-117">Agora, vamos dar uma olhada em como recuperar dados do Microsoft Teams a partir do registro de auditoria:</span><span class="sxs-lookup"><span data-stu-id="8fa4d-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="8fa4d-118">Para recuperar as informações de registro de auditoria, navegue até o [Centro de Administração de Segurança e Conformidade](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="8fa4d-118">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="8fa4d-119">Em *Pesquisa e Investigação*, selecione **Pesquisa por registro de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="8fa4d-119">Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="8fa4d-120">a.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-120">a.</span></span>  <span data-ttu-id="8fa4d-121">O Microsoft Teams determinou que as atividades de auditoria podem ser selecionadas conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-121">Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="8fa4d-123">Depois de selecionar as atividades de seu interesse, insira um intervalo de datas e usuários para recuperar as informações do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-123">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from.</span></span> <span data-ttu-id="8fa4d-124">Clique em **Pesquisar** para recuperar os resultados.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-124">Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="8fa4d-125">Essas informações podem ser exportadas para o Excel e filtradas conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-125">This information can be exported to Excel and filtered as needed.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8fa4d-126">Se a auditoria ainda não tiver sido habilitada, será necessário habilitá-la para que os dados sejam exibidos no Log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="8fa4d-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>


