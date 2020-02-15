---
title: 'Lync Server 2013: relatório de inventário de telefones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="9d9fe-102">Relatório de inventário de telefone IP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d9fe-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d9fe-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="9d9fe-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="9d9fe-p101">O Relatório de inventário de telefones IP relata informações sobre os telefones IP em uso no momento em sua organização. O Relatório de inventário de telefones IP fornece uma lista detalhada de telefones IP que foram usados durante o período de relatório especificado. Entre outras coisas, esse relatório permite que os administradores saibam se há algum telefone velho e desatualizado em uso que deveria ser substituído; ele também alerta os administradores para o fato de que há telefones caros na organização, que raramente são usados. Esse tipo de informação pode ser inestimável quando se trata de comprar novos telefones ou redistribuir os existentes. (Por exemplo, um usuário que raramente usa seu telefone caro pode pedir para trocar com um usuário que usa seu telefone com muito mais frequência).</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="9d9fe-109">Deve-se observar que esse relatório tem algumas limitações quando se trata de ser usado como um relatório de inventário verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="9d9fe-110">Por um motivo, o relatório de telefone IP simplesmente lista todos os telefones que fizeram logon no Lync Server durante o período de tempo especificado, classificados pelo último horário de logon.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="9d9fe-111">Se um telefone não fizer logon durante o período de tempo especificado, então ele não será listado no relatório de inventário.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="9d9fe-112">Isso inclui telefones que fizeram logon antes do período de tempo iniciar e que ainda estavam logados durante esse intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="9d9fe-113">Por exemplo, suponha que você queira examinar todo o inventário de telefones de julho de 2012.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="9d9fe-114">Imagine, também, que vários telefones estejam conectados ao Lync Server em 30 de junho de 2012 e ainda estavam conectados a partir de 1º de julho.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="9d9fe-115">Esses telefones não serão exibidos no relatório de inventário do dia 1º de julho.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="9d9fe-p103">É também importante observar que o relatório de inventário pode incluir telefones que sua organização não usa mais. Por exemplo, suponha uma série de telefones da Fabrikam logados no sistema no dia 1 de julho de 2012; 5 dias mais tarde sua organização decide se livrar de todos esses telefones da Fabrikam e substituí-los por um novo modelo Contoso. Os telefones da Fabrikam ainda aparecerão no relatório de "inventário" simplesmente porque eles estavam logados no sistema durante o mês de julho.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="9d9fe-p104">Além disso, o Relatório de inventário de telefones IP não relata totais resumidos de diferentes tipos de telefones. Por exemplo, suponha que você tenha 105 telefones Polycom CX600. O relatório não dirá que você tem 105 desses telefones; em vez disso, ele simplesmente vê 105 entidades separadas do Polycom CX600. A unica maneira de saber que há 105 entradas do Polycom Cx600 seria contar cada uma dessas entradas manualmente.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9d9fe-123">Ou exportar os dados e usar o Microsoft Excel ou Windows PowerShell para fazer essa contagem.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="9d9fe-124">Como acessar o Relatório de inventário de telefones IP</span><span class="sxs-lookup"><span data-stu-id="9d9fe-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="9d9fe-p105">O Relatório de inventário de telefones IP é acessado a partir da página inicial dos Relatórios de Monitoramento. Se você clicar na métrica URI do Usuário, você pode acessar o Relatório de atividades do usuário desse usuário. Clicar na métrica Última atividade para uma chamada ponto a ponto levará você ao Relatório de detalhes de sessão ponto a ponto; clicar na mesma métrica de uma conferência levará ao Relatório de detalhes de conferência.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="9d9fe-128">Como usar melhor o Relatório de inventário de telefones IP</span><span class="sxs-lookup"><span data-stu-id="9d9fe-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="9d9fe-129">Se você estiver interessado apenas em informações de uso de um determinado tipo de telefone (por exemplo, "com que frequência os usuários usam um telefone Polycom CX600?"), você pode obter essas informações diretamente do relatório de inventário de telefone IP filtrando esse tipo específico de telefone.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="9d9fe-130">No entanto, se você deseja informações resumidas para todos os seus telefones (quantas pessoas estão usando um CX600 Polycom, quantos estão usando um LG-Nortel IP8540, etc.), será necessário exportar os dados e usar outro aplicativo (como o Windows PowerShell) para fazer esse tipo de analisa.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="9d9fe-131">Por exemplo, suponha que você exportou os dados para um arquivo de valores separados por\\vírgula\\(\_C\_:\_data IP Phone Inventory Report. csv).</span><span class="sxs-lookup"><span data-stu-id="9d9fe-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="9d9fe-132">Nesse caso, você poderia usar esses dois comandos para fornecer dados de resumo para todos os telefones:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="9d9fe-133">Que retornará dados similares a esses:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="9d9fe-134">Similarmente, esses dois comandos dizem quais telefones fizeram logon no sistema, mas nunca foram realmente usados para fazer uma chamada (o valor da métrica Última atividade está em branco, indicando que nunca houve nenhuma última atividade):</span><span class="sxs-lookup"><span data-stu-id="9d9fe-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="9d9fe-135">Isso retorna dados similares a esses para cada telefone que não foi usado:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="9d9fe-136">Outra maneira interessante de usar o Relatório de inventário de telefones IP é esse: se você tiver o endereço MAC de um telefone IP, você poderá descobrir o usuário que usou o telefone por último, simplesmente inserindo esse endereço na caixa de texto do endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="9d9fe-137">O Relatório de inventário de telefones IP irá então relatar de volta (entre outras coisas) o endereço SIP do usuário que fez o logon por último com esse telefone.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="9d9fe-138">Como alternativa, você pode inserir o endereço SIP do usuário (na caixa de prefixo do URI do usuário) para descobrir todos os telefones que foram usados por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9d9fe-139">Filtros</span><span class="sxs-lookup"><span data-stu-id="9d9fe-139">Filters</span></span>

