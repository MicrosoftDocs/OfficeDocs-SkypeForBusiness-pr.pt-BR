---
title: Amostras de Desenvolvimento para o CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Resumo: Revise amostras de desenvolvimento e tutorial para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 6bd6031e1d7fc94ed463c53efb068fd1e2e51378
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296123"
---
# <a name="cqd-development-samples"></a>Amostras de Desenvolvimento para o CQD

**Resumo:** revisar um tutorial e amostras de desenvolvimento do Painel de Qualidade da Chamada. o Painel de Qualidade da Chamada é uma ferramenta para Skype for Business Server 2015.

Este artigo apresenta um tutorial e amostras de desenvolvimento para o Painel de Qualidade da Chamada (CQD).

## <a name="call-quality-dashboard-cqd-development-samples"></a>Amostras de desenvolvimento para o Painel de Qualidade da Chamada (CQD)

Tutorial: apresentação da criação de relatórios personalizados com o Serviço de Dados do CQD e as APIs do Serviço de Repositório.

### <a name="introduction-to-cqd"></a>Introdução ao CQD

O CQD oferece acesso rápido e fácil às informações de qualidade da chamada agregadas nas implantações locais do Skype for Business Server. O CQD consiste em três componentes: o banco de dados do Arquivamento QoE, o Cubo e o Portal. O Portal é a camada de apresentação principal e pode ser dividido nos três componentes abaixo:

1. Serviço de dados, que é acessível para usuários autenticados por meio da [API de dados para chamar qualidade Dashboard (CQD) no Skype para Business Server 2015](data-api.md).

2. Serviço de repositório, que é acessível para usuários autenticados por meio da [API de repositório para chamar qualidade Dashboard (CQD) no Skype para Business Server 2015](repository-api.md).

3. Portal da Web, que é a interface baseada em HTML5 que os usuários do CQD veem e com a qual interagem. Ele pode ser acessado por usuários autenticados.

Os relatórios mostrados no portal da web são agrupados em "conjuntos de relatório". A figura mostra um conjunto de relatórios com dois relatórios. Cada relatório do painel abaixo mostra os resultados da consulta sobre o número de chamadas boas, chamadas ruins e porcentagem de chamadas ruins em vários meses, com vários filtros aplicados. 

