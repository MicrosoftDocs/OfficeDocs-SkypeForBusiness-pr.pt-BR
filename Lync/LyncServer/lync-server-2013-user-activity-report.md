---
title: 'Lync Server 2013: relatório de atividades do usuário'
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
ms.openlocfilehash: 38df7f9f8c457ac68ee441a6806b87f37b10539b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="30222-102">Relatório de atividades do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30222-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30222-103">_**Última modificação do tópico:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="30222-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="30222-104">O relatório de atividades do usuário fornece uma lista detalhada das sessões ponto a ponto e de conferência executadas pelos usuários em um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="30222-104">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period.</span></span> <span data-ttu-id="30222-105">Ao contrário de muitos dos relatórios de monitoramento, o relatório de atividades do usuário vincula cada chamada a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="30222-105">Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users.</span></span> <span data-ttu-id="30222-106">Por exemplo, sessões ponto a ponto especificam os URIs SIP da pessoa que iniciou a chamada (o usuário de) e a pessoa que está sendo chamada (o para o usuário).</span><span class="sxs-lookup"><span data-stu-id="30222-106">For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user).</span></span> <span data-ttu-id="30222-107">Se você expandir as informações de uma conferência, verá uma lista de todos os participantes da conferência e a função que eles realizaram para a conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-107">If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="30222-108">O relatório de atividades do usuário às vezes é chamado de relatório "Help Desk".</span><span class="sxs-lookup"><span data-stu-id="30222-108">The User Activity Report is sometimes referred to as the "help desk" report.</span></span> <span data-ttu-id="30222-109">Isso ocorre porque o relatório é geralmente usado pela equipe de assistência técnica para recuperar informações de sessão de um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="30222-109">That's because the report is often used by help desk personnel to retrieve session information for a specific user.</span></span> <span data-ttu-id="30222-110">Você pode filtrar por chamadas feitas ou feitas por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa prefixo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-110">You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="30222-111">Se você fizer isso, o relatório de atividades do usuário retornará informações para qualquer usuário cujo URI de SIP comece com a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="30222-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="30222-112">Por exemplo, se você digitar **Ken** na caixa URI, o relatório de atividades do usuário localizará **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="30222-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="30222-113">No entanto, ele também localizará estes usuários:</span><span class="sxs-lookup"><span data-stu-id="30222-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="30222-114">**ken**Azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30222-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="30222-115">**ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30222-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="30222-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30222-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="30222-117">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30222-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="30222-118">Para garantir que as informações somente para Ken Myer sejam retornadas, digite o URI completo (Ken.Myer@litwareinc.com) na caixa de pesquisa ou pelo menos o tipo de URI de Ken para distingui-lo exclusivamente de outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="30222-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="30222-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="30222-119">For example:</span></span>

<span data-ttu-id="30222-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="30222-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="30222-121">Para acessar o relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="30222-121">To access the user activity report</span></span>

