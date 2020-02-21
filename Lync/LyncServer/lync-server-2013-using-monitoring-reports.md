---
title: 'Lync Server 2013: usando relatórios de monitoramento'
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
ms.openlocfilehash: 582554c8f744c48b3eadab58359b965f910152f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Usando relatórios de monitoramento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

O Lync Server 2013 inclui um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados com um navegador da Web, oferecem informações sobre utilização, diagnóstico de chamadas e qualidade de mídia, todas baseadas nos registros de detalhes das chamadas (CDR) e de Qualidade da Experiência (QoE) armazenados nos bancos de dados de CDR e QoE.

Para usar esses relatórios, você deve instalar os relatórios de monitoramento em um computador que esteja executando uma instância do SQL Server.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [O uso do painel de monitoramento no Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   fornece aos administradores uma visão geral rápida da integridade do sistema e do uso do sistema.

  - [Relatórios de uso do sistema no Lync Server 2013](lync-server-2013-system-usage-reports.md)   fornece informações de uso do sistema com base em dados de CDR coletados pelo Lync Server.

  - [Os relatórios de diagnóstico de chamadas (por usuário) no Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   oferecem informações por usuário sobre sessões ponto a ponto e de conferência com falha.

  - [Os relatórios de diagnóstico de chamada no Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   fornecem informações de resumo e dados de diagnóstico para sessões ponto a ponto e de conferência com falha.

  - [Relatórios de diagnóstico de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fornece informações sobre a qualidade da chamada e informações de diagnóstico e solução de problemas para chamadas com falha.

</div>

<div>

## <a name="locating-records"></a>Localizar registros

Os relatórios de monitoramento mostram apenas um número limitado de registros na tela a qualquer momento. O número real de registros exibidos em uma tela varia de acordo com o relatório. Para exibir os registros que não são mostrados na tela, você pode usar o controle padrão para ir para frente ou para trás (encontrado em cada barra de ferramentas do relatório) que permitem percorrer os dados. Você pode saltar rapidamente para a primeira página ou a última página do conjunto de dados.

Além disso, usando os controles para ir para frente e para trás, você pode também saltar para qualquer página no conjunto de dados simplesmente digitando o número da página na caixa **Página Atual** e pressionando ENTER.

Além de fornecer a capacidade de percorrer os dados, cada relatório também inclui a capacidade limitada para localizar registros. Para localizar registros com base em um determinado valor, digite esse valor na caixa **Localizar** e clique em **Localizar**. O relatório procura nos dados e para na primeira ocorrência do valor inserido na caixa **Localizar**. Para localizar o próximo registro que satisfaça os critérios de pesquisa, clique em **Avançar**.

Como observado, os relatórios de monitoramento fornecem apenas as funções mais básicas de pesquisa. Por exemplo, você não pode especificar em qual campo o valor deve ser encontrado. O mecanismo de pesquisa automaticamente procura valores correspondentes em cada campo de cada registro. Você não pode usar caracteres curinga em pesquisas e todas as pesquisas procura valores parciais. Isso significa que se você procurar 111 a pesquisa retorna o valor 111 junto com os valores 11100, 811, 3112, 611A5B e outros campos que incluam o valor 111 em qualquer lugar dentro desse campo.

Cada relatório é configurado para exibir um conjunto de registros padrão. Por exemplo, por padrão o Relatório de Registro de Usuário exibe as atividades de registro de usuário da semana passada. Em alguns casos, isso pode resultar em um relatório que não retorna registros. Nesse caso, significa que nenhum registro de usuário ocorreu na semana passada. Se você vir a mensagem "Nenhum resultado corresponde aos filtros de relatório", tente alterar os valores de filtro (por exemplo, alterar o período de tempo no último mês, em vez de na semana passada) e execute novamente a consulta. Para obter detalhes, consulte "Filtragem de dados", seção que está mais adiante neste tópico.

</div>

<div>

## <a name="filtering-data"></a>Filtragem de dados

Provavelmente haverá momentos nos quais você deseje examinar apenas um subconjunto de registros. Por exemplo, somente sessões ponto a ponto, em vez de duas sessões ponto a ponto e sessões de conferência. Da mesma forma, haverá momentos nos quais você precise reduzir o número de registros retornados. Por padrão, um relatório só pode exibir os primeiros 1.000 registros em um conjunto de dados. Para resolver esses problemas, a maioria dos relatórios incluem um número de opções de filtragem. Por exemplo, se você quiser exibir apenas os registros para o período de 1 de janeiro de 2011 até 15 de janeiro de 2011, poderá inserir 1 de janeiro de 2011 na caixa **De** e 15 de janeiro de 2011 na caixa **Para**. Se você clicar em **Exibir relatório**, os dados retornados estarão limitados às atividades realizadas entre 1 de janeiro de 2011 e 15 de janeiro de 2011.

Os filtros disponíveis variam dependendo do relatório exibido. Para obter detalhes sobre um relatório específico, consulte o tópico Ajuda para esse relatório.

</div>

<div>

## <a name="exporting-data"></a>Exportação de dados

Os relatórios de monitoramento fornecem pelo menos duas maneiras diferentes de exportar os dados incluídos em um relatório. Você pode usar a opção **Exportar** na barra de ferramentas exibida na parte superior de cada relatório. Para usar esta opção, selecione o formato de exportação desejado na lista suspensa **Selecione um formato**. Os seguintes formatos estão disponíveis:

  - Arquivo XML com dados de relatório

  - CSV (delimitado por vírgula)

  - Arquivo Acrobat (PDF)

  - MHTML (arquivo da web)

  - Excel

  - Arquivo TIFF

  - Word

Após selecionar um formato, clique em **Exportar**. Quando a caixa de diálogo **Download de arquivo** for exibida, clique em **Salvar**. Na caixa de diálogo **Salvar como**, selecione uma pasta de destino, insira um nome de arquivo e clique em **Salvar**.

Se o Microsoft OneNote estiver instalado, você também pode copiar os dados do relatório para o OneNote. Para fazer isso, clique com o botão direito no botão **Exibir Relatório** da barra de ferramentas. Na caixa de diálogo **Selecionar Local no OneNote**, selecione a seção do OneNote onde você deseja copiar os dados e clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

