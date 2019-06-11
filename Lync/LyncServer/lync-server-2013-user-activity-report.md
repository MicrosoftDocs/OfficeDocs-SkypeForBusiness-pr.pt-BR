---
title: 'Lync Server 2013: relatório de atividade do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04a7dd3dd1f2a061a327cc2a0bac79ee05f21d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="2df65-102">Relatório de atividade do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2df65-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2df65-103">_**Tópico da última modificação:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="2df65-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="2df65-p101">O Relatório de Atividades do Usuário oferece uma lista detalhada das sessões ponto a ponto e de conferência realizadas pelos usuários em um determinado período. Diferente de muitos dos Relatórios de Monitoramento, o Relatório de Atividades do Usuário vincula cada chamada a usuários individuais. Por exemplo, as sessões ponto a ponto especificam URIs do SIP da pessoa que iniciou a chamada (o usuário de origem) e a pessoa que está sendo chamada (o usuário de destino). Se as informações forem ampliadas para uma conferência, será possível ver uma lista de todos os participantes da conferência e a função que desempenham na conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="2df65-p102">O Relatório de Atividades do Usuário é referenciado algumas vezes como o relatório do "suporte técnico". Isso se deve ao fato de o relatório ser sempre usado pela equipe do suporte técnico para recuperar informações sobre a sessão para um usuário específico. É possível filtrar chamadas feitas para ou por um usuário individual simplesmente digitando o URI do SIP do usuário na caixa URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="2df65-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="2df65-111">Se você fizer isso, o relatório de atividade do usuário retornará informações para qualquer usuário cujo URI SIP comece com a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="2df65-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="2df65-112">Por exemplo, se você digitar **ken** na caixa URI, o Relatório de Atividades do usuário localizará **Ken**.Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="2df65-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="2df65-113">No entanto, ele localizará também esses usuários:</span><span class="sxs-lookup"><span data-stu-id="2df65-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="2df65-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2df65-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="2df65-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2df65-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="2df65-116">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2df65-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="2df65-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2df65-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="2df65-p104">Para garantir que somente informações sobre Ken Myer sejam retornadas, digite sua URI completa (Ken.Myer@litwareinc.com) na caixa de pesquisa ou, pelo menos, digite a URl do Ken o bastante para distingui-lo de outros usuários na organização. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df65-p104">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization. For example:</span></span>

<span data-ttu-id="2df65-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="2df65-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="2df65-121">Para acessar o Relatório de Atividades do Usuário</span><span class="sxs-lookup"><span data-stu-id="2df65-121">To access the user activity report</span></span>

<span data-ttu-id="2df65-122">O Relatório de Atividades do Usuário é acessado pela home page dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2df65-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2df65-123">Você também pode acessar o relatório de atividade do usuário clicando na métrica de URI de usuário no [relatório de inventário de telefone IP do Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="2df65-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="2df65-124">No Relatório de Atividades do Usuário, ao clicar em URI da Conferência (para uma conferência), você será levado para o Relatório Detalhado de Conferências.</span><span class="sxs-lookup"><span data-stu-id="2df65-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="2df65-125">Da mesma forma, clicar na métrica de detalhes de uma chamada ponto a ponto leva você ao [relatório de detalhes da sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="2df65-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="2df65-126">Fazendo o melhor uso do relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="2df65-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="2df65-127">Embora haja muitas informações relevantes no Relatório de Atividades do Usuário, essas informações podem, por vezes, ser difíceis de localizar.</span><span class="sxs-lookup"><span data-stu-id="2df65-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="2df65-128">Por exemplo, todas as atividades do usuário que ocorrem em sua organização durante um período especificado são incluídas no relatório de atividades do usuário; Isso significa que, em seguida, incluído no relatório há informações sobre quais usuários realmente usaram o Microsoft Lync Server 2013 de alguma maneira.</span><span class="sxs-lookup"><span data-stu-id="2df65-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2df65-129">Tecnicamente, é possível que algumas atividades do usuário possam estar desgravadas: enquanto o Lync Server se empenha para manter as informações sobre todas as chamadas telefônicas, é possível que uma chamada tenha sido feita sem as informações sobre essa chamada sendo gravada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2df65-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="2df65-130">O Lync Server foi projetado para fornecer uma visão extremamente precisa, mas não necessariamente perfeita sobre como o Lync Server 2013 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="2df65-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="2df65-131">(O fato não há nenhuma garantia de que 100% de todas as chamadas sejam registradas explica por que o monitoramento do Lync Server não deve ser usado como um sistema de cobrança.)</span><span class="sxs-lookup"><span data-stu-id="2df65-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="2df65-132">Segundo, um relatório de relatório de monitoramento só pode exibir, no máximo, 1.000 registros.</span><span class="sxs-lookup"><span data-stu-id="2df65-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="2df65-133">Dependendo da quantidade de usuários que você tem e também de período com o qual está trabalhado, isso significa que sua consulta pode não retornar todos os dados realmente armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2df65-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="2df65-134">Quais usuários usaram realmente o sistema durante este período?</span><span class="sxs-lookup"><span data-stu-id="2df65-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="2df65-135">Quais dentre meus usuários foram os mais ativos durante este período?</span><span class="sxs-lookup"><span data-stu-id="2df65-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="2df65-136">Os usuários que fazem a maioria das chamadas são também aqueles que participam da maioria das sessões de mensagens instantâneas?</span><span class="sxs-lookup"><span data-stu-id="2df65-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="2df65-137">Se precisar responder a essas perguntas, será possível exportar os dados recuperados pelos Relatórios de Monitoramento para uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="2df65-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="2df65-138">Utilize essa planilha e/ou um arquivo de valores separados por vírgulas para analisar os dados como faz o Relatório de Atividades do Usuário.</span><span class="sxs-lookup"><span data-stu-id="2df65-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="2df65-139">Por exemplo, suponha que os dados do relatório tenham sido exportados para o Excel e depois para um arquivo de valores separados por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="2df65-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="2df65-140">Nesse ponto, você pode importar os dados do. CSV para o Windows PowerShell usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="2df65-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="2df65-141">Depois que os dados forem importados, você poderá usar comandos simples do Windows PowerShell para ajudar a responder suas perguntas.</span><span class="sxs-lookup"><span data-stu-id="2df65-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="2df65-142">Por exemplo, este comando retorna uma lista de usuários exclusivos que atuaram como "usuário de origem" em pelo menos uma sessão:</span><span class="sxs-lookup"><span data-stu-id="2df65-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="2df65-143">Em outras palavras:</span><span class="sxs-lookup"><span data-stu-id="2df65-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="2df65-144">Este comando lista os usuários exclusivos (com base no número total de sessões das quais participaram:</span><span class="sxs-lookup"><span data-stu-id="2df65-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="2df65-145">Este retorna dados semelhantes a estes:</span><span class="sxs-lookup"><span data-stu-id="2df65-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="2df65-146">Este comando limita as sessões reportadas àquelas que incluíram áudio como modalidade:</span><span class="sxs-lookup"><span data-stu-id="2df65-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="2df65-147">Se você pousar o mouse sobre qualquer ID do diagnóstico mostrado no relatório, uma dica de ferramenta será exibida descrevendo o ID.</span><span class="sxs-lookup"><span data-stu-id="2df65-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2df65-148">Filtros</span><span class="sxs-lookup"><span data-stu-id="2df65-148">Filters</span></span>

<span data-ttu-id="2df65-p111">O filtro é uma maneira de retornar um conjunto de dados mais refinado e direcionado, ou ver os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Atividades do Usuário permite filtrar os dados retornados com base em itens como tipo de atividade (isto é, sessão ponto a ponto ou de conferência) ou pelo endereço SIP do usuário (permitindo exibir as atividades para um usuário). Você também pode escolher como os dados serão agrupados; neste caso, os usos são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="2df65-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2df65-153">A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades do Usuário.</span><span class="sxs-lookup"><span data-stu-id="2df65-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="2df65-154">Filtros do relatório de atividades do usuário</span><span class="sxs-lookup"><span data-stu-id="2df65-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df65-155">Nome</span><span class="sxs-lookup"><span data-stu-id="2df65-155">Name</span></span></th>
<th><span data-ttu-id="2df65-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="2df65-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df65-157"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-p112">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="2df65-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2df65-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2df65-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="2df65-p113">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="2df65-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2df65-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="2df65-163">7/17/12012</span></span></p>
<p><span data-ttu-id="2df65-164">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2df65-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2df65-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="2df65-165">7/13/2012</span></span></p>
<p><span data-ttu-id="2df65-166">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2df65-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-167"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-p114">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="2df65-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2df65-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2df65-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="2df65-p115">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="2df65-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2df65-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="2df65-173">7/17/12012</span></span></p>
<p><span data-ttu-id="2df65-174">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2df65-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2df65-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="2df65-175">7/13/2012</span></span></p>
<p><span data-ttu-id="2df65-176">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2df65-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-177"><strong>Tipo de atividade</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-p116">Tipo de atividade. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2df65-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2df65-180">[Todos]</span><span class="sxs-lookup"><span data-stu-id="2df65-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="2df65-181">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="2df65-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="2df65-182">Conferência</span><span class="sxs-lookup"><span data-stu-id="2df65-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-183"><strong>Modalidade</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-184">A Modalidade disponível para você varia de acordo com o Tipo de Atividade selecionado.</span><span class="sxs-lookup"><span data-stu-id="2df65-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="2df65-185">Se o tipo de atividade for ponto a ponto, você poderá selecionar mensagens instantâneas; Transferência de arquivos; Compartilhamento de aplicativos; Voz ou vídeo como a modalidade.</span><span class="sxs-lookup"><span data-stu-id="2df65-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="2df65-186">Se o Tipo de Atividade for Conferência, você poderá selecionar conferência Telefônica de Mensagem Instantânea; conferência da Web; Compartilhamento de Aplicativos; conferência de Voz/Vídeo; ou conferência Telefônica.</span><span class="sxs-lookup"><span data-stu-id="2df65-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-187"><strong>Categoria da sessão</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-p118">Indica se a atividade em questão teve sucesso ou falhou. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2df65-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2df65-190">[Todos]</span><span class="sxs-lookup"><span data-stu-id="2df65-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="2df65-191">Sucesso</span><span class="sxs-lookup"><span data-stu-id="2df65-191">Success</span></span></p></li>
<li><p><span data-ttu-id="2df65-192">Falha esperada</span><span class="sxs-lookup"><span data-stu-id="2df65-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="2df65-193">Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="2df65-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="2df65-194">Uma &quot;falha&quot; esperada é uma falha que se espera que aconteça; por exemplo, se um usuário tiver definido seu status como não incomodar, você esperaria qualquer chamada para esse usuário falhar.</span><span class="sxs-lookup"><span data-stu-id="2df65-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="2df65-195">Uma &quot;falha&quot; inesperada é uma falha que ocorre em que parece ser um sistema de outra forma saudável.</span><span class="sxs-lookup"><span data-stu-id="2df65-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="2df65-196">Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera.</span><span class="sxs-lookup"><span data-stu-id="2df65-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="2df65-197">Se isso ocorrer, será sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="2df65-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-198"><strong>Prefixo de URI do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-p120">Endereço SIP para o usuário. Para exibir registros somente para o usuário Ken Myer, digite o endereço SIP de Ken Myer. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2df65-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="2df65-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2df65-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2df65-203">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="2df65-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="2df65-204">A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões ponto a ponto (isto é, as que envolvem apenas dois participantes).</span><span class="sxs-lookup"><span data-stu-id="2df65-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2df65-205">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="2df65-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df65-206">Nome</span><span class="sxs-lookup"><span data-stu-id="2df65-206">Name</span></span></th>
<th><span data-ttu-id="2df65-207">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2df65-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2df65-208">Descrição</span><span class="sxs-lookup"><span data-stu-id="2df65-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df65-209"><strong>Detalhe</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-210">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-210">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-211">Quando você clica neste item, é mostrado o Relatório de Detalhes de Sessão Ponto a Ponto para a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="2df65-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-212"><strong>Usuário "De"</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-213">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-214">Endereço SIP do usuário que iniciou a sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="2df65-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-215"><strong>Usuário "Para"</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-216">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-217">Endereço SIP do usuário que entrou na sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="2df65-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-218"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-219">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-p121">Tipo de comunicação usado na sessão. Por exemplo, IM, áudio ou transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2df65-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-222"><strong>Hora do convite</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-223">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-224">Data e hora em que o convite inicial para entrar na sessão ponto a ponto foi enviado.</span><span class="sxs-lookup"><span data-stu-id="2df65-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-225"><strong>Hora da resposta</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-226">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-227">Data e hora em que &quot;o&quot; usuário para aceitou o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="2df65-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-228"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-229">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-230">Data e hora em que a sessão ponto a ponto terminou.</span><span class="sxs-lookup"><span data-stu-id="2df65-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-231"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-232">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-p122">Identificador exclusivo (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para resolução de erros. Os cabeçalhos de diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente em sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="2df65-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2df65-235">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="2df65-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="2df65-236">A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para a sessões de conferência (isto é, as que envolvem três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="2df65-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2df65-237">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="2df65-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df65-238">Nome</span><span class="sxs-lookup"><span data-stu-id="2df65-238">Name</span></span></th>
<th><span data-ttu-id="2df65-239">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2df65-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2df65-240">Descrição</span><span class="sxs-lookup"><span data-stu-id="2df65-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df65-241"><strong>URI de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-242">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-243">Identificador exclusivo da conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-243">Unique conference identifier.</span></span> <span data-ttu-id="2df65-244">Quando você clica neste item, é mostrado o Relatório de Detalhes da Conferência para a sessão selecionada.</span><span class="sxs-lookup"><span data-stu-id="2df65-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="2df65-245">Quando você expande esse item, o relatório mostra as informações sobre os participantes.</span><span class="sxs-lookup"><span data-stu-id="2df65-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="2df65-246">Para obter detalhes, consulte &quot;a seção métricas para&quot; participantes da conferência mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2df65-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-247"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-248">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-249">Endereço SIP do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-251">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-252">Nome do Servidor de Borda (se houver) usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-253"><strong>Hora inicial</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-254">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-255">Data e hora em que a conferência começou.</span><span class="sxs-lookup"><span data-stu-id="2df65-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-256"><strong>Hora final</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-257">Sim</span><span class="sxs-lookup"><span data-stu-id="2df65-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="2df65-258">Data e hora em que a conferência terminou.</span><span class="sxs-lookup"><span data-stu-id="2df65-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="2df65-259">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="2df65-259">Metrics for conference participants</span></span>

<span data-ttu-id="2df65-260">A tabela a seguir lista as informações fornecidas no Relatório de Atividades do Usuário para cada participante de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="2df65-261">Métricas para participantes da conferência</span><span class="sxs-lookup"><span data-stu-id="2df65-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2df65-262">Nome</span><span class="sxs-lookup"><span data-stu-id="2df65-262">Name</span></span></th>
<th><span data-ttu-id="2df65-263">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2df65-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2df65-264">Descrição</span><span class="sxs-lookup"><span data-stu-id="2df65-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2df65-265"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-266">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-266">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-267">Função do usuário na conferência (por exemplo, Apresentador).</span><span class="sxs-lookup"><span data-stu-id="2df65-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-268"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-269">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-269">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-270">Endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="2df65-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-271"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-272">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-272">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-273">Tipo de conexão da rede.</span><span class="sxs-lookup"><span data-stu-id="2df65-273">Network connection type.</span></span> <span data-ttu-id="2df65-274">Por exemplo &quot;, de&quot; interno para conexão interna &quot;ou da&quot; PSTN para usuários de discagem.</span><span class="sxs-lookup"><span data-stu-id="2df65-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-275"><strong>Hora da ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-276">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-276">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-277">Data e hora em que o usuário entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2df65-278"><strong>Hora da saída</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-279">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-279">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-280">Data e hora em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="2df65-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2df65-281"><strong>ID do Diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="2df65-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2df65-282">Não</span><span class="sxs-lookup"><span data-stu-id="2df65-282">No</span></span></p></td>
<td><p><span data-ttu-id="2df65-p125">Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="2df65-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

