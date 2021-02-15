---
title: Amostras de Desenvolvimento para o CQD
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 'Resumo: Revise um tutorial e exemplos de desenvolvimento para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832721"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="3a907-104">Amostras de Desenvolvimento para o CQD</span><span class="sxs-lookup"><span data-stu-id="3a907-104">CQD Development Samples</span></span>

<span data-ttu-id="3a907-105">**Resumo:** Revise um tutorial e exemplos de desenvolvimento para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="3a907-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="3a907-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a907-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="3a907-107">Este artigo fornece um tutorial e exemplos sobre desenvolvimento para o Painel de Qualidade de Chamada (CQD).</span><span class="sxs-lookup"><span data-stu-id="3a907-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="3a907-108">Amostras de desenvolvimento do Painel de Qualidade da Chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="3a907-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="3a907-109">Tutorial: Criação de apresentação de relatório personalizado usando as APIs de Serviço de Dados e Repositório do CQD.</span><span class="sxs-lookup"><span data-stu-id="3a907-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="3a907-110">Introdução ao CQD</span><span class="sxs-lookup"><span data-stu-id="3a907-110">Introduction to CQD</span></span>

<span data-ttu-id="3a907-111">O CQD oferece acesso rápido e fácil a informações agregadas de qualidade de chamada para implantações locais do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a907-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="3a907-112">O CQD consiste em três componentes: o banco de dados de Arquivo QoE, o Cubo e o Portal.</span><span class="sxs-lookup"><span data-stu-id="3a907-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="3a907-113">O Portal é a camada de apresentação principal e pode ser dividido nos três componentes a seguir:</span><span class="sxs-lookup"><span data-stu-id="3a907-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="3a907-114">Serviço de Dados, que pode ser acessado por usuários autenticados por meio da API de Dados para Painel de Qualidade de Chamadas [(CQD) no Skype for Business Server.](data-api.md)</span><span class="sxs-lookup"><span data-stu-id="3a907-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="3a907-115">Serviço de Repositório, que pode ser acessado por usuários autenticados por meio da API de Repositório para Painel de Qualidade de Chamadas [(CQD) no Skype for Business Server.](repository-api.md)</span><span class="sxs-lookup"><span data-stu-id="3a907-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="3a907-116">Portal da Web, que é a interface baseada em HTML5 com a qual os usuários do CQD veem e interagem.</span><span class="sxs-lookup"><span data-stu-id="3a907-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="3a907-117">Isso pode ser acessado por usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="3a907-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="3a907-118">Os relatórios mostrados no portal da Web são agrupados em "conjuntos de relatórios".</span><span class="sxs-lookup"><span data-stu-id="3a907-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="3a907-119">A figura mostra um conjunto de relatórios com dois relatórios.</span><span class="sxs-lookup"><span data-stu-id="3a907-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="3a907-120">Cada relatório neste painel abaixo mostra os resultados da consulta sobre o número de chamadas boas, chamadas ruins e porcentagem de chamadas ruins por vários meses, com vários filtros aplicados.</span><span class="sxs-lookup"><span data-stu-id="3a907-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![Relatório de amostra do CQD](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="3a907-122">O CQD é criado seguindo a Metodologia de Qualidade de Chamada (CQM), portanto, o conjunto padrão de relatórios é projetado para se alinhar ao fluxo de investigação introduzido pelo CQM.</span><span class="sxs-lookup"><span data-stu-id="3a907-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="3a907-123">Os usuários também têm a flexibilidade de editar ou criar relatórios personalizados para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="3a907-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="3a907-124">No entanto, como há várias maneiras de visualizar os dados, a visualização fornecida pelo CQD pode não atender totalmente às necessidades de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="3a907-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="3a907-125">Nessas situações, um usuário pode aproveitar as APIs de Dados e as APIs de Repositório para criar páginas de relatório personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3a907-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="3a907-126">Vamos passar por uma série de exemplos neste tutorial.</span><span class="sxs-lookup"><span data-stu-id="3a907-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="3a907-127">Como o painel consome o serviço de dados</span><span class="sxs-lookup"><span data-stu-id="3a907-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="3a907-128">Ao navegar para a home page do CQD (por exemplo, o conjunto de relatórios e os relatórios correspondentes para um usuário autenticado e autorizado serão recuperados do Serviço de http://localhost/cqd) Repositório.</span><span class="sxs-lookup"><span data-stu-id="3a907-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="3a907-129">Uma URL completa será construída a partir da ID do conjunto de relatório e do ano-mês (a ID do conjunto de relatório é o número inteiro após a seção '/#/' na URL e, por padrão, o ano-mês atual é acrescentado no final da ID do conjunto de relatório após a barra).</span><span class="sxs-lookup"><span data-stu-id="3a907-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="3a907-130">As definições de relatório são armazenadas no formato JSON e, quando recuperadas do Serviço de Repositório, serão usadas como entrada para o Serviço de Dados.</span><span class="sxs-lookup"><span data-stu-id="3a907-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="3a907-131">O Serviço de Dados gera consultas MDX (expressões de várias dimensões) com base na entrada e, em seguida, executar essas consultas MDX no Cubo para recuperar dados de cada relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="3a907-132">Criando relatórios personalizados</span><span class="sxs-lookup"><span data-stu-id="3a907-132">Building customized reports</span></span>

<span data-ttu-id="3a907-133">O CQD já tem muita flexibilidade na personalização de relatórios, mas pode haver situações em que os usuários podem querer agregar dados em vários relatórios criados no CQD.</span><span class="sxs-lookup"><span data-stu-id="3a907-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="3a907-134">Por exemplo, pode haver a necessidade de criar um relatório que mostre as porcentagens de chamadas ruins de todas as combinações possíveis de chamadas com fio em uma tabela (um resultado como a figura):</span><span class="sxs-lookup"><span data-stu-id="3a907-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![Tabela CQD](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="3a907-136">Usando o Portal fornecido pelo CQD, um usuário teria que navegar até vários relatórios para extrair e registrar a % de chamada ruim para cada um deles, o que pode ser trabalhoso se houver muitos pontos de dados que precisam ser coletados.</span><span class="sxs-lookup"><span data-stu-id="3a907-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="3a907-137">As APIs de dados fornecem aos usuários uma maneira programática de fazer isso, recuperando dados do Serviço de Dados (por exemplo, por meio de chamadas AJAX).</span><span class="sxs-lookup"><span data-stu-id="3a907-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="3a907-138">**Exemplo 1: Amostra de relatório simples**</span><span class="sxs-lookup"><span data-stu-id="3a907-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="3a907-139">Vamos ver um exemplo simples primeiro.</span><span class="sxs-lookup"><span data-stu-id="3a907-139">Let us take a simple example first.</span></span> <span data-ttu-id="3a907-140">Se quisermos mostrar a contagem de fluxos de Áudio Bom e Áudio Ruim de fevereiro de 2015 em uma página HTML como a figura:</span><span class="sxs-lookup"><span data-stu-id="3a907-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![Relatório de exemplo do CQD](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="3a907-142">O que precisamos é enviar uma chamada para o Serviço de Dados com os parâmetros adequados e mostrar os resultados da consulta em uma tabela HTML.</span><span class="sxs-lookup"><span data-stu-id="3a907-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="3a907-143">Veja a seguir um exemplo do código JavaScript:</span><span class="sxs-lookup"><span data-stu-id="3a907-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
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

<span data-ttu-id="3a907-144">Este exemplo pode ser desconstruído em três etapas:</span><span class="sxs-lookup"><span data-stu-id="3a907-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="3a907-145">Construir a consulta (no exemplo, isso é definido na variável 'query').</span><span class="sxs-lookup"><span data-stu-id="3a907-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="3a907-146">A consulta é definida como um objeto JSON, que inclui os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="3a907-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="3a907-147">a.</span><span class="sxs-lookup"><span data-stu-id="3a907-147">a.</span></span> <span data-ttu-id="3a907-148">Zero ou mais dimensões.</span><span class="sxs-lookup"><span data-stu-id="3a907-148">Zero or more dimensions.</span></span> <span data-ttu-id="3a907-149">Cada dimensão é indicada por um DataModelName.</span><span class="sxs-lookup"><span data-stu-id="3a907-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="3a907-150">b.</span><span class="sxs-lookup"><span data-stu-id="3a907-150">b.</span></span> <span data-ttu-id="3a907-151">Zero ou mais filtros.</span><span class="sxs-lookup"><span data-stu-id="3a907-151">Zero or more filters.</span></span> <span data-ttu-id="3a907-152">Cada filtro tem:</span><span class="sxs-lookup"><span data-stu-id="3a907-152">Each filter has:</span></span>

   - <span data-ttu-id="3a907-153">DataModelName (a dimensão que terá o filtro definido).</span><span class="sxs-lookup"><span data-stu-id="3a907-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="3a907-154">Valor (o valor que será comparado pelo operand).</span><span class="sxs-lookup"><span data-stu-id="3a907-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="3a907-155">Operand (tipo de comparação, 0 significa "Igual").</span><span class="sxs-lookup"><span data-stu-id="3a907-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="3a907-156">c.</span><span class="sxs-lookup"><span data-stu-id="3a907-156">c.</span></span> <span data-ttu-id="3a907-157">Uma ou mais medidas.</span><span class="sxs-lookup"><span data-stu-id="3a907-157">One or more measurements.</span></span>

2. <span data-ttu-id="3a907-158">Envie a consulta para o Serviço de Dados por meio de chamada AJAX.</span><span class="sxs-lookup"><span data-stu-id="3a907-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="3a907-159">Os seguintes parâmetros de solicitação precisam ser fornecidos:</span><span class="sxs-lookup"><span data-stu-id="3a907-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="3a907-160">a.</span><span class="sxs-lookup"><span data-stu-id="3a907-160">a.</span></span> <span data-ttu-id="3a907-161">url (que deve ser http://[ServerName]/QoEDataService/RunQuery).</span><span class="sxs-lookup"><span data-stu-id="3a907-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="3a907-162">b.</span><span class="sxs-lookup"><span data-stu-id="3a907-162">b.</span></span> <span data-ttu-id="3a907-163">data (esta é a representação de cadeia de caracteres do objeto JSON definido na variável 'query').</span><span class="sxs-lookup"><span data-stu-id="3a907-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="3a907-164">O Serviço de Dados retornará os resultados da consulta como um parâmetro da função de retorno de chamada para o sucesso.</span><span class="sxs-lookup"><span data-stu-id="3a907-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="3a907-165">c.</span><span class="sxs-lookup"><span data-stu-id="3a907-165">c.</span></span> <span data-ttu-id="3a907-166">type (para QoEDataService, RunQuery aceita apenas solicitações 'POST').</span><span class="sxs-lookup"><span data-stu-id="3a907-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="3a907-167">d.</span><span class="sxs-lookup"><span data-stu-id="3a907-167">d.</span></span> <span data-ttu-id="3a907-168">assíncrono (um sinalizador indicando se a chamada AJAX deve ser síncrona ou assíncrona).</span><span class="sxs-lookup"><span data-stu-id="3a907-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="3a907-169">e.</span><span class="sxs-lookup"><span data-stu-id="3a907-169">e.</span></span> <span data-ttu-id="3a907-170">contentType (deve ser "application/json").</span><span class="sxs-lookup"><span data-stu-id="3a907-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="3a907-171">f.</span><span class="sxs-lookup"><span data-stu-id="3a907-171">f.</span></span> <span data-ttu-id="3a907-172">sucesso (função de retorno de chamada para quando a chamada AJAX terminar com êxito).</span><span class="sxs-lookup"><span data-stu-id="3a907-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="3a907-173">g.</span><span class="sxs-lookup"><span data-stu-id="3a907-173">g.</span></span> <span data-ttu-id="3a907-174">erro (função de tratamento de erro para quando a chamada AJAX falha).</span><span class="sxs-lookup"><span data-stu-id="3a907-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="3a907-175">Coloque dados em elementos div no HTML (no exemplo no código, isso é feito por meio da chamada de função anônima depois que a solicitação AJAX é concluída com êxito).</span><span class="sxs-lookup"><span data-stu-id="3a907-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="3a907-176">Colocar o código JavaScript em uma página HTML, e a página mostrará um relatório como o mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="3a907-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="3a907-177">O html completo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a907-177">The full html is as follows:</span></span>

```javascript
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

<span data-ttu-id="3a907-178">Até agora, o relatório ainda é muito simples.</span><span class="sxs-lookup"><span data-stu-id="3a907-178">So far, the report is still very simple.</span></span> <span data-ttu-id="3a907-179">O usuário pode adicionar mais medidas, dimensões ou filtros para personalizar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="3a907-180">Por exemplo, se você quiser mostrar a porcentagem de chamada ruim appSharing, uma nova medida em relação ao AppSharing precisa ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="3a907-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="3a907-181">Se você quiser mostrar todas as chamadas TCP v.s.</span><span class="sxs-lookup"><span data-stu-id="3a907-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="3a907-182">Chamadas UDP, uma nova dimensão em relação ao tipo de transporte deve ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="3a907-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="3a907-183">Se você quiser mostrar o número de chamadas ruins em um edifício específico, um novo filtro deverá ser adicionado para selecionar as chamadas de e para esse edifício.</span><span class="sxs-lookup"><span data-stu-id="3a907-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="3a907-184">**Exemplo 2: Amostra de definição de relatório**</span><span class="sxs-lookup"><span data-stu-id="3a907-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="3a907-185">Pode ser difícil para alguém descobrir como gravar a lista completa de medidas/dimensões/filtros e seus valores correspondentes ao construir uma consulta.</span><span class="sxs-lookup"><span data-stu-id="3a907-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="3a907-186">Nesse caso, você pode ir para o Portal, criar um relatório usando o editor de relatório e exibir a cadeia de caracteres JSON da definição de relatório e, em seguida, copiar a definição em um relatório personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a907-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="3a907-187">Neste exemplo, criaremos uma página da Web como a mostrada na figura em que um usuário pode inserir a ID de qualquer conjunto de relatório (ou relatório) existente e mostrar a definição do conjunto de relatório ou relatório na página da Web.</span><span class="sxs-lookup"><span data-stu-id="3a907-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="3a907-188">Em seguida, o usuário pode conectar a cadeia de caracteres JSON de cada relatório em um código semelhante ao mostrado no Exemplo 1 e construir qualquer relatório personalizado que o usuário desejar.</span><span class="sxs-lookup"><span data-stu-id="3a907-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![Exemplo de CQD](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="3a907-190">Para criar a ferramenta visualizador de definições de relatório, precisamos enviar chamadas para o Serviço de Repositório para recuperar as representações da cadeia de caracteres JSON das definições de cada conjunto de relatório que quisermos.</span><span class="sxs-lookup"><span data-stu-id="3a907-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="3a907-191">A API de repositório retornará a definição do conjunto de relatório com base em uma determinada ID do conjunto de relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="3a907-192">Um exemplo rápido é o seguinte: o código contém um bloco que é um exemplo simples para enviar uma consulta ao serviço repositório para obter o conteúdo de um item de repositório com base em seu identificador.</span><span class="sxs-lookup"><span data-stu-id="3a907-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="3a907-193">E a próxima parte do código (método processReportSetData) é enviar chamadas AJAX para obter a definição de cada relatório dentro desse conjunto de relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="3a907-194">Como a ID no portal da Web do CQD é a ID de um conjunto de relatório, a chamada AJAX retornará um item de conjunto de relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="3a907-195">Mais detalhes sobre a API de repositório e, especificamente, GetItems, podem ser encontrados em [Obter itens](get-items.md).</span><span class="sxs-lookup"><span data-stu-id="3a907-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
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

<span data-ttu-id="3a907-196">O acima resultará em uma página da Web como a da figura (sem a definição do relatório na visita inicial).</span><span class="sxs-lookup"><span data-stu-id="3a907-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="3a907-197">Obter a ID do conjunto de relatório do portal do CQD (é depois de "/#/" entrar na URL do portal do CQD (por exemplo,</span><span class="sxs-lookup"><span data-stu-id="3a907-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="3a907-198">na primeira figura, a ID do conjunto de relatório é 3024) e coloque essa ID de conjunto de relatório na seção de entrada desta página da Web.</span><span class="sxs-lookup"><span data-stu-id="3a907-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="3a907-199">Pressione o botão "carregar" e veja a definição completa (medidas, dimensões, listas de filtros) do conjunto de relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="3a907-200">Em resumo, para obter rapidamente a definição completa de um conjunto de relatório/relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="3a907-201">As etapas são:</span><span class="sxs-lookup"><span data-stu-id="3a907-201">The steps are:</span></span>

1. <span data-ttu-id="3a907-202">Vá para o Portal e use o editor de consulta para personalizar um relatório (clique no botão "Editar" acima de um relatório para editar, adicionar, remover medidas/dimensões/filtros e salvar o relatório).</span><span class="sxs-lookup"><span data-stu-id="3a907-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="3a907-203">Obter a ID do conjunto de relatório da URL (o número inteiro após a URL de login '/#/').</span><span class="sxs-lookup"><span data-stu-id="3a907-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="3a907-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span><span class="sxs-lookup"><span data-stu-id="3a907-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="3a907-205">**Exemplo 3: exemplo de scorecard**</span><span class="sxs-lookup"><span data-stu-id="3a907-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="3a907-206">Tempo para uma tarefa mais complicada.</span><span class="sxs-lookup"><span data-stu-id="3a907-206">Time for a more complicated task.</span></span> <span data-ttu-id="3a907-207">E se quisermos criar uma página da Web como a figura?</span><span class="sxs-lookup"><span data-stu-id="3a907-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="3a907-208">Precisamos atualizar o Exemplo 1 (com a ajuda da página da Web gerada no Exemplo 2 para recuperar a definição completa de qualquer relatório) para que possamos lidar com uma quantidade maior de dados.</span><span class="sxs-lookup"><span data-stu-id="3a907-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="3a907-209">Nesse caso, precisamos atualizar a lista de medidas e dimensões.</span><span class="sxs-lookup"><span data-stu-id="3a907-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="3a907-210">A maneira de descobrir como adicionar/editar uma medida e/ou uma dimensão é seguir as instruções no Exemplo 2 e recuperar a definição completa do relatório, incluindo as listas completas de medidas e dimensões.</span><span class="sxs-lookup"><span data-stu-id="3a907-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="3a907-211">Conecte a definição completa do relatório ao código de exemplo.</span><span class="sxs-lookup"><span data-stu-id="3a907-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="3a907-212">Aqui estão as etapas detalhadas para chegar à página de scorecard na figura da amostra fornecida no Exemplo 1:</span><span class="sxs-lookup"><span data-stu-id="3a907-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="3a907-213">Atualizar medições na variável de "consulta" de  `[Measures].[Audio Good Streams JPDR Count]` e `[Measures].[Audio Poor Streams JPDR Count]` para `[Measures].[AudioPoorJPDRPercentage]` .</span><span class="sxs-lookup"><span data-stu-id="3a907-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="3a907-214">Atualize os filtros.</span><span class="sxs-lookup"><span data-stu-id="3a907-214">Update the filters.</span></span> <span data-ttu-id="3a907-215">Os dados JSON para Filtros no Exemplo 1 têm um filtro, que é definido na  `[StartDate].[Month]` dimensão.</span><span class="sxs-lookup"><span data-stu-id="3a907-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="3a907-216">Como Filters é uma matriz JSON, dimensões adicionais podem ser adicionadas à lista de filtros.</span><span class="sxs-lookup"><span data-stu-id="3a907-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="3a907-217">Por exemplo, para obter o cliente-servidor dentro de chamadas com fio para o "currentMonth", devemos ter os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="3a907-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
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

   <span data-ttu-id="3a907-218">Aqui, a dimensão  `[Scenarios].[ScenarioPair]` é definida como `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` igual.</span><span class="sxs-lookup"><span data-stu-id="3a907-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="3a907-219">É  `[Scenario.][ScenarioPair]` uma dimensão especial criada para simplificar a criação de relatório.</span><span class="sxs-lookup"><span data-stu-id="3a907-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="3a907-220">Ele tem seis valores correspondentes a `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` .</span><span class="sxs-lookup"><span data-stu-id="3a907-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="3a907-221">Portanto, em vez de usar uma combinação de seis filtros para definir um cenário, precisamos usar apenas um filtro.</span><span class="sxs-lookup"><span data-stu-id="3a907-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="3a907-222">No nosso exemplo, o valor é traduzido para o cenário em que: primeiro é o servidor, o segundo não é o servidor, o primeiro está dentro, o segundo está dentro, o primeiro tipo de conexão é com fio e o segundo tipo de conexão é com fio, que é a definição exata  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` de "Servidor-Cliente-Dentro com Fio".</span><span class="sxs-lookup"><span data-stu-id="3a907-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="3a907-223">Crie um conjunto de filtros por cenário.</span><span class="sxs-lookup"><span data-stu-id="3a907-223">Create one filter set per scenario.</span></span> <span data-ttu-id="3a907-224">Cada linha no scorecard, na figura, representa um cenário diferente, que será um filtro diferente (enquanto as dimensões e medidas permanecem as mesmas).</span><span class="sxs-lookup"><span data-stu-id="3a907-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="3a907-225">Analisar os resultados das chamadas AJAX e posicioná-los na posição correta da tabela.</span><span class="sxs-lookup"><span data-stu-id="3a907-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="3a907-226">Como isso é principalmente manipulação de HTML e JavaScript, não entraremos em detalhes aqui.</span><span class="sxs-lookup"><span data-stu-id="3a907-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="3a907-227">Em vez disso, o código é fornecido no Apêndice A.</span><span class="sxs-lookup"><span data-stu-id="3a907-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="3a907-228">Se o CORS (Compartilhamento de Recursos entre Origens) estiver habilitado, os usuários poderão encontrar erros como "Nenhum header "Access-Control-Allow-Origin" está presente no recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="3a907-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="3a907-229">A origem 'null' não tem, portanto, acesso permitido".</span><span class="sxs-lookup"><span data-stu-id="3a907-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="3a907-230">Para resolver o problema, coloque o arquivo HTML na pasta onde o Portal está instalado (por padrão, ele deve ser `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` .</span><span class="sxs-lookup"><span data-stu-id="3a907-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="3a907-231">Em seguida, acesse o html por meio de qualquer navegador com a  `http://<servername>/cqd/<html_file_name>` URL.</span><span class="sxs-lookup"><span data-stu-id="3a907-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="3a907-232">(A URL padrão para o painel CQD local é  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="3a907-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="3a907-233">Apêndice A</span><span class="sxs-lookup"><span data-stu-id="3a907-233">Appendix A</span></span>

<span data-ttu-id="3a907-234">Código HTML para o Exemplo 3 (exemplo de scorecard):</span><span class="sxs-lookup"><span data-stu-id="3a907-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
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
