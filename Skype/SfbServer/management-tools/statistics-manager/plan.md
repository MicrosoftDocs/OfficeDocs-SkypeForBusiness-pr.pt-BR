---
title: Planejar o Gerenciador de estatísticas do Skype for Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f0ec68e1-de01-4a92-b67d-703149b05caf
description: 'Resumo: Leia este tópico para saber mais sobre o Gerenciador de estatísticas para Skype para Business Server.'
ms.openlocfilehash: 7e086dda9bfea755265d2c77413989f8cc634df7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236143"
---
# <a name="plan-for-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="8052d-103">Planejar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8052d-103">Plan for Statistics Manager for Skype for Business Server</span></span>

<span data-ttu-id="8052d-104">**Resumo:** Leia este tópico para saber mais sobre o Gerenciador de estatísticas para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8052d-104">**Summary:** Read this topic to learn about Statistics Manager for Skype for Business Server.</span></span>

 <span data-ttu-id="8052d-105">O Gerenciador de Estatísticas do Skype for Business Server é uma poderosa ferramenta que permite exibir o desempenho e a integridade do Skype for Business Server em tempo real.</span><span class="sxs-lookup"><span data-stu-id="8052d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="8052d-106">É possível sondar dados de desempenho em centenas de servidores em intervalos de alguns segundos e ver os resultados instantaneamente no site do Gerenciador de Estatísticas.</span><span class="sxs-lookup"><span data-stu-id="8052d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>

<span data-ttu-id="8052d-107">Você pode usar o Gerenciador de estatísticas para identificar problemas de desempenho em andamento, exiba os resultados de uma alteração planejada ao seu ambiente, para controlar a resolução de interrupções e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8052d-107">You can use Statistics Manager to identify ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="8052d-108">Imediato, gerente de estatísticas é configurado com limites de indicador de integridade de chave (KHI) e pode ser personalizado para atender às necessidades exclusivas da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="8052d-108">Out of the box, Statistics Manager is configured with Key Health Indicator (KHI) thresholds, and can be customized to suit your deployment's unique needs.</span></span>

<span data-ttu-id="8052d-109">Você pode implantar o Gerenciador de estatísticas em uma implantação no local em que um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor.</span><span class="sxs-lookup"><span data-stu-id="8052d-109">You can deploy Statistics Manager in an on-premises deployment in which a single server hosts all of the server-side Statistics Manager components.</span></span> <span data-ttu-id="8052d-110">Para obter mais informações sobre como implantar o Gerenciador de estatísticas, consulte [Implantar o Gerenciador de estatísticas para Skype para Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="8052d-110">For more information about deploying Statistics Manager, see [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span> <span data-ttu-id="8052d-111">Se você já tiver uma implantação existente do Gerenciador de estatísticas, mas você ainda não tiver atualizado para a versão 2.0, consulte [o que há de novo na versão 2.0](plan.md#BKMK_WhatsNew) e [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="8052d-111">If you already have an existing deployment of Statistics Manager, but you have not yet upgraded to Release 2.0, see [What's new in Release 2.0](plan.md#BKMK_WhatsNew) and [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

<span data-ttu-id="8052d-112">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="8052d-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="8052d-113">Recursos e capacidades</span><span class="sxs-lookup"><span data-stu-id="8052d-113">Features and capabilities</span></span>](plan.md#BKMK_Features)

- [<span data-ttu-id="8052d-114">O que há de novo na versão 2.0</span><span class="sxs-lookup"><span data-stu-id="8052d-114">What's new in Release 2.0</span></span>](plan.md#BKMK_WhatsNew)

- [<span data-ttu-id="8052d-115">Componentes</span><span class="sxs-lookup"><span data-stu-id="8052d-115">Components</span></span>](plan.md#BKMK_Components)

- [<span data-ttu-id="8052d-116">Implantação no local</span><span class="sxs-lookup"><span data-stu-id="8052d-116">On-premises deployment</span></span>](plan.md#BKMK_DeploymentOptions)

- [<span data-ttu-id="8052d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8052d-117">Requirements</span></span>](plan.md#BKMK_Requirements)

- [<span data-ttu-id="8052d-118">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="8052d-118">Security considerations</span></span>](plan.md#BKMK_Security)

## <a name="features-and-capabilities"></a><span data-ttu-id="8052d-119">Recursos e capacidades</span><span class="sxs-lookup"><span data-stu-id="8052d-119">Features and capabilities</span></span>
<span data-ttu-id="8052d-120"><a name="BKMK_Features"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-120"></span></span>

<span data-ttu-id="8052d-121">Gerenciador de estatísticas permite que você:</span><span class="sxs-lookup"><span data-stu-id="8052d-121">Statistics Manager allows you to:</span></span>

- <span data-ttu-id="8052d-122">Exibir dados brutos para todos os servidores em tempo real.</span><span class="sxs-lookup"><span data-stu-id="8052d-122">View raw data for all servers in real time.</span></span> <span data-ttu-id="8052d-123">(Dados em uma muito alta taxa de amostra e enviados para o site em menos de um segundo.)</span><span class="sxs-lookup"><span data-stu-id="8052d-123">(Data is sampled at a very high rate and sent to the website in less than one second.)</span></span>

- <span data-ttu-id="8052d-124">Exibir os dados que são agregados para uma função específica; Por exemplo, servidor Front-End, servidor de mediação, servidor de borda e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8052d-124">View data that is aggregated for a specific role; for example, Front End Server, Mediation Server, Edge Server, and so on.</span></span>

- <span data-ttu-id="8052d-125">Ver os detalhes de dados de modo de exibição de sites específicos, pools específicos dentro do site e os servidores, em seguida, específicos dentro do pool.</span><span class="sxs-lookup"><span data-stu-id="8052d-125">Drill down to view data for specific sites, specific pools within the site, and then specific servers within the pool.</span></span>

- <span data-ttu-id="8052d-126">Crie gráficos personalizados para escolhido contadores são mostrados por padrão.</span><span class="sxs-lookup"><span data-stu-id="8052d-126">Create custom charts so that chosen counters are shown by default.</span></span>

- <span data-ttu-id="8052d-127">Aplicar zoom e panorâmica em ambos o x e y-eixos ou no eixo x apenas.</span><span class="sxs-lookup"><span data-stu-id="8052d-127">Zoom and pan on both the x- and y- axes or on the x-axis only.</span></span>

- <span data-ttu-id="8052d-128">Use os intervalos de data ou pontos em tempo para filtrar dados.</span><span class="sxs-lookup"><span data-stu-id="8052d-128">Use date ranges or points in time to filter data.</span></span>

- <span data-ttu-id="8052d-129">Exibir o desempenho do servidor com base em indicadores de integridade de chave estabelecida (KHIs).</span><span class="sxs-lookup"><span data-stu-id="8052d-129">View server performance based on established key health indicators (KHIs).</span></span> <span data-ttu-id="8052d-130">KHIs representam um conjunto de contadores de desempenho com um intervalo definido de Íntegro.</span><span class="sxs-lookup"><span data-stu-id="8052d-130">KHIs represent a collection of performance counters with a defined healthy range.</span></span>

- <span data-ttu-id="8052d-131">Exiba métricas detalhadas de cada contador.</span><span class="sxs-lookup"><span data-stu-id="8052d-131">View detailed metrics for each counter.</span></span>

- <span data-ttu-id="8052d-132">Compare dados entre vários servidores ou população.</span><span class="sxs-lookup"><span data-stu-id="8052d-132">Compare data across multiple populations or servers.</span></span>

- <span data-ttu-id="8052d-133">Exibir relatórios de contador latente para identificar os operadores que não são relatórios dados atuais para o serviço de painel.</span><span class="sxs-lookup"><span data-stu-id="8052d-133">View latent counter reports to identify agents that are not reporting current data to the dashboard service.</span></span>

- <span data-ttu-id="8052d-134">Salve uma instância específica de dados do gráfico em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8052d-134">Save a particular instance of chart data to a file.</span></span>

- <span data-ttu-id="8052d-135">Modo de exibição KHIs em tempo real, incluindo atualizações.</span><span class="sxs-lookup"><span data-stu-id="8052d-135">View KHIs in real time, including updates.</span></span> <span data-ttu-id="8052d-136">Se o modo de exibição de histórico estiver habilitado, apenas novas falhas são mostradas.</span><span class="sxs-lookup"><span data-stu-id="8052d-136">If the history view is enabled, only new failures are shown.</span></span>

  - <span data-ttu-id="8052d-137">Exibir todos os KHIs ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="8052d-137">View all KHIs at one time</span></span>

  - <span data-ttu-id="8052d-138">Exibir KHIs pelo servidor (modo paisagem)</span><span class="sxs-lookup"><span data-stu-id="8052d-138">View KHIs by server (Landscape view)</span></span>

  - <span data-ttu-id="8052d-139">Exibir KHI definições</span><span class="sxs-lookup"><span data-stu-id="8052d-139">View KHI definitions</span></span>

## <a name="whats-new-in-release-20"></a><span data-ttu-id="8052d-140">O que há de novo na versão 2.0</span><span class="sxs-lookup"><span data-stu-id="8052d-140">What's new in Release 2.0</span></span>
<span data-ttu-id="8052d-141"><a name="BKMK_WhatsNew"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-141"></span></span>

<span data-ttu-id="8052d-142">O exemplo a seguir descreve o que há de novo na versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="8052d-142">The following describes what's new in Release 2.0.</span></span> <span data-ttu-id="8052d-143">Se você tiver uma implantação existente do Gerenciador de estatísticas e você ainda não tiver atualizado, consulte [Atualizar o Gerenciador de estatísticas para Skype para Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="8052d-143">If you have an existing deployment of Statistics Manager and you've not yet upgraded, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span>

- <span data-ttu-id="8052d-144">Modos de exibição do cenário foram adicionados para a mídia de borda, integridade malha, Failover de Pool e cenários de registro.</span><span class="sxs-lookup"><span data-stu-id="8052d-144">Scenario views have been added for Edge Media, Fabric Health, Pool Failover and Registration scenarios.</span></span>

- <span data-ttu-id="8052d-145">Muitos novos contadores foram adicionados para SQL servers, mais Skype contadores de uso de negócios e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="8052d-145">Many new counters have been added for SQL servers, more Skype for Business usage counters, and so on.</span></span>

- <span data-ttu-id="8052d-146">Integração do nó de inspetor para o agente do Gerenciador de estatísticas - se o agente está instalado em um nó de Inspetor, ele reportará estatísticas de transação sintética como contadores ao Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="8052d-146">Watcher node integration for the Statistics Manager Agent - if the Agent is installed on a watcher node, it will report synthetic transaction statistics as counters back to Statistics Manager.</span></span>

- <span data-ttu-id="8052d-147">Diversos aperfeiçoamentos de desempenho e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="8052d-147">Numerous reliability and performance improvements.</span></span>

<span data-ttu-id="8052d-148">Para verificar a versão do site do Gerenciador de estatísticas você está executando:</span><span class="sxs-lookup"><span data-stu-id="8052d-148">To verify the version of the Statistics Manager Website you are running:</span></span>

- <span data-ttu-id="8052d-149">No Gerenciador de arquivos, abra (diretório padrão) C:\Program Files\Skype para Business Server StatsMan WebSite\bin</span><span class="sxs-lookup"><span data-stu-id="8052d-149">In File Explorer, open (default directory) C:\Program Files\Skype for Business Server StatsMan WebSite\bin</span></span>

- <span data-ttu-id="8052d-150">Clique com o botão direito em StatsManHubWebSite.dll e exiba suas propriedades</span><span class="sxs-lookup"><span data-stu-id="8052d-150">Right click on StatsManHubWebSite.dll and view its properties</span></span>

- <span data-ttu-id="8052d-151">A versão do produto será mostrada nos detalhes de Descrição.</span><span class="sxs-lookup"><span data-stu-id="8052d-151">The product version will be shown in the Description details.</span></span>

## <a name="components"></a><span data-ttu-id="8052d-152">Componentes</span><span class="sxs-lookup"><span data-stu-id="8052d-152">Components</span></span>
<span data-ttu-id="8052d-153"><a name="BKMK_Components"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-153"></span></span>

<span data-ttu-id="8052d-154">Gerenciador de estatísticas consiste dos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="8052d-154">Statistics Manager consists of the following components:</span></span>

- <span data-ttu-id="8052d-155">**Agente.**</span><span class="sxs-lookup"><span data-stu-id="8052d-155">**Agent.**</span></span> <span data-ttu-id="8052d-156">Um agente leve executado em cada servidor monitorado.</span><span class="sxs-lookup"><span data-stu-id="8052d-156">A lightweight agent that runs on each monitored server.</span></span> <span data-ttu-id="8052d-157">O agente permite sondagem configurável alta taxa de contadores de desempenho com a agregação de local.</span><span class="sxs-lookup"><span data-stu-id="8052d-157">The Agent allows configurable high rate polling of performance counters with local aggregation.</span></span>

- <span data-ttu-id="8052d-158">**Ouvinte.**</span><span class="sxs-lookup"><span data-stu-id="8052d-158">**Listener.**</span></span> <span data-ttu-id="8052d-159">A API de lado do servidor que recebe os dados de todos os operadores e agrega os dados população.</span><span class="sxs-lookup"><span data-stu-id="8052d-159">The server side API that receives data from all Agents, and aggregates data across populations.</span></span>

- <span data-ttu-id="8052d-160">**Hub.**</span><span class="sxs-lookup"><span data-stu-id="8052d-160">**Hub.**</span></span> <span data-ttu-id="8052d-161">Serve como a API do cliente para o sistema, é executado em todos os servidores web e fornece as atualizações de dados em tempo real para os clientes conectados por meio do site.</span><span class="sxs-lookup"><span data-stu-id="8052d-161">Serves as the client API for the system, runs on the web server(s), and provides real-time data updates to clients connected via the website.</span></span> <span data-ttu-id="8052d-162">(O Hub é instalado automaticamente como parte do msi do site).</span><span class="sxs-lookup"><span data-stu-id="8052d-162">(The Hub is automatically installed as part of the Website msi.)</span></span>

- <span data-ttu-id="8052d-163">**Site da Web.**</span><span class="sxs-lookup"><span data-stu-id="8052d-163">**Website.**</span></span> <span data-ttu-id="8052d-164">Uma interface de usuário que reúne todos os recursos disponíveis no sistema.</span><span class="sxs-lookup"><span data-stu-id="8052d-164">A user interface that pulls together all the features available in the system.</span></span>

<span data-ttu-id="8052d-165">Além disso, o Gerenciador de estatísticas requer **relacionada**, um servidor de estrutura de dados de código aberto para armazenar em cache na memória.</span><span class="sxs-lookup"><span data-stu-id="8052d-165">In addition, Statistics Manager requires **Redis**, an open-sourced data structure server for in-memory caching.</span></span> <span data-ttu-id="8052d-166">Para obter mais informações sobre como baixar relacionada, consulte [Implantar o Gerenciador de estatísticas](deploy.md#BKMK_Deploy) .</span><span class="sxs-lookup"><span data-stu-id="8052d-166">For more information about downloading Redis, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy) .</span></span>

## <a name="on-premises-deployment"></a><span data-ttu-id="8052d-167">Implantação no local</span><span class="sxs-lookup"><span data-stu-id="8052d-167">On-premises deployment</span></span>
<span data-ttu-id="8052d-168"><a name="BKMK_DeploymentOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-168"></span></span>

<span data-ttu-id="8052d-169">Em uma implantação local, um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor.</span><span class="sxs-lookup"><span data-stu-id="8052d-169">In an on-premises deployment, a single server hosts all of the server-side Statistics Manager components.</span></span>

<span data-ttu-id="8052d-170">O diagrama a seguir mostra uma implantação local, no qual o site do Gerenciador de estatísticas, Hub, ouvinte e relacionada no sistema de armazenamento em cache são hospedados em uma única máquina.</span><span class="sxs-lookup"><span data-stu-id="8052d-170">The following diagram shows an on-premises deployment, in which the Statistics Manager Website, Hub, Listener, and Redis caching system are hosted on a single machine.</span></span> <span data-ttu-id="8052d-171">Gerenciador de estatísticas está monitorando três Skype para servidores de negócios, cada um deles têm um único operador transmitir dados para o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8052d-171">Statistics Manager is monitoring three Skype for Business servers, each of which have a single Agent transmitting data to the Listener.</span></span> <span data-ttu-id="8052d-172">Os usuários se conectar a um único site para exibir todos os dados agregados pelo Gerenciador de estatísticas:</span><span class="sxs-lookup"><span data-stu-id="8052d-172">Users connect to a single Website to view all data aggregated by Statistics Manager:</span></span>

![Implantação do Stats Manager local](../../media/c7c9d0b5-a70b-4d8c-aec4-0128a29b90b6.png)

## <a name="requirements"></a><span data-ttu-id="8052d-174">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8052d-174">Requirements</span></span>
<span data-ttu-id="8052d-175"><a name="BKMK_Requirements"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-175"></span></span>

<span data-ttu-id="8052d-176">Você precisará considerar os seguintes requisitos de hardware, software e rede antes de implantar o Gerenciador de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="8052d-176">You will need to consider the following software, networking, and hardware requirements before you deploy Statistics Manager.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="8052d-177">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="8052d-177">Software requirements</span></span>

- <span data-ttu-id="8052d-178">Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="8052d-178">Windows Server 2016 and 2019</span></span>

- <span data-ttu-id="8052d-179">IIS (instalado automaticamente)</span><span class="sxs-lookup"><span data-stu-id="8052d-179">IIS (automatically installed)</span></span>

- <span data-ttu-id="8052d-180">Relacionada</span><span class="sxs-lookup"><span data-stu-id="8052d-180">Redis</span></span>

- <span data-ttu-id="8052d-181">Serviços do Gerenciador de estatísticas (instalados automaticamente)</span><span class="sxs-lookup"><span data-stu-id="8052d-181">Statistics Manager services (automatically installed)</span></span>

- <span data-ttu-id="8052d-182">PSExec - necessário para fazer a implantação do agente remoto</span><span class="sxs-lookup"><span data-stu-id="8052d-182">PSExec - Required to do remote agent deployment</span></span>

- <span data-ttu-id="8052d-183">.NET 4.5 (incluído no 2012 R2) - necessário para agentes e componentes de servidor</span><span class="sxs-lookup"><span data-stu-id="8052d-183">.NET 4.5 (included with 2012 R2) - Required for agents and server-side components</span></span>
- <span data-ttu-id="8052d-184">Baixe o [Skype para Business Server, gerente de estatísticas em tempo real (64 bits)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span><span class="sxs-lookup"><span data-stu-id="8052d-184">Download the [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="8052d-185">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="8052d-185">Networking requirements</span></span>


|<span data-ttu-id="8052d-186">**Servidor de hospedagem**</span><span class="sxs-lookup"><span data-stu-id="8052d-186">**Hosting server**</span></span>|<span data-ttu-id="8052d-187">**Agentes**</span><span class="sxs-lookup"><span data-stu-id="8052d-187">**Agents**</span></span>|<span data-ttu-id="8052d-188">**Ouvinte**</span><span class="sxs-lookup"><span data-stu-id="8052d-188">**Listener**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8052d-189">Rede de gigabit mínimo full-duplex.</span><span class="sxs-lookup"><span data-stu-id="8052d-189">Minimum gigabit full duplex networking.</span></span>  <br/> |<span data-ttu-id="8052d-190">Porta TCP de saída 8443 (número de porta personalizável) para se comunicar com o ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8052d-190">Outbound TCP port 8443 (customizable port number) to communicate with the Listener.</span></span>  <br/> |<span data-ttu-id="8052d-191">A porta de escuta deve ser o mesmo em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="8052d-191">The Listener port must be the same on all servers.</span></span>  <br/> |
|<span data-ttu-id="8052d-192">A porta TCP 80 ou 443 open para hospedar o site de entrada.</span><span class="sxs-lookup"><span data-stu-id="8052d-192">Inbound TCP port 80 or 443 open to host the website.</span></span>  <br/> |||
|<span data-ttu-id="8052d-193">Porta TCP 8443 (número de porta personalizável) de entrada para os agentes de se comunicar com ele.</span><span class="sxs-lookup"><span data-stu-id="8052d-193">Inbound TCP port 8443 (customizable port number) for the agents to communicate with it.</span></span>  <br/> |||

<span data-ttu-id="8052d-194">Durante a instalação, portas de firewall para o ouvinte e o site da Web são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8052d-194">During installation, firewall ports for the Listener and the Website are automatically created.</span></span> <span data-ttu-id="8052d-195">Para os agentes, a instalação pressupõe que as conexões TCP de saída são permitidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="8052d-195">For the Agents, the installation assumes that outbound TCP connections are allowed by default.</span></span>

### <a name="hardware-requirements"></a><span data-ttu-id="8052d-196">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="8052d-196">Hardware requirements</span></span>

<span data-ttu-id="8052d-197">Em uma implantação local, em que um único servidor hospeda todos os componentes do Gerenciador de estatísticas do servidor, um servidor com 16 GB de RAM e 4 CPU deve ser capaz de suportar cerca de 150 amostras por segundo em média.</span><span class="sxs-lookup"><span data-stu-id="8052d-197">In an on-premises deployment, in which a single server hosts all of the server-side Statistics Manager components, a server with 16 GB of RAM and 4 CPU's should be able to support about 150 samples per second on average.</span></span> <span data-ttu-id="8052d-198">Para determinar quantos contadores/agentes que você pode oferecer suporte, use o seguinte cálculo:</span><span class="sxs-lookup"><span data-stu-id="8052d-198">To determine how many counters/agents you can support, use the following calculation:</span></span>

<span data-ttu-id="8052d-199">100 servidores \*80 contadores \* 1 amostra por minuto de cada agente / 60 segundos = ~ 133 amostras por segundo.</span><span class="sxs-lookup"><span data-stu-id="8052d-199">100 servers \*80 counters \* 1 sample per minute from each agent / 60 seconds = ~ 133 samples per second.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="8052d-200">Considerações de segurança</span><span class="sxs-lookup"><span data-stu-id="8052d-200">Security considerations</span></span>
<span data-ttu-id="8052d-201"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-201"></span></span>

<span data-ttu-id="8052d-202">Todo o tráfego entre os servidores é criptografado.</span><span class="sxs-lookup"><span data-stu-id="8052d-202">All traffic between servers is encrypted.</span></span>

- <span data-ttu-id="8052d-203">Tráfego HTTPS criptografado será enviado através da porta 8443 (por padrão) do agente para o servidor de ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8052d-203">Encrypted HTTPS traffic will be sent over port 8443 (by default) from the Agent to the Listener server.</span></span>

- <span data-ttu-id="8052d-204">O agente verificará a impressão digital SSL no servidor para garantir que o servidor de ouvinte é o destinatário esperado.</span><span class="sxs-lookup"><span data-stu-id="8052d-204">The Agent will verify the SSL thumbprint on the server to ensure the Listener server is the expected recipient.</span></span> <span data-ttu-id="8052d-205">Observe que o Agente utiliza a verificação de impressão digital do certificado (em vez de verificação de cadeia).</span><span class="sxs-lookup"><span data-stu-id="8052d-205">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="8052d-206">Ele não fará a validação completa do certificado, pois é possível usar certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="8052d-206">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>

- <span data-ttu-id="8052d-207">Depois que o agente está satisfeito o ouvinte é autêntico, uma senha será apresentada pelo agente que depois é verificado pelo ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8052d-207">After the Agent is satisfied the Listener is authentic, a password will be presented by the Agent which is then verified by the Listener.</span></span>

- <span data-ttu-id="8052d-208">O agente começa a transmissão de dados de desempenho pela conexão ao ouvinte.</span><span class="sxs-lookup"><span data-stu-id="8052d-208">The Agent begins transmitting performance data over the connection to the Listener.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8052d-209">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="8052d-209">For more information</span></span>
<span data-ttu-id="8052d-210"><a name="BKMK_Security"> </a></span><span class="sxs-lookup"><span data-stu-id="8052d-210"></span></span>

<span data-ttu-id="8052d-211">Para obter mais informações, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8052d-211">For more information, see the following:</span></span>

- [<span data-ttu-id="8052d-212">Implantar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8052d-212">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)

- [<span data-ttu-id="8052d-213">Atualizar o Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8052d-213">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)

- [<span data-ttu-id="8052d-214">Solução de problemas do Gerenciador de estatísticas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8052d-214">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
