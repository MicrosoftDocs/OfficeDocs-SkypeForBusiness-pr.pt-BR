---
title: 'Lync Server 2013: usando relatórios de monitoramento'
description: 'Lync Server 2013: usando relatórios de monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e19b266e0580a89b814e80982c5f4ff2146ec01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580307"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="2b416-103">Usando relatórios de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b416-103">Using Monitoring Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b416-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2b416-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2b416-105">O Lync Server 2013 inclui um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="2b416-105">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="2b416-106">Esses relatórios, que podem ser acessados com um navegador da Web, oferecem informações sobre utilização, diagnóstico de chamadas e qualidade de mídia, todas baseadas nos registros de detalhes das chamadas (CDR) e de Qualidade da Experiência (QoE) armazenados nos bancos de dados de CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="2b416-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="2b416-107">Para usar esses relatórios, você deve instalar os relatórios de monitoramento em um computador que esteja executando uma instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b416-107">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b416-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2b416-108">In This Section</span></span>

  - <span data-ttu-id="2b416-109">[Usando o painel de monitoramento no Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)     Fornece aos administradores uma visão geral rápida da integridade do sistema e do uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="2b416-109">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="2b416-110">[Relatórios de uso do sistema no Lync Server 2013](lync-server-2013-system-usage-reports.md)     Fornece informações de uso do sistema com base nos dados de CDR coletados pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b416-110">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="2b416-111">[Relatórios de diagnóstico de chamada (por usuário) no Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)     Fornece informações por usuário sobre falhas de sessões ponto a ponto e de conferência.</span><span class="sxs-lookup"><span data-stu-id="2b416-111">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="2b416-112">[Relatórios de diagnóstico de chamada no Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     Fornece informações de resumo e dados de diagnóstico para sessões ponto a ponto e de conferência com falha.</span><span class="sxs-lookup"><span data-stu-id="2b416-112">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="2b416-113">[Relatórios de diagnóstico de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     Fornece informações sobre a qualidade da chamada, bem como informações de diagnóstico e solução de problemas para chamadas com falha.</span><span class="sxs-lookup"><span data-stu-id="2b416-113">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="2b416-114">Localizar registros</span><span class="sxs-lookup"><span data-stu-id="2b416-114">Locating Records</span></span>

<span data-ttu-id="2b416-p102">Os relatórios de monitoramento mostram apenas um número limitado de registros na tela a qualquer momento. O número real de registros exibidos em uma tela varia de acordo com o relatório. Para exibir os registros que não são mostrados na tela, você pode usar o controle padrão para ir para frente ou para trás (encontrado em cada barra de ferramentas do relatório) que permitem percorrer os dados. Você pode saltar rapidamente para a primeira página ou a última página do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="2b416-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="2b416-119">Além disso, usando os controles para ir para frente e para trás, você pode também saltar para qualquer página no conjunto de dados simplesmente digitando o número da página na caixa **Página Atual** e pressionando ENTER.</span><span class="sxs-lookup"><span data-stu-id="2b416-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="2b416-p103">Além de fornecer a capacidade de percorrer os dados, cada relatório também inclui a capacidade limitada para localizar registros. Para localizar registros com base em um determinado valor, digite esse valor na caixa **Localizar** e clique em **Localizar**. O relatório procura nos dados e para na primeira ocorrência do valor inserido na caixa **Localizar**. Para localizar o próximo registro que satisfaça os critérios de pesquisa, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2b416-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="2b416-p104">Como observado, os relatórios de monitoramento fornecem apenas as funções mais básicas de pesquisa. Por exemplo, você não pode especificar em qual campo o valor deve ser encontrado. O mecanismo de pesquisa automaticamente procura valores correspondentes em cada campo de cada registro. Você não pode usar caracteres curinga em pesquisas e todas as pesquisas procura valores parciais. Isso significa que se você procurar 111 a pesquisa retorna o valor 111 junto com os valores 11100, 811, 3112, 611A5B e outros campos que incluam o valor 111 em qualquer lugar dentro desse campo.</span><span class="sxs-lookup"><span data-stu-id="2b416-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="2b416-p105">Cada relatório é configurado para exibir um conjunto de registros padrão. Por exemplo, por padrão o Relatório de Registro de Usuário exibe as atividades de registro de usuário da semana passada. Em alguns casos, isso pode resultar em um relatório que não retorna registros. Nesse caso, significa que nenhum registro de usuário ocorreu na semana passada. Se você vir a mensagem "Nenhum resultado corresponde aos filtros de relatório", tente alterar os valores de filtro (por exemplo, alterar o período de tempo no último mês, em vez de na semana passada) e execute novamente a consulta. Para obter detalhes, consulte "Filtragem de dados", seção que está mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2b416-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="2b416-135">Filtragem de dados</span><span class="sxs-lookup"><span data-stu-id="2b416-135">Filtering Data</span></span>

<span data-ttu-id="2b416-p106">Provavelmente haverá momentos nos quais você deseje examinar apenas um subconjunto de registros. Por exemplo, somente sessões ponto a ponto, em vez de duas sessões ponto a ponto e sessões de conferência. Da mesma forma, haverá momentos nos quais você precise reduzir o número de registros retornados. Por padrão, um relatório só pode exibir os primeiros 1.000 registros em um conjunto de dados. Para resolver esses problemas, a maioria dos relatórios incluem um número de opções de filtragem. Por exemplo, se você quiser exibir apenas os registros para o período de 1 de janeiro de 2011 até 15 de janeiro de 2011, poderá inserir 1 de janeiro de 2011 na caixa **De** e 15 de janeiro de 2011 na caixa **Para**. Se você clicar em **Exibir relatório**, os dados retornados estarão limitados às atividades realizadas entre 1 de janeiro de 2011 e 15 de janeiro de 2011.</span><span class="sxs-lookup"><span data-stu-id="2b416-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="2b416-p107">Os filtros disponíveis variam dependendo do relatório exibido. Para obter detalhes sobre um relatório específico, consulte o tópico Ajuda para esse relatório.</span><span class="sxs-lookup"><span data-stu-id="2b416-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="2b416-145">Exportação de dados</span><span class="sxs-lookup"><span data-stu-id="2b416-145">Exporting Data</span></span>

<span data-ttu-id="2b416-p108">Os relatórios de monitoramento fornecem pelo menos duas maneiras diferentes de exportar os dados incluídos em um relatório. Você pode usar a opção **Exportar** na barra de ferramentas exibida na parte superior de cada relatório. Para usar esta opção, selecione o formato de exportação desejado na lista suspensa **Selecione um formato**. Os seguintes formatos estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="2b416-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="2b416-150">Arquivo XML com dados de relatório</span><span class="sxs-lookup"><span data-stu-id="2b416-150">XML file with report data</span></span>

  - <span data-ttu-id="2b416-151">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="2b416-151">CSV (comma delimited)</span></span>

  - <span data-ttu-id="2b416-152">Arquivo Acrobat (PDF)</span><span class="sxs-lookup"><span data-stu-id="2b416-152">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="2b416-153">MHTML (arquivo da web)</span><span class="sxs-lookup"><span data-stu-id="2b416-153">MHTML (web archive)</span></span>

  - <span data-ttu-id="2b416-154">Excel</span><span class="sxs-lookup"><span data-stu-id="2b416-154">Excel</span></span>

  - <span data-ttu-id="2b416-155">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="2b416-155">TIFF file</span></span>

  - <span data-ttu-id="2b416-156">Word</span><span class="sxs-lookup"><span data-stu-id="2b416-156">Word</span></span>

<span data-ttu-id="2b416-p109">Após selecionar um formato, clique em **Exportar**. Quando a caixa de diálogo **Download de arquivo** for exibida, clique em **Salvar**. Na caixa de diálogo **Salvar como**, selecione uma pasta de destino, insira um nome de arquivo e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b416-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="2b416-p110">Se o Microsoft OneNote estiver instalado, você também pode copiar os dados do relatório para o OneNote. Para fazer isso, clique com o botão direito no botão **Exibir Relatório** da barra de ferramentas. Na caixa de diálogo **Selecionar Local no OneNote**, selecione a seção do OneNote onde você deseja copiar os dados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b416-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

