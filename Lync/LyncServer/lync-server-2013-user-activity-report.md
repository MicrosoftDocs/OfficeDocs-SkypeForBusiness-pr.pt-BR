---
title: 'Lync Server 2013: relatório de atividades do usuário'
description: 'Lync Server 2013: relatório de atividades do usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569827"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="85048-103">Relatório de atividades do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85048-103">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85048-104">_**Última modificação do tópico:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="85048-104">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="85048-105">O relatório de atividades do usuário fornece uma lista detalhada das sessões ponto a ponto e de conferência executadas pelos usuários em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="85048-105">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period.</span></span> <span data-ttu-id="85048-106">Ao contrário de muitos dos relatórios de monitoramento, o relatório de atividades do usuário vincula cada chamada a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="85048-106">Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users.</span></span> <span data-ttu-id="85048-107">Por exemplo, sessões ponto a ponto especificam os URIs SIP da pessoa que iniciou a chamada (o usuário de) e a pessoa que está sendo chamada (o para o usuário).</span><span class="sxs-lookup"><span data-stu-id="85048-107">For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user).</span></span> <span data-ttu-id="85048-108">Se você expandir as informações de uma conferência, verá uma lista de todos os participantes da conferência e a função que eles realizaram para a conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-108">If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="85048-109">O relatório de atividades do usuário às vezes é chamado de relatório "Help Desk".</span><span class="sxs-lookup"><span data-stu-id="85048-109">The User Activity Report is sometimes referred to as the "help desk" report.</span></span> <span data-ttu-id="85048-110">Isso ocorre porque o relatório é geralmente usado pela equipe de assistência técnica para recuperar informações de sessão de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="85048-110">That's because the report is often used by help desk personnel to retrieve session information for a specific user.</span></span> <span data-ttu-id="85048-111">Você pode filtrar por chamadas feitas ou feitas por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa prefixo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-111">You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="85048-112">Se você fizer isso, o relatório de atividades do usuário retornará informações para qualquer usuário cujo URI de SIP comece com a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="85048-112">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="85048-113">Por exemplo, se você digitar **Ken** na caixa URI, o relatório de atividades do usuário localizará **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="85048-113">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="85048-114">No entanto, ele também localizará estes usuários:</span><span class="sxs-lookup"><span data-stu-id="85048-114">However, it will also locate these users:</span></span>

  - <span data-ttu-id="85048-115">**ken**Azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85048-115">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="85048-116">**ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85048-116">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="85048-117">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85048-117">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="85048-118">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85048-118">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="85048-119">Para garantir que as informações somente para Ken Myer sejam retornadas, digite o URI completo (Ken.Myer@litwareinc.com) na caixa de pesquisa ou pelo menos o tipo de URI de Ken para distingui-lo exclusivamente de outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="85048-119">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="85048-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="85048-120">For example:</span></span>

<span data-ttu-id="85048-121">Ken.my</span><span class="sxs-lookup"><span data-stu-id="85048-121">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="85048-122">Para acessar o relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="85048-122">To access the user activity report</span></span>

