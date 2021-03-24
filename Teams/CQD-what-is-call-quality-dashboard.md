---
title: O que é o Painel de Qualidade de Chamada (CQD)?
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre o CQD (Painel de Qualidade de Chamada) e como usá-lo para ver relatórios sobre a qualidade da reunião e da chamada no Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094935"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="80536-103">O que é o Painel de Qualidade de Chamada (CQD)?</span><span class="sxs-lookup"><span data-stu-id="80536-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="80536-104">O Painel de Qualidade de Chamadas da Microsoft (CQD) - mostra a qualidade da chamada e da reunião, no nível de toda a organização, para o Microsoft Teams, o Skype for Business Online e o [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019. </span><span class="sxs-lookup"><span data-stu-id="80536-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="80536-105">A versão mais recente do CQD apresenta um feed de dados quase em tempo [real (NRT),](CQD-data-and-reports.md)o que significa que os registros de chamada estão disponíveis no CQD dentro de 30 minutos após o final de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="80536-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="80536-106">Sempre que o CQD inclui dados de informações de identificação do usuário final [(EUII),](CQD-data-and-reports.md#euii-data)ele é gerenciado da mesma maneira que o EUII em todo [o Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="80536-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="80536-107">O CQD foi projetado para ajudar administradores do Teams, administradores do Skype for Business e engenheiros de rede a monitorar a qualidade de chamadas e reuniões em nível de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="80536-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="80536-108">Você usará o CQD para ajudá-lo a **otimizar sua rede para** impulsionar a qualidade do desempenho.</span><span class="sxs-lookup"><span data-stu-id="80536-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="80536-109">Quando você precisar procurar informações de chamada e reunião para um usuário **específico,** use dados CQD em conjunto com a análise de chamada [por usuário.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="80536-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="80536-110">Por exemplo, usando o CQD, você pode determinar que a qualidade de chamada ruim de um usuário (que você observou usando análise de chamada por usuário) é devido a um problema de rede que também afeta muitos outros usuários.</span><span class="sxs-lookup"><span data-stu-id="80536-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="80536-111">O CQD captura a experiência de chamada individual e a qualidade geral das chamadas feitas usando o Teams ou o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="80536-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="80536-112">Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas da qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="80536-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="80536-113">O CQD fornece relatórios de métricas de qualidade de chamada que proporcionam uma visão geral da qualidade da chamada, fluxos de cliente-cliente, fluxos cliente-cliente e SLA de qualidade de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="80536-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Captura de tela do Painel de Qualidade de Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="80536-115">No CQD, recomendamos que você carregue informações de construção e ponto de extremidade, o que permite que você use Location-Enhanced Relatórios para analisar a qualidade e a confiabilidade de chamada no edifício de um usuário.</span><span class="sxs-lookup"><span data-stu-id="80536-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="80536-116">Os dados podem ser avaliados para determinar se o problema está isolado para um único usuário ou afeta um segmento maior de usuários.</span><span class="sxs-lookup"><span data-stu-id="80536-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="80536-117">Para ativar exibições específicas de criação ou ponto [](CQD-upload-tenant-building-data.md) de extremidade no CQD, um administrador deve carregar informações de construção ou ponto de extremidade na página CQD **Tenant Data Upload.**</span><span class="sxs-lookup"><span data-stu-id="80536-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Captura de tela dos relatórios de Location-Enhanced do Painel de Qualidade de Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="80536-119">Não perca nosso artigo [Gerenciar](quality-of-experience-review-guide.md) qualidade de chamada e reunião, que oferece orientações detalhadas para o administrador ou engenheiro de suporte do Teams responsável pelo gerenciamento da qualidade do serviço no Teams.</span><span class="sxs-lookup"><span data-stu-id="80536-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="80536-120">Versão mais antiga do CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="80536-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="80536-121">A versão atual do CQD ( https://CQD.Teams.microsoft.com) está substituindo a versão mais antiga do CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="80536-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="80536-122">Você ainda pode usar CQD.lync.com (disponível no Centro de administração do Skype for Business), mas, a partir de 1º de julho de 2020, ele está usando os dados do CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="80536-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="80536-123">Desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve mudar para o CQD. Teams.microsoft.com se você ainda não fez isso.</span><span class="sxs-lookup"><span data-stu-id="80536-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80536-124">A partir de 1º de julho de 2020, você não pode mais exibir ou modificar seus dados de construção ou consulta do CQD antigo (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="80536-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="80536-125">Se você ainda não tiver migrado esses dados do CQD.lync.com e ainda precisar deles, registre um tíquete de suporte.</span><span class="sxs-lookup"><span data-stu-id="80536-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="80536-126">Usar o Power BI para analisar dados CQD</span><span class="sxs-lookup"><span data-stu-id="80536-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="80536-127">Novidade em janeiro de 2020: Baixar modelos de [consulta do Power BI para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="80536-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="80536-128">Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.</span><span class="sxs-lookup"><span data-stu-id="80536-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="80536-129">Leia [Use o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="80536-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="80536-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="80536-130">Related topics</span></span>

[<span data-ttu-id="80536-131">Melhorar e monitorar a qualidade das chamada para o Teams</span><span class="sxs-lookup"><span data-stu-id="80536-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="80536-132">Configurar o Painel de Qualidade de Chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="80536-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="80536-133">Carregar dados de locatário e construção</span><span class="sxs-lookup"><span data-stu-id="80536-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="80536-134">Dados e relatórios do CQD</span><span class="sxs-lookup"><span data-stu-id="80536-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="80536-135">Usar o CQD para gerenciar a qualidade de chamada e reunião</span><span class="sxs-lookup"><span data-stu-id="80536-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="80536-136">Dimensões e medidas disponíveis no CQD</span><span class="sxs-lookup"><span data-stu-id="80536-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="80536-137">Classificação de fluxo no CQD</span><span class="sxs-lookup"><span data-stu-id="80536-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="80536-138">Usar o Power BI para analisar dados CQD</span><span class="sxs-lookup"><span data-stu-id="80536-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="80536-139">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="80536-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)