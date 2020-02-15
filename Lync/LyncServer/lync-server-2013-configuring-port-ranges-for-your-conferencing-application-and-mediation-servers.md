---
title: 'Lync Server 2013: Configurando intervalos de portas para seus servidores de conferência, aplicativos e mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="6bd58-102">Configurando intervalos de portas no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação</span><span class="sxs-lookup"><span data-stu-id="6bd58-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd58-103">_**Última modificação do tópico:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="6bd58-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="6bd58-p101">A fim de implementar a Qualidade do serviço, você deve configurar intervalos de porta idênticos para áudio, vídeo e compartilhamento de aplicativo no seu servidor de Conferência, de Aplicativo e de Mediação; além disso, esses intervalos de porta não devem se sobrepor de nenhuma maneira. Para usar um exemplo simples, imagine que você utilize as portas de 10000 a 10999 para vídeo nos seus servidores de Conferência. Isso significa que você deve reservar as portas de 10000 a 10999 para vídeo nos seus servidores de Aplicativo e de Mediação. Caso não o faça, a Qualidade do serviço não funcionará como esperado.</span><span class="sxs-lookup"><span data-stu-id="6bd58-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="6bd58-p102">De forma semelhante, imagine que você reserva as portas de 10000 a 10999 para vídeo e, em seguida, reserva as portas de 10500 a 11999 para áudio. Isso pode gerar problemas na Qualidade do serviço porque os intervalos de porta se sobrepõem. Com a QoS, cada modalidade deve possuir um conjunto de portas único: se usar as portas de 10000 a 10999 para vídeo, então você deverá usar um intervalo diferente (por exemplo, de 11000 a 11999 para áudio).</span><span class="sxs-lookup"><span data-stu-id="6bd58-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="6bd58-111">Por padrão, os intervalos de porta de áudio e vídeo não se sobrepõem no Microsoft Lync Server 2013; no entanto, os intervalos de portas atribuídos ao compartilhamento de aplicativos se sobrepõem com os intervalos de porta de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="6bd58-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="6bd58-112">(O que, por sua vez, significa que nenhum desses intervalos é exclusivo.) Você pode verificar os intervalos de portas existentes para seus servidores de conferência, aplicativo e de mediação executando os seguintes três comandos de dentro do Shell de gerenciamento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6bd58-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="6bd58-p104">Como você pode observar nos comandos precedentes, é atribuído a cada tipo de porta – áudio, vídeo e compartilhamento de aplicativo – dois valores separados de propriedade: a porta inicial e a contagem de porta. A porta inicial indica a primeira porta usada por essa modalidade; por exemplo, se a porta inicial de áudio é igual a 50000, significa que a primeira porta usada para o tráfego de áudio é a porta 50000. Se a porta de contagem de áudio é 2 (valor inválido, mas é usado aqui pelo seu valor ilustrativo), significa que apenas duas portas estão alocadas para o áudio. Se a primeira porta é a porta 50000 e há um total de duas portas, significa que a segunda porta será a porta 50001 (os intervalos de porta devem ser contíguos). Dessa forma, o intervalo de porta para áudio seria da porta 50000 até a 50001, ambas incluídas.</span><span class="sxs-lookup"><span data-stu-id="6bd58-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="6bd58-118">Observe que o servidor de Aplicativo e o servidor de Mediação suportam QoS somente para áudio; você não precisa modificar as portas de vídeo ou as de compartilhamento de aplicativo nos seus servidores de Aplicativo ou de Mediação.</span><span class="sxs-lookup"><span data-stu-id="6bd58-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="6bd58-119">Se você executar os três comandos anteriores, verá que os valores de porta padrão para o Lync Server 2013 estão configurados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="6bd58-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bd58-120">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6bd58-120">Property</span></span></th>
<th><span data-ttu-id="6bd58-121">Servidor de Conferência</span><span class="sxs-lookup"><span data-stu-id="6bd58-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="6bd58-122">Servidor de Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6bd58-122">Application Server</span></span></th>
<th><span data-ttu-id="6bd58-123">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6bd58-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bd58-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="6bd58-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="6bd58-125">49152</span><span class="sxs-lookup"><span data-stu-id="6bd58-125">49152</span></span></p></td>
<td><p><span data-ttu-id="6bd58-126">49152</span><span class="sxs-lookup"><span data-stu-id="6bd58-126">49152</span></span></p></td>
<td><p><span data-ttu-id="6bd58-127">49152</span><span class="sxs-lookup"><span data-stu-id="6bd58-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd58-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="6bd58-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="6bd58-129">8348</span><span class="sxs-lookup"><span data-stu-id="6bd58-129">8348</span></span></p></td>
<td><p><span data-ttu-id="6bd58-130">8348</span><span class="sxs-lookup"><span data-stu-id="6bd58-130">8348</span></span></p></td>
<td><p><span data-ttu-id="6bd58-131">8348</span><span class="sxs-lookup"><span data-stu-id="6bd58-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd58-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="6bd58-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="6bd58-133">57501</span><span class="sxs-lookup"><span data-stu-id="6bd58-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd58-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="6bd58-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="6bd58-135">8034</span><span class="sxs-lookup"><span data-stu-id="6bd58-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd58-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="6bd58-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="6bd58-137">49152</span><span class="sxs-lookup"><span data-stu-id="6bd58-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd58-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="6bd58-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="6bd58-139">16383</span><span class="sxs-lookup"><span data-stu-id="6bd58-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6bd58-140">Conforme observado anteriormente, ao configurar as portas do Lync Server para QoS, você deve garantir que: 1) as configurações de porta de áudio são idênticas nos seus servidores de conferência, aplicativo e mediação; e, 2) os intervalos de porta não se sobrepõem.</span><span class="sxs-lookup"><span data-stu-id="6bd58-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="6bd58-141">Se você observar com atenção a tabela anterior, verá que os intervalos de porta são idênticos nos três tipos de servidores.</span><span class="sxs-lookup"><span data-stu-id="6bd58-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="6bd58-142">Por exemplo, a porta inicial de áudio está configurada para a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é igual: 8348.</span><span class="sxs-lookup"><span data-stu-id="6bd58-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="6bd58-143">No entanto, os intervalos de porta se sobrepõem: as portas de áudio iniciam na porta 49152, mas o mesmo acontece com as portas configuradas para o compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6bd58-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="6bd58-144">Para usar a Qualidade do serviço de forma ótima, o compartilhamento de aplicativo deve ser reconfigurado para que use um único intervalo de porta.</span><span class="sxs-lookup"><span data-stu-id="6bd58-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="6bd58-145">Por exemplo, você poderia configurar o compartilhamento de aplicativo para iniciar na porta 40803 e para usar as portas 8348.</span><span class="sxs-lookup"><span data-stu-id="6bd58-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="6bd58-146">(Por que as portas 8348?</span><span class="sxs-lookup"><span data-stu-id="6bd58-146">(Why 8348 ports?</span></span> <span data-ttu-id="6bd58-147">Se você adicionar esses valores juntos--40803 + 8348--isso significa que o compartilhamento de aplicativos usará as portas 40803 através da porta 49150.</span><span class="sxs-lookup"><span data-stu-id="6bd58-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="6bd58-148">Já que as portas de áudio não começam até a porta 49152, você não terá mais nenhum intervalo de porta em sobreposição.)</span><span class="sxs-lookup"><span data-stu-id="6bd58-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="6bd58-p106">Após selecionar os novos intervalos de porta do compartilhamento de aplicativo, você será capaz de realizar suas modificações por meio do cmdlet Set-CsConferencingServer. Essa alteração não precisa ser feita no seus servidores de Aplicativo ou de Mediação, já que esses servidores não manipulam o tráfego do compartilhamento de aplicativos. Você precisa alterar somente os valores de porta nesses servidores caso decida reatribuir as portas usadas no tráfego de áudio.</span><span class="sxs-lookup"><span data-stu-id="6bd58-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="6bd58-152">Para modificar os valores de porta para compartilhamento de aplicativos em um único servidor de conferência, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6bd58-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="6bd58-153">Se deseja realizar essas alterações em todos os seus servidores de Conferência, você pode executar esse comando:</span><span class="sxs-lookup"><span data-stu-id="6bd58-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="6bd58-154">Após alterar as configurações de porta, você deverá parar e, em seguida, reiniciar cada serviço afetado pelas alterações.</span><span class="sxs-lookup"><span data-stu-id="6bd58-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="6bd58-p107">Não é obrigatório que seus servidores de Conferência, de Aplicativo e de Mediação compartilhem os mesmos intervalos de porta; o único requisito é que você configure intervalos de porta únicos em todos os servidores. No entanto, a administração será normalmente mais fácil se você usar os mesmo conjuntos de portas em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="6bd58-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

