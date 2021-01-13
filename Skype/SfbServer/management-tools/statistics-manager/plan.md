---
title: Planejar o Gerenciador de Estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de Estatísticas do Skype for Business Server.'
ms.openlocfilehash: cdc536abcbd1bd98c4a3c7ce974247a716865582
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821821"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="38798-103">Planejar o Gerenciador de Estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38798-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="38798-104">**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de Estatísticas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="38798-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="38798-105">O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir dados de desempenho e de saúde do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="38798-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="38798-106">Você pode sondar dados de desempenho em centenas de servidores a cada poucos segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="38798-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="38798-107">Você pode usar o Gerenciador de Estatísticas para identificar problemas de desempenho contínuos, exibir os resultados de uma alteração planejada em seu ambiente, controlar a resolução de paralisações e muito mais.</span><span class="sxs-lookup"><span data-stu-id="38798-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="38798-108">O Gerenciador de Estatísticas está configurado com limites de KHI (Indicador Chave de Saúde) e pode ser personalizado de acordo com as necessidades exclusivas da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="38798-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="38798-109">Você pode implantar o Gerenciador de Estatísticas em uma implantação local na qual um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="38798-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="38798-110">Para obter mais informações sobre como implantar o Gerenciador de Estatísticas, consulte [Implantar o Gerenciador de Estatísticas do Skype for Business Server.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="38798-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="38798-111">Se você já tiver uma implantação existente do Gerenciador de Estatísticas, mas ainda não tiver atualizado para a versão 2.0, consulte Novidades na versão [2.0](plan.md#BKMK_WhatsNew) e Atualize o Gerenciador de Estatísticas do [Skype for Business Server.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="38798-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="38798-112">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="38798-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="38798-113">Recursos</span><span class="sxs-lookup"><span data-stu-id="38798-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="38798-114">Novidades na versão 2.0</span><span class="sxs-lookup"><span data-stu-id="38798-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="38798-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="38798-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="38798-116">Implantação no local</span><span class="sxs-lookup"><span data-stu-id="38798-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="38798-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38798-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="38798-118">Considerações sobre segurança</span><span class="sxs-lookup"><span data-stu-id="38798-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="38798-119">Recursos</span><span class="sxs-lookup"><span data-stu-id="38798-119">Features and capabilities</span></span>
<span data-ttu-id="38798-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-120"><a name="BKMK_Features"> </a></span></span>

<span data-ttu-id="38798-121">O Gerenciador de Estatísticas permite que você:</span><span class="sxs-lookup"><span data-stu-id="38798-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="38798-122">Exibir dados brutos de todos os servidores em tempo real.</span><span class="sxs-lookup"><span data-stu-id="38798-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="38798-123">(Os dados são amostrados a uma taxa muito alta e enviados ao site em menos de um segundo.)</span><span class="sxs-lookup"><span data-stu-id="38798-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="38798-124">Exibir dados agregados para uma função específica; por exemplo, Servidor Front-End, Servidor de Mediação, Servidor de Borda e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="38798-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="38798-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span><span class="sxs-lookup"><span data-stu-id="38798-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="38798-126">Crie gráficos personalizados para que os contadores escolhidos sejam mostrados por padrão.</span><span class="sxs-lookup"><span data-stu-id="38798-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="38798-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span><span class="sxs-lookup"><span data-stu-id="38798-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="38798-128">Use intervalos de datas ou pontos no tempo para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="38798-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="38798-129">Exibir o desempenho do servidor com base nos principais indicadores de saúde (KHIs) estabelecidos.</span><span class="sxs-lookup"><span data-stu-id="38798-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="38798-130">KHIs representam uma coleção de contadores de desempenho com um intervalo almente definido.</span><span class="sxs-lookup"><span data-stu-id="38798-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="38798-131">Exibir métricas detalhadas para cada contador.</span><span class="sxs-lookup"><span data-stu-id="38798-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="38798-132">Compare dados entre várias populações ou servidores.</span><span class="sxs-lookup"><span data-stu-id="38798-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="38798-133">Exibir relatórios de contador latentes para identificar agentes que não estão relatando dados atuais para o serviço de painel.</span><span class="sxs-lookup"><span data-stu-id="38798-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="38798-134">Salve uma instância específica dos dados do gráfico em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="38798-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="38798-135">Exibir KHIs em tempo real, incluindo atualizações.</span><span class="sxs-lookup"><span data-stu-id="38798-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="38798-136">Se o modo de exibição de histórico estiver habilitado, somente novas falhas serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="38798-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="38798-137">Exibir todos os KHIs de uma só vez</span><span class="sxs-lookup"><span data-stu-id="38798-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="38798-138">Exibir KHIs por servidor (exibição paisagem)</span><span class="sxs-lookup"><span data-stu-id="38798-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="38798-139">Exibir definições de KHI</span><span class="sxs-lookup"><span data-stu-id="38798-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="38798-140">Novidades na versão 2.0</span><span class="sxs-lookup"><span data-stu-id="38798-140">What's new in Release 2.0</span></span>
<span data-ttu-id="38798-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-141"><a name="BKMK_WhatsNew"> </a></span></span>

<span data-ttu-id="38798-142">O exemplo a seguir descreve as novidades da versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="38798-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="38798-143">Se você tiver uma implantação existente do Gerenciador de Estatísticas e ainda não tiver atualizado, consulte Atualizar o Gerenciador de Estatísticas do [Skype for Business Server.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="38798-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="38798-144">As exibições de cenário foram adicionadas para cenários de Mídia de Borda, Fabric Health, Failover de Pool e Registro.</span><span class="sxs-lookup"><span data-stu-id="38798-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="38798-145">Muitos contadores novos foram adicionados para servidores SQL, mais contadores de uso do Skype for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="38798-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="38798-146">Integração do nó do watcher para o Agente do Gerenciador de Estatísticas - se o Agente estiver instalado em um nó do watcher, ele relatará estatísticas de transação sintética como contadores de volta para o Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="38798-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="38798-147">Vários aprimoramentos de confiabilidade e desempenho.</span><span class="sxs-lookup"><span data-stu-id="38798-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="38798-148">Para verificar a versão do site do Gerenciador de Estatísticas que você está executando:</span><span class="sxs-lookup"><span data-stu-id="38798-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="38798-149">No Explorador de Arquivos, abra (diretório padrão) C:\Arquivos de Programas\Skype for Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="38798-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="38798-150">Clique com o botão direito do StatsManHubWebSite.dll e veja suas propriedades</span><span class="sxs-lookup"><span data-stu-id="38798-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="38798-151">A versão do produto será mostrada nos detalhes de Descrição.</span><span class="sxs-lookup"><span data-stu-id="38798-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="38798-152">Componentes</span><span class="sxs-lookup"><span data-stu-id="38798-152">Components</span></span>
<span data-ttu-id="38798-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-153"><a name="BKMK_Components"> </a></span></span>

<span data-ttu-id="38798-154">O Gerenciador de Estatísticas consiste nos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="38798-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="38798-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="38798-155">**Agent.**</span></span> <span data-ttu-id="38798-156">Um agente leve que é executado em cada servidor monitorado.</span><span class="sxs-lookup"><span data-stu-id="38798-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="38798-157">O Agente permite sondagem de alta taxa configurável de contadores de desempenho com agregação local.</span><span class="sxs-lookup"><span data-stu-id="38798-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="38798-158">**Ouvinte.**</span><span class="sxs-lookup"><span data-stu-id="38798-158">**Listener.**</span></span> <span data-ttu-id="38798-159">A API do lado do servidor que recebe dados de todos os Agentes e agrega dados entre populações.</span><span class="sxs-lookup"><span data-stu-id="38798-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="38798-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="38798-160">**Hub.**</span></span> <span data-ttu-id="38798-161">Serve como a API do cliente para o sistema, é executado nos servidores Web e fornece atualizações de dados em tempo real para clientes conectados por meio do site.</span><span class="sxs-lookup"><span data-stu-id="38798-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="38798-162">(O Hub é instalado automaticamente como parte do site msi.)</span><span class="sxs-lookup"><span data-stu-id="38798-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="38798-163">**Site.**</span><span class="sxs-lookup"><span data-stu-id="38798-163">**Website.**</span></span> <span data-ttu-id="38798-164">Uma interface do usuário que reúne todos os recursos disponíveis no sistema.</span><span class="sxs-lookup"><span data-stu-id="38798-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="38798-165">Além disso, o Gerenciador de Estatísticas requer **o Redis**, um servidor de estrutura de dados de código aberto para armazenamento em cache na memória.</span><span class="sxs-lookup"><span data-stu-id="38798-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="38798-166">Para obter mais informações sobre como baixar o Redis, [consulte Implantar o Gerenciador de Estatísticas.](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="38798-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="38798-167">Implantação no local</span><span class="sxs-lookup"><span data-stu-id="38798-167">On-premises deployment</span></span>
<span data-ttu-id="38798-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-168"><a name="BKMK_DeploymentOptions"> </a></span></span>

<span data-ttu-id="38798-169">Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="38798-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="38798-170">O diagrama a seguir mostra uma implantação local, na qual o site do Gerenciador de Estatísticas, o Hub, o Ouvinte e o sistema de cache redis estão hospedados em um único computador.</span><span class="sxs-lookup"><span data-stu-id="38798-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="38798-171">O Gerenciador de Estatísticas está monitorando três servidores do Skype for Business, cada um deles com um único Agente transmitindo dados para o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="38798-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="38798-172">Os usuários se conectam a um único site para exibir todos os dados agregados pelo Gerenciador de Estatísticas:</span><span class="sxs-lookup"><span data-stu-id="38798-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implantação local do Gerenciador de Estatísticas](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="38798-174">Requirements</span><span class="sxs-lookup"><span data-stu-id="38798-174">Requirements</span></span>
<span data-ttu-id="38798-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-175"><a name="BKMK_Requirements"> </a></span></span>

<span data-ttu-id="38798-176">Você precisará considerar os seguintes requisitos de software, rede e hardware antes de implantar o Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="38798-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="38798-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="38798-177">Software requirements</span></span>

- <span data-ttu-id="38798-178">Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="38798-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="38798-179">IIS (instalado automaticamente)</span><span class="sxs-lookup"><span data-stu-id="38798-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="38798-180">Redis</span><span class="sxs-lookup"><span data-stu-id="38798-180">Redis</span></span>

- <span data-ttu-id="38798-181">Serviços do Gerenciador de Estatísticas (instalados automaticamente)</span><span class="sxs-lookup"><span data-stu-id="38798-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="38798-182">PSExec - Necessário para fazer a implantação do agente remoto</span><span class="sxs-lookup"><span data-stu-id="38798-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="38798-183">.NET 4.5 (incluído no 2012 R2) - Necessário para agentes e componentes do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="38798-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="38798-184">Baixar o [Skype for Business Server, Real-Time Statistics Manager (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="38798-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="38798-185">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="38798-185">Networking requirements</span></span>


|<span data-ttu-id="38798-186">**Servidor de hospedagem**</span><span class="sxs-lookup"><span data-stu-id="38798-186">**Hosting server**</span></span>|<span data-ttu-id="38798-187">**Agentes**</span><span class="sxs-lookup"><span data-stu-id="38798-187">**Agents**</span></span>|<span data-ttu-id="38798-188">**Ouvinte**</span><span class="sxs-lookup"><span data-stu-id="38798-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38798-189">Rede full duplex de gigabit mínima.</span><span class="sxs-lookup"><span data-stu-id="38798-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="38798-190">Porta TCP de saída 8443 (número de porta personalizável) para se comunicar com o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="38798-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="38798-191">A porta ouvinte deve ser a mesma em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="38798-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="38798-192">Porta TCP de entrada 80 ou 443 aberta para hospedar o site.</span><span class="sxs-lookup"><span data-stu-id="38798-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="38798-193">Porta TCP de entrada 8443 (número da porta personalizável) para os agentes se comunicarem com ela.</span><span class="sxs-lookup"><span data-stu-id="38798-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="38798-194">Durante a instalação, as portas de firewall para o Ouvinte e o Site são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38798-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="38798-195">Para os Agentes, a instalação supõe que as conexões TCP de saída são permitidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="38798-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="38798-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="38798-196">Hardware requirements</span></span>

<span data-ttu-id="38798-197">Em uma implantação local, na qual um único servidor hospeda todos os componentes do Gerenciador de Estatísticas do lado do servidor, um servidor com 16 GB de RAM e 4 CPU deve ser capaz de suportar cerca de 150 amostras por segundo em média.</span><span class="sxs-lookup"><span data-stu-id="38798-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="38798-198">Para determinar quantos contadores/agentes você pode suportar, use o seguinte cálculo:</span><span class="sxs-lookup"><span data-stu-id="38798-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="38798-199">100 servidores 80 contadores 1 amostra por minuto de cada agente \* \* / 60 segundos = ~ 133 amostras por segundo.</span><span class="sxs-lookup"><span data-stu-id="38798-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="38798-200">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="38798-200">Security considerations</span></span>
<span data-ttu-id="38798-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-201"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="38798-202">Todo o tráfego entre servidores é criptografado.</span><span class="sxs-lookup"><span data-stu-id="38798-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="38798-203">O tráfego HTTPS criptografado será enviado pela porta 8443 (por padrão) do Agente para o servidor Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="38798-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="38798-204">O Agente verificará a impressão digital SSL no servidor para garantir que o servidor Ouvinte seja o destinatário esperado.</span><span class="sxs-lookup"><span data-stu-id="38798-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="38798-205">Observe que o Agente usa a verificação de impressão digital do certificado (em vez de verificação em cadeia).</span><span class="sxs-lookup"><span data-stu-id="38798-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="38798-206">Ele não fará a validação completa do certificado porque é possível usar certificados auto-assinados.</span><span class="sxs-lookup"><span data-stu-id="38798-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="38798-207">Depois que o Agente estiver satisfeito com a autenticidade do Ouvinte, uma senha será apresentada pelo Agente que, em seguida, será verificada pelo Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="38798-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="38798-208">O Agente começa a transmitir dados de desempenho pela conexão com o Ouvinte.</span><span class="sxs-lookup"><span data-stu-id="38798-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="38798-209">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="38798-209">For more information</span></span>
<span data-ttu-id="38798-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="38798-210"><a name="BKMK_Security"> </a></span></span>

<span data-ttu-id="38798-211">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="38798-211">For more information, see the following:</span></span>

- [<span data-ttu-id="38798-212">Implantar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38798-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="38798-213">Atualizar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38798-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="38798-214">Solução de problemas do Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="38798-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