<span data-ttu-id="85048-123">O relatório de atividades do usuário é acessado a partir da Home Page de relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="85048-123">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="85048-124">Você também pode acessar o relatório de atividades do usuário clicando na métrica URI do sistema de [telefonia IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="85048-124">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="85048-125">No relatório de atividades do usuário, clicar no URI da conferência (para uma conferência) leva você para o relatório de detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-125">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="85048-126">Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você para o [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="85048-126">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="85048-127">Fazendo o melhor uso do relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="85048-127">Making the best use of the user activity report</span></span>

<span data-ttu-id="85048-128">Embora haja muitas informações boas no relatório de atividades do usuário, essas informações podem, às vezes, ser difíceis de localizar.</span><span class="sxs-lookup"><span data-stu-id="85048-128">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="85048-129">Por exemplo, toda a atividade do usuário que ocorre na sua organização durante um período especificado é incluída no relatório de atividades do usuário; Isso significa que, neste caso, as informações sobre quais usuários realmente usaram o Microsoft Lync Server 2013 de alguma forma.</span><span class="sxs-lookup"><span data-stu-id="85048-129">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="85048-130">Tecnicamente, é possível que alguma atividade de usuário seja não gravada: enquanto o Lync Server se esforça para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem que as informações sobre a chamada sejam gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85048-130">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="85048-131">O Lync Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita, como o Lync Server 2013 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="85048-131">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="85048-132">(O fato de não haver garantia de que 100% de todas as chamadas são registradas explica por que o monitoramento do Lync Server não deve ser usado como um sistema de cobrança.)</span><span class="sxs-lookup"><span data-stu-id="85048-132">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="85048-133">Segundo, um relatório de relatório de monitoramento só pode exibir, no máximo, 1.000 registros.</span><span class="sxs-lookup"><span data-stu-id="85048-133">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="85048-134">Dependendo da quantidade de atividade do usuário que você tem e, dependendo do período de tempo com o qual você está trabalhando, isso significa que a consulta pode não retornar todos os dados realmente armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85048-134">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="85048-135">Quais usuários usaram realmente o sistema durante esse período de tempo?</span><span class="sxs-lookup"><span data-stu-id="85048-135">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="85048-136">Quais dos meus usuários foram os mais ativos durante esse período de tempo?</span><span class="sxs-lookup"><span data-stu-id="85048-136">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="85048-137">Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?</span><span class="sxs-lookup"><span data-stu-id="85048-137">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="85048-138">Se você precisar responder a perguntas como esta, é possível exportar os dados recuperados pelos relatórios de monitoramento para uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="85048-138">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="85048-139">Em seguida, você usa essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados de forma que o relatório de atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-139">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="85048-140">Por exemplo, suponha que você tenha exportado os dados do relatório para o Excel e, em seguida, para um arquivo de valores separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="85048-140">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="85048-141">Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="85048-141">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="85048-142">Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas.</span><span class="sxs-lookup"><span data-stu-id="85048-142">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="85048-143">Por exemplo, este comando retorna uma lista de usuários exclusivos que serviam como "de usuário" em pelo menos uma sessão:</span><span class="sxs-lookup"><span data-stu-id="85048-143">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="85048-144">Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="85048-144">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="85048-145">Este comando lista os usuários exclusivos (com base no número total de sessões nas quais participaram:</span><span class="sxs-lookup"><span data-stu-id="85048-145">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="85048-146">Ele retorna dados semelhantes a isto:</span><span class="sxs-lookup"><span data-stu-id="85048-146">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="85048-147">Este comando limita as sessões relatadas àquelas que incluíram áudio como modalidade:</span><span class="sxs-lookup"><span data-stu-id="85048-147">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="85048-148">Se você mantiver o mouse sobre qualquer ID de diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo essa ID.</span><span class="sxs-lookup"><span data-stu-id="85048-148">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="85048-149">Filtros</span><span class="sxs-lookup"><span data-stu-id="85048-149">Filters</span></span>

<span data-ttu-id="85048-150">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="85048-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="85048-151">Por exemplo, o relatório de atividades do usuário permite que você filtre os dados retornados com base em coisas como o tipo de atividade (ou seja, sessões ponto a ponto ou sessões de conferência) ou pelo endereço SIP do usuário (permitindo que você exiba as atividades de um usuário).</span><span class="sxs-lookup"><span data-stu-id="85048-151">For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user).</span></span> <span data-ttu-id="85048-152">Também é possível escolher como os dados devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="85048-152">You can also choose how data should be grouped.</span></span> <span data-ttu-id="85048-153">Nesse caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="85048-153">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="85048-154">A tabela a seguir lista os filtros que podem ser usados com o relatório de atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-154">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="85048-155">Filtros de relatórios de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="85048-155">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85048-156">Nome</span><span class="sxs-lookup"><span data-stu-id="85048-156">Name</span></span></th>
<th><span data-ttu-id="85048-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="85048-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85048-158"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="85048-158"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-p112">Data/hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="85048-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="85048-161">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="85048-161">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="85048-p113">Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="85048-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="85048-164">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="85048-164">7/17/12012</span></span></p>
<p><span data-ttu-id="85048-165">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="85048-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="85048-166">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="85048-166">7/13/2012</span></span></p>
<p><span data-ttu-id="85048-167">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="85048-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-168"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="85048-168"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-p114">Data/hora de término para o intervalo de tempo. Para exibir os dados por horas, digite a data e hora de término da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="85048-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="85048-171">17/07/12012 13:00</span><span class="sxs-lookup"><span data-stu-id="85048-171">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="85048-p115">Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="85048-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="85048-174">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="85048-174">7/17/12012</span></span></p>
<p><span data-ttu-id="85048-175">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="85048-175">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="85048-176">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="85048-176">7/13/2012</span></span></p>
<p><span data-ttu-id="85048-177">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="85048-177">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-178"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="85048-178"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-p116">Tipo de atividade. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="85048-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="85048-181">Todos os</span><span class="sxs-lookup"><span data-stu-id="85048-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="85048-182">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="85048-182">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="85048-183">Conferência</span><span class="sxs-lookup"><span data-stu-id="85048-183">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-184"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="85048-184"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-185">A modalidade disponível para você varia de acordo com o tipo de atividade SELECT.</span><span class="sxs-lookup"><span data-stu-id="85048-185">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="85048-186">Se o tipo de atividade for ponto a ponto, você poderá selecionar IM; Transferência de arquivos; Compartilhamento de aplicativos; Voice ou vídeo como a modalidade.</span><span class="sxs-lookup"><span data-stu-id="85048-186">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="85048-187">Se o tipo de atividade for conferência, você poderá selecionar conferência telefônica de mensagens instantâneas; Conferência da Web; Compartilhamento de aplicativos; Conferência de voz/vídeo; ou conferência telefônica.</span><span class="sxs-lookup"><span data-stu-id="85048-187">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-188"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="85048-188"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-p118">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="85048-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="85048-191">Todos os</span><span class="sxs-lookup"><span data-stu-id="85048-191">[All]</span></span></p></li>
<li><p><span data-ttu-id="85048-192">Sucesso</span><span class="sxs-lookup"><span data-stu-id="85048-192">Success</span></span></p></li>
<li><p><span data-ttu-id="85048-193">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="85048-193">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="85048-194">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="85048-194">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="85048-195">Uma &quot; falha esperada &quot; é uma falha que deve ocorrer; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="85048-195">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="85048-196">Uma &quot; falha inesperada &quot; é uma falha que ocorre no que parece ser um sistema saudável de outra forma.</span><span class="sxs-lookup"><span data-stu-id="85048-196">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="85048-197">Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="85048-197">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="85048-198">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="85048-198">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-199"><strong>Prefixo URI do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="85048-199"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-200">Endereço SIP para o usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-200">SIP address for the user.</span></span> <span data-ttu-id="85048-201">Para exibir registros apenas para o usuário Ken Myer, você precisa inserir o endereço SIP de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="85048-201">To view records only for the user Ken Myer you need to enter Ken Myer's SIP address.</span></span> <span data-ttu-id="85048-202">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="85048-202">For example:</span></span></p>
<p><span data-ttu-id="85048-203">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="85048-203">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="85048-204">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="85048-204">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="85048-205">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).</span><span class="sxs-lookup"><span data-stu-id="85048-205">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="85048-206">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="85048-206">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85048-207">Nome</span><span class="sxs-lookup"><span data-stu-id="85048-207">Name</span></span></th>
<th><span data-ttu-id="85048-208">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="85048-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="85048-209">Descrição</span><span class="sxs-lookup"><span data-stu-id="85048-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85048-210"><strong>Ver os detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="85048-210"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-211">Não</span><span class="sxs-lookup"><span data-stu-id="85048-211">No</span></span></p></td>
<td><p><span data-ttu-id="85048-212">Quando você clica nesse item, o relatório mostra o relatório de detalhes de sessão ponto a ponto da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="85048-212">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-213"><strong>Do usuário </strong></span><span class="sxs-lookup"><span data-stu-id="85048-213"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-214">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-215">Endereço SIP do usuário que iniciou a sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="85048-215">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-216"><strong>Para usuário</strong></span><span class="sxs-lookup"><span data-stu-id="85048-216"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-217">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-218">Endereço SIP do usuário que ingressou na sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="85048-218">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-219"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="85048-219"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-220">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-221">Tipo de comunicação usada na sessão.</span><span class="sxs-lookup"><span data-stu-id="85048-221">Type of communication used in the session.</span></span> <span data-ttu-id="85048-222">Por exemplo, IM, áudio ou transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="85048-222">For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-223"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="85048-223"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-224">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-225">Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.</span><span class="sxs-lookup"><span data-stu-id="85048-225">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-226"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="85048-226"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-227">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-228">Data e hora em que &quot; o &quot; usuário deve aceitar o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="85048-228">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-229"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="85048-229"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-230">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-231">Data e hora em que a sessão ponto a ponto terminou.</span><span class="sxs-lookup"><span data-stu-id="85048-231">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-232"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="85048-232"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-233">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-p122">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="85048-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="85048-236">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="85048-236">Metrics for conferencing sessions</span></span>

