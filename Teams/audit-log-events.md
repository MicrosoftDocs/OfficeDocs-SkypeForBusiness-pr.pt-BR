---
title: Pesquisar o registro de auditoria de eventos no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como recuperar dados do Microsoft Teams a partir do registro de auditoria.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 558db88d32229fcaef70ea5278d7437fbea92198
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="7ad9c-103">Pesquisar o registro de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ad9c-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="7ad9c-104">O registro de auditoria oferece recursos de pesquisa ad-hoc de eventos notáveis nos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-104">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services.</span></span> <span data-ttu-id="7ad9c-105">Especificamente para o Microsoft Teams, seguem abaixo alguns exemplos de eventos capturados:</span><span class="sxs-lookup"><span data-stu-id="7ad9c-105">For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="7ad9c-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="7ad9c-106">Team Creation</span></span>

-   <span data-ttu-id="7ad9c-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="7ad9c-107">Team Deletion</span></span>

-   <span data-ttu-id="7ad9c-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="7ad9c-108">Added Channel</span></span>

-   <span data-ttu-id="7ad9c-109">Configuração de canal</span><span class="sxs-lookup"><span data-stu-id="7ad9c-109">Changed Setting</span></span>

<span data-ttu-id="7ad9c-110">A lista completa de eventos do Office 365 é bastante extensa e pode ser encontrada [aqui](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="7ad9c-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="7ad9c-111">Antes que você possa se aprofundar em insights de auditoria, a auditoria precisa primeiro ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-111">Before you can dig into audit insights, auditing must first be enabled.</span></span> <span data-ttu-id="7ad9c-112">Para habilitar a auditoria, navegue para o Centro de Administração de *Segurança e Conformidade*.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-112">To enable Auditing, navigate to the *Security & Compliance* Admin Center.</span></span> <span data-ttu-id="7ad9c-113">Em *Pesquisa por atividade*, clique em **Iniciar registro agora**.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-113">Under *Search for activity*, click on **Start recording now**.</span></span> <span data-ttu-id="7ad9c-114">Depois de 24 horas, os dados de auditoria estarão disponíveis via *Pesquisa de registro de auditoria* localizada na guia de *Pesquisa e Investigação*.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-114">After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="7ad9c-115">Importante</span><span class="sxs-lookup"><span data-stu-id="7ad9c-115">Important:</span></span>     |<span data-ttu-id="7ad9c-116">Os dados de auditoria estão disponíveis apenas a partir do ponto em que a auditoria foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-116">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="7ad9c-117">Agora, vamos dar uma olhada em como recuperar dados do Microsoft Teams a partir do registro de auditoria:</span><span class="sxs-lookup"><span data-stu-id="7ad9c-117">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="7ad9c-118">Para recuperar as informações de registro de auditoria, navegue até o [Centro de Administração de Segurança e Conformidade](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="7ad9c-118">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="7ad9c-119">Em *Pesquisa e Investigação*, selecione **Pesquisa por registro de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="7ad9c-119">Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="7ad9c-120">a.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-120">A</span></span>  <span data-ttu-id="7ad9c-121">O Microsoft Teams determinou que as atividades de auditoria podem ser selecionadas conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-121">Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="7ad9c-122">Depois de selecionar as atividades de seu interesse, insira um intervalo de datas e usuários para recuperar as informações do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-122">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from.</span></span> <span data-ttu-id="7ad9c-123">Clique em **Pesquisar** para recuperar os resultados.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-123">Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="7ad9c-124">Essas informações podem ser exportadas para o Excel e filtradas conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-124">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="7ad9c-125">Importante</span><span class="sxs-lookup"><span data-stu-id="7ad9c-125">Important:</span></span> |<span data-ttu-id="7ad9c-126">Se a auditoria não tiver sido habilitada anteriormente, ela deve ser habilitada para que os dados sejam exibidos no registro de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7ad9c-126">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
