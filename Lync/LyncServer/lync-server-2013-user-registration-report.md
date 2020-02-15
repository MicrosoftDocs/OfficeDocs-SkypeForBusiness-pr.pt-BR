---
title: 'Lync Server 2013: relatório de registro do usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716d8324fba8346fa1326da2ed253dfa07bc3915
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="180e7-102">Relatório de registro de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180e7-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180e7-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="180e7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="180e7-104">O relatório de registro de usuário fornece uma visão geral da atividade de logon do usuário, mais notavelmente informações sobre o número de usuários que fizeram logon no Microsoft Lync Server 2013 durante um período de tempo especificado (por hora, diariamente, semanalmente, mensalmente).</span><span class="sxs-lookup"><span data-stu-id="180e7-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="180e7-105">Lembre-se de que o relatório mostra apenas quantas pessoas fizeram logon.</span><span class="sxs-lookup"><span data-stu-id="180e7-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="180e7-106">Ele não mostra *quais* pessoas fizeram logon.</span><span class="sxs-lookup"><span data-stu-id="180e7-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="180e7-107">Os relatórios de monitoramento não fornecem informações sobre quais usuários específicos estão usando o Lync Server 2013 (e quais não são).</span><span class="sxs-lookup"><span data-stu-id="180e7-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="180e7-108">No entanto, você pode obter uma estimativa aproximada de informações de usuário usando o Relatório de Atividades de Usuário.</span><span class="sxs-lookup"><span data-stu-id="180e7-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="180e7-109">Ao fornecer informações sobre logons de usuários, o Relatório de Registro de Usuário faz duas distinções importantes.</span><span class="sxs-lookup"><span data-stu-id="180e7-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="180e7-110">Primeiro, ele desdobra os logons  em duas categorias primárias: logons internos e logons externos.</span><span class="sxs-lookup"><span data-stu-id="180e7-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="180e7-111">Logons internos representam usuários que fizeram logon de dentro da firewall de sua organização (isto é, enquanto contectados à rede corporativa).</span><span class="sxs-lookup"><span data-stu-id="180e7-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="180e7-112">Os logons externos representam usuários que fizeram logon de fora do firewall por meio de um servidor de borda (por exemplo, um usuário que fez logon a partir de um café da Internet, conta como um logon externo).</span><span class="sxs-lookup"><span data-stu-id="180e7-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="180e7-113">Caso precise saber quantas de seus usuários estão fazendo logon de fora da firewall, o Relatório de Registro de Usuário pode fornecer essa informação a você.</span><span class="sxs-lookup"><span data-stu-id="180e7-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="180e7-114">Além disseo, o Relatório de Registro de Usuário indica quantos usuários *ativos* estavam presentes durante um dado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="180e7-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="180e7-115">Um usuário ativo é um usuário que fez parte de uma sessão de mensagens instantâneas (IM), participou de uma reunião do Lync, fez ou recebeu uma chamada telefônica, ou então usava o Lync Server durante esse período de tempo.</span><span class="sxs-lookup"><span data-stu-id="180e7-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="180e7-116">Isso é diferente de um usuário que fez logon mas nunca realmente usou o sistema.</span><span class="sxs-lookup"><span data-stu-id="180e7-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="180e7-117">Acessando o Relatório de Registro de Usuário</span><span class="sxs-lookup"><span data-stu-id="180e7-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="180e7-p104">Você acessa o Relatório de Registro de Usuário apenas a partir da página inicial de Relatórios de Monitoramento. O Relatório de Registro de Usuário não leva a qualquer outro relatório.</span><span class="sxs-lookup"><span data-stu-id="180e7-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="180e7-120">Usando o Relatório de Registro de Usuário da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="180e7-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="180e7-121">Depois de implantar o Lync Server uma pergunta frequente é esta: como saber se meus usuários estão realmente usando essa nova tecnologia?</span><span class="sxs-lookup"><span data-stu-id="180e7-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="180e7-122">Embora tenha algumas limitações neste sentido, o Relatório de Registro de Usuário pode ajudar você a responder esta pergunta.</span><span class="sxs-lookup"><span data-stu-id="180e7-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="180e7-123">Para determinar se os usuários estão usando o Lync Server, você precisa fazer duas coisas.</span><span class="sxs-lookup"><span data-stu-id="180e7-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="180e7-124">Primeiro, obtenha o valor da métrica de Usuários de logon exclusivos, do Relatório de Registro de Usuário.</span><span class="sxs-lookup"><span data-stu-id="180e7-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="180e7-125">Esse valor informa quantas pessoas distintas fizeram logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e7-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="180e7-126">Por comparação, a métrica total de logons mostra quantas vezes o total de alguém fez logon no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e7-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="180e7-127">Por exemplo, suponha que Ken Myer fez logon no Lync Server cinco vezes diferentes em um único dia.</span><span class="sxs-lookup"><span data-stu-id="180e7-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="180e7-128">Nesse caso, Ken Myer contaria como cinco sessões de logon separadas para a métrica de Total de logons, mas como apenas um usuário de logon para a métrica de Usuários de logon exclusivos.</span><span class="sxs-lookup"><span data-stu-id="180e7-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="180e7-129">Do mesmo modo, não é incomum que um usuário faça logon de vários dispositivos ou locais.</span><span class="sxs-lookup"><span data-stu-id="180e7-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="180e7-130">Por exemplo, um usuário pode fazer logon usando seu computador desktop, seu computador laptop e pode ter um telefone IP que faz logon automaticamente no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e7-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="180e7-131">Neste exemplo, existe um usuário exclusivo com três logons.</span><span class="sxs-lookup"><span data-stu-id="180e7-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="180e7-132">Para explicar de modo mais aprofundado a diferença entre total de logons e logons exclusivos, considere os logons para um dado período de tempo na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="180e7-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180e7-133">Usuário</span><span class="sxs-lookup"><span data-stu-id="180e7-133">User</span></span></th>
<th><span data-ttu-id="180e7-134">Horário de logon</span><span class="sxs-lookup"><span data-stu-id="180e7-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180e7-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="180e7-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="180e7-136">07/07/2012 08:45</span><span class="sxs-lookup"><span data-stu-id="180e7-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="180e7-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="180e7-138">07/07/2012 08:46</span><span class="sxs-lookup"><span data-stu-id="180e7-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180e7-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="180e7-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="180e7-140">07/07/2012 09:17</span><span class="sxs-lookup"><span data-stu-id="180e7-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="180e7-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="180e7-142">07/07/2012 09:22</span><span class="sxs-lookup"><span data-stu-id="180e7-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180e7-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="180e7-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="180e7-144">07/07/2012 09:31</span><span class="sxs-lookup"><span data-stu-id="180e7-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="180e7-p107">Observe que há um total de cinco logons; no entanto, existem apenas dois usuários de logon exclusivos: Ken Myer (que fez logon três vezes) e Pilar Ackerman (que fez logon duas vezes). Essa é a diferença entre logons e usuários de logon exclusivos.</span><span class="sxs-lookup"><span data-stu-id="180e7-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="180e7-147">Além de saber o número de logons exclusivos, você precisa saber o número total de usuários que foram habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e7-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="180e7-148">Esse valor pode ser recuperado abrindo o Shell de gerenciamento do Lync Server 2013 e executando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="180e7-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="180e7-149">Se o comando anterior retornar um valor de 1.236 e a métrica de usuários de logon exclusivos retornar um valor médio de 667, isso indica que uma pequena parte dos seus usuários permite que o Lync esteja realmente fazendo logon no sistema por dia (ou seja, 667 dividido por 1.236 , que é de aproximadamente 54%).</span><span class="sxs-lookup"><span data-stu-id="180e7-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="180e7-150">Lembre-se de que as métricas de logon registram usuários que realmente fizeram logons durante o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="180e7-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="180e7-151">Elas não rastreiam os usuários que já estão logados no sistema.</span><span class="sxs-lookup"><span data-stu-id="180e7-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="180e7-152">Por exemplo, se a sua métrica de Usuários de logon exclusivos mostra 667 logons e você possui 1.236 usuários, isso sugere que quase a metade de seus usuários estão fazendo logon no sistema.</span><span class="sxs-lookup"><span data-stu-id="180e7-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="180e7-153">No entanto, suponha que 300 usuários já estavam logados no sistema no momento em que você começou a verificar os dados de logon.</span><span class="sxs-lookup"><span data-stu-id="180e7-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="180e7-154">Isso significa que, na verdade, você tinha quase 1.000 usuários conectados ao Lync Server, o que significaria que mais perto de 80% dos seus usuários fizeram logon.</span><span class="sxs-lookup"><span data-stu-id="180e7-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="180e7-155">Você também deve comparar o valor de Usuários de logon exclusivos com o valor da métrica de Usuários ativos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="180e7-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="180e7-156">A métrica de usuários ativos exclusivos informa quantos usuários exclusivos realmente usavam o Lync Server: eles fizeram uma chamada telefônica, ingressaram em uma reunião do Lync ou participaram de uma sessão de IM.</span><span class="sxs-lookup"><span data-stu-id="180e7-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="180e7-157">Essa é uma informação útil, pois o Microsoft Lync 2013 pode ser configurado para iniciar automaticamente cada vez que um usuário iniciar o Windows.</span><span class="sxs-lookup"><span data-stu-id="180e7-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="180e7-158">Por isso, você pode ter um grande número de usuários que fazem logon automaticamente no Lync quando fazem logon no Windows a cada dia, mas nunca usa o Lync Server durante esse período de tempo.</span><span class="sxs-lookup"><span data-stu-id="180e7-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="180e7-159">A métrica de usuários ativos exclusivos também fornece dados mais significativos em uma organização onde os usuários normalmente não fazem logoff do Windows no final do dia.</span><span class="sxs-lookup"><span data-stu-id="180e7-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="180e7-160">Em vez disso, eles simplesmente bloqueiam seus computadores e deixam o Windows e o Lync em execução.</span><span class="sxs-lookup"><span data-stu-id="180e7-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="180e7-161">Em uma situação assim, você pode acabar com poucos logons por dia, pois seus usuários fizeram logon vários dias atrás e nunca fizeram o logoff.</span><span class="sxs-lookup"><span data-stu-id="180e7-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="180e7-162">No entanto, os usuários ativos exclusivos informam se os usuários estão ativamente usando o Lync ou outro cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="180e7-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="180e7-163">Filtros</span><span class="sxs-lookup"><span data-stu-id="180e7-163">Filters</span></span>