<span data-ttu-id="85048-237">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="85048-237">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="85048-238">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="85048-238">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85048-239">Nome</span><span class="sxs-lookup"><span data-stu-id="85048-239">Name</span></span></th>
<th><span data-ttu-id="85048-240">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="85048-240">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="85048-241">Descrição</span><span class="sxs-lookup"><span data-stu-id="85048-241">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85048-242"><strong>URI de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="85048-242"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-243">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-243">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-244">Identificador de conferência exclusivo.</span><span class="sxs-lookup"><span data-stu-id="85048-244">Unique conference identifier.</span></span> <span data-ttu-id="85048-245">Quando você clica nesse item, o relatório mostra o relatório de detalhes da conferência da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="85048-245">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="85048-246">Quando você expande esse item, o relatório mostra informações sobre os participantes da conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-246">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="85048-247">Para obter detalhes, consulte a &quot; seção métricas para participantes da conferência &quot; mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="85048-247">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-248"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="85048-248"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-249">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-249">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-250">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-250">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-251"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="85048-251"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-252">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-252">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-253">Nome do servidor de borda (se houver) usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-253">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-254"><strong>Hora de início</strong></span><span class="sxs-lookup"><span data-stu-id="85048-254"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-255">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-255">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-256">Data e hora em que a conferência começou.</span><span class="sxs-lookup"><span data-stu-id="85048-256">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-257"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="85048-257"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-258">Sim</span><span class="sxs-lookup"><span data-stu-id="85048-258">Yes</span></span></p></td>
<td><p><span data-ttu-id="85048-259">Data e hora de encerramento da conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-259">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="85048-260">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="85048-260">Metrics for conference participants</span></span>

