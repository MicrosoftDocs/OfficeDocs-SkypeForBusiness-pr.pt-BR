---
title: Planejar o conector de dados de chamada
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Visão geral do uso Skype para as ferramentas de telemetria Business Online para monitorar uma implementação local em um cenário híbrido.
ms.openlocfilehash: 2c491a217f02af77a25f362697e6f89aceb9470c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "25030697"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="6b278-103">Planejar o conector de dados de chamada</span><span class="sxs-lookup"><span data-stu-id="6b278-103">Plan Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="6b278-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="6b278-104">Overview</span></span>
<span data-ttu-id="6b278-105">Este tópico descreve os benefícios, considerações sobre planejamento e requisitos para implementar o Skype para Business Server chamada dados Connector.</span><span class="sxs-lookup"><span data-stu-id="6b278-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="6b278-106">Para obter mais informações sobre como configurar o conector de dados da chamada, consulte [Configurar o conector de dados da chamada](configure-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="6b278-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6b278-107">Nesta versão de demonstração pública, painel de análise de chamadas somente está disponível.</span><span class="sxs-lookup"><span data-stu-id="6b278-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="6b278-108">Conector de dados chamada simplifica bastante chamada monitoramento em um ambiente híbrido porque não precisar mais usar diferentes conjuntos de locais e ferramentas online para monitorar a qualidade da chamada seus usuários.</span><span class="sxs-lookup"><span data-stu-id="6b278-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="6b278-109">Se os usuários estão hospedados no local ou online, você pode optar por exibir a qualidade da chamada de toda sua organização online.</span><span class="sxs-lookup"><span data-stu-id="6b278-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="6b278-110">Com o conector de dados de chamada, você pode executar as seguintes tarefas usando um único conjunto de ferramentas:</span><span class="sxs-lookup"><span data-stu-id="6b278-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="6b278-111">Monitore sua experiência do usuário em produtos Microsoft Teams, Skype para Business Online e Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b278-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="6b278-112">Visualizar e solucionar problemas em sua rede.</span><span class="sxs-lookup"><span data-stu-id="6b278-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="6b278-113">Atribua funções de administrador e assistência técnica para a análise de chamada, para que você pode capacitar os trabalhadores de assistência técnica para visualizar e solucionar problemas de suas áreas de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="6b278-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="6b278-114">Com o conector de dados de chamadas, o Skype para Business Server envia dados de chamada ao serviço de nuvem para que você pode aproveitar o Skype para ferramentas de análise de chamada Online corporativos (CA) e o painel de controle de qualidade de chamada (CQD), conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="6b278-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![Caixa postal de nuvem SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="6b278-116">O servidor encaminha o Quality of Experience (QoE) e a gravação de detalhes das chamadas (CDR) de dados para o serviço online.</span><span class="sxs-lookup"><span data-stu-id="6b278-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="6b278-117">As ferramentas CQD e uma análise de chamada permitem que você monitorar a qualidade das chamadas e solucionar problemas de conexão com o Microsoft Teams e Skype para serviços corporativos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6b278-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="6b278-118">Chama enfatiza a análise em problemas de qualidade com chamadas específicos.</span><span class="sxs-lookup"><span data-stu-id="6b278-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="6b278-119">Ela mostra informações detalhadas sobre chamadas e reuniões para cada usuário em um Skype para a conta de negócios.</span><span class="sxs-lookup"><span data-stu-id="6b278-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="6b278-120">Com a análise de chamada, você pode atribuir permissões para um operador de assistência técnica, que pode monitorar chamadas sem ter acesso ao restante do Skype para Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="6b278-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="6b278-121">Painel de controle de qualidade de chamada se concentra no desempenho da rede e questões em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="6b278-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="6b278-122">Skype para administradores de negócios e os engenheiros de rede usar essa ferramenta para solucionar problemas e otimizar o desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="6b278-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="6b278-123">Para obter mais informações, consulte [análise de chamada e o painel de controle de qualidade de chamada](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="6b278-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="6b278-124">Obviamente, você talvez queira manter alguns dados de qualidade de chamada no local.</span><span class="sxs-lookup"><span data-stu-id="6b278-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="6b278-125">Isso pode ser o caso, por exemplo, se você estiver usando uma solução de terceiros com fluxos de trabalho e relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="6b278-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="6b278-126">Conector de dados de chamada permite que você configure o envio de dados para o serviço online enquanto mantém também uma cópia dos dados no servidor local, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="6b278-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![Caixa postal de nuvem SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a><span data-ttu-id="6b278-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b278-128">Requirements</span></span>

<span data-ttu-id="6b278-129">Os requisitos a seguir pressupõem que você já tem Skype para Business Server implantado em uma topologia com suporte.</span><span class="sxs-lookup"><span data-stu-id="6b278-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="6b278-130">Para obter mais informações sobre como implantar o Skype para Business Server e topologias com suporte, consulte [Noções básicas de topologia](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span><span class="sxs-lookup"><span data-stu-id="6b278-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span>

- <span data-ttu-id="6b278-131">Conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="6b278-131">Hybrid connectivity.</span></span> <span data-ttu-id="6b278-132">Se você já tiver Skype para Business Server implantado e você deseja habilitar o conector de dados de chamadas, certifique-se de que você tem conectividade híbrida configurada entre seu local e ambientes on-line.</span><span class="sxs-lookup"><span data-stu-id="6b278-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="6b278-133">Às vezes, isso é chamado uma configuração de domínio dividido.</span><span class="sxs-lookup"><span data-stu-id="6b278-133">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="6b278-134">Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md) e a [Configurar a conectividade de híbrido entre Skype para Business Server e Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="6b278-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="6b278-135">Para configurar o conector de dados da chamada, você deve autenticar seu locatário do Office 365 e verifique se você tem as seguintes funções habilitadas:</span><span class="sxs-lookup"><span data-stu-id="6b278-135">To configure Call Data Connector, you must authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

   - <span data-ttu-id="6b278-136">Skype para o administrador de servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="6b278-136">Skype for Business Server Administrator</span></span> 
   - <span data-ttu-id="6b278-137">Administrador Global do Office 365</span><span class="sxs-lookup"><span data-stu-id="6b278-137">Office 365 Global Administrator</span></span> 

- <span data-ttu-id="6b278-138">Se ainda não tiver feito isso, ative o painel de controle de qualidade de chamada conforme descrito em [ativem e usando o painel de qualidade de chamada para equipes da Microsoft e Skype para negócios Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="6b278-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="6b278-139">Relatórios de comparação dos locais e online painel de controle de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="6b278-139">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="6b278-140">Relatórios de recurso</span><span class="sxs-lookup"><span data-stu-id="6b278-140">Feature reports</span></span> | <span data-ttu-id="6b278-141">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b278-141">Skype for Business Online</span></span> | <span data-ttu-id="6b278-142">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6b278-142">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="6b278-143">Métrica de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6b278-143">Application sharing metric</span></span> |<span data-ttu-id="6b278-144">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-144">Yes</span></span> | <span data-ttu-id="6b278-145">Limitado</span><span class="sxs-lookup"><span data-stu-id="6b278-145">Limited</span></span> |
| <span data-ttu-id="6b278-146">Informações de construção do cliente</span><span class="sxs-lookup"><span data-stu-id="6b278-146">Customer building information</span></span>| <span data-ttu-id="6b278-147">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-147">Yes</span></span> | <span data-ttu-id="6b278-148">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-148">Yes</span></span> |
| <span data-ttu-id="6b278-149">Análise de detalhamento</span><span class="sxs-lookup"><span data-stu-id="6b278-149">Drill-down analytics</span></span> | <span data-ttu-id="6b278-150">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-150">Yes</span></span> | <span data-ttu-id="6b278-151">Não</span><span class="sxs-lookup"><span data-stu-id="6b278-151">No</span></span> |
| <span data-ttu-id="6b278-152">Métricas de confiabilidade de mídia</span><span class="sxs-lookup"><span data-stu-id="6b278-152">Media reliability metrics</span></span> | <span data-ttu-id="6b278-153">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-153">Yes</span></span> | <span data-ttu-id="6b278-154">Limitado</span><span class="sxs-lookup"><span data-stu-id="6b278-154">Limited</span></span> |
| <span data-ttu-id="6b278-155">Relatórios de caixa</span><span class="sxs-lookup"><span data-stu-id="6b278-155">Out-of-the-box reports</span></span> | <span data-ttu-id="6b278-156">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-156">Yes</span></span> | <span data-ttu-id="6b278-157">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-157">Yes</span></span> |
| <span data-ttu-id="6b278-158">Visão geral de relatórios</span><span class="sxs-lookup"><span data-stu-id="6b278-158">Overview reports</span></span> | <span data-ttu-id="6b278-159">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-159">Yes</span></span> | <span data-ttu-id="6b278-160">Não</span><span class="sxs-lookup"><span data-stu-id="6b278-160">No</span></span> |
| <span data-ttu-id="6b278-161">Por relatórios do usuário</span><span class="sxs-lookup"><span data-stu-id="6b278-161">Per user reports</span></span> | <span data-ttu-id="6b278-162">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-162">Yes</span></span> | <span data-ttu-id="6b278-163">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-163">Yes</span></span> |
| <span data-ttu-id="6b278-164">Personalização de conjunto de relatórios</span><span class="sxs-lookup"><span data-stu-id="6b278-164">Report set customization</span></span> <br> <span data-ttu-id="6b278-165">(Adicionar, excluir, modificar relatórios)</span><span class="sxs-lookup"><span data-stu-id="6b278-165">(add, delete, modify reports)</span></span> | <span data-ttu-id="6b278-166">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-166">Yes</span></span> | <span data-ttu-id="6b278-167">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-167">Yes</span></span> |
| <span data-ttu-id="6b278-168">Métricas de compartilhamento de tela com base em vídeo</span><span class="sxs-lookup"><span data-stu-id="6b278-168">Video-based screen sharing metrics</span></span> | <span data-ttu-id="6b278-169">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-169">Yes</span></span> | <span data-ttu-id="6b278-170">Não</span><span class="sxs-lookup"><span data-stu-id="6b278-170">No</span></span> |
| <span data-ttu-id="6b278-171">APIs de dados para acesso programático</span><span class="sxs-lookup"><span data-stu-id="6b278-171">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="6b278-172">para CQD</span><span class="sxs-lookup"><span data-stu-id="6b278-172">to CQD</span></span> | <span data-ttu-id="6b278-173">Não</span><span class="sxs-lookup"><span data-stu-id="6b278-173">No</span></span> | <span data-ttu-id="6b278-174">Sim</span><span class="sxs-lookup"><span data-stu-id="6b278-174">Yes</span></span> |



















