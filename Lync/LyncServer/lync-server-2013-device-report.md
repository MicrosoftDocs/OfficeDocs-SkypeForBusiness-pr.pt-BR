---
title: 'Lync Server 2013: relatório de dispositivos'
description: 'Lync Server 2013: relatório de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575117"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="7124d-103">Relatório de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7124d-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7124d-104">_**Última modificação do tópico:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="7124d-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="7124d-105">O Relatório de Dispositivos pode ser melhor chamado de Relatório de Microfones e Alto-Falantes; isso porque o Relatório de Dispositivos recupera métricas relacionadas às chamadas (tais como o percentual de chamadas ruins, eco e tempo de troca de voz) agrupadas por microfone e alto-falante usados na chamada.</span><span class="sxs-lookup"><span data-stu-id="7124d-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="7124d-106">Se você estiver interessado em telefones IP (também conhecidos como "dispositivos"), use o relatório de [inventário de telefones IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="7124d-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="7124d-p102">O Relatório de Dispositivos é extremamente útil para os administradores ao determinar se um tipo específico de dispositivo está experienciando mais chamadas de baixa qualidade do que outros. Por outro lado, pode influenciar decisões relacionadas à compra de novos dispositivos ou à substituição de dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7124d-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="7124d-p103">Por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, suponha que você tem vários usuários que utilizam os seguintes dispositivos de captura e renderização: por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, suponha que você tem vários usuários que utilizam os seguintes dispositivos de captura e renderização:</span><span class="sxs-lookup"><span data-stu-id="7124d-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="7124d-112">Dispositivo de captura -- Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="7124d-113">Dispositivo de renderização -- Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="7124d-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="7124d-114">Se esses usuários fizerem um total de 254 chamadas, você verá uma entrada como esta no relatório:</span><span class="sxs-lookup"><span data-stu-id="7124d-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7124d-115">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="7124d-115">Capture device</span></span></th>
<th><span data-ttu-id="7124d-116">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="7124d-116">Render device</span></span></th>
<th><span data-ttu-id="7124d-117">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="7124d-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7124d-118">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7124d-119">Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="7124d-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="7124d-120">254</span><span class="sxs-lookup"><span data-stu-id="7124d-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7124d-p104">Agora, suponha que você tem um número de usuários que usam esse mesmo dispositivo de captura, mas usam um dispositivo de renderização diferente. Neste caso, você terá uma segunda linha no relatório, uma para uma para essa combinação única de dispositivo de captura e dispositivo de renderização:</span><span class="sxs-lookup"><span data-stu-id="7124d-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7124d-123">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="7124d-123">Capture device</span></span></th>
<th><span data-ttu-id="7124d-124">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="7124d-124">Render device</span></span></th>
<th><span data-ttu-id="7124d-125">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="7124d-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7124d-126">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7124d-127">Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="7124d-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="7124d-128">254</span><span class="sxs-lookup"><span data-stu-id="7124d-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-129">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7124d-130">Alto-falantes (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7124d-131">319</span><span class="sxs-lookup"><span data-stu-id="7124d-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7124d-p105">Se você preferir ver os totais combinados para um determinado dispositivo (por exemplo, para o dispositivo de captura SoundMAX, independente do dispositivo de renderização usado), selecione a opção apropriada na lista suspensa de tipo de dispositivo (dispositivo de captura ou dispositivo de renderização). Se você selecionar dispositivo de captura neste exemplo, terá algo parecido com isso:</span><span class="sxs-lookup"><span data-stu-id="7124d-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7124d-134">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="7124d-134">Capture device</span></span></th>
<th><span data-ttu-id="7124d-135">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="7124d-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7124d-136">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="7124d-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="7124d-137">573</span><span class="sxs-lookup"><span data-stu-id="7124d-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="7124d-138">Acessando o relatório de dispositivos</span><span class="sxs-lookup"><span data-stu-id="7124d-138">Accessing the Device Report</span></span>

<span data-ttu-id="7124d-139">O Relatório de Dispositivos é geralmente acessado na página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="7124d-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7124d-140">No entanto, se você estiver exibindo o [relatório de detalhes de chamada no Lync Server 2013](lync-server-2013-call-detail-report.md) , poderá aprofundar até o relatório de dispositivo para um dispositivo específico clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="7124d-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7124d-141">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="7124d-141">Capture Device</span></span>

  - <span data-ttu-id="7124d-142">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="7124d-142">Render Device</span></span>

<span data-ttu-id="7124d-143">No relatório de dispositivos, você pode fazer uma busca detalhada [no relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="7124d-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7124d-144">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="7124d-144">Call volume</span></span>

  - <span data-ttu-id="7124d-145">Percentual de chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="7124d-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="7124d-146">Como usar melhor o Relatório de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="7124d-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="7124d-147">Tratando-se de nomes de dispositivos, o Relatório de Dispositivos é extremamente detalhado. Por exemplo, suponha que você tem os seguintes dispositivos de captura:</span><span class="sxs-lookup"><span data-stu-id="7124d-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="7124d-148">Microfone Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="7124d-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="7124d-149">Microfone Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="7124d-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="7124d-150">Microfone Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="7124d-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="7124d-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="7124d-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="7124d-152">Microfone Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-153">Microfone Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="7124d-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7124d-154">Microfone Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-155">Microfone Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-156">Microfone Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-157">Microfone Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-158">Microfone Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-159">Microfone Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-160">Microfone Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-161">Microfone Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="7124d-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7124d-162">Microfone Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="7124d-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="7124d-163">Microfone Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="7124d-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="7124d-164">Microfone Aastra 6725ip (Dispositivo de áudio USB)</span><span class="sxs-lookup"><span data-stu-id="7124d-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="7124d-165">Microfone Aastra 6725ip (Dispositivo de áudio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="7124d-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7124d-166">Tenha em mente que os nomes de dispositivos de captura podem não ser os mesmos se você estiver executando versões localizadas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7124d-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="7124d-167">Um dispositivo denominado Microfone Aastra 6725ip (Aastra 6725ip)-V0 em português pode ter um nome diferente em francês ou espanhol.</span><span class="sxs-lookup"><span data-stu-id="7124d-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="7124d-168">Muitas vezes você desejará este nível de detalhe; mas em outros momentos, você só estará interessado na quantidade de chamadas que usam um microfone Aastra, independente do número do modelo.</span><span class="sxs-lookup"><span data-stu-id="7124d-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="7124d-169">Uma maneira de obter informações como essa é para exportar os dados de relatório do dispositivo para o Microsoft Excel e, em seguida, salvar os dados em um arquivo de valores separados por vírgula (por exemplo, \\ os dispositivos de dados \\ \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="7124d-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="7124d-170">É possível usar um conjunto de comandos parecidos com esses para importar o arquivo .CSV no Windows PowerShell e relatar o número total de chamadas feitas usando um dispositivo de captura Aastra:</span><span class="sxs-lookup"><span data-stu-id="7124d-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="7124d-p109">Esse procedimento retornará um único valor que representa o número total de chamadas usando um dispositivo de captura Aastra. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7124d-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7124d-173">Filtros</span><span class="sxs-lookup"><span data-stu-id="7124d-173">Filters</span></span>

<span data-ttu-id="7124d-p110">Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. Por exemplo, o Relatório de Dispositivo permite filtrar coisas como o tipo de chamada (isto é, a chamada foi realizada pelo cliente), uma chamada de conferência ou chamada PSTN. Também é possível escolher como os dados devem ser agrupados. Neste caso, os dispositivos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="7124d-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7124d-178">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7124d-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="7124d-179">Filtros do Relatório de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="7124d-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7124d-180">Nome</span><span class="sxs-lookup"><span data-stu-id="7124d-180">Name</span></span></th>
<th><span data-ttu-id="7124d-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="7124d-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7124d-182"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p111">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="7124d-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7124d-185">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="7124d-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7124d-p112">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="7124d-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7124d-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7124d-188">7/7/2012</span></span></p>
<p><span data-ttu-id="7124d-189">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="7124d-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7124d-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7124d-190">7/3/2012</span></span></p>
<p><span data-ttu-id="7124d-191">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="7124d-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-192"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p113">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="7124d-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7124d-195">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="7124d-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7124d-p114">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="7124d-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7124d-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7124d-198">7/7/2012</span></span></p>
<p><span data-ttu-id="7124d-199">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="7124d-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7124d-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7124d-200">7/3/2012</span></span></p>
<p><span data-ttu-id="7124d-201">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="7124d-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-202"><strong>Causa de troca de voz</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p115">Motivo pelo qual uma chamada precisou ser colocada no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-206">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-207">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7124d-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-208">Carimbo de data/hora inválido</span><span class="sxs-lookup"><span data-stu-id="7124d-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-209">Eco</span><span class="sxs-lookup"><span data-stu-id="7124d-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-210">DNLP (processador não linear dinâmico)</span><span class="sxs-lookup"><span data-stu-id="7124d-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-211">Baixa complexidade</span><span class="sxs-lookup"><span data-stu-id="7124d-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-212">Estado do dispositivo inválido</span><span class="sxs-lookup"><span data-stu-id="7124d-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-213">Eco pós-AEC (cancelamento do eco acústico)</span><span class="sxs-lookup"><span data-stu-id="7124d-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-214"><strong>Causa do eco</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p116">Motivo pelo qual o eco acima do aceitável foi detectado em uma chamada. (Em telecomunicações, o eco é um reflexo do som, o mesmo fenômeno que você ouvirá se gritar em um poço). Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-217">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-218">Nenhum</span><span class="sxs-lookup"><span data-stu-id="7124d-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-219">Carimbo de data/hora inválido</span><span class="sxs-lookup"><span data-stu-id="7124d-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-220">Eco pós-AEC (cancelamento do eco acústico)</span><span class="sxs-lookup"><span data-stu-id="7124d-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-221">ANLP (processador não linear adaptado)</span><span class="sxs-lookup"><span data-stu-id="7124d-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-222">DNLP (processador não linear dinâmico)</span><span class="sxs-lookup"><span data-stu-id="7124d-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-223">Distorção do microfone</span><span class="sxs-lookup"><span data-stu-id="7124d-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-224"><strong>Tipo de chamada</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p117">Indica o tipo de chamada realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-227">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-228">Chamada do cliente</span><span class="sxs-lookup"><span data-stu-id="7124d-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-229">Chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="7124d-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-230">Chamada de conferência</span><span class="sxs-lookup"><span data-stu-id="7124d-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-231"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p118">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-234">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-235">Interno</span><span class="sxs-lookup"><span data-stu-id="7124d-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-236">Externo</span><span class="sxs-lookup"><span data-stu-id="7124d-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-237"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p119">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-240">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-241">Com fio</span><span class="sxs-lookup"><span data-stu-id="7124d-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-242">Conexão</span><span class="sxs-lookup"><span data-stu-id="7124d-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p120">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-246">Todos os</span><span class="sxs-lookup"><span data-stu-id="7124d-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-247">VPN</span><span class="sxs-lookup"><span data-stu-id="7124d-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-248">Não VPN</span><span class="sxs-lookup"><span data-stu-id="7124d-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-249"><strong>Tipo de dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p121">Indica o tipo de dispositivo. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="7124d-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-252">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="7124d-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-253">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="7124d-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="7124d-254">Par de dispositivos de captura/renderização</span><span class="sxs-lookup"><span data-stu-id="7124d-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-255"><strong>Nome do dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-p122">Nome do dispositivo de captura ou renderização. É possível inserir o nome completo do dispositivo ou qualquer parte do nome. Por exemplo para encontrar o dispositivo Microfone (Microsoft LifeCam VX-1000.), é possível inserir o nome completo do dispositivo, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="7124d-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="7124d-259">Microfone (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="7124d-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="7124d-p123">Em alternativa, é possível inserir apenas uma parte do nome. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7124d-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="7124d-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="7124d-262">LifeCam</span></span></p>
<p><span data-ttu-id="7124d-263">Observe que o filtro anterior retorna qualquer dispositivo que contenha a cadeia de caracteres &quot; LifeCam &quot; em qualquer lugar em seu nome.</span><span class="sxs-lookup"><span data-stu-id="7124d-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7124d-264">Métrica</span><span class="sxs-lookup"><span data-stu-id="7124d-264">Metrics</span></span>

<span data-ttu-id="7124d-265">A tabela a seguir lista a informação oferecida no Relatório do Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7124d-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="7124d-266">Métricas do Relatório do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="7124d-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7124d-267">Nome</span><span class="sxs-lookup"><span data-stu-id="7124d-267">Name</span></span></th>
<th><span data-ttu-id="7124d-268">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="7124d-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7124d-269">Descrição</span><span class="sxs-lookup"><span data-stu-id="7124d-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7124d-270"><strong>Dispositivo de captura</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-271">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-272">Dispositivo (por exemplo, um microfone ou webcam) usado para transmitir áudio.</span><span class="sxs-lookup"><span data-stu-id="7124d-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-273"><strong>Dispositivos de renderização</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-274">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-275">Dispositivo (por exemplo, um fone de ouvido ou alto falantes) usados para receber áudio.</span><span class="sxs-lookup"><span data-stu-id="7124d-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-276"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-277">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-278">Número total de chamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="7124d-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-279"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-280">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-281">Porcentagem de chamadas classificadas como &quot; ruins. &quot; Uma chamada ruim é qualquer chamada que pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="7124d-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-282"><strong>Usuários exclusivos</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-283">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-p124">Usuários exclusivos que utilizaram o dispositivo. Se um usuário utilizou o dispositivo 13 vezes, ele ou ela deve contar como um usuário exclusivo, o mesmo que um usuário que utilizou o dispositivo uma única vez.</span><span class="sxs-lookup"><span data-stu-id="7124d-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-286"><strong>Tempo de troca da taxa de voz</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-287">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-p125">Porcentagem da chamada que precisou ser conduzida no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="7124d-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-290"><strong>Taxa de microfone não funcionando</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-291">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-p126">Porcentagem da chamada na qual o dispositivo de captura não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de captura não estar funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="7124d-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-294"><strong>Taxa de alto falante não funcionando</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-295">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-p127">Porcentagem da chamada na qual o dispositivo de renderização não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de renderização não estar funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="7124d-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-298"><strong>Chamadas com opção de voz (%)</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-299">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-p128">Porcentagem do total de chamadas que precisaram ser colocadas no modo half duplex. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="7124d-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-302"><strong>Eco do microfone em (%)</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-303">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-304">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="7124d-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="7124d-305">Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos.</span><span class="sxs-lookup"><span data-stu-id="7124d-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="7124d-306">Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="7124d-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="7124d-307">Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7124d-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7124d-308"><strong>Envio de eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-309">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-310">Porcentagem de eco transmitido para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="7124d-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7124d-311"><strong>Chamadas com eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="7124d-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="7124d-312">Sim</span><span class="sxs-lookup"><span data-stu-id="7124d-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="7124d-313">Porcentagem do total de chamadas que tiveram eco excedendo o nível aceitável.</span><span class="sxs-lookup"><span data-stu-id="7124d-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

