---
title: 'Lync Server 2013: configuração de integridade no Lync Server'
description: 'Lync Server 2013: configuração de integridade no Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552847"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="f764c-103">Configuração de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f764c-103">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f764c-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f764c-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f764c-105">Entre vários sites, artigos da base de conhecimento da Microsoft e ferramentas do Lync Server Resource Kit, os administradores que encontram problemas ao executar o Lync Server nunca estão longe de uma maneira de resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="f764c-105">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="f764c-106">Obviamente, não há uma maneira de garantir que você nunca encontrará problemas no Lync Server 2013 porque o Lync Server pode ser afetado por muitas coisas, como falhas de rede e falhas de hardware, que o próprio produto não pode controlar.</span><span class="sxs-lookup"><span data-stu-id="f764c-106">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="f764c-107">Ao implementar o monitoramento de integridade, os administradores podem identificar problemas potenciais antes que se transformem em problemas reais.</span><span class="sxs-lookup"><span data-stu-id="f764c-107">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="f764c-108">Por exemplo, os administradores podem usar o monitoramento do Lync Server para identificar tendências e Tendencies.</span><span class="sxs-lookup"><span data-stu-id="f764c-108">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="f764c-109">Por exemplo, um aumento contínuo no número de conferências de áudio/vídeo pode indicar uma necessidade de adicionar mais capacidade antes do sistema ficar sobrecarregado.</span><span class="sxs-lookup"><span data-stu-id="f764c-109">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="f764c-110">De modo semelhante, os administradores podem usar o System Center Operations Manager para fazer coisas como emitir alertas em tempo real quando os eventos especificados ocorrerem e executar transações sintéticas que testem proativamente o sistema.</span><span class="sxs-lookup"><span data-stu-id="f764c-110">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="f764c-111">As transações sintéticas são usadas no Lync Server para verificar se os usuários podem concluir com êxito tarefas comuns, como fazer logon no sistema, trocar mensagens instantâneas ou fazer chamadas a um telefone localizado na rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="f764c-111">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="f764c-112">Por exemplo, a execução periódica desses testes pode alertá-lo sobre possíveis problemas com os usuários que fazem logon no Lync Server e lhe dá a oportunidade de corrigir o problema antes que a equipe de suporte seja inundada com chamadas de usuários que não podem fazer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f764c-112">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="f764c-113">Usando o System Center Operations Manager para executar essas transações sintéticas, os administradores podem monitorar rotineiramente sua implantação do Lync Server continuamente por 24 horas por dia, sem ter que fazer muito nada além de responder a qualquer alerta que possa ser emitido.</span><span class="sxs-lookup"><span data-stu-id="f764c-113">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f764c-114">Para o Lync Server 2013, o pacote de gerenciamento do System Center Operations Manager também é capaz de detectar problemas "externos" que podem afetar adversamente o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f764c-114">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="f764c-115">Por exemplo, os administradores podem ser notificados se o IIS (serviços de informações da Internet) ficar offline, os recursos do sistema em um computador do Lync Server estiverem abaixo de uma quantidade específica ou se um computador do Lync Server apresentar uma falha de hardware.</span><span class="sxs-lookup"><span data-stu-id="f764c-115">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="f764c-116">A configuração de integridade no Lync Server 2013 é criada sobre o System Center Operations Manager e o uso de pacotes de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f764c-116">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="f764c-117">Esses Pacotes de gerenciamento incluem um número de novos recursos e aprimoramentos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f764c-117">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="f764c-118">**Disponibilidade de cenário de qualquer local.**</span><span class="sxs-lookup"><span data-stu-id="f764c-118">**Scenario availability from any location.**</span></span> <span data-ttu-id="f764c-119">O pacote de gerenciamento do Lync Server 2010 introduziu o conceito de monitoramento da disponibilidade de cenário do usuário final com transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="f764c-119">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="f764c-120">No Lync Server 2013, esses agentes têm mais transações sintéticas e podem ser executados a partir de uma variedade de locais dentro da empresa, de locais geográficos remotos fora da empresa, em filiais de escritório e em implantações do Lync Server 2010 para adicionar cobertura a implantações de borda herdadas.</span><span class="sxs-lookup"><span data-stu-id="f764c-120">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="f764c-121">**Logs de transação sintéticos.**</span><span class="sxs-lookup"><span data-stu-id="f764c-121">**Synthetic transaction logs.**</span></span> <span data-ttu-id="f764c-122">Quando uma transação sintética falhar, os administradores têm acesso a logs HTML para ajudar a determinar onde está a falha.</span><span class="sxs-lookup"><span data-stu-id="f764c-122">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="f764c-123">Isso inclui entender que ação falhou, a latência de cada ação, a linha de comando usado para executar o teste e o erro encontrado.</span><span class="sxs-lookup"><span data-stu-id="f764c-123">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="f764c-124">**Maior cobertura de confiabilidade de chamada.**</span><span class="sxs-lookup"><span data-stu-id="f764c-124">**Increased call reliability coverage.**</span></span> <span data-ttu-id="f764c-125">O pacote de gerenciamento do Lync Server 2010 introduziu o alerta de confiabilidade de chamada para detectar problemas de conectividade sérios que afetam as chamadas de áudio de usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f764c-125">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="f764c-126">Os pacotes de gerenciamento do Lync Server 2013 adicionam cobertura para mensagens instantâneas de ponto a ponto (IM) e outros recursos básicos de conferência para maximizar a cobertura enquanto reduzem o ruído.</span><span class="sxs-lookup"><span data-stu-id="f764c-126">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="f764c-127">**Monitoramento de dependência.**</span><span class="sxs-lookup"><span data-stu-id="f764c-127">**Dependency monitoring.**</span></span> <span data-ttu-id="f764c-128">Cenários do Lync Server podem falhar devido a uma variedade de fatores externos como o IIS offline, recursos limitados de CPU e memória e problemas de disco.</span><span class="sxs-lookup"><span data-stu-id="f764c-128">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="f764c-129">Os novos pacotes de gerenciamento verificam várias dependências importantes para garantir que os administradores estejam cientes do impacto.</span><span class="sxs-lookup"><span data-stu-id="f764c-129">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="f764c-130">**Relatórios avançados.**</span><span class="sxs-lookup"><span data-stu-id="f764c-130">**Enhanced reporting.**</span></span> <span data-ttu-id="f764c-131">Um conjunto de relatórios que ajuda os administradores a estimar a disponibilidade do cenários, planejar a capacidade e ver quais componentes têm mais problemas.</span><span class="sxs-lookup"><span data-stu-id="f764c-131">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="f764c-132">Os pacotes de gerenciamento também incluem uma variedade de recursos para ajudar a detectar e diagnosticar fornecer visibilidade em tempo real para a integridade da implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f764c-132">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="f764c-133">Esses recursos estão listados na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="f764c-133">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="f764c-134">Recursos do pacote de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="f764c-134">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f764c-135">Recurso</span><span class="sxs-lookup"><span data-stu-id="f764c-135">Feature</span></span></th>
<th><span data-ttu-id="f764c-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="f764c-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f764c-137">Transações sintéticas</span><span class="sxs-lookup"><span data-stu-id="f764c-137">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="f764c-138">Os cmdlets do Windows PowerShell que podem ser executados de vários locais para garantir que os cenários de usuário final, como entrada, presença, IM e conferências, estejam prontamente disponíveis para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f764c-138">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f764c-139">Alertas de confiabilidade de chamada</span><span class="sxs-lookup"><span data-stu-id="f764c-139">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="f764c-140">Consultas de banco de dados para CDR (Registros de detalhes de chamada).</span><span class="sxs-lookup"><span data-stu-id="f764c-140">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="f764c-141">Esses registros são gravados por servidores front-end para refletir se os usuários finais foram capazes de se conectar a uma chamada ou por que uma chamada foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="f764c-141">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="f764c-142">Essas consultas resultam em alertas que indicam quando uma ampla variedade de usuários finais estão passando por problemas de conectividade de chamadas ponto a ponto ou a funcionalidade de conferência básica.</span><span class="sxs-lookup"><span data-stu-id="f764c-142">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f764c-143">Alertas de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="f764c-143">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="f764c-p112">As consultas de banco de dados que visualizam os relatórios de Qualidade da Experiência (QoE) publicados por clientes ao fim de cada chamada. Essas consultas resultam em alertas que identificam cenários nos quais os usuários provavelmente observaram qualidade de mídia ruim durante chamadas e conferências. Os dados aproveitam métricas-chave como latência e perda de pacote, métricas que contribuem diretamente para a qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="f764c-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f764c-147">Integridade do componente</span><span class="sxs-lookup"><span data-stu-id="f764c-147">Component Health</span></span></p></td>
<td><p><span data-ttu-id="f764c-p113">Componentes individuais do servidor geram alertas usando logs de eventos e contadores de desempenho. Esses alertas indicam condições de falha que podem ter um impacto crítico em um ou mais cenários do usuário final. Esses alertas também podem indicar várias outras condições de falha, incluindo serviços que não estão funcionando, alta taxa de falhas, alta latência de mensagens ou problemas de conectividade.</span><span class="sxs-lookup"><span data-stu-id="f764c-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f764c-151">Integridade da dependência</span><span class="sxs-lookup"><span data-stu-id="f764c-151">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="f764c-152">As falha podem ocorrer por vários motivos externos.</span><span class="sxs-lookup"><span data-stu-id="f764c-152">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="f764c-153">Os pacotes de gerenciamento agora monitoram e coletam dados para algumas das dependência externas críticas que podem indicar vários problemas, incluindo a disponibilidade IIS, o uso da CPU e da memória por servidores e processos, além de métricas de disco.</span><span class="sxs-lookup"><span data-stu-id="f764c-153">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f764c-154">Os alertas emitidos pelo sistema foram classificados em três categorias gerais:</span><span class="sxs-lookup"><span data-stu-id="f764c-154">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="f764c-155">**Alertas de alta prioridade.**</span><span class="sxs-lookup"><span data-stu-id="f764c-155">**High-priority Alerts.**</span></span> <span data-ttu-id="f764c-156">Esses alertas indicam condições que resultaram em falhas no serviço para grandes grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="f764c-156">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="f764c-157">Por exemplo, uma falha de componente em uma única máquina não é um alerta de alta prioridade porque o Lync Server 2013 tem recursos de alta disponibilidade internos.</span><span class="sxs-lookup"><span data-stu-id="f764c-157">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="f764c-158">Em vez disso, os alertas de alta prioridade representam problemas sérios o suficiente para “tirar o sono dos administradores”.</span><span class="sxs-lookup"><span data-stu-id="f764c-158">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="f764c-159">As falha detectadas por transações sintéticas e serviços offline (por exemplo, conferências de áudio/vídeo) são qualificadas como alertas de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="f764c-159">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="f764c-160">**Alertas de prioridade média.**.</span><span class="sxs-lookup"><span data-stu-id="f764c-160">**Medium-priority alerts.**.</span></span> <span data-ttu-id="f764c-161">Esses alertas indicam condições que afetam um subconjunto de usuários ou indicam a degradação da qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="f764c-161">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="f764c-162">Isso inclui problemas como falhas de componentes, latência no estabelecimento da chamada ou qualidade de áudio degradada em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="f764c-162">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="f764c-163">Os alertas nesta categoria são têm monitoração de estado e indicam o status atual do problema.</span><span class="sxs-lookup"><span data-stu-id="f764c-163">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="f764c-164">Por exemplo, considere que o tempo de estabelecimento de chamada excede o limite de alerta.</span><span class="sxs-lookup"><span data-stu-id="f764c-164">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="f764c-165">Se o tempo de estabelecimento de chamadas retornar ao normal, esses alertas serão resolvidos automaticamente no System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f764c-165">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="f764c-166">A expectativa para esses alertas é de que um administrador os notará no mesmo dia útil.</span><span class="sxs-lookup"><span data-stu-id="f764c-166">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="f764c-167">**Outros alertas.**</span><span class="sxs-lookup"><span data-stu-id="f764c-167">**Other alerts.**</span></span> <span data-ttu-id="f764c-168">São alertas de componentes que podem afetar um usuário específico ou um subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="f764c-168">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="f764c-169">Por exemplo, talvez o serviço de Catálogo de endereços não consiga analisar a entrada do Active Directory de determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="f764c-169">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="f764c-170">A expectativa para esses alertas é que que os administradores os solucionarão quando tiverem tempo disponível.</span><span class="sxs-lookup"><span data-stu-id="f764c-170">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f764c-171">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f764c-171">In This Section</span></span>

  - [<span data-ttu-id="f764c-172">Configurando o Lync Server 2013 para trabalhar com o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="f764c-172">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="f764c-173">Usando o registro avançado de transações sintéticas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f764c-173">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="f764c-174">Usando o Microsoft SQL Server 2008 R2 como seu banco de dados do System Center Operations Manager para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f764c-174">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

