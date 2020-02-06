---
title: Planejar o Gerenciador de estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de estatísticas do Skype for Business Server.'
ms.openlocfilehash: 0bf7a5366047a0f4435a98cd8bca75eeb3ebc8d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816230"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5c2c1-103">Planejar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c2c1-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="5c2c1-104">**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="5c2c1-105">O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir o desempenho e a integridade do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5c2c1-106">É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="5c2c1-107">Você pode usar o Gerenciador de estatísticas para identificar problemas de desempenho contínuos, Ver os resultados de uma alteração planejada em seu ambiente, acompanhar a resolução de paralisações e muito mais.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="5c2c1-108">A partir da caixa, o Gerenciador de estatísticas é configurado com os principais limiares do Key Health Indicator (KHI) e pode ser personalizado para atender às necessidades exclusivas da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="5c2c1-109">Você pode implantar o Gerenciador de estatísticas em uma implantação local na qual um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="5c2c1-110">Para obter mais informações sobre a implantação do Gerenciador de estatísticas, consulte [implantar o Gerenciador de estatísticas para o Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="5c2c1-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="5c2c1-111">Se você já tiver uma implantação existente do Gerenciador de estatísticas, mas ainda não atualizou para o lançamento do 2,0, Confira as novidades [na versão 2,0 e o](plan.md#BKMK_WhatsNew) [Gerenciador de estatísticas de atualização para o Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5c2c1-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="5c2c1-112">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="5c2c1-113">Recursos e funcionalidades</span><span class="sxs-lookup"><span data-stu-id="5c2c1-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="5c2c1-114">O que há de novo no lançamento 2,0</span><span class="sxs-lookup"><span data-stu-id="5c2c1-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="5c2c1-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="5c2c1-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="5c2c1-116">Implantação local</span><span class="sxs-lookup"><span data-stu-id="5c2c1-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="5c2c1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c2c1-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="5c2c1-118">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="5c2c1-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="5c2c1-119">Recursos e funcionalidades</span><span class="sxs-lookup"><span data-stu-id="5c2c1-119">Features and capabilities</span></span>
<span data-ttu-id="5c2c1-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="5c2c1-121">O Gerenciador de estatísticas permite que você:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="5c2c1-122">Exiba dados brutos para todos os servidores em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="5c2c1-123">(Os dados são amostrados a uma taxa muito alta e enviados para o website em menos de um segundo.)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="5c2c1-124">Exibir dados agregados para uma função específica; por exemplo, servidor front-end, servidor de mediação, servidor de borda e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="5c2c1-125">Faça drill down para exibir dados de sites específicos, pools específicos dentro do site e, em seguida, servidores específicos dentro do pool.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="5c2c1-126">Crie gráficos personalizados para que os contadores escolhidos sejam mostrados por padrão.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="5c2c1-127">Aplicar zoom e panorâmica nos eixos x e y ou somente no eixo x.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="5c2c1-128">Use intervalos de datas ou pontos no tempo para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="5c2c1-129">Exibir o desempenho do servidor com base em indicadores chave de integridade estabelecidos (KHIs).</span><span class="sxs-lookup"><span data-stu-id="5c2c1-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="5c2c1-130">KHIs representa uma coleção de contadores de desempenho com um intervalo saudável definido.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="5c2c1-131">Exiba métricas detalhadas para cada contador.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="5c2c1-132">Comparar dados em várias populações ou servidores.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="5c2c1-133">Exiba relatórios de contador latentes para identificar agentes que não estão relatando dados atuais para o serviço de painel.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="5c2c1-134">Salvar uma instância específica de dados de gráfico em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="5c2c1-135">Exiba KHIs em tempo real, incluindo atualizações.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="5c2c1-136">Se a exibição do histórico estiver habilitada, apenas novas falhas serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="5c2c1-137">Exibir todas as KHIs ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="5c2c1-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="5c2c1-138">Exibir KHIs por servidor (modo de exibição paisagem)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="5c2c1-139">Exibir definições KHI</span><span class="sxs-lookup"><span data-stu-id="5c2c1-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="5c2c1-140">O que há de novo no lançamento 2,0</span><span class="sxs-lookup"><span data-stu-id="5c2c1-140">What's new in Release 2.0</span></span>
<span data-ttu-id="5c2c1-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="5c2c1-142">Veja a seguir as novidades da versão 2,0.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="5c2c1-143">Se você tiver uma implantação existente do Gerenciador de estatísticas e ainda não tiver atualizado, consulte [Gerenciador de estatísticas de atualização para o Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="5c2c1-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="5c2c1-144">Os modos de exibição de cenário foram adicionados para mídia de borda, integridade da malha, failover de pool e cenários de registro.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="5c2c1-145">Muitos novos contadores foram adicionados para SQL Servers, mais contadores de uso do Skype for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="5c2c1-146">Integração do nó do inspetor para o agente do Gerenciador de estatísticas-se o agente estiver instalado em um nó do Inspetor, ele reportará as estatísticas de transação sintética como contadores de volta para o Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="5c2c1-147">Diversas melhorias de confiabilidade e desempenho.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="5c2c1-148">Para verificar a versão do site do Gerenciador de estatísticas que você está executando:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="5c2c1-149">No explorador de arquivos, abra (diretório padrão) C:\Program Files\Skype for Business Server stats WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="5c2c1-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="5c2c1-150">Clique com o botão direito do mouse em StatsManHubWebSite. dll e veja suas propriedades</span><span class="sxs-lookup"><span data-stu-id="5c2c1-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="5c2c1-151">A versão do produto será mostrada nos detalhes de Descrição.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="5c2c1-152">Componentes</span><span class="sxs-lookup"><span data-stu-id="5c2c1-152">Components</span></span>
<span data-ttu-id="5c2c1-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="5c2c1-154">O Gerenciador de estatísticas consiste nos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="5c2c1-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-155">**Agent.**</span></span> <span data-ttu-id="5c2c1-156">Um agente leve que é executado em cada servidor monitorado.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="5c2c1-157">O agente permite a sondagem de taxa alta configurável de contadores de desempenho com agregação local.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="5c2c1-158">**Ouvinte.**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-158">**Listener.**</span></span> <span data-ttu-id="5c2c1-159">A API do lado do servidor que recebe dados de todos os agentes e agrega dados em populações.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="5c2c1-160">**Borda.**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-160">**Hub.**</span></span> <span data-ttu-id="5c2c1-161">Funciona como a API do cliente para o sistema, é executada no (s) servidor (es) da Web e fornece atualizações de dados em tempo real para os clientes conectados pelo website.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="5c2c1-162">(O Hub é instalado automaticamente como parte do MSI do site.)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="5c2c1-163">**Site.**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-163">**Website.**</span></span> <span data-ttu-id="5c2c1-164">Uma interface de usuário que reúne todos os recursos disponíveis no sistema.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="5c2c1-165">Além disso, o Gerenciador de estatísticas requer o **Redis**, um servidor de estrutura de dados aberto em cache para cache na memória.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="5c2c1-166">Para obter mais informações sobre como baixar o Redis, consulte [implantar o Gerenciador de estatísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="5c2c1-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="5c2c1-167">Implantação local</span><span class="sxs-lookup"><span data-stu-id="5c2c1-167">On-premises deployment</span></span>
<span data-ttu-id="5c2c1-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="5c2c1-169">Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="5c2c1-170">O diagrama a seguir mostra uma implantação local, na qual o site do Gerenciador de estatísticas, o Hub, o ouvinte e o sistema de cache do Redis são hospedados em uma única máquina.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="5c2c1-171">O Gerenciador de estatísticas está monitorando três servidores do Skype for Business, cada um com um único agente que transmite dados para o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="5c2c1-172">Os usuários se conectam a um único site para exibir todos os dados agregados pelo Gerenciador de estatísticas:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implantação do Gerenciador de estatísticas local](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="5c2c1-174">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c2c1-174">Requirements</span></span>
<span data-ttu-id="5c2c1-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="5c2c1-176">Você precisará considerar os requisitos de software, rede e hardware a seguir antes de implantar o Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="5c2c1-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="5c2c1-177">Software requirements</span></span>

- <span data-ttu-id="5c2c1-178">Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="5c2c1-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="5c2c1-179">IIS (instalado automaticamente)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="5c2c1-180">Redis</span><span class="sxs-lookup"><span data-stu-id="5c2c1-180">Redis</span></span>

- <span data-ttu-id="5c2c1-181">Serviços do Gerenciador de estatísticas (instalado automaticamente)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="5c2c1-182">PSExec-necessário para a implantação de agente remoto</span><span class="sxs-lookup"><span data-stu-id="5c2c1-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="5c2c1-183">.NET 4,5 (incluído no 2012 R2)-necessário para agentes e componentes do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="5c2c1-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="5c2c1-184">Baixar o [Skype for Business Server, Gerenciador de estatística em tempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="5c2c1-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="5c2c1-185">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="5c2c1-185">Networking requirements</span></span>


|<span data-ttu-id="5c2c1-186">**Servidor de hospedagem**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-186">**Hosting server**</span></span>|<span data-ttu-id="5c2c1-187">**Agentes**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-187">**Agents**</span></span>|<span data-ttu-id="5c2c1-188">**Ouvinte**</span><span class="sxs-lookup"><span data-stu-id="5c2c1-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c2c1-189">Rede mínima Gigabit Full duplex.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="5c2c1-190">Porta TCP de saída 8443 (número da porta personalizável) para se comunicar com o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="5c2c1-191">A porta do ouvinte deve ser igual em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="5c2c1-192">Entrada de porta TCP 80 ou 443 aberta para hospedar o site.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="5c2c1-193">Porta TCP de entrada 8443 (número de porta personalizável) dos agentes para se comunicar com ele.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="5c2c1-194">Durante a instalação, as portas do firewall para o ouvinte e o site são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="5c2c1-195">Para os agentes, a instalação pressupõe que conexões TCP de saída são permitidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="5c2c1-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="5c2c1-196">Hardware requirements</span></span>

<span data-ttu-id="5c2c1-197">Em uma implantação local, na qual um único servidor hospeda todos os componentes do Gerenciador de estatísticas do lado do servidor, um servidor com 16 GB de RAM e 4 CPUs deve ser capaz de dar suporte a 150 exemplos por segundo, em média.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="5c2c1-198">Para determinar a quantos contadores/agentes você pode dar suporte, use o seguinte cálculo:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="5c2c1-199">servidores \*do 100 80 \* contadores 1 amostra por minuto de cada agente/60 segundos = ~ 133 amostras por segundo.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="5c2c1-200">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="5c2c1-200">Security considerations</span></span>
<span data-ttu-id="5c2c1-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5c2c1-202">Todo o tráfego entre servidores é criptografado.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="5c2c1-203">O tráfego HTTPS criptografado será enviado pela porta 8443 (por padrão) do agente para o servidor de ouvinte.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="5c2c1-204">O agente verificará a impressão digital SSL no servidor para garantir que o servidor de ouvintes seja o destinatário esperado.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="5c2c1-205">Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia).</span><span class="sxs-lookup"><span data-stu-id="5c2c1-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="5c2c1-206">Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="5c2c1-207">Depois que o agente estiver satisfeito, o ouvinte será autêntico, uma senha será apresentada pelo agente que então será verificado pela escuta.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="5c2c1-208">O agente começa a transmitir dados de desempenho pela conexão com o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="5c2c1-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="5c2c1-209">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="5c2c1-209">For more information</span></span>
<span data-ttu-id="5c2c1-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="5c2c1-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="5c2c1-211">Para obter mais informações, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5c2c1-211">For more information, see the following:</span></span>

- [<span data-ttu-id="5c2c1-212">Implantar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c2c1-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="5c2c1-213">Atualizar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c2c1-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="5c2c1-214">Solução de problemas do Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c2c1-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
