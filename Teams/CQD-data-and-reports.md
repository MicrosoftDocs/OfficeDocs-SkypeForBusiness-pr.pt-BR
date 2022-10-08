---
title: Dados e relatórios no Painel de Qualidade de Chamadas (CQD)
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre os dados e relatórios disponíveis no Microsoft Call Quality Dashboard (CQD).
ms.openlocfilehash: 7d89c17f299302f39e00e6aebcfd9309ead3eaae
ms.sourcegitcommit: 021cfac01a38282a8cde6e913d74be2d54c39162
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218510"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dados e relatórios no Painel de Qualidade de Chamadas (CQD)

O CQD (Painel de Qualidade de Chamadas da Microsoft) usa um feed de dados quase em tempo real (NRT). Os registros de chamada estão disponíveis no CQD dentro de 30 minutos após o final de uma chamada. Os registros de chamada do pipeline NRT só estão disponíveis por alguns meses antes de serem removidos do conjunto de dados.

## <a name="many-ways-to-access-cqd-data"></a>Muitas maneiras de acessar dados CQD

Você pode acessar dados CQD por vários caminhos diferentes. Escolha o que melhor atende às suas necessidades:

|&nbsp;|&nbsp;|
|---|---|
|Centro de administração do Teams [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)|Os dados do CQD são incluídos  na página Usuários no Centro de administração do Teams, mostrando os dados mais comuns de que você precisa em um formato fácil de ler. Você não pode personalizar os dados CQD que encontrar em **Usuários**.|
|Portal do CQD [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)|Resumo robusto e relatórios detalhados que atendem à maioria das necessidades, com filtragem de detalhamento. Você também pode personalizar relatórios no portal do CQD. <br><br>Obtenha dois [modelos de relatório CQD](#import-the-cqd-report-templates) para ajudá-lo a analisar dados no portal do CQD.|
|Power BI|Use consultas diretas para exibir seus dados CQD no Power BI usando [modelos personalizáveis do Power BI](CQD-Power-BI-query-templates.md). [Baixe modelos de consulta do Power BI para CQD](https://www.microsoft.com/download/details.aspx?id=102291).<br><br>Você também pode [usar a API REST para acessar dados CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) por meio do Power BI. Use esse método se quiser baixar seus dados CQD para que você possa trabalhar neles offline. O benefício de usar esse método é o melhor desempenho, especialmente útil para grandes conjuntos de dados que se ajoeçam no Power BI quando você está online.|
|API do Graph|Acesse os dados de qualidade da chamada por conta própria [usando o API do Graph](/graph/api/resources/callrecords-api-overview). Esse é o método mais complexo, mas oferece mais controle e flexibilidade na análise de seus dados de qualidade de chamada. Por exemplo, se você precisar ingressá-lo com outros dados para sua organização, poderá usar o API do Graph para criar um modelo de dados e incorporar dados de qualidade de chamada.|

## <a name="import-the-cqd-report-templates"></a>Importar os modelos de relatório CQD

Baixe [dois modelos de relatório CQD coletados](https://aka.ms/qertemplates) (Todas as Redes e Redes Gerenciadas) para ajudá-lo a se atualizar rapidamente com o CQD. O modelo Todas as Redes, embora otimizado para trabalhar com um arquivo de dados de construção, pode ser usado enquanto você trabalha para coletar e carregar informações de compilação no CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) no CQD**:

1. No CQD, selecione **Relatórios Detalhados** no menu na parte superior da página.

2. No painel esquerdo, selecione **Importar**. Navegue até o primeiro modelo CQDX e selecione **Abrir**.

3. Depois que o modelo for carregado, uma janela pop-up exibirá a mensagem "A importação de relatório foi bem-sucedida".

4. Repita as etapas 2 e 3 para o segundo modelo CQD.

   > [!NOTE]
   > Cada usuário deve importar os modelos CQD para sua instância CQD.

## <a name="euii-data"></a>Dados EUII

Por motivos de conformidade, os dados euII (informações de identificação do usuário final) (também conhecidos como informações de identificação pessoal ou PII) são mantidos apenas por 28 dias. À medida que os dados NRT cruzam a marca de 28 dias, os campos que contêm EUII são limpos, resultando em dados NRT sem EUII. Os campos que contêm dados EUII são:

- Endereço IP completo
- Endereço MAC (Controle de Acesso mídia)
- BSSID (identificador básico do conjunto de serviços)
- URI do PROTOCOLO SIP (somente Skype for Business)
- Nome UPN
- Nome do Ponto de Extremidade do Computador
- Comentários textuais do usuário
- ID do objeto (a ID de objeto do Active Directory do usuário do ponto de extremidade)
- Número de telefone
- Identidade do Atendedor Automático
- Chamar Identidade da Fila
- Nome do dispositivo VTC (Video Teleconferencing)
- Detalhes do dispositivo VTC (Video Teleconferencing)

### <a name="admin-roles-with-and-without-euii-access"></a>Administração funções com e sem acesso à UEII

Essas [funções RBAC](/azure/role-based-access-control/overview) **têm** acesso a EUII:

- Configurações Administração
- Serviço do Teams Administração
- Comunicações do Teams Administração
- Engenheiro de Suporte de Comunicações de Equipes
- Leitor Global
- Skype for Business Administração

Essas funções RBAC **não têm** acesso a EUII:

- Leitor de Relatórios
- Especialista em Suporte de Comunicações do Teams

## <a name="date-controls"></a>Controles de data

O CQD dá suporte aos seguintes tipos de tendência sem interrupção:

- 5 dias
- 7 dias
- 30 dias
- 60 dias
- 90 dias

O parâmetro Data da URL aceita um campo Dia. Os relatórios de dia sem interrupção usam datas especificadas no formato AAAA-MM-DD como o último dia da tendência. O parâmetro de Data da URL "00" indica "hoje".

|URL|Data de término da tendência de dia sem interrupção|
|:---|:---|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02/</span>|Dia Atual de fevereiro de 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/2019-02-15/</span>|15 de fevereiro de 2019|
|<span>\<cqdv3>https:///spd/#/Dashboard/\<reportid>/00/</span>|Dia Atual|

Por padrão, o dia atual do mês é usado como o último dia da Tendência de Dia Sem Interrupção.

## <a name="data-available-in-cqd-reports"></a>Dados disponíveis em relatórios CQD

O resumo padrão e os relatórios detalhados do CQD podem ser tudo o que você precisa para gerenciar a qualidade da chamada para sua organização. Se for necessário, você pode [criar relatórios personalizados](#create-custom-detailed-reports).

Se você quiser usar o Power BI para analisar seus dados do CQD, leia [Usar o Power BI para analisar dados do CQD para o Teams](CQD-Power-BI-query-templates.md).

|Recurso|Relatórios resumidos|Relatórios detalhados|
|:---|:---|:---|
|Métrica de compartilhamento de aplicativos|Não|Sim|
|Suporte a informações de criação de clientes|Sim|Sim|
|Suporte a informações do ponto de extremidade do cliente|Somente em <span>cqd.teams.microsoft.com<span/>|Somente em <span>cqd.teams.microsoft.com<span/>|
|Suporte à análise de busca detalhada|Não|Sim|
|Métricas de confiabilidade de mídia|Não|Sim|
|Relatórios de primeira linha|Sim|Sim|
|Relatórios de visão geral|Sim|Sim|
|Conjunto de relatórios por usuário|Não|Sim|
|Personalização do conjunto de relatórios (adicionar, excluir, modificar relatórios)|Não|Sim|
|Métricas de compartilhamento de tela baseadas em vídeo|Não|Sim|
|Métricas de vídeo|Não|Sim|
|Quantidade de dados disponíveis|Últimos 12 meses|Últimos 12 meses|
|Dados do Microsoft Teams|Sim|Sim|

### <a name="select-product-data-to-see-in-reports"></a>Selecionar dados do produto para ver em relatórios

Nos Relatórios resumo e Location-Enhanced, você pode usar a lista suspensa Filtro de  Produto para mostrar todos os dados do produto, somente dados do Microsoft Teams ou apenas Skype for Business online.

> [!div class="mx-imgBorder"]
> ![Captura de tela: mostra as opções de controle filtro de produto.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

Em relatórios detalhados, você pode usar a dimensão **Do Is Teams** para filtrar os dados para o Microsoft Teams ou Skype for Business online.

## <a name="summary-reports"></a>Relatórios resumidos

Estes são os relatórios que você verá no Painel do CQD quando entrar pela primeira vez no CQD. Eles fornecem uma visão rápida das tendências de qualidade com relatórios diários, mensais e de tabela para ajudar na identificação de sub-redes com baixa qualidade.

|Guia|Descrição|
|---|---|
|Qualidade geral da chamada|Agregação das outras três guias.|
|Servidor – Cliente|Detalhes dos fluxos entre os pontos de extremidade do servidor e do cliente.|
|Cliente – Cliente|Detalhes dos fluxos entre dois pontos de extremidade do cliente.|
|SLA de Qualidade de Voz|Informações sobre chamadas incluídas no [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) Skype for Business qualidade de voz.|

### <a name="overall-call-quality-tab"></a>Guia Qualidade Geral da Chamada

Use os dados nesta guia para avaliar o status e as tendências de qualidade da chamada com base em contagens de fluxo e porcentagens ruins. A legenda no canto superior direito mostra quais cores e elementos visuais representam essas métricas.

> [!div class="mx-imgBorder"]
> ![Captura de tela: mostrar a guia Qualidade da Chamada.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

Os fluxos são classificados em três grupos: Bom, Ruim e Não Classificado. Também há valores de *% Pobres calculados* que fornecem a taxa de fluxos classificados como Ruim  para a contagem total de fluxos classificados. Como *% Ruim = Fluxos ruins/(Fluxos ruins+ Fluxos bons) \* 100*, o *%* Ruim não é afetado pela presença de vários fluxos *não classificados.* Para ver o que classifica um fluxo como ruim ou bom, consulte a Classificação de [Fluxo no Painel de Qualidade de Chamada](stream-classification-in-call-quality-dashboard.md).

Use a escala à esquerda para medir os valores de contagem de fluxo.

> [!div class="mx-imgBorder"]
> ![Captura de tela: mostra os valores de contagem de fluxo.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

Use a escala à direita para medir os valores de % Ruim.

> [!div class="mx-imgBorder"]
> ![Captura de tela: mostra valores de % ruins.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

Você também pode obter os valores numéricos reais passando o mouse sobre uma barra.

> [!NOTE]
> O exemplo a seguir é de um conjunto de dados de exemplo muito pequeno e os valores não são realistas para uma implantação real.

> [!div class="mx-imgBorder"]
> ![Captura de tela: mostra o mouse usado para acessar dados.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

O volume de fluxo geral ajuda a determinar o quão relevantes são as porcentagens ruins calculadas. Quanto menor o volume de fluxos gerais, menos confiáveis são os valores de porcentagem ruim relatados.

### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client guia e Client-Client guias

Essas duas guias fornecem detalhes para os fluxos que ocorreram em seus cenários de ponto de extremidade para ponto de extremidade. A Server-Client guia tem quatro seções recolhíveis que representam quatro cenários sob os quais fluxos de mídia fluiriam.

- Com fio interno
- Com fio externo
- WiFi Interno
- WiFi Externo

Da mesma forma, a Client-Client guia tem cinco seções recolhíveis:

- Com fio interno — com fio interno
- Com fio interno — Com fio externo
- Com fio externo — com fio externo
- Com fio interno — Wi-Fi interno
- Com fio interno — Wi-Fi externo

#### <a name="inside-versus-outside"></a>Dentro versus Fora

O CQD classifica um fluxo como  *Dentro*  ou *Fora usando informações*  de compilação, se ele existir. Os pontos de extremidade de cada fluxo são associados a um endereço de sub-rede. Se a sub-rede estiver na lista de sub-redes marcadas como InsideCorp nas informações de build carregadas, ela será considerada *Interna*. Se a criação de informações ainda não tiver sido carregada, o Inside Test sempre classifica os fluxos como *Externos*.

O Inside Test para um cenário Server-Client considera apenas o ponto de extremidade do cliente. Como os servidores estão sempre fora da perspectiva de um usuário, isso não é contado no teste.

#### <a name="wired-versus-wifi"></a>Com fio versus Wi-Fi

Como os nomes indicam, os critérios de classificação se baseiam no tipo de conexões de cliente. O servidor está sempre com fio e não está incluído no cálculo. Em um determinado fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, o CQD o classifica como WiFi.

> [!NOTE]
> Dado um fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, ele será classificado como WiFi no CQD.

## <a name="tenant-data-information"></a>Informações de dados do locatário

O painel Relatórios de Resumo do CQD inclui uma  página de Upload de Dados de Locatário, acessada selecionando o Carregamento de Dados do Locatário no menu de configurações no canto superior direito. Esta página é usada para administradores carregarem suas próprias informações, como:

- Um mapa de endereço IP e informações geográficas.
- Um mapa de cada AP sem fio e seu endereço MAC.
- Um mapa do ponto de extremidade para a criação/modelo/tipo de ponto de extremidade etc.

Recomendamos que você carregue seus dados de locatário, de compilação e de localização para que o CQD possa incluir essas informações em seus relatórios. Se você ainda não tiver carregado esses dados, leia Carregar [locatário e compilar dados](CQD-upload-tenant-building-data.md).

## <a name="detailed-reports"></a>Relatórios detalhados

|Nome|Descrição|
|---|---|
|Location-Enhanced relatórios|Mostra tendências de qualidade com base nas informações de localização. Esse relatório só será exibido se você tiver [carregado seus dados de locatário](CQD-upload-tenant-building-data.md).|
|Relatórios de confiabilidade|Inclui áudio, vídeo, compartilhamento de tela baseado em vídeo (VBSS) e relatórios de compartilhamento de aplicativos.|
|Relatórios de qualidade de experiência|Qualidade e confiabilidade de áudio para todos os clientes e dispositivos, incluindo salas de reunião. Esses relatórios são uma versão "reduzida" dos modelos CQD baixáveis, concentrando-se nas principais [áreas](https://aka.ms/QERtemplates) para analisar a qualidade e a confiabilidade do áudio.|
|Relatórios de drill down de qualidade|Drill downs: data por região, locais, sub-redes, hora e usuários.|
|Relatórios de busca detalhada de falha|Drill downs: data por região, locais, sub-redes, hora e usuários.|
|Classificar Meus Relatórios de Chamadas|Analise as classificações de chamadas do usuário por região, local ou por usuário. Inclui comentários textuais.|
|Relatórios do Suporte Técnica|Os Relatórios de Suporte Técnica pesquisam dados de chamada e reunião para usuários individuais, grupos de usuários ou todos. Incorporando dados de compilação e EUII, esses relatórios ajudam a identificar possíveis problemas do sistema com base no local da rede, detalhes da conferência, dispositivos ou firmware.|
|Relatórios de versão do cliente|Resumo da versão do cliente: exibir as sessões e as contagens de usuários para cada versão do aplicativo cliente<br><br>Versão do cliente por usuário: exibir nomes de usuário para cada versão do aplicativo cliente <br><br>Os filtros pré-criados para Produto e Tipo de Cliente ajudam a concentrar as versões em clientes específicos.|
|Relatórios de ponto de extremidade|Mostra a qualidade da chamada por pontos de extremidade do computador (modelo e make do computador). Esses relatórios incluem a criação de dados, caso você os tenha carregado.|

## <a name="create-custom-detailed-reports"></a>Criar relatórios detalhados personalizados

Se os relatórios CQD padrão não atenderem às suas necessidades, use estas instruções para criar um relatório personalizado. Ou (a partir de janeiro de 2020) [Use o Power BI para relatórios CQD ](cqd-power-bi-query-templates.md).

Na lista suspensa de relatórios \(\) na parte superior da tela exibida no logon, na tela Relatórios de Resumo, selecione Relatórios  Detalhados e, em **seguida, Novo**. Clique **em Editar** em um relatório para ver o Editor de Consultas. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de Consultas ajuda você a editar essas consultas e as opções de exibição do relatório.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados quanto a intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar quaisquer sobreposições e corrigir o problema antes de carregar novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos incorretos de sub-redes para edifícios nos relatórios. Determinadas implementações de VPN não relatam com precisão as informações da sub-rede. É recomendável que, ao adicionar uma sub-rede VPN ao arquivo de construção, em vez de uma entrada para a sub-rede, entradas separadas sejam adicionadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive.
>
> A coluna VPN é opcional e usará como padrão 0.  Se o valor da coluna VPN for definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede.  Use isso com moderação e somente para sub-redes VPN, pois a expansão total dessas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a criação de dados.

Aponte para gráficos de barras e linhas de tendência no relatório para exibir valores detalhados. O relatório que tem o foco mostrará o menu de ação: **Editar**, **Clonar**, **Excluir**, **Baixar** e **Exportar Árvore de Relatórios**.

## <a name="query-filters"></a>Filtros de consulta

Os filtros de consulta são implementados usando o Editor de Consultas no CQD. Esses filtros são usados para reduzir o número de registros retornados pelo CQD, minimizando assim o tamanho geral do relatório e os tempos de consulta. Isso é especialmente útil para filtrar redes não gerenciadas. Os filtros listados na tabela a seguir usam expressões regulares (RegEx).

|Filter|Descrição|Exemplo de filtro de consulta CQD|
|---|---|---|
|Nenhum valor em branco|Alguns filtros não têm a opção de filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e defina o filtro como Igual ou Não Igual a, dependendo de suas necessidades.|Second Building Name \<\> \^\\s\*\$|
|Excluir sub-redes comuns|Sem um arquivo de construção válido para separar o gerenciado de redes não gerenciadas, as redes base serão incluídas nos relatórios. Essas sub-redes base estão fora do escopo do controle de TI e podem ser rapidamente excluídas de um relatório. As sub-redes comuns, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0.|Segunda Sub-rede \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Exibir somente dentro|Usado para filtrar um relatório para gerenciado (dentro) ou não gerenciado (fora). O modelo CQD gerenciado já está pré-configurado com esses filtros.|Second Inside Corp = Inside|

## <a name="report-filters"></a>Filtros de relatório

Use filtros de relatório CQD para restringir o foco de suas investigações. Use filtros de relatório adicionando um filtro ao relatório renderizado no Editor de Consultas ou diretamente no relatório. Os filtros de relatório a seguir são usados em todos os [modelos CQD](https://aka.ms/QERtemplates).

|Filter|Descrição|Exemplo de filtro de relatório CQD|
|---|---|---|
|Mês|Comece com o ano primeiro, depois o mês.|2017-10|
|Alfabético|Filtra todos os caracteres alfabéticos.|[a-z]|
|Numérico|Filtra todos os caracteres numéricos.|[0-9]|
|Porcentagem|Filtra uma porcentagem.|([3-9]\\.)\| ([3-9])\| ([1-9][0-9])|

### <a name="drill-down-filters"></a>Filtros de busca detalhada

Os relatórios CQD apresentam vários filtros de busca detalhada, que são ferramentas avançadas para restringir o foco de suas investigações de qualidade de chamada. Se você selecionar um campo de busca detalhada, o relatório abrirá automaticamente a guia apropriada e filtra o valor selecionado. Se essa guia tiver seus próprios campos de drill down e um estiver selecionado, ambos os conjuntos de filtros serão aplicados, restringindo progressivamente o conjunto de dados resultante.

![Diagrama ilustrando o fluxo de relatório de busca detalhada.](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>Adicionar e editar campos de busca detalhada

Ao editar um relatório, você tem a opção de especificar campos de drill down por conta própria usando o Editor de Consultas.

Comece clicando **em ...** para o relatório que você deseja editar e selecione **Editar**.

![Captura de tela da edição de um campo de busca detalhada.](media/qerguide-image-addeditdrilldownfields.png)

Selecione uma Dimensão na lista no lado esquerdo do Editor de Consultas. Em seguida, clique na lista suspensa abaixo  do rótulo Navegar para e selecione a guia e o grupo expansor para o qual você deseja que a Dimensão faça drill through. Observação: atualmente, a funcionalidade de drill down só funciona navegando para diferentes guias. O suporte para detalhamento em um expansor específico será adicionado posteriormente. Por fim, **clique em** Fechar para salvar as alterações na Dimensão e,  em seguida, clique em Salvar para salvar e fechar o Editor de Consultas.

![Captura de tela da seleção de uma dimensão no Editor de Consultas.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de seleção multissuletor

Além da funcionalidade de drill down, o CQD também dá suporte à especificação de Filtros com vários valores (ou filtros).

Para selecionar vários valores de filtro, comece adicionando um novo filtro ao relatório. Clique **+** ao lado **do rótulo** Filtros, insira o nome da Dimensão que você deseja usar e clique em **Adicionar**.

![Captura de tela da adição de um filtro com várias seleções.](media/qerguide-image-addmultiselectfilter.png)

Em seguida, **clique em Pesquisar** (um ícone de lupa ao lado do novo filtro). Você verá um campo de texto e várias opções, incluindo **Selecionar Tudo** **e Inverter**. Insira um valor e clique **em Pesquisar** ao lado desse campo para pesquisar. Como alternativa, deixe o campo de texto vazio e clique **em Pesquisar** para exibir até as primeiras 100 opções.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo:

![Captura de tela da adição de um filtro de consulta.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros no nível do painel

Determinados relatórios CQD têm filtros no nível do painel adicionados a eles, facilitando a filtragem por parâmetros comuns. Esses filtros aparecem fora das guias de relatório regulares e diretamente abaixo do filtro Produto, e se aplicam a todos os filtros no Painel.

![Captura de tela de um filtro de painel.](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de URL

O CQD dá suporte à adição de filtros à URL. Isso facilita o compartilhamento ou o indicador de uma consulta CQD. Você pode definir parâmetros na URL, como Mês de Tendência, ID do locatário ou idioma. Você também pode adicionar filtros de nível de produto ou painel à URL.
A exclusão de dados federados de relatórios CQD é útil quando você está corrigindo edifícios gerenciados ou redes em que pontos de extremidade federados podem influenciar seus relatórios.

Para adicionar um filtro, acrescente o seguinte ao final da URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo:

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Para adicionar um filtro no nível do painel a uma URL, esse filtro deve existir no CQD como um filtro de nível de produto ou painel. Adicione esses filtros à URL após o Mês de Tendência e antes dos parâmetros de URL:

`filter/DATA_MODEL_NAME|VALUE`

Por exemplo, para aplicar um valor de filtro produto do Microsoft Teams, adicione o seguinte:

`filter/[AllStreams].[Is%20Teams]|[True]`

Sua URL inteira seria semelhante a esta:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Para aplicar filtros de URL com valores de seleção multisseleção, separe cada valor com um caractere pipe (|). Por exemplo:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Se você especificar um nome ou valor inválido, o filtro de URL não será aplicado.

Você pode usar um filtro de URL para filtrar cada relatório para uma dimensão específica. Os filtros de URL mais comuns são usados para filtrar relatórios para excluir a telemetria de participantes federados ou se concentrar apenas no Teams ou Skype for Business Online. A exclusão de dados federados de relatórios CQD é útil quando você está corrigindo edifícios gerenciados ou redes em que pontos de extremidade federados podem influenciar seus relatórios.

|Filter|Descrição|Exemplo de filtro de consulta CQD|
|---|---|---|
|Nenhum valor em branco|Alguns filtros não têm a opção de filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e defina o filtro como Igual ou Não Igual a, dependendo de suas necessidades.|Second Building Name \<\> \^\\s\*\$|
|Excluir sub-redes comuns|Sem um arquivo de construção válido para separar o gerenciado de redes não gerenciadas, as redes base serão incluídas nos relatórios. Essas sub-redes base estão fora do escopo do controle de TI e podem ser rapidamente excluídas de um relatório. As sub-redes comuns, conforme definido neste artigo, são 10.0.0.0, 192.168.1.0 e 192.168.0.0.|Segunda Sub-rede \<\> 10.0.0.0 \|192.168.0.0 \|192.168.1.0|
|Exibir somente dentro|Usado para filtrar um relatório para gerenciado (dentro) ou não gerenciado (fora). O modelo CQD gerenciado já está pré-configurado com esses filtros.|Second Inside Corp = Inside|

#### <a name="how-to-find-your-tenant-id"></a>Como encontrar sua ID de locatário

A ID do locatário no CQD corresponde à ID do Diretório no Azure. Se você não souber a ID do diretório, poderá encontrá-la no portal do Azure:

1. Entre no Microsoft portal do Azure:<https://portal.azure.com>

2. Selecione **o Azure Active Directory**.

3. Em **Gerenciar**, selecione **Propriedades**. Sua ID de locatário está na caixa **ID do** Diretório.

Você também pode encontrar sua ID de locatário usando o PowerShell:

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparando o Teams e Skype for Business dados CQD

Ao examinar seus dados, você poderá ver diferenças nos dados entre o Teams e o Skype for Business. Alguns motivos:

- Diferenças nos mecanismos para garantir o desempenho e a confiabilidade:
  - O Teams tem reconexão automática e roaming rápido. Skype for Business não.
  - O Teams tem gerenciamento dinâmico de largura de banda. Skype for Business não.
- Diferenças nos [intervalos de endereços IP](Office-365-URLs-IP-address-ranges.md) entre o Teams e o Skype for Business. Os intervalos de IP do Teams são mais recentes, o que pode causar problemas de conectividade no firewall.

## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de criação](CQD-upload-tenant-building-data.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