<span data-ttu-id="85048-261">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para cada participante de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-261">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="85048-262">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="85048-262">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85048-263">Nome</span><span class="sxs-lookup"><span data-stu-id="85048-263">Name</span></span></th>
<th><span data-ttu-id="85048-264">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="85048-264">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="85048-265">Descrição</span><span class="sxs-lookup"><span data-stu-id="85048-265">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85048-266"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="85048-266"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-267">Não</span><span class="sxs-lookup"><span data-stu-id="85048-267">No</span></span></p></td>
<td><p><span data-ttu-id="85048-268">Função de conferência (por exemplo, apresentador) para o usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-268">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-269"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="85048-269"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-270">Não</span><span class="sxs-lookup"><span data-stu-id="85048-270">No</span></span></p></td>
<td><p><span data-ttu-id="85048-271">Endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="85048-271">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-272"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="85048-272"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-273">Não</span><span class="sxs-lookup"><span data-stu-id="85048-273">No</span></span></p></td>
<td><p><span data-ttu-id="85048-274">Tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="85048-274">Network connection type.</span></span> <span data-ttu-id="85048-275">Por exemplo, &quot; de interno &quot; para conexão interna ou &quot; da PSTN &quot; para usuários de discagem.</span><span class="sxs-lookup"><span data-stu-id="85048-275">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-276"><strong>Hora de ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="85048-276"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-277">Não</span><span class="sxs-lookup"><span data-stu-id="85048-277">No</span></span></p></td>
<td><p><span data-ttu-id="85048-278">Data e hora em que o usuário entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-278">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85048-279"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="85048-279"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-280">Não</span><span class="sxs-lookup"><span data-stu-id="85048-280">No</span></span></p></td>
<td><p><span data-ttu-id="85048-281">Data e hora em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="85048-281">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85048-282"><strong>ID de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="85048-282"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="85048-283">Não</span><span class="sxs-lookup"><span data-stu-id="85048-283">No</span></span></p></td>
<td><p><span data-ttu-id="85048-p125">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="85048-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