![Relatório de amostra de CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

O CQD é criado de acordo com a Metodologia de Qualidade de Chamada (CQM), portanto, o conjunto padrão de relatórios é projetado para se alinhar ao fluxo de investigação introduzido pela CQM. Os usuários também têm a flexibilidade para editar ou criar relatórios personalizados para atender às suas necessidades. No entanto, como existem várias maneiras para visualizar os dados, a visualização fornecida pelo CQD pode não atender completamente às necessidades de cada usuário. Nessas situações, um usuário pode aproveitar as APIs de Dados e de Repositório para criar páginas de relatório personalizadas. Veremos alguns exemplos neste tutorial.

### <a name="how-the-dashboard-consumes-the-data-service"></a>Como o painel usa o serviço de dados

Quando você navegar até a página inicial CQD (por exemplo, http://localhost/cqd), defina o relatório e relatórios correspondentes para um usuário autorizado e autenticado serão recuperados do serviço de repositório. Uma URL completa será construída contra a ID do conjunto de relatório e o ano / mês (ID do conjunto de relatório é o número de inteiro após a seção '/ #/' na URL e, por padrão o ano-mês atual foi acrescentado ao final da identificação do conjunto de relatório após a barra). As definições de relatório são armazenadas no formato JSON e, quando recuperadas do Serviço de Repositório, serão usadas como entrada do Serviço de Dados. O Serviço de Dados gera consultas de expressões multidimensionais (MDX) com base na entrada e executa essas consultas de MDX no Cubo para recuperar os dados de cada relatório. 

### <a name="building-customized-reports"></a>Criar relatórios personalizados

O CQD já é bastante flexível para personalizar relatórios, mas pode haver situações em que os usuários precisam agregar os dados em diversos relatórios criados no CQD. Por exemplo, pode haver a necessidade de criar um relatório que mostra o percentual de chamadas ruins em todas as combinações possíveis de chamadas com fio em uma tabela (um resultado como a figura):

![Tabela do CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

Com o Portal fornecido pelo CQD, um usuário precisaria navegar até vários relatórios para extrair e registrar a porcentagem de chamadas ruins para cada um, o que pode ser laborioso se houver muitos pontos de dados a serem coletados. As APIs de Dados fornecem aos usuários uma forma programática de fazer isso recuperando dados do Serviço de Dados (por exemplo, via chamadas AJAX). 

 **Exemplo 1: amostra de relatório simples**

Vejamos um exemplo simples primeiro. Se quisermos mostrar a contagem de Fluxos de áudio bons e fluxo de áudio ruins de fevereiro de 2015 em uma página HTML como a figura:

![Relatório de exemplo de CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

É preciso enviar uma chamada para o Serviço de Dados com os parâmetros corretos e mostrar os resultados da consulta em uma tabela HTML. A seguir, uma amostra do código JavaScript:

```        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

Este exemplo pode ser segmentado em três etapas:

1. Construa a consulta (no exemplo que isso é definido na variável 'consulta'). A consulta é definida como um objeto JSON, que inclui os seguintes dados:

   a. Zero ou mais dimensões. Cada dimensão é indicada por um DataModelName.

   b. Zero ou mais filtros. Cada filtro tem:

   - DataModelName (a dimensão que terá o conjunto de filtros).

   - Value (o valor que será comparado pelo operando).

   - Operando (tipo de comparação, 0 significa "Igual a").

     c. Uma ou mais medidas.

2. Enviar a consulta ao Serviço de Dados via chamada AJAX. Os seguintes parâmetros da solicitação devem ser fornecidos:

   a. url (que deve ser http://[ServerName]/QoEDataService/RunQuery).

   b. dados (isto é a representação de cadeia de caracteres do objeto JSON definido na variável de 'consulta'). O Serviço de Dados retornará resultados da consulta como um parâmetro da função de retorno de chamada para o sucesso.

   c. Digite (para QoEDataService, RunQuery aceita somente ' POST' solicitações).

   d. async (um sinalizador que indica se a chamada AJAX deve ser síncrona ou assíncrona).

   f. contentType (deve ser "application json").

   f. success (função de retorno de chamada para quando a chamada AJAX for concluída com sucesso).

   g. error (função de tratamento de erros para quando a chamada AJAX falhar).

3. Colocar dados em elementos div no HTML (no exemplo, isso é feito através da chamada de função anônima depois que a solicitação AJAX for concluída com êxito).

Colocar o código JavaScript em uma página HTML, e a página mostrará um relatório como o que é mostrado na imagem. O HTML completo fica assim:

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

Até agora, o relatório ainda é muito simples. O usuário pode adicionar mais medidas, dimensões ou filtros para personalizá-lo. Por exemplo, se você quiser mostrar a porcentagem de chamadas ruins de AppSharing, uma nova medida de AppSharing precisará ser adicionada. Se você quiser mostrar todas as chamadas TCP x UDP, uma nova dimensão sobre o tipo de transporte deverá ser adicionada. Se você quiser mostrar o número de chamadas ruins dentro de um edifício específico, um novo filtro deverá ser adicionado para selecionar as chamadas de e para esse edifício.

 **Exemplo 2: amostra de definição do relatório**

Pode ser difícil para alguém descobrir como gravar a lista completa de medidas/dimensões/filtros e seus valores correspondentes ao criar uma consulta. Nesse caso, você pode ir ao Portal, criar um relatório usando o editor de relatórios, visualizar a cadeia de caracteres JSON da definição de relatório e copiar a definição para um relatório personalizado. 

Neste exemplo, criaremos uma página da Web como a que é mostrada na figura, em que um usuário pode inserir o ID de qualquer conjunto de relatórios (ou de um relatório) existente para exibir a definição do conjunto de relatórios ou do relatório na página da Web. Em seguida, o usuário pode conectar a cadeia de caracteres JSON de cada relatório em um código semelhante ao mostrado no Exemplo 1 e criar qualquer relatório personalizado que desejar. 

![Exemplo de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

Para criar a ferramenta de visualização da definição do relatório, precisamos enviar chamadas para o Serviço de Repositório para recuperar as representações da cadeia de caracteres JSON das definições de cada conjunto de relatórios que quisermos. A API de Repositório retornará a definição do conjunto de relatórios com base em determinado ID de conjunto de relatórios. 

A seguir, apresentamos um exemplo rápido, o código contém um bloco que é um exemplo simples para enviar uma consulta ao Serviço de Repositório para obter o conteúdo de um item do repositório com base em seu identificador. E a próxima parte do código (método processReportSetData) está enviando chamadas AJAX para obter a definição de cada relatório dentro desse conjunto de relatórios. Como o ID no portal da Web do CQD é o ID de um conjunto de relatórios, a chamada AJAX retornará um item de conjunto de relatórios. Mais detalhes sobre a API do repositório e especificamente, GetItems, podem ser encontrados na [Obter itens](get-items.md). 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

O processo acima resultará em uma página da Web como a da figura (sem a definição de relatório na visita inicial). Obter a ID do conjunto de relatório do portal CQD (ele é depois '/ #/' entrar no portal CQD URL (ex.: na primeira figura o relatório de identificação do conjunto é 3024) e colocar a ID do conjunto de relatório para a seção de entrada desta página da web. Pressione o botão "carga" e consulte a definição completa (medidas, dimensões, listas de filtros) do conjunto de relatório.

Em resumo, a fim de obter rapidamente a definição completa de um conjunto de report/relatório. As etapas são as seguintes:

1. Vá para o Portal e use o editor de consulta para personalizar um relatório (clique "Editar" botão acima de um relatório para editar, adicionar, remover filtros/de dimensões de medidas e, então, salve o relatório).

2. Obter a identificação de conjunto de relatório da URL (o inteiro após '/ #/' entrar na URL).

3. Lance a página da Web de Definição do Relatório criada no Exemplo 2 e insira o ID do conjunto de relatórios para recuperar a definição completa de um conjunto de relatórios (para uso nas chamadas da API de Dados).

   **Exemplo 3: amostra de scorecard**

É hora de uma tarefa mais complicada. E se quisermos criar uma página da Web como a da figura? Precisamos atualizar o Exemplo 1 (com a ajuda da página da Web gerada no Exemplo 2 para recuperar a definição completa de qualquer relatório) para podermos lidar com uma quantidade maior de dados.

Neste caso, precisamos atualizar a lista de medidas e dimensões. O caminho para descobrir como adicionar/editar uma medida e/ou uma dimensão é seguir as instruções no Exemplo 2 e recuperar a definição completa do relatório, incluindo as listas de medições e dimensões completas. Conecte a definição completa do relatório no código de exemplo. 

Aqui estão as etapas detalhadas para acessar a página de scorecard na figura da amostra apresentada no Exemplo 1:

1. Atualizar medições na variável de 'consulta' `[Measures].[Audio Good Streams JPDR Count]` e `[Measures].[Audio Poor Streams JPDR Count]` para `[Measures].[AudioPoorJPDRPercentage]`. 

2. Atualize os filtros. Os dados JSON para filtros no exemplo 1 tem um filtro, que é definido na dimensão `[StartDate].[Month]`. Como Filters é uma matriz JSON, dimensões adicionais podem ser adicionadas à lista de filtros. Por exemplo, para obter o cliente do servidor em chamadas com fio para "currentMonth", podemos deve ter os seguintes filtros:

   ```
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   Aqui a dimensão `[Scenarios].[ScenarioPair]` for definido como igual `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`. O `[Scenario.][ScenarioPair]` é uma dimensão especial criada para simplificar a criação de relatórios. Ela tem seis valores correspondentes a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`. Portanto, em vez de usar uma combinação de seis filtros para definir um cenário, basta usar um filtro. No nosso exemplo, o valor `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` converte o cenário onde: primeiro é servidor, segundo não for server, primeiro está dentro, segundo está dentro, primeiro tipo de conexão é por fio, e o segundo tipo de conexão é por fio, qual é a definição exata de " Servidor-cliente-Inside com fio".

3. Crie um conjunto de filtros por cenário. Cada linha do scorecard, na figura, representa um cenário diferente, que será um filtro diferente (enquanto as dimensões e as medições permanecem as mesmas). 

4. Analise os resultados das chamadas AJAX e coloque-os na posição correta na tabela. Como isso é majoritariamente manipulação de HTML e JavaScript, não entraremos em detalhes aqui. Em vez disso, o código é fornecido no Anexo A.

    > [!NOTE]
    >  Se o compartilhamento de recursos entre origens (CORS) estiver habilitado, os usuários podem ocorrer erros like "sem cabeçalho 'Acesso controle-permitir-origem' está presente no recurso solicitado. Origem 'nulo', portanto, não é permitida acesso". Para resolver o problema, coloque o arquivo HTML sob a pasta onde o Portal é instalado (por padrão, ele deve ser `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`. Então acessar o html por meio de qualquer navegador com a URL `http://<servername>/cqd/<html_file_name>`. (É a URL padrão do painel CQD local `http://<servername>/cqd.`) 

### <a name="appendix-a"></a>Anexo A

Código HTML do Exemplo 3 (amostra de scorecard):

```
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```