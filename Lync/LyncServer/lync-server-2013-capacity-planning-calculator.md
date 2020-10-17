---
title: Calculadora de planejamento de capacidade do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512818"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="f9498-102">Usando a calculadora de planejamento de capacidade para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9498-102">Using the capacity planning calculator for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9498-103">_**Última modificação do tópico:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="f9498-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="f9498-104">A calculadora de planejamento de capacidade do Microsoft® Lync™ Server 2013 está disponível para download em <https://www.microsoft.com/download/details.aspx?id=36828> .</span><span class="sxs-lookup"><span data-stu-id="f9498-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="f9498-105">Ele foi projetado para ajudá-lo a determinar os requisitos de servidor com base em números de usuários e modalidades de comunicação habilitados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f9498-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="f9498-106">Você insere o perfil da sua organização e a calculadora fornece recomendações que ajudam você a planejar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f9498-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="f9498-107">As recomendações criadas pela calculadora são apenas para fins de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f9498-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="f9498-108">A simulação de carga real é necessária para garantir que o Lync Server 2013 seja adequadamente provisionado.</span><span class="sxs-lookup"><span data-stu-id="f9498-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="f9498-109">Para realizar testes de estresse sob uma carga simulada, use a [ferramenta de estresse e desempenho do Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).</span><span class="sxs-lookup"><span data-stu-id="f9498-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="f9498-110">Depois de determinar o perfil do usuário e as modalidades que você deseja habilitar para os usuários, é hora de usar a calculadora para planejar o número de servidores, memória e largura de banda de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="f9498-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="f9498-111">Esta versão da calculadora não fornece orientações para os requisitos de e/s de disco.</span><span class="sxs-lookup"><span data-stu-id="f9498-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="f9498-112">Esta calculadora complementa o [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) e o [Microsoft Lync Server](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="f9498-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="f9498-113">Use a calculadora após revisar o guia e criar uma topologia recomendada usando a ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f9498-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="f9498-114">Você pode aproveitar a maior parte da calculadora se tiver informações precisas e detalhadas sobre seu perfil de usuário específico.</span><span class="sxs-lookup"><span data-stu-id="f9498-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="f9498-115">Por exemplo, a porcentagem de usuários habilitados para voz, média de chamadas por usuário por hora, duração da chamada e a porcentagem de usuários simultâneos em conferências podem fazer uma grande diferença nos requisitos do servidor.</span><span class="sxs-lookup"><span data-stu-id="f9498-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="f9498-116">A precisão das recomendações criadas pela calculadora depende da precisão das informações que você fornece.</span><span class="sxs-lookup"><span data-stu-id="f9498-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="f9498-117">Usando a calculadora de capacidade</span><span class="sxs-lookup"><span data-stu-id="f9498-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="f9498-118">A calculadora é uma planilha do Microsoft Excel®.</span><span class="sxs-lookup"><span data-stu-id="f9498-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="f9498-119">As células coloridas de laranja são para entrada.</span><span class="sxs-lookup"><span data-stu-id="f9498-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="f9498-120">Os valores padrão são inseridos (80.000 usuários em um pool com doze servidores front-end), mas você pode alterar esses valores de acordo com as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f9498-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="f9498-121">O modelo de uso contém as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="f9498-121">The usage model contains the following sections.</span></span> <span data-ttu-id="f9498-122">Para calcular os requisitos de capacidade, insira os dados descritos:</span><span class="sxs-lookup"><span data-stu-id="f9498-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="f9498-123">**Mensagens instantâneas e presença**</span><span class="sxs-lookup"><span data-stu-id="f9498-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="f9498-124">Em número de usuários, digite o número de usuários que serão conectados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="f9498-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="f9498-125">Esse número geralmente é de 80% do número total de usuários provisionados.</span><span class="sxs-lookup"><span data-stu-id="f9498-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="f9498-126">Na maioria das situações, 100% de seus usuários simultâneos serão habilitados para IM e presença.</span><span class="sxs-lookup"><span data-stu-id="f9498-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="f9498-127">O padrão é 80.000.</span><span class="sxs-lookup"><span data-stu-id="f9498-127">The default is 80,000.</span></span>

  - <span data-ttu-id="f9498-128">Número médio de contatos na lista de contatos indica o número de contatos que estamos usando para validar os requisitos do sistema.</span><span class="sxs-lookup"><span data-stu-id="f9498-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="f9498-129">Esse número não é alterado.</span><span class="sxs-lookup"><span data-stu-id="f9498-129">This number is not changeable.</span></span>

<span data-ttu-id="f9498-130">**Enterprise Voice**</span><span class="sxs-lookup"><span data-stu-id="f9498-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="f9498-131">Em usuários habilitados para o Enterprise Voice, digite a porcentagem de seus usuários que estão habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f9498-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f9498-132">O padrão é 60%.</span><span class="sxs-lookup"><span data-stu-id="f9498-132">The default is 60%.</span></span>

  - <span data-ttu-id="f9498-133">Em número médio de chamadas por usuário por hora (pico), digite o número de chamadas por hora que você espera que o usuário médio participe durante horários de carga de pico.</span><span class="sxs-lookup"><span data-stu-id="f9498-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="f9498-134">O padrão é 4.</span><span class="sxs-lookup"><span data-stu-id="f9498-134">The default is 4.</span></span>

  - <span data-ttu-id="f9498-135">Em porcentagem de chamadas que usam bypass de mídia, digite a porcentagem de chamadas feitas por seus usuários que irão ignorar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f9498-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="f9498-136">O padrão é 65%.</span><span class="sxs-lookup"><span data-stu-id="f9498-136">The default is 65%.</span></span>

  - <span data-ttu-id="f9498-137">Em porcentagem de usuários de voz envolvidos nas chamadas UC-PSTN, digite a porcentagem das chamadas da sua organização que são chamadas telefônicas UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="f9498-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="f9498-138">O padrão é 60%</span><span class="sxs-lookup"><span data-stu-id="f9498-138">The default is 60%</span></span>

  - <span data-ttu-id="f9498-139">Em percentual de usuários de voz envolvidos nas chamadas UC-UC mostra a porcentagem de usuários que estão habilitados para o Enterprise Voice que serão habilitados apenas para as chamadas UC-UC.</span><span class="sxs-lookup"><span data-stu-id="f9498-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="f9498-140">Esse número é calculado com base no que você insere para porcentagem de usuários de voz habilitados para chamadas UC-PSTN.</span><span class="sxs-lookup"><span data-stu-id="f9498-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="f9498-141">**Conferências**</span><span class="sxs-lookup"><span data-stu-id="f9498-141">**Conferencing**</span></span>

  - <span data-ttu-id="f9498-142">Em porcentagem de usuários em conferências simultâneas, digite a porcentagem de usuários que participarão simultaneamente em conferências.</span><span class="sxs-lookup"><span data-stu-id="f9498-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="f9498-143">O padrão é 5%.</span><span class="sxs-lookup"><span data-stu-id="f9498-143">The default is 5%.</span></span>

  - <span data-ttu-id="f9498-144">Em porcentagem de conferências com somente IM de grupo (sem voz), digite a porcentagem de conferências cujas conferências envolverão apenas mensagens instantâneas; Isto é, que não incluem um componente de áudio.</span><span class="sxs-lookup"><span data-stu-id="f9498-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="f9498-145">O padrão é 10%</span><span class="sxs-lookup"><span data-stu-id="f9498-145">The default is 10%</span></span>

  - <span data-ttu-id="f9498-146">Em porcentagem de usuários que usam conferência discada, digite a porcentagem de participantes simultâneos em conferências que usarão a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="f9498-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="f9498-147">O padrão é 15%.</span><span class="sxs-lookup"><span data-stu-id="f9498-147">The default is 15%.</span></span>

  - <span data-ttu-id="f9498-148">Em porcentagem de conferências usando voz, digite a porcentagem de conferências que incluirão um componente de áudio.</span><span class="sxs-lookup"><span data-stu-id="f9498-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="f9498-149">Se 20% de suas conferências de voz também incluirem vídeo normal, marque a caixa de seleção incluindo vídeo (sem exibição múltipla).</span><span class="sxs-lookup"><span data-stu-id="f9498-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="f9498-150">Se 20% de suas conferências também incluir vídeo de várias exibições, marque a caixa de seleção incluir vários modos de exibição.</span><span class="sxs-lookup"><span data-stu-id="f9498-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="f9498-151">Se 50% de suas conferências de voz também incluem compartilhamento de aplicativo, marque a caixa de seleção incluir compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f9498-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="f9498-152">Se 20% de suas conferências de voz incluírem carregamentos de dados, como apresentações do Microsoft PowerPoint®, marque a caixa de seleção incluir webconferências.</span><span class="sxs-lookup"><span data-stu-id="f9498-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="f9498-153">**Mobilidade**</span><span class="sxs-lookup"><span data-stu-id="f9498-153">**Mobility**</span></span>

  - <span data-ttu-id="f9498-154">Em porcentagem de usuários habilitados para mobilidade, digite a porcentagem de seus usuários que serão habilitados para se conectarem ao Lync Server usando dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="f9498-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="f9498-155">O padrão é 40%.</span><span class="sxs-lookup"><span data-stu-id="f9498-155">The default is 40%.</span></span>

<span data-ttu-id="f9498-156">Quando você inserir todas as informações necessárias, a calculadora de capacidade estimará suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="f9498-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="f9498-157">As células amarelas mostram valores calculados para requisitos de CPU, memória e largura de banda com base nos testes executados nos laboratórios de desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9498-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="f9498-158">Os números são fornecidos como uma diretriz, nem cada única variação é testada e validada.</span><span class="sxs-lookup"><span data-stu-id="f9498-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="f9498-159">Os seguintes valores são calculados:</span><span class="sxs-lookup"><span data-stu-id="f9498-159">The following values are calculated:</span></span>

  - <span data-ttu-id="f9498-160">CPU de front end: porcentagem de uso da CPU se a carga inteira estava sendo manipulada por um servidor front-end das mesmas especificações que o servidor usado no teste da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9498-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="f9498-161">Rede em Mbps: requisitos de largura de banda em megabits por segundo (Mbps) para a carga de trabalho correspondente.</span><span class="sxs-lookup"><span data-stu-id="f9498-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="f9498-162">Memória em GB: memória necessária em gigabytes (GB) para a carga de trabalho correspondente.</span><span class="sxs-lookup"><span data-stu-id="f9498-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="f9498-163">As células verdes mostram recomendações para o modelo de uso inserido.</span><span class="sxs-lookup"><span data-stu-id="f9498-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="f9498-164">Total de servidores front-end: o número de servidores físicos exigidos baseia-se em servidores dedicados que executam o Lync Server 2013 com processador duplo, um núcleo-Core, com 2.260 megaciclos.</span><span class="sxs-lookup"><span data-stu-id="f9498-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="f9498-165">Observe que a habilitação do hyperthreading é recomendada e comprovada para melhorar o desempenho de servidores que oferecem suporte a áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="f9498-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="f9498-166">Servidores de borda: o número de servidores de borda necessários, com base em 30% de todos os usuários simultâneos que estão se comunicando por meio dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="f9498-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="f9498-167">Essa porcentagem não pode ser alterada na calculadora.</span><span class="sxs-lookup"><span data-stu-id="f9498-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="f9498-168">Repositório de serviços de arquivamento/registro de detalhes de chamada/qualidade da experiência: o número de repositórios necessários para recursos de arquivamento ou monitoramento, se eles estiverem habilitados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f9498-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="f9498-169">Servidor de banco de dados back-end necessário (pools necessários): o número de servidores de banco de dados back-end necessários para suportar a carga de trabalho selecionada.</span><span class="sxs-lookup"><span data-stu-id="f9498-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="f9498-170">Além disso, na linha ao lado de total dos servidores front-end, mais informações são fornecidas sobre a carga nos servidores e na rede para todas as cargas de trabalho planejadas combinadas.</span><span class="sxs-lookup"><span data-stu-id="f9498-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="f9498-171">Carga média da CPU: o uso médio da CPU por servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="f9498-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="f9498-172">Rede em Mbps: a alocação de largura de banda necessária para suportar o modelo de uso inserido.</span><span class="sxs-lookup"><span data-stu-id="f9498-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="f9498-173">Memória em GB: memória, em gigabytes, necessária para cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="f9498-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="f9498-174">Ajustando para seus processadores</span><span class="sxs-lookup"><span data-stu-id="f9498-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="f9498-175">Todos os valores de uso da CPU na planilha presumem que cada servidor tenha um processador duplo, um núcleo hex com 2,26 GHz, pelo menos 32 GB de memória, e 8 ou mais unidades de disco rígido de 10.000-RPM com pelo menos 72 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="f9498-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="f9498-176">Se seus servidores tiverem processadores diferentes, você poderá ajustar os números para que correspondam ao seu hardware.</span><span class="sxs-lookup"><span data-stu-id="f9498-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

