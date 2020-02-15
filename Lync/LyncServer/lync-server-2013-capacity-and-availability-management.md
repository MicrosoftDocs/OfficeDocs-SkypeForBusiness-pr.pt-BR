---
title: 'Lync Server 2013: gerenciamento de capacidade e disponibilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 315b8a70451e762c6eafd82a221b3266696034eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="9056e-102">Gerenciamento de capacidade e disponibilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9056e-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9056e-103">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="9056e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="9056e-104">O objetivo do gerenciamento de capacidade e gerenciamento de disponibilidade é medir e controlar o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="9056e-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="9056e-105">É recomendável implementar os procedimentos de gerenciamento de capacidade e gerenciamento de disponibilidade para que você possa medir e controlar o desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="9056e-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="9056e-106">Você deve saber se o sistema está disponível e se pode lidar com as demandas atuais e projetadas configurando as linhas de base e monitorando o sistema para procurar tendências.</span><span class="sxs-lookup"><span data-stu-id="9056e-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="9056e-107">Gerenciamento de capacidade</span><span class="sxs-lookup"><span data-stu-id="9056e-107">Capacity management</span></span>

<span data-ttu-id="9056e-108">O gerenciamento de capacidade envolve planejamento, dimensionamento e controle da capacidade de serviço para ajudar a garantir que os níveis de desempenho mínimos especificados no SLA sejam excedidos.</span><span class="sxs-lookup"><span data-stu-id="9056e-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="9056e-109">O bom gerenciamento de capacidade ajuda a garantir que você possa fornecer serviços de ti a um custo razoável e ainda atender aos níveis de desempenho definidos em seus SLAs com o cliente.</span><span class="sxs-lookup"><span data-stu-id="9056e-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="9056e-110">Esses critérios podem incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9056e-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="9056e-111">**Tempo de resposta do sistema**   esse é o tempo medido que o sistema leva para executar ações típicas.</span><span class="sxs-lookup"><span data-stu-id="9056e-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="9056e-112">Os exemplos incluem o tempo necessário para que a função de servidor de áudio/vídeo processe o tráfego de áudio/vídeo, o tempo necessário para um cliente criar e ingressar em uma conferência ou o tempo gasto para que a presença seja atualizada em todos os clientes do observador.</span><span class="sxs-lookup"><span data-stu-id="9056e-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="9056e-113">**Capacidade de armazenamento**   esta é a capacidade de um sistema de armazenamento, seja um banco de dados de conteúdo, um dispositivo de backup ou uma unidade local.</span><span class="sxs-lookup"><span data-stu-id="9056e-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="9056e-114">Os exemplos incluem a quantidade máxima de espaço de armazenamento a ser fornecida por site e o momento em que os backups devem ser armazenados antes de serem substituídos.</span><span class="sxs-lookup"><span data-stu-id="9056e-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="9056e-115">O ajuste da capacidade geralmente é um caso de garantir que recursos físicos suficientes estejam disponíveis, como espaço em disco e largura de banda da rede.</span><span class="sxs-lookup"><span data-stu-id="9056e-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="9056e-116">A tabela a seguir lista as resoluções típicas para problemas relacionados à capacidade.</span><span class="sxs-lookup"><span data-stu-id="9056e-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="9056e-117">Soluções típicas para problemas relacionados à capacidade</span><span class="sxs-lookup"><span data-stu-id="9056e-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9056e-118">Problema</span><span class="sxs-lookup"><span data-stu-id="9056e-118">Issue</span></span></th>
<th><span data-ttu-id="9056e-119">Solução possível</span><span class="sxs-lookup"><span data-stu-id="9056e-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9056e-120">Usuários remotos com desempenho ruim de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="9056e-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="9056e-121">Verifique se a largura de banda apropriada está disponível nos links WAN e se a QoS está habilitada e corretamente configurada.</span><span class="sxs-lookup"><span data-stu-id="9056e-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="9056e-122">Verifique os dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="9056e-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9056e-123">A resposta geral do ambiente do Lync é lenta.</span><span class="sxs-lookup"><span data-stu-id="9056e-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="9056e-124">Execute testes para verificar se os servidores front-end existentes podem lidar com a carga.</span><span class="sxs-lookup"><span data-stu-id="9056e-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="9056e-125">Introduza um novo servidor front-end, se necessário. Verifique os tempos de resposta do banco de dados SQL e corrija as causas dos atrasos (por exemplo, melhorar a e/s de disco).</span><span class="sxs-lookup"><span data-stu-id="9056e-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9056e-126">A solução de problemas mais detalhada é abordada no guia de rede do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9056e-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="9056e-127">A capacidade é afetada pela configuração do sistema e depende de recursos físicos, como a largura de banda da rede.</span><span class="sxs-lookup"><span data-stu-id="9056e-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="9056e-128">Por exemplo, se um ambiente do Lync é configurado para executar um backup completo à noite, deve-se tomar cuidado para ajudar a garantir que o efeito no desempenho interativo experiente por usuários finais seja minimizado.</span><span class="sxs-lookup"><span data-stu-id="9056e-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="9056e-129">O gerenciamento de capacidade é o processo de manter a capacidade de um sistema em níveis aceitáveis e aborda os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="9056e-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="9056e-130">**Reagindo a alterações nos requisitos de**   capacidade precisam ser ajustados para que as alterações sejam feitas no sistema ou na organização.</span><span class="sxs-lookup"><span data-stu-id="9056e-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="9056e-131">Por exemplo, se seu ambiente decidir implementar o Enterprise Voice, o número e o posicionamento de servidores de mediação e gateways PSTN (rede telefônica pública comutada) serão muito importantes.</span><span class="sxs-lookup"><span data-stu-id="9056e-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="9056e-132">Se você estiver fazendo um tronco SIP (Session Initiation Protocol) ou SIP direto, o design geral será alterado significativamente para fornecer o melhor desempenho do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9056e-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="9056e-133">**Prever requisitos**   futuros alguns requisitos de capacidade mudam de forma preditiva com o tempo.</span><span class="sxs-lookup"><span data-stu-id="9056e-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="9056e-134">Ao controlar as tendências, você pode planejar atualizações com antecedência.</span><span class="sxs-lookup"><span data-stu-id="9056e-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="9056e-135">Por exemplo, a largura de banda disponível entre vários sites do Lync deve ser monitorada para criar uma linha de base.</span><span class="sxs-lookup"><span data-stu-id="9056e-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="9056e-136">Essa linha de base permitirá a você prever quando você precisa adicionar mais largura de banda a esses links, já que a contagem de usuários nesses sites remotos aumenta com o tempo.</span><span class="sxs-lookup"><span data-stu-id="9056e-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="9056e-137">Gerenciamento de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="9056e-137">Availability management</span></span>

<span data-ttu-id="9056e-138">O gerenciamento de disponibilidade é o processo de garantir que todos os serviços de ti de forma consistente e econômico forneça o nível de serviço consistente e confiável exigido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="9056e-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="9056e-139">O gerenciamento de disponibilidade lida com a redução da perda de serviço e com a execução da ação apropriada se o serviço for perdido.</span><span class="sxs-lookup"><span data-stu-id="9056e-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="9056e-140">Em um ambiente do Lync, você pode estar preocupado se o serviço Enterprise Voice está disponível, se os usuários podem participar de conferências agendadas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="9056e-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="9056e-141">Um SLA define uma frequência e um comprimento aceitáveis e permite determinados períodos quando o sistema não está disponível para manutenção planejada.</span><span class="sxs-lookup"><span data-stu-id="9056e-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="9056e-142">Se você precisar fornecer relatórios para seu gerenciamento sobre a disponibilidade de sistemas, ou se você tiver penalidades financeiras ou outras, você deve registrar os dados de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="9056e-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="9056e-143">Mesmo que você não tenha esses requisitos formais, é uma boa ideia, pelo menos, saber com que frequência um sistema falhou em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="9056e-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="9056e-144">Por exemplo, a disponibilidade do sistema nos últimos 12 meses e quanto tempo levou para se recuperar de cada falha.</span><span class="sxs-lookup"><span data-stu-id="9056e-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="9056e-145">Essas informações ajudarão você a medir e aprimorar a eficácia da sua equipe em responder a uma falha do sistema.</span><span class="sxs-lookup"><span data-stu-id="9056e-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="9056e-146">Ele também pode fornecer informações úteis se houver uma contestação.</span><span class="sxs-lookup"><span data-stu-id="9056e-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="9056e-147">As medidas relacionadas à disponibilidade são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="9056e-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="9056e-148">**Disponibilidade**   isso geralmente é expresso como o tempo que um sistema ou serviço pode ser acessado em comparação com o momento em que está inativo.</span><span class="sxs-lookup"><span data-stu-id="9056e-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="9056e-149">Normalmente, é expresso como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="9056e-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="9056e-150">(Você pode ver referências de "três noves" ou "cinco noves".</span><span class="sxs-lookup"><span data-stu-id="9056e-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="9056e-151">Eles se referem à disponibilidade de 99,9% ou 99,999%.)</span><span class="sxs-lookup"><span data-stu-id="9056e-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="9056e-152">**Confiabilidade**   esta é uma medida do tempo entre as falhas de um sistema e, às vezes, expressa como média (ou média) de tempo entre falhas (MTBF).</span><span class="sxs-lookup"><span data-stu-id="9056e-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="9056e-153">**Tempo para reparar**   este é o tempo necessário para recuperar um serviço após uma falha, e geralmente é expresso como média (significando média) tempo de reparo (MTTR).</span><span class="sxs-lookup"><span data-stu-id="9056e-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="9056e-154">Disponibilidade, confiabilidade e tempo para reparo estão relacionados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9056e-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="9056e-155">**Disponibilidade = (MTBF – MTTR)/MTBF**   por exemplo, se um servidor falhar duas vezes em um período de seis meses e não estiver disponível para uma média de 20 minutos, o MTBF será de três meses ou 90 dias e o MTTR será de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="9056e-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="9056e-156">Portanto, disponibilidade = (90 dias – 20 minutos)/90 dias = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="9056e-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="9056e-157">O gerenciamento de disponibilidade é o processo de garantir que a disponibilidade seja maximizada e mantida nos parâmetros definidos em SLAs.</span><span class="sxs-lookup"><span data-stu-id="9056e-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="9056e-158">O gerenciamento de disponibilidade inclui os seguintes processos:</span><span class="sxs-lookup"><span data-stu-id="9056e-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="9056e-159">**Monitoramento**     examinando quando e por quanto tempo os serviços não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9056e-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="9056e-160">\*\*\*\*   Os valores de disponibilidade de relatórios devem ser fornecidos regularmente para equipes de gerenciamento, usuários e operações.</span><span class="sxs-lookup"><span data-stu-id="9056e-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="9056e-161">Esses relatórios devem realçar tendências e identificar áreas que são bem e áreas que exigem atenção.</span><span class="sxs-lookup"><span data-stu-id="9056e-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="9056e-162">O relatório deve resumir a conformidade com os destinos definidos nos SLAs.</span><span class="sxs-lookup"><span data-stu-id="9056e-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="9056e-163">**Melhoria**   se a disponibilidade não atender aos destinos definidos nos SLAs ou em que a tendência estiver em relação à disponibilidade reduzida, o processo de gerenciamento de disponibilidade deverá planejar etapas de correções.</span><span class="sxs-lookup"><span data-stu-id="9056e-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="9056e-164">Isso deve incluir o trabalho com outras equipes responsáveis realçar os motivos de paralisações e planejar ações corretivas para evitar uma recorrência das interrupções.</span><span class="sxs-lookup"><span data-stu-id="9056e-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="9056e-165">As medições de capacidade e disponibilidade são tarefas repetitivas que são ideais para ferramentas automatizadas e scripts como o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager), que é abordado posteriormente neste documento.</span><span class="sxs-lookup"><span data-stu-id="9056e-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9056e-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="9056e-166">See Also</span></span>


[<span data-ttu-id="9056e-167">Monitoramento do Lync Server 2013 com o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="9056e-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

