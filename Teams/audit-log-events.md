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
ms.openlocfilehash: 90de6c2267eb2828f2f681287d4b43c001d0ceb4
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="49eb9-103">Pesquisar o registro de auditoria de eventos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49eb9-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="49eb9-104">O registro de auditoria oferece recursos de pesquisa ad-hoc de eventos notáveis nos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="49eb9-104">The Audit Log provides ad-hoc search capabilities into notable events across Office 365 services.</span></span> <span data-ttu-id="49eb9-105">Especificamente para o Microsoft Teams, seguem abaixo alguns exemplos de eventos capturados:</span><span class="sxs-lookup"><span data-stu-id="49eb9-105">For Microsoft Teams specifically, below are a few examples of events captured:</span></span>

-   <span data-ttu-id="49eb9-106">Criação de equipes</span><span class="sxs-lookup"><span data-stu-id="49eb9-106">Team Creation</span></span>

-   <span data-ttu-id="49eb9-107">Exclusão de equipes</span><span class="sxs-lookup"><span data-stu-id="49eb9-107">Team Deletion</span></span>

-   <span data-ttu-id="49eb9-108">Canal adicionado</span><span class="sxs-lookup"><span data-stu-id="49eb9-108">Added Channel</span></span>

-   <span data-ttu-id="49eb9-109">Configuração de canal</span><span class="sxs-lookup"><span data-stu-id="49eb9-109">Changed Setting</span></span>

<span data-ttu-id="49eb9-110">A lista completa de eventos do Office 365 é bastante extensa e pode ser encontrada [aqui](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span><span class="sxs-lookup"><span data-stu-id="49eb9-110">The complete event list across Office 365 is quite extensive and can be found [here](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).</span></span>

<span data-ttu-id="49eb9-111">Antes que você possa se aprofundar em insights de auditoria, a auditoria precisa primeiro ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="49eb9-111">Before you can dig into audit insights, auditing must first be enabled.</span></span> <span data-ttu-id="49eb9-112">Para habilitar a auditoria, navegue para o Centro de Administração de *Segurança e Conformidade*.</span><span class="sxs-lookup"><span data-stu-id="49eb9-112">To enable Auditing, navigate to the *Security & Compliance* Admin Center.</span></span> <span data-ttu-id="49eb9-113">Em *Pesquisa por atividade*, clique em **Iniciar registro agora**.</span><span class="sxs-lookup"><span data-stu-id="49eb9-113">Under *Search for activity*, click on **Start recording now**.</span></span> <span data-ttu-id="49eb9-114">Depois de 24 horas, os dados de auditoria estarão disponíveis via *Pesquisa de registro de auditoria* localizada na guia de *Pesquisa e Investigação*.</span><span class="sxs-lookup"><span data-stu-id="49eb9-114">After 24hrs, audit data will be available via *Audit Log Search* located under the *Search & Investigation* tab.</span></span>


| |  |
|---------|---------|
|![Captura de tela da página inicial do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="49eb9-116">Importante</span><span class="sxs-lookup"><span data-stu-id="49eb9-116">Important</span></span>     |<span data-ttu-id="49eb9-117">Os dados de auditoria estão disponíveis apenas a partir do ponto em que a auditoria foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="49eb9-117">Audit data is only available from the point at which Auditing was enabled.</span></span>         |

![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

<span data-ttu-id="49eb9-119">Agora, vamos dar uma olhada em como recuperar dados do Microsoft Teams a partir do registro de auditoria:</span><span class="sxs-lookup"><span data-stu-id="49eb9-119">Now, let’s look at how to retrieve Microsoft Teams data from the Audit Log:</span></span>

1.  <span data-ttu-id="49eb9-120">Para recuperar as informações de registro de auditoria, navegue até o [Centro de Administração de Segurança e Conformidade](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="49eb9-120">To retrieve Audit Log information, navigate to the [Security & Compliance Admin Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="49eb9-121">Em *Pesquisa e Investigação*, selecione **Pesquisa por registro de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="49eb9-121">Under *Search & Investigation*, select **Audit log search.**</span></span>

    <span data-ttu-id="49eb9-122">a.</span><span class="sxs-lookup"><span data-stu-id="49eb9-122">a.</span></span>  <span data-ttu-id="49eb9-123">O Microsoft Teams determinou que as atividades de auditoria podem ser selecionadas conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="49eb9-123">Microsoft Teams has defined audit activities that can be selected as shown below.</span></span>

![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  <span data-ttu-id="49eb9-125">Depois de selecionar as atividades de seu interesse, insira um intervalo de datas e usuários para recuperar as informações do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49eb9-125">After selecting the activities of interest, supply a date range and users to retrieve Microsoft Teams information from.</span></span> <span data-ttu-id="49eb9-126">Clique em **Pesquisar** para recuperar os resultados.</span><span class="sxs-lookup"><span data-stu-id="49eb9-126">Click **Search** to retrieve the results.</span></span>

3.  <span data-ttu-id="49eb9-127">Essas informações podem ser exportadas para o Excel e filtradas conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="49eb9-127">This information can be exported to Excel and filtered as needed.</span></span>


|  | |
|---------|---------|
|![Ícone de ponto de exclamação.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="49eb9-129">Importante</span><span class="sxs-lookup"><span data-stu-id="49eb9-129">Important</span></span> |<span data-ttu-id="49eb9-130">Se a auditoria não tiver sido habilitada anteriormente, ela deve ser habilitada para que os dados sejam exibidos no registro de auditoria.</span><span class="sxs-lookup"><span data-stu-id="49eb9-130">If auditing has not been enabled previously, that needs to be enabled before data will appear in the Audit Log.</span></span>         |