<span data-ttu-id="9d9fe-p108">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Inventário de Telefones IP permite exibir somente os telefones fabricados por uma empresa específica ou até mesmo uma versão específica desses telefones. Você também pode escolher como os dados serão agrupados. Neste caso, os registros são agrupados por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9d9fe-144">A tabela seguir lista os filtros que podem ser usados com o Relatório de Inventário de Telefones IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="9d9fe-145">Filtros do Relatório de Inventário de Telefones IP</span><span class="sxs-lookup"><span data-stu-id="9d9fe-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d9fe-146">Nome</span><span class="sxs-lookup"><span data-stu-id="9d9fe-146">Name</span></span></th>
<th><span data-ttu-id="9d9fe-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d9fe-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-148"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p109">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9d9fe-151">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="9d9fe-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9d9fe-p110">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9d9fe-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9d9fe-154">7/7/2012</span></span></p>
<p><span data-ttu-id="9d9fe-155">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9d9fe-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9d9fe-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9d9fe-156">7/3/2012</span></span></p>
<p><span data-ttu-id="9d9fe-157">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p111">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9d9fe-161">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="9d9fe-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9d9fe-p112">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9d9fe-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9d9fe-164">7/7/2012</span></span></p>
<p><span data-ttu-id="9d9fe-165">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9d9fe-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9d9fe-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9d9fe-166">7/3/2012</span></span></p>
<p><span data-ttu-id="9d9fe-167">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-168"><strong>Fabricantes</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p113">Nome da empresa que fabricou o telefone IP. Os valores para este filtro são preenchidos automaticamente, com base nos telefones IP que estão atualmente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-171"><strong>Versão do hardware</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-172">Número da versão to telefone IP; usando os filtros Fabricante e Versão do hardware, é possível identificar de forma única um tipo em particular de telefone.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="9d9fe-173">Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-174"><strong>Agente de usuário</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p115">Identificador do software usado pelo telefone IP. Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-177"><strong>Endereço MAC</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p116">Identificador único da interface de rede no telefone IP. O endereço de Controle de Acesso de Mídia (MAC) normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="9d9fe-p117">Para pesquisar registros pertencentes a um endereço MAC específico, simplesmente insira o endereço. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="9d9fe-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="9d9fe-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="9d9fe-p118">Você deve inserir o endereço completo. Um endereço parcial (por exemplo, 00-08-5D) não retorna dados.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-185"><strong>Dias antes da última atividade</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-186">Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d9fe-187">Todos os</span><span class="sxs-lookup"><span data-stu-id="9d9fe-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-188">10 </span><span class="sxs-lookup"><span data-stu-id="9d9fe-188">10</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-189">508</span><span class="sxs-lookup"><span data-stu-id="9d9fe-189">20</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-190">até</span><span class="sxs-lookup"><span data-stu-id="9d9fe-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-191"><strong>Dias antes da hora do último logoff:</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-192">Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9d9fe-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d9fe-193">Todos os</span><span class="sxs-lookup"><span data-stu-id="9d9fe-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-194">10 </span><span class="sxs-lookup"><span data-stu-id="9d9fe-194">10</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-195">508</span><span class="sxs-lookup"><span data-stu-id="9d9fe-195">20</span></span></p></li>
<li><p><span data-ttu-id="9d9fe-196">até</span><span class="sxs-lookup"><span data-stu-id="9d9fe-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-197"><strong>Prefixo URI do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-198">Endereço SIP do usuário que utilizou o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9d9fe-199">Métricas</span><span class="sxs-lookup"><span data-stu-id="9d9fe-199">Metrics</span></span>

<span data-ttu-id="9d9fe-200">A tabela a seguir lista as informações fornecidas no Relatório de Inventário de Telefones IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="9d9fe-201">Métricas do Relatório de Inventário de Telefones IP</span><span class="sxs-lookup"><span data-stu-id="9d9fe-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d9fe-202">Nome</span><span class="sxs-lookup"><span data-stu-id="9d9fe-202">Name</span></span></th>
<th><span data-ttu-id="9d9fe-203">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="9d9fe-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9d9fe-204">Descrição</span><span class="sxs-lookup"><span data-stu-id="9d9fe-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-205"><strong>Fabricantes</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-206">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-207">Nome da empresa que fabricou o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-208"><strong>Versão do hardware</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-209">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-210">Número da versão do telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-211"><strong>Endereço MAC</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-212">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-p119">Identificador único da interface de rede no telefone IP. O endereço MAC normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-215"><strong>URI do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-216">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-217">Endereço SIP do usuário que utilizou o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-218"><strong>Agente do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-219">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-220">Identificador do software usado pelo telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-221"><strong>Horário do último logon</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-222">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-223">Data e hora em que o telefone IP foi conectado pela última vez no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d9fe-224"><strong>Horário do último logoff</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-225">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-226">Data e hora do último logoff do telefone IP do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d9fe-227"><strong>Última atividade</strong></span><span class="sxs-lookup"><span data-stu-id="9d9fe-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="9d9fe-228">Sim</span><span class="sxs-lookup"><span data-stu-id="9d9fe-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="9d9fe-229">Data e hora em que o telefone IP foi utilizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="9d9fe-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