<span data-ttu-id="180e7-164">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="180e7-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="180e7-165">Por exemplo, o relatório de registro de usuário permite que você visualize os dados de todos os seus servidores de registro de registradores e de borda ou para exibir dados de um pool individual.</span><span class="sxs-lookup"><span data-stu-id="180e7-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="180e7-166">Você também pode escolher como os dados devem ser agrupados.</span><span class="sxs-lookup"><span data-stu-id="180e7-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="180e7-167">Nesse caso, registros agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="180e7-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="180e7-168">A tabela a seguir lista os filtros que você pode usar com o Relatório de registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="180e7-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="180e7-169">Filtros do Relatório de registro do usuário</span><span class="sxs-lookup"><span data-stu-id="180e7-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180e7-170">Nome</span><span class="sxs-lookup"><span data-stu-id="180e7-170">Name</span></span></th>
<th><span data-ttu-id="180e7-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="180e7-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180e7-172"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-p113">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="180e7-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="180e7-175">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="180e7-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="180e7-p114">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="180e7-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="180e7-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="180e7-178">7/7/2012</span></span></p>
<p><span data-ttu-id="180e7-179">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="180e7-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="180e7-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="180e7-180">7/3/2012</span></span></p>
<p><span data-ttu-id="180e7-181">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="180e7-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-p115">Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="180e7-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="180e7-185">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="180e7-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="180e7-p116">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="180e7-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="180e7-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="180e7-188">7/7/2012</span></span></p>
<p><span data-ttu-id="180e7-189">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="180e7-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="180e7-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="180e7-190">7/3/2012</span></span></p>
<p><span data-ttu-id="180e7-191">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="180e7-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180e7-192"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-p117">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="180e7-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="180e7-195">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="180e7-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="180e7-196">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="180e7-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="180e7-197">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="180e7-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="180e7-198">Por mês (um máximo de 12 meses pode ser exibido)</span><span class="sxs-lookup"><span data-stu-id="180e7-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="180e7-p118">Se as datas iniciais e finais excedem o número máximo de valores permitidos para o intervalo selecionado, apenas o número de valores máximos (começando pela data inicial) é exibido. Por exemplo, se você selecionar o intervalo Diário com uma data inicial em 07.07.12 e data final em 28.02.12, os dados são exibidos pelo intervalo de 07.08.12 12:00 AM a 07.09.12 12:00 AM (isto é, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="180e7-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-202">FQDN do pool do Registrador ou Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="180e7-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="180e7-203">Você pode tanto selecionar um pool individual ou escolher <strong>[Todos]</strong> para visualizar os dados de todos os pools.</span><span class="sxs-lookup"><span data-stu-id="180e7-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="180e7-204">Essa lista suspensa é automaticamente preenchida por você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="180e7-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="180e7-205">Métricas</span><span class="sxs-lookup"><span data-stu-id="180e7-205">Metrics</span></span>

<span data-ttu-id="180e7-206">A tabela a seguir lista as informações fornecidas no Relatório de registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="180e7-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="180e7-207">Métrica do Relatório de registro do usuário</span><span class="sxs-lookup"><span data-stu-id="180e7-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180e7-208">Nome</span><span class="sxs-lookup"><span data-stu-id="180e7-208">Name</span></span></th>
<th><span data-ttu-id="180e7-209">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="180e7-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="180e7-210">Descrição</span><span class="sxs-lookup"><span data-stu-id="180e7-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180e7-211"><strong>A cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="180e7-212"><strong>Diariamente</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="180e7-213"><strong>Semanalmente</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="180e7-214"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-215">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-215">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-p120">Indica o intervalo de tempo selecionado na barra de ferramentas do filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 07.07.12, você verá uma divisão por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="180e7-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-219"><strong>Total de logons</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-220">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-220">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-221">Número total de sessões de logon bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="180e7-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180e7-222"><strong>Logons internos</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-223">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-223">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-224">Número total de logons dentro da rede interna.</span><span class="sxs-lookup"><span data-stu-id="180e7-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-225"><strong>Logons externos</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-226">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-226">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-227">Número total logons de fora da rede interna, usando o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="180e7-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180e7-228"><strong>Usuários de logon exclusivo</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-229">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-229">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-p121">Número total de usuário com ao menos uma sessão de logon. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão de logon.</span><span class="sxs-lookup"><span data-stu-id="180e7-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180e7-232"><strong>Usuários ativos exclusivos</strong></span><span class="sxs-lookup"><span data-stu-id="180e7-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="180e7-233">Não</span><span class="sxs-lookup"><span data-stu-id="180e7-233">No</span></span></p></td>
<td><p><span data-ttu-id="180e7-p122">Número total de usuários envolvidos em uma sessão ponto a ponto ou de conferência. Um usuário com várias sessões de logon conta como um usuário, da mesma forma que uma pessoa que teve uma única sessão.</span><span class="sxs-lookup"><span data-stu-id="180e7-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

