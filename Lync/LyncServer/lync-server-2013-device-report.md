---
title: 'Lync Server 2013: relatório de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="d6d71-102">Relatório de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6d71-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d71-103">_**Tópico da última modificação:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d6d71-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d6d71-104">O Relatório de Dispositivos poderia trocar de nome para Relatório de Microfones e Alto-Falantes; isso porque o Relatório de Dispositivos recupera métricas relacionadas às chamadas (como o percentual de chamadas ruins, eco e tempo de troca de voz) agrupadas por microfone e alto-falante usados na chamada.</span><span class="sxs-lookup"><span data-stu-id="d6d71-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="d6d71-105">Se você estiver interessado em telefones IP (também chamados de "dispositivos"), use o relatório de [inventário de telefone IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="d6d71-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="d6d71-p102">O Relatório de Dispositivos é extremamente útil para os administradores ao determinar se um tipo específico de dispositivo está apresentando mais chamadas de baixa qualidade que outros. Por outro lado, pode influenciar decisões relacionadas à compra de novos dispositivos ou à substituição de dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="d6d71-p103">Por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, vamos supor que você tenha vários usuários que utilizam os seguintes dispositivos de captura e renderização: por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, vamos supor que você tenha vários usuários que utilizam os seguintes dispositivos de captura e renderização:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="d6d71-111">Dispositivo de captura -- Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="d6d71-112">Dispositivo de renderização -- Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d6d71-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="d6d71-113">Se esses usuários fizerem um total de 254 chamadas, você verá uma entrada como esta no relatório:</span><span class="sxs-lookup"><span data-stu-id="d6d71-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d71-114">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d6d71-114">Capture device</span></span></th>
<th><span data-ttu-id="d6d71-115">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="d6d71-115">Render device</span></span></th>
<th><span data-ttu-id="d6d71-116">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="d6d71-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-117">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-118">Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d6d71-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-119">254</span><span class="sxs-lookup"><span data-stu-id="d6d71-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6d71-p104">Agora, suponha que você tem um número de usuários que usam esse mesmo dispositivo de captura, mas que usam um dispositivo de renderização diferente. Neste caso, você terá uma segunda linha no relatório, uma para essa combinação exclusiva de dispositivo de captura e dispositivo de renderização:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d71-122">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d6d71-122">Capture device</span></span></th>
<th><span data-ttu-id="d6d71-123">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="d6d71-123">Render device</span></span></th>
<th><span data-ttu-id="d6d71-124">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="d6d71-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-125">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-126">Fone de ouvido com headset (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d6d71-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-127">254</span><span class="sxs-lookup"><span data-stu-id="d6d71-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-128">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-129">Alto-falantes (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-130">319</span><span class="sxs-lookup"><span data-stu-id="d6d71-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d6d71-p105">Se você preferir ver os totais combinados para um determinado dispositivo (por exemplo, para o dispositivo de captura SoundMAX, independente do dispositivo de renderização usado), selecione a opção apropriada na lista suspensa de tipo de dispositivo (dispositivo de captura ou dispositivo de renderização). Se você selecionar dispositivo de captura neste exemplo, terá algo parecido com isso:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d71-133">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d6d71-133">Capture device</span></span></th>
<th><span data-ttu-id="d6d71-134">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="d6d71-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-135">Microfone (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="d6d71-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d6d71-136">573</span><span class="sxs-lookup"><span data-stu-id="d6d71-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="d6d71-137">Acessando o relatório de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d6d71-137">Accessing the Device Report</span></span>

<span data-ttu-id="d6d71-138">O Relatório de Dispositivos é geralmente acessado na página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d6d71-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d6d71-139">No entanto, se você estiver exibindo o [relatório de detalhes de chamadas no Lync Server 2013](lync-server-2013-call-detail-report.md) , poderá fazer uma busca detalhada no relatório de dispositivo para um dispositivo específico clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="d6d71-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d6d71-140">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d6d71-140">Capture Device</span></span>

  - <span data-ttu-id="d6d71-141">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="d6d71-141">Render Device</span></span>

<span data-ttu-id="d6d71-142">No relatório do dispositivo, você pode fazer uma busca detalhada [no relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="d6d71-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d6d71-143">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="d6d71-143">Call volume</span></span>

  - <span data-ttu-id="d6d71-144">Porcentagem de chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="d6d71-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="d6d71-145">Como usar melhor o Relatório de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="d6d71-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="d6d71-146">Tratando-se de nomes de dispositivos, o Relatório de Dispositivos é extremamente detalhado. Por exemplo, suponha que você tem os seguintes dispositivos de captura:</span><span class="sxs-lookup"><span data-stu-id="d6d71-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="d6d71-147">Microfone Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d6d71-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="d6d71-148">Microfone Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d6d71-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="d6d71-149">Microfone Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d6d71-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="d6d71-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="d6d71-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="d6d71-151">Microfone Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-152">Microfone Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="d6d71-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d6d71-153">Microfone Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-154">Microfone Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-155">Microfone Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-156">Microfone Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-157">Microfone Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-158">Microfone Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-159">Microfone Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-160">Microfone Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="d6d71-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d6d71-161">Microfone Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d6d71-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="d6d71-162">Microfone Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="d6d71-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d6d71-163">Microfone Aastra 6725ip (Dispositivo de áudio USB)</span><span class="sxs-lookup"><span data-stu-id="d6d71-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="d6d71-164">Microfone Aastra 6725ip (Dispositivo de áudio USB)-V0</span><span class="sxs-lookup"><span data-stu-id="d6d71-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6d71-165">Lembre-se de que capturar nomes de dispositivos podem não ser iguais se você estiver executando versões localizadas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6d71-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="d6d71-166">Um dispositivo denominado Microfone Aastra 6725ip (Aastra 6725ip)-V0 em português pode ter um nome diferente em francês ou espanhol.</span><span class="sxs-lookup"><span data-stu-id="d6d71-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="d6d71-167">Muitas vezes você precisará desse nível de detalhe; mas, em outros momentos, você só estará interessado na quantidade de chamadas que usam um microfone Aastra, independente do número do modelo.</span><span class="sxs-lookup"><span data-stu-id="d6d71-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="d6d71-168">Uma maneira de obter informações como essa é exportar os dados do relatório do dispositivo para o Microsoft Excel e, em seguida, salvar esses dados em um arquivo de valores separados por vírgula\\(\\por\_exemplo, C: dispositivos de dados Report. csv).</span><span class="sxs-lookup"><span data-stu-id="d6d71-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="d6d71-169">É possível usar um conjunto de comandos parecidos com esses para importar o arquivo .CSV no Windows PowerShell e relatar o número total de chamadas feitas usando um dispositivo de captura Aastra:</span><span class="sxs-lookup"><span data-stu-id="d6d71-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="d6d71-p109">Esse procedimento retornará um único valor que representa o número total de chamadas usando um dispositivo de captura Aastra. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d6d71-172">Filtros</span><span class="sxs-lookup"><span data-stu-id="d6d71-172">Filters</span></span>

<span data-ttu-id="d6d71-p110">Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. Por exemplo, o Relatório de Dispositivos permite filtrar coisas como o tipo de chamada (isto é, a chamada foi realizada pelo cliente), uma chamada de conferência ou chamada PSTN. É possível também escolher como os dados devem ser agrupados. Neste caso, os dispositivos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d6d71-177">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6d71-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="d6d71-178">Filtros do Relatório de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="d6d71-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d71-179">Nome</span><span class="sxs-lookup"><span data-stu-id="d6d71-179">Name</span></span></th>
<th><span data-ttu-id="d6d71-180">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6d71-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-181"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p111">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d6d71-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d6d71-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d6d71-p112">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d6d71-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d6d71-187">7/7/2012</span></span></p>
<p><span data-ttu-id="d6d71-188">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="d6d71-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d6d71-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d6d71-189">7/3/2012</span></span></p>
<p><span data-ttu-id="d6d71-190">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="d6d71-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-191"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p113">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d6d71-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d6d71-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d6d71-p114">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d6d71-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d6d71-197">7/7/2012</span></span></p>
<p><span data-ttu-id="d6d71-198">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="d6d71-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d6d71-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d6d71-199">7/3/2012</span></span></p>
<p><span data-ttu-id="d6d71-200">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="d6d71-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-201"><strong>Causa de troca de voz</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p115">Motivo pelo qual uma chamada precisou ser colocada no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-205">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-206">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d6d71-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-207">Carimbo de data/hora inválido</span><span class="sxs-lookup"><span data-stu-id="d6d71-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-208">Eco</span><span class="sxs-lookup"><span data-stu-id="d6d71-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-209">DNLP (processador não linear dinâmico)</span><span class="sxs-lookup"><span data-stu-id="d6d71-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-210">Baixa complexidade</span><span class="sxs-lookup"><span data-stu-id="d6d71-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-211">Estado do dispositivo inválido</span><span class="sxs-lookup"><span data-stu-id="d6d71-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-212">Eco pós-AEC (cancelamento do eco acústico)</span><span class="sxs-lookup"><span data-stu-id="d6d71-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-213"><strong>Causa do eco</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p116">Motivo pelo qual o eco acima do aceitável foi detectado em uma chamada. (Em telecomunicações, o eco é um reflexo do som, o mesmo fenômeno que você ouvirá se gritar em um poço). Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-216">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-217">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d6d71-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-218">Carimbo de data/hora inválido</span><span class="sxs-lookup"><span data-stu-id="d6d71-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-219">Eco pós-AEC (cancelamento do eco acústico)</span><span class="sxs-lookup"><span data-stu-id="d6d71-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-220">ANLP (processador não linear adaptado)</span><span class="sxs-lookup"><span data-stu-id="d6d71-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-221">DNLP (processador não linear dinâmico)</span><span class="sxs-lookup"><span data-stu-id="d6d71-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-222">Distorção do microfone</span><span class="sxs-lookup"><span data-stu-id="d6d71-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-223"><strong>Tipo de chamada</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p117">Indica o tipo de chamada realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-226">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-227">Chamada do cliente</span><span class="sxs-lookup"><span data-stu-id="d6d71-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-228">Chamada PSTN</span><span class="sxs-lookup"><span data-stu-id="d6d71-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-229">Chamada de conferência</span><span class="sxs-lookup"><span data-stu-id="d6d71-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-230"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p118">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-233">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-234">Interno</span><span class="sxs-lookup"><span data-stu-id="d6d71-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-235">Externo</span><span class="sxs-lookup"><span data-stu-id="d6d71-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-236"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p119">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-239">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-240">Com fio</span><span class="sxs-lookup"><span data-stu-id="d6d71-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-241">Sem fio</span><span class="sxs-lookup"><span data-stu-id="d6d71-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p120">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-245">[Todos]</span><span class="sxs-lookup"><span data-stu-id="d6d71-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-246">VPN</span><span class="sxs-lookup"><span data-stu-id="d6d71-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-247">Não VPN</span><span class="sxs-lookup"><span data-stu-id="d6d71-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-248"><strong>Tipo de dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p121">Indica o tipo de dispositivo. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-251">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d6d71-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-252">Dispositivos de renderização</span><span class="sxs-lookup"><span data-stu-id="d6d71-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d6d71-253">Par de dispositivos de captura/renderização</span><span class="sxs-lookup"><span data-stu-id="d6d71-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-254"><strong>Nome do dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-p122">Nome do dispositivo de captura ou renderização. É possível inserir o nome completo do dispositivo ou qualquer parte do nome. Por exemplo para encontrar o dispositivo Microfone (Microsoft LifeCam VX-1000.), é possível inserir o nome completo do dispositivo, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="d6d71-258">Microfone (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="d6d71-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="d6d71-p123">Como alternativa, é possível inserir apenas uma parte do nome. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d6d71-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="d6d71-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="d6d71-261">LifeCam</span></span></p>
<p><span data-ttu-id="d6d71-262">Observe que o filtro anterior retorna qualquer dispositivo que contém a cadeia &quot;de&quot; caracteres LifeCam em qualquer lugar em seu nome.</span><span class="sxs-lookup"><span data-stu-id="d6d71-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d6d71-263">Métricas</span><span class="sxs-lookup"><span data-stu-id="d6d71-263">Metrics</span></span>

<span data-ttu-id="d6d71-264">A tabela a seguir lista a informação apresentada no Relatório de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6d71-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="d6d71-265">Métricas do Relatório de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="d6d71-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d71-266">Nome</span><span class="sxs-lookup"><span data-stu-id="d6d71-266">Name</span></span></th>
<th><span data-ttu-id="d6d71-267">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="d6d71-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d6d71-268">Descrição</span><span class="sxs-lookup"><span data-stu-id="d6d71-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-269"><strong>Dispositivo de captura</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-270">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-271">Dispositivo (por exemplo, um microfone ou webcam) usado para transmitir áudio.</span><span class="sxs-lookup"><span data-stu-id="d6d71-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-272"><strong>Dispositivo de renderização</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-273">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-274">Dispositivo (por exemplo, um fone de ouvido ou alto falantes) usados para receber áudio.</span><span class="sxs-lookup"><span data-stu-id="d6d71-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-275"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-276">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-277">Número total de chamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="d6d71-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-278"><strong>Porcentagem de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-279">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-280">Porcentagem de chamadas classificadas como &quot;ruins. &quot; Uma chamada ruim é qualquer chamada que pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada que sofreu tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="d6d71-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-281"><strong>Usuários únicos</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-282">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p124">Usuários exclusivos que utilizaram o dispositivo. Se um usuário utilizou o dispositivo 13 vezes, ele ou ela deve contar como um usuário exclusivo, o mesmo que um usuário que utilizou o dispositivo uma única vez.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-285"><strong>Tempo de troca da taxa de voz</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-286">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p125">Porcentagem da chamada que precisou ser conduzida no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-289"><strong>Taxa de microfones não funcionando</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-290">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p126">Porcentagem da chamada na qual o dispositivo de captura não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de captura não estar funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-293"><strong>Taxa de alto falantes não funcionando</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-294">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p127">Porcentagem da chamada na qual o dispositivo de renderização não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de renderização não estar funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-297"><strong>Chamadas com troca de voz (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-298">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p128">Porcentagem do total de chamadas que precisaram ser colocadas no modo half duplex. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-301"><strong>Microfone com eco em (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-302">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-p129">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6d71-p129">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d71-307"><strong>Envio de eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-308">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-309">Porcentagem de eco transmitido para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d6d71-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d71-310"><strong>Chamadas com eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d6d71-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d6d71-311">Sim</span><span class="sxs-lookup"><span data-stu-id="d6d71-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="d6d71-312">Porcentagem do total de chamadas que tiveram eco excedendo o nível aceitável.</span><span class="sxs-lookup"><span data-stu-id="d6d71-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