<span data-ttu-id="30222-122">O relatório de atividades do usuário é acessado a partir da Home Page de relatórios de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="30222-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="30222-123">Você também pode acessar o relatório de atividades do usuário clicando na métrica URI do sistema de [telefonia IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="30222-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="30222-124">No relatório de atividades do usuário, clicar no URI da conferência (para uma conferência) leva você para o relatório de detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="30222-125">Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você para o [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="30222-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="30222-126">Fazendo o melhor uso do relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="30222-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="30222-127">Embora haja muitas informações boas no relatório de atividades do usuário, essas informações podem, às vezes, ser difíceis de localizar.</span><span class="sxs-lookup"><span data-stu-id="30222-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="30222-128">Por exemplo, toda a atividade do usuário que ocorre na sua organização durante um período especificado é incluída no relatório de atividades do usuário; Isso significa que, neste caso, as informações sobre quais usuários realmente usaram o Microsoft Lync Server 2013 de alguma forma.</span><span class="sxs-lookup"><span data-stu-id="30222-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="30222-129">Tecnicamente, é possível que alguma atividade de usuário seja não gravada: enquanto o Lync Server se esforça para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem que as informações sobre a chamada sejam gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="30222-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="30222-130">O Lync Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita, como o Lync Server 2013 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="30222-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="30222-131">(O fato de não haver garantia de que 100% de todas as chamadas são registradas explica por que o monitoramento do Lync Server não deve ser usado como um sistema de cobrança.)</span><span class="sxs-lookup"><span data-stu-id="30222-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="30222-132">Segundo, um relatório de relatório de monitoramento só pode exibir, no máximo, 1.000 registros.</span><span class="sxs-lookup"><span data-stu-id="30222-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="30222-133">Dependendo da quantidade de atividade do usuário que você tem e, dependendo do período de tempo com o qual você está trabalhando, isso significa que a consulta pode não retornar todos os dados realmente armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="30222-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="30222-134">Quais usuários usaram realmente o sistema durante esse período de tempo?</span><span class="sxs-lookup"><span data-stu-id="30222-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="30222-135">Quais dos meus usuários foram os mais ativos durante esse período de tempo?</span><span class="sxs-lookup"><span data-stu-id="30222-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="30222-136">Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?</span><span class="sxs-lookup"><span data-stu-id="30222-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="30222-137">Se você precisar responder a perguntas como esta, é possível exportar os dados recuperados pelos relatórios de monitoramento para uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="30222-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="30222-138">Em seguida, você usa essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados de forma que o relatório de atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="30222-139">Por exemplo, suponha que você tenha exportado os dados do relatório para o Excel e, em seguida, para um arquivo de valores separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="30222-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="30222-140">Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="30222-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="30222-141">Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas.</span><span class="sxs-lookup"><span data-stu-id="30222-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="30222-142">Por exemplo, este comando retorna uma lista de usuários exclusivos que serviam como "de usuário" em pelo menos uma sessão:</span><span class="sxs-lookup"><span data-stu-id="30222-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="30222-143">Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="30222-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="30222-144">Este comando lista os usuários exclusivos (com base no número total de sessões nas quais participaram:</span><span class="sxs-lookup"><span data-stu-id="30222-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="30222-145">Ele retorna dados semelhantes a isto:</span><span class="sxs-lookup"><span data-stu-id="30222-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="30222-146">Este comando limita as sessões relatadas àquelas que incluíram áudio como modalidade:</span><span class="sxs-lookup"><span data-stu-id="30222-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="30222-147">Se você mantiver o mouse sobre qualquer ID de diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo essa ID.</span><span class="sxs-lookup"><span data-stu-id="30222-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="30222-148">Filtros</span><span class="sxs-lookup"><span data-stu-id="30222-148">Filters</span></span>

<span data-ttu-id="30222-149">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="30222-149">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="30222-150">Por exemplo, o relatório de atividades do usuário permite que você filtre os dados retornados com base em coisas como o tipo de atividade (ou seja, sessões ponto a ponto ou sessões de conferência) ou pelo endereço SIP do usuário (permitindo que você exiba as atividades de um usuário).</span><span class="sxs-lookup"><span data-stu-id="30222-150">For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user).</span></span> <span data-ttu-id="30222-151">Também é possível escolher como os dados devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="30222-151">You can also choose how data should be grouped.</span></span> <span data-ttu-id="30222-152">Nesse caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="30222-152">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="30222-153">A tabela a seguir lista os filtros que podem ser usados com o relatório de atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="30222-154">Filtros de relatórios de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="30222-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30222-155">Nome</span><span class="sxs-lookup"><span data-stu-id="30222-155">Name</span></span></th>
<th><span data-ttu-id="30222-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="30222-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30222-157"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="30222-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-p112">Data/hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="30222-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="30222-160">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="30222-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="30222-p113">Se você não digitar um horário de início, o relatório começará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="30222-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="30222-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="30222-163">7/17/12012</span></span></p>
<p><span data-ttu-id="30222-164">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="30222-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="30222-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="30222-165">7/13/2012</span></span></p>
<p><span data-ttu-id="30222-166">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="30222-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="30222-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-p114">Data/hora de término para o intervalo de tempo. Para exibir os dados por horas, digite a data e hora de término da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="30222-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="30222-170">17/07/12012 13:00</span><span class="sxs-lookup"><span data-stu-id="30222-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="30222-p115">Se você não digitar um horário de término, o relatório terminará automaticamente às 12:00 AM no dia especificado. Para exibir os dados por dia, digite apenas a data:</span><span class="sxs-lookup"><span data-stu-id="30222-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="30222-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="30222-173">7/17/12012</span></span></p>
<p><span data-ttu-id="30222-174">Para exibir por semana ou por mês, insira uma data cai em qualquer lugar dentro da semana ou mês que você deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="30222-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="30222-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="30222-175">7/13/2012</span></span></p>
<p><span data-ttu-id="30222-176">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="30222-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-177"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="30222-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-p116">Tipo de atividade. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="30222-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="30222-180">Todos os</span><span class="sxs-lookup"><span data-stu-id="30222-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="30222-181">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="30222-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="30222-182">Conferência</span><span class="sxs-lookup"><span data-stu-id="30222-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-183"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="30222-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-184">A modalidade disponível para você varia de acordo com o tipo de atividade SELECT.</span><span class="sxs-lookup"><span data-stu-id="30222-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="30222-185">Se o tipo de atividade for ponto a ponto, você poderá selecionar IM; Transferência de arquivos; Compartilhamento de aplicativos; Voice ou vídeo como a modalidade.</span><span class="sxs-lookup"><span data-stu-id="30222-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="30222-186">Se o tipo de atividade for conferência, você poderá selecionar conferência telefônica de mensagens instantâneas; Conferência da Web; Compartilhamento de aplicativos; Conferência de voz/vídeo; ou conferência telefônica.</span><span class="sxs-lookup"><span data-stu-id="30222-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-187"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="30222-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-p118">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="30222-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="30222-190">Todos os</span><span class="sxs-lookup"><span data-stu-id="30222-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="30222-191">Êxito</span><span class="sxs-lookup"><span data-stu-id="30222-191">Success</span></span></p></li>
<li><p><span data-ttu-id="30222-192">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="30222-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="30222-193">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="30222-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="30222-194">Uma &quot;falha&quot; esperada é uma falha que deve acontecer; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="30222-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="30222-195">Uma &quot;falha&quot; inesperada é uma falha que ocorre no que parece ser um sistema saudável de outra forma.</span><span class="sxs-lookup"><span data-stu-id="30222-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="30222-196">Por exemplo, uma chamada não deveria ser terminada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="30222-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="30222-197">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="30222-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-198"><strong>Prefixo URI do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="30222-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-199">Endereço SIP para o usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-199">SIP address for the user.</span></span> <span data-ttu-id="30222-200">Para exibir registros apenas para o usuário Ken Myer, você precisa inserir o endereço SIP de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="30222-200">To view records only for the user Ken Myer you need to enter Ken Myer's SIP address.</span></span> <span data-ttu-id="30222-201">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="30222-201">For example:</span></span></p>
<p><span data-ttu-id="30222-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="30222-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="30222-203">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="30222-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="30222-204">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).</span><span class="sxs-lookup"><span data-stu-id="30222-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="30222-205">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="30222-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30222-206">Nome</span><span class="sxs-lookup"><span data-stu-id="30222-206">Name</span></span></th>
<th><span data-ttu-id="30222-207">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="30222-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="30222-208">Descrição</span><span class="sxs-lookup"><span data-stu-id="30222-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30222-209"><strong>Ver os detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="30222-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-210">Não</span><span class="sxs-lookup"><span data-stu-id="30222-210">No</span></span></p></td>
<td><p><span data-ttu-id="30222-211">Quando você clica nesse item, o relatório mostra o relatório de detalhes de sessão ponto a ponto da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="30222-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-212"><strong>Do usuário </strong></span><span class="sxs-lookup"><span data-stu-id="30222-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-213">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-214">Endereço SIP do usuário que iniciou a sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="30222-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-215"><strong>Para usuário</strong></span><span class="sxs-lookup"><span data-stu-id="30222-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-216">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-217">Endereço SIP do usuário que ingressou na sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="30222-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-218"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="30222-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-219">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-220">Tipo de comunicação usada na sessão.</span><span class="sxs-lookup"><span data-stu-id="30222-220">Type of communication used in the session.</span></span> <span data-ttu-id="30222-221">Por exemplo, IM, áudio ou transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="30222-221">For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-222"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="30222-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-223">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-224">Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.</span><span class="sxs-lookup"><span data-stu-id="30222-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-225"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="30222-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-226">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-227">Data e hora em que &quot;o&quot; usuário deve aceitar o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="30222-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-228"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="30222-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-229">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-230">Data e hora em que a sessão ponto a ponto terminou.</span><span class="sxs-lookup"><span data-stu-id="30222-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-231"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="30222-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-232">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-p122">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="30222-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="30222-235">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="30222-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="30222-236">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="30222-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="30222-237">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="30222-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30222-238">Nome</span><span class="sxs-lookup"><span data-stu-id="30222-238">Name</span></span></th>
<th><span data-ttu-id="30222-239">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="30222-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="30222-240">Descrição</span><span class="sxs-lookup"><span data-stu-id="30222-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30222-241"><strong>URI de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="30222-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-242">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-243">Identificador de conferência exclusivo.</span><span class="sxs-lookup"><span data-stu-id="30222-243">Unique conference identifier.</span></span> <span data-ttu-id="30222-244">Quando você clica nesse item, o relatório mostra o relatório de detalhes da conferência da sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="30222-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="30222-245">Quando você expande esse item, o relatório mostra informações sobre os participantes da conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="30222-246">Para obter detalhes, consulte &quot;a seção métricas para&quot; participantes da conferência mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="30222-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-247"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="30222-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-248">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-249">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="30222-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-251">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-252">Nome do servidor de borda (se houver) usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-253"><strong>Hora de início</strong></span><span class="sxs-lookup"><span data-stu-id="30222-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-254">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-255">Data e hora em que a conferência começou.</span><span class="sxs-lookup"><span data-stu-id="30222-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-256"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="30222-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-257">Sim</span><span class="sxs-lookup"><span data-stu-id="30222-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="30222-258">Data e hora de encerramento da conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="30222-259">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="30222-259">Metrics for conference participants</span></span>

<span data-ttu-id="30222-260">A tabela a seguir lista as informações fornecidas no relatório de atividades do usuário para cada participante de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="30222-261">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="30222-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30222-262">Nome</span><span class="sxs-lookup"><span data-stu-id="30222-262">Name</span></span></th>
<th><span data-ttu-id="30222-263">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="30222-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="30222-264">Descrição</span><span class="sxs-lookup"><span data-stu-id="30222-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30222-265"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="30222-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-266">Não</span><span class="sxs-lookup"><span data-stu-id="30222-266">No</span></span></p></td>
<td><p><span data-ttu-id="30222-267">Função de conferência (por exemplo, apresentador) para o usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-268"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="30222-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-269">Não</span><span class="sxs-lookup"><span data-stu-id="30222-269">No</span></span></p></td>
<td><p><span data-ttu-id="30222-270">Endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="30222-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-271"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="30222-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-272">Não</span><span class="sxs-lookup"><span data-stu-id="30222-272">No</span></span></p></td>
<td><p><span data-ttu-id="30222-273">Tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="30222-273">Network connection type.</span></span> <span data-ttu-id="30222-274">Por exemplo &quot;, de&quot; interno para conexão interna &quot;ou da&quot; PSTN para usuários de discagem.</span><span class="sxs-lookup"><span data-stu-id="30222-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-275"><strong>Hora de ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="30222-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-276">Não</span><span class="sxs-lookup"><span data-stu-id="30222-276">No</span></span></p></td>
<td><p><span data-ttu-id="30222-277">Data e hora em que o usuário entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30222-278"><strong>Hora de saída</strong></span><span class="sxs-lookup"><span data-stu-id="30222-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-279">Não</span><span class="sxs-lookup"><span data-stu-id="30222-279">No</span></span></p></td>
<td><p><span data-ttu-id="30222-280">Data e hora em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="30222-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30222-281"><strong>ID de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="30222-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="30222-282">Não</span><span class="sxs-lookup"><span data-stu-id="30222-282">No</span></span></p></td>
<td><p><span data-ttu-id="30222-p125">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente fornece informações úteis para solução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não incluem esses cabeçalhos) e os IDs de diagnóstico são reportadas somente para sessões que enfrentaram problemas de algum tipo.</span><span class="sxs-lookup"><span data-stu-id="30222-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

