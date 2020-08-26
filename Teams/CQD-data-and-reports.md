---
title: Dados e relatórios no painel de qualidade de chamada (CQD)
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre os dados e relatórios disponíveis no painel de qualidade de chamada da Microsoft (CQD).
ms.openlocfilehash: 4b96f64f7f182c0d4c95796358b20b38d8c726b4
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897841"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dados e relatórios no painel de qualidade de chamada (CQD)

O Microsoft Call Quality Dashboard (CQD) usa um feed de dados near-real-time (NRT). Os registros de chamadas estão disponíveis no CQD dentro de 30 minutos após o término de uma chamada. Os registros de chamadas do pipeline do NRT só estão disponíveis por alguns meses antes de serem removidos do conjunto de dados. 


## <a name="many-ways-to-access-cqd-data"></a>Muitas maneiras de acessar dados do CQD

Você pode acessar os dados do CQD por várias avenidas diferentes. Escolha uma que melhor atenda às suas necessidades:

|  |  |
|---------|---------|
|Centro de administração [do https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com) Teams (    | Os dados do CQD estão incluídos na página **usuários** no centro de administração do Teams, mostrando os dados mais comuns que você precisa em um formato fácil de ler. Não é possível personalizar dados do CQD que você encontra em **usuários**.  |
|Portal [de CQD https://cqd.teams.microsoft.com) (](https://cqd.teams.microsoft.com)     | Resumos robustos e relatórios detalhados que atendem à maioria das necessidades, com filtragem de Drill-through. Você também pode personalizar relatórios no portal do CQD. <br><br>Obtenha dois [modelos de relatório CQD](#import-the-cqd-report-templates) para ajudá-lo a analisar dados no portal do CQD.       |
|Power BI     | Use consultas diretas para exibir seus dados do CQD no Power BI usando [modelos personalizáveis do Power bi](CQD-Power-BI-query-templates.md). [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).<br><br>Você também pode [usar a API REST para acessar dados do CQD](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) por meio do Power bi. Use esse método se desejar baixar seus dados do CQD para que você possa trabalhar nele offline. A vantagem de usar esse método é um desempenho melhor, especialmente útil para grandes conjuntos de dados que Bog no Power BI quando você estiver online.       |
|API do Graph     | Acesse os dados de qualidade da chamada usando a [API do Graph](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta). Esse é o método mais complexo, mas oferece o maior controle e flexibilidade na análise dos dados de qualidade da chamada. Por exemplo, se você precisar ingressar com outros dados para sua organização, poderá usar a API do Graph para criar um modelo de dados e incorporar os dados de qualidade da chamada.        |

## <a name="import-the-cqd-report-templates"></a>Importar os modelos de relatório do CQD

Baixe [dois modelos de relatório CQDs](https://aka.ms/qertemplates) (todas as redes e redes gerenciadas) para ajudá-lo a se familiarizar rapidamente com o CQD. O modelo todas as redes, embora otimizado para trabalhar com um arquivo de construção de dados, pode ser usado enquanto você trabalha para coletar e carregar informações de construção no CQD, conforme descrito na próxima seção.

**Para importar os modelos (. CQDX) em CQD**

1. No CQD, selecione **relatórios detalhados** no menu na parte superior da página.

2. No painel esquerdo, selecione **importar**. Navegue até o primeiro modelo CQDX e selecione **abrir**.

3. Após o carregamento do modelo, uma janela pop-up exibirá a mensagem "relatório de importação foi bem-sucedido". 

4. Repita as etapas 2 e 3 para o segundo modelo CQD.

   > [!NOTE]
   > Cada usuário deve importar os modelos do CQD para a sua instância do CQD. 



## <a name="euii-data"></a>Dados do EUII

Por motivos de conformidade, os dados de informações de identificação de usuário final (EUII) (também conhecidos como informações de identificação pessoal ou PII) só são mantidos por 28 dias. Como os dados do NRT atravessam a marca de 28 dias, os campos que contêm EUII são limpos, resultando em dados de NRT grátis de EUII. Os campos que contêm dados EUII são:

- Endereço IP completo
- Endereço de controle de acesso à mídia (MAC)
- Identificador do conjunto de serviços básico (BSSID)
- URI de protocolo SIP (protocolo de iniciação de sessão) (somente Skype for Business)
- Nome UPN
- Nome do ponto de extremidade do computador
- Feedback textual do usuário
- ID do objeto (a ID de objeto do Active Directory do usuário do ponto de extremidade)

### <a name="admin-roles-with-and-without-euii-access"></a>Funções de administrador com e sem o acesso EUII

Estas [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) funções RBAC **DO** têm acesso EUII:
- Administrador global
- Administrador do teams Service
- Administrador de comunicações do teams
- Engenheiro de Suporte de Comunicações de Equipes
- Leitor global
- Administrador do Skype for Business

Essas funções RBAC **não** têm acesso EUII:
- Leitor de relatórios
- Especialista em suporte do teams Communications


## <a name="date-controls"></a>Controles de data

O CQD dá suporte aos seguintes tipos de tendência revertida:

- 5 dias
- 7 dias
- 30 dias
- 60-dia
- 90-dia

O parâmetro de data da URL aceita um campo Day. Os relatórios de dia transcorrido usam datas especificadas no formato AAAA-MM-DD como o último dia da tendência. O parâmetro de data de URL "00" indica "hoje".

|URL| Data de término da tendência do dia transcorrido|
|:---|:---|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02/</span>   |Dia atual de fevereiro de 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /2019-02-15/</span>|15 de fevereiro de 2019|
|<span>https:// <cqdv3> /SPD/#/Dashboard/ <reportid> /00/</span>        |Dia atual|
|||

Por padrão, o dia atual do mês é usado como o último dia da tendência do dia transcorrido.


## <a name="data-available-in-cqd-reports"></a>Dados disponíveis nos relatórios do CQD

O resumo padrão e os relatórios detalhados do CQD podem ser tudo o que você precisa para gerenciar a qualidade das chamadas para a sua organização. Se for necessário, você pode [criar relatórios personalizados](#create-custom-detailed-reports). 

Se você quiser usar o Power BI para analisar os dados do CQD, leia [usar o Power bi para analisar os dados do CQD para o Teams](CQD-Power-BI-query-templates.md).

|Recurso|Relatórios de resumo|Relatórios detalhados|
|:--- |:--- |:--- |
|Métrica de compartilhamento de aplicativos | Não | Sim |
|Suporte a informações de prédio do cliente | Sim | Sim |
|Suporte a informações de ponto de extremidade do cliente | Somente no <span> CQD.Teams.Microsoft.com<span/> | Somente no <span> CQD.Teams.Microsoft.com<span/> |
|Suporte para análise de busca detalhada   | Não   | Sim   |
|Métricas de confiabilidade de mídia   | Não   | Sim   |
|Relatórios prontos da caixa   | Sim   | Sim   |
|Relatórios de visão geral   | Sim   | Sim   |
|Conjunto de relatórios por usuário   | Não   | Sim   |
|Personalização do conjunto de relatórios (adicionar, excluir, modificar relatórios)   | Não   | Sim   |
|Métricas de compartilhamento de tela com base em vídeo   | Não   | Sim   |
|Métricas de vídeo   | Não   | Sim   |
|Quantidade de dados disponíveis   | Últimos 12 meses   | Últimos 12 meses   |
|Dados do Microsoft Teams   | Sim   | Sim   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Selecionar dados do produto para ver nos relatórios

Nos relatórios Resumo e local-avançado, você pode usar o menu suspenso **filtro do produto** para mostrar todos os dados do produto, somente dados do Microsoft Teams ou somente dados do Skype for Business online.
  
![Captura de tela: mostra as opções de controle de filtro do produto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Em relatórios detalhados, você pode usar a dimensão **is Teams** para filtrar os dados para o Microsoft Teams ou dados do Skype for Business online.

## <a name="summary-reports"></a>Relatórios de resumo

Estes são os relatórios que você verá no painel CQD ao entrar pela primeira vez no CQD. Elas fornecem uma visão geral de tendências de qualidade com relatórios diários, mensais e de tabela para ajudar a identificar sub-redes com baixa qualidade. 

| Abas | Descrição |
|---------|---------|
|Qualidade geral das chamadas     | Agregar das outras 3 guias.       |
|Servidor — cliente     |Detalhes dos fluxos entre os pontos de extremidade do servidor e do cliente.        |
|Cliente — cliente     |Detalhes dos fluxos entre dois pontos de extremidade do cliente.        |
|SLA de qualidade de voz     |Informações sobre chamadas incluídas no [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualidade de voz do Skype for Business.        |

### <a name="overall-call-quality-tab"></a>Guia qualidade geral da chamada

Use os dados nesta guia para avaliar o status e as tendências da qualidade da chamada com base em contagens de fluxo e percentuais insatisfatórios. A legenda no canto superior direito mostra quais elementos visuais e de cor representam essas métricas.
  
![Captura de tela: mostrar a guia qualidade da chamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Os fluxos são classificados em três grupos: satisfatório, fraco e não classificados. Também são calculados valores de  *baixa qualidade*  que proporcionam a taxa de fluxos classificados como *deficientes*  para a contagem total de fluxos classificados. Como *baixa% = fluxos ruins/(fluxos de má qualidade + bom fluxo) * 100*, os *% deficientes*  não são afetados pela presença de vários fluxos não *classificados*  . Para ver o que classifica um fluxo como ruim ou bom, consulte [classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md).
  
Use a escala à esquerda para medir os valores de contagem de fluxo.
  
![Captura de tela: mostra os valores de contagem de fluxo](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use a escala à direita para medir os valores de baixa%.
  
![Captura de tela: mostra valores de baixa qualidade](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Você também pode obter os valores numéricos reais passando o mouse sobre uma barra.
  
> [!NOTE]
> O exemplo a seguir é de um conjunto de dados de exemplo muito pequeno, e os valores não são realistas para uma implantação real.
  
![Captura de tela: mostra o mouse usado para acessar dados](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
O volume de fluxo geral ajuda a determinar a relevância das porcentagens insatisfatórias calculadas. Quanto menor for o volume de fluxos gerais, menos confiável será a porcentagem dos valores de porcentagem deficientes reportados.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Guias servidor-cliente e cliente-cliente

Essas duas guias fornecem detalhes para os fluxos que ocorreram em seus cenários de ponto de extremidade a ponto de extremidade. A guia servidor-cliente tem quatro seções recolhíveis que representam quatro cenários em que os fluxos de mídia fluiriam.
  
- Com fio interno
- Com fio externo
- Sem fio dentro
- Sem fio externo

Da mesma forma, a guia cliente/cliente tem cinco seções recolhíveis:

- Com fio interno – com fio dentro
- Com fio interno – com fio externo
- Com fio externo — com fio externo
- Com fio interno — WiFi Inside
- Com fio interno — WiFi externo

#### <a name="inside-versus-outside"></a>Dentro e fora

O CQD classifica um fluxo de  *dentro*  ou de *fora*  usando as informações de construção, se houver. Os pontos de extremidade de cada fluxo estão associados a um endereço de sub-rede. Se a sub-rede estiver na lista das sub-redes marcadas InsideCorp nas informações de construção carregadas, ela será considerada *dentro*. Se as informações de construção ainda não tiverem sido carregadas, então dentro do teste sempre classifica os fluxos como *fora*. 

O teste interno para um cenário de servidor-cliente apenas considera o ponto de extremidade do cliente. Como os servidores estão sempre fora da perspectiva de um usuário, isso não é contabilizado no teste.
  
#### <a name="wired-versus-wifi"></a>Com fio versus WiFi

Conforme os nomes indicam, os critérios de classificação são baseados no tipo de conexões de cliente. O servidor é sempre conectado e não está incluído no cálculo. Em um determinado fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, o CQD o classificará como WiFi.

> [!NOTE]
> Dado um fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, ele será classificado como WiFi no CQD.
  
  
## <a name="tenant-data-information"></a>Informações de dados do locatário

O painel relatórios de resumo CQD inclui uma página de **carregamento de dados de locatários** , acessada selecionando **carregar dados do locatário** no menu configurações no canto superior direito. Esta página é usada para os administradores carregarem suas próprias informações, como:

- Um mapa de endereço IP e informações geográficas.
- Um mapa de cada AP sem fio e seu endereço MAC.
- Um mapa de ponto de extremidade para marca/modelo/tipo de ponto de extremidade, etc.
  
Recomendamos que você carregue os dados do locatário, da criação e do local para que o CQD possa incluir essas informações em seus relatórios. Se você ainda não carregou esses dados, leia [locatário de carregamento de carregamento e dados de construção](CQD-upload-tenant-building-data.md). 


## <a name="detailed-reports"></a>Relatórios detalhados

| Nome | Descrição |
|---------|---------|
|Localização-relatórios aprimorados     |Mostra as tendências de qualidade com base nas informações de localização. Esse relatório só será exibido se você tiver [carregado seus dados locatário](CQD-upload-tenant-building-data.md).        |
|Relatórios de confiabilidade     |Inclui áudio, vídeo, compartilhamento de tela baseado em vídeo (VBSS) e relatórios de compartilhamento de aplicativos.        |
|Relatórios de qualidade da experiência     |Qualidade de áudio e confiabilidade para todos os clientes e dispositivos, incluindo salas de reunião. Esses relatórios são uma versão "reduzida" dos [modelos CQD](https://aka.ms/QERtemplates)para download, com foco em áreas essenciais para a análise da qualidade e da confiabilidade do áudio.         |
|Relatórios de busca detalhada de qualidade     | Buscas detalhadas: data por região, locais, sub-redes, hora e usuários.        |
|Relatórios de busca detalhada de falha     | Buscas detalhadas: data por região, locais, sub-redes, hora e usuários.        |
|Classificar relatórios de minhas chamadas     |Analisar classificações de chamadas do usuário por região, local ou por usuário. Inclui feedback textual.         |
|Relatórios de Help Desk     |Relatórios de suporte técnico Veja os dados de chamada e reunião para usuários individuais, grupos de usuários ou todos. A incorporação de dados de construção e EUII, esses relatórios ajudam a identificar possíveis problemas de sistema com base no local de rede, nos detalhes da conferência, em dispositivos ou firmware.         |
|Relatórios de versão do cliente     |Resumo da versão do cliente: exibir as contagens de sessões e usuários para cada versão do aplicativo cliente<br><br>Versão do cliente por usuário: exibir nomes de usuário para cada versão do aplicativo cliente <br><br>Os filtros predefinidos para o produto e o tipo de cliente ajudam a concentrar as versões em clientes específicos.         |
|Relatórios de ponto de extremidade     |Mostra a qualidade da chamada por pontos de extremidade do computador (marca e modelo do computador). Esses relatórios incluem a criação de dados, se você o carregou.         |


## <a name="create-custom-detailed-reports"></a>Criar relatórios detalhados personalizados

Se os relatórios padrão do CQD não atenderem às suas necessidades, use estas instruções para criar um relatório personalizado. Ou (desde janeiro de 2020), [use os relatórios do Power bi para CQD ](cqd-power-bi-query-templates.md).

Na lista suspensa de relatórios na parte superior da tela exibida ao fazer logon \( na tela **relatórios resumidos** , \) selecione **relatórios detalhados**  e **novo**. Clique em **Editar** em um relatório para ver o editor de consultas. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O editor de consultas ajuda você a editar essas consultas e as opções de exibição do relatório.

> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema antes de carregá-lo novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para prédios nos relatórios. Algumas implementações de VPN não reportam precisamente as informações de sub-rede. É recomendável que, ao adicionar uma sub-rede VPN ao arquivo de construção, em vez de uma entrada para a sub-rede, as entradas separadas sejam adicionadas para cada endereço na sub-rede VPN como uma rede de 32 bits separada. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive.
>
> A coluna VPN é opcional e será definida como padrão 0.  Se o valor da coluna VPN estiver definido como 1, a sub-rede representada por essa linha será totalmente expandida para corresponder a todos os endereços IP dentro da sub-rede.  Use isso de maneira moderada e somente para sub-redes VPN, já que expandir totalmente essas sub-redes terá um impacto negativo nos tempos de consulta para consultas que envolvem a construção de dados.

Aponte para gráficos de barras e linhas de tendências no relatório para exibir valores detalhados. O relatório que tem o foco mostrará o menu de ação: **Editar**, **clonar**, **excluir**, **baixar**e **Exportar árvore de relatórios**.



## <a name="query-filters"></a>Filtros de consulta

Os filtros de consulta são implementados usando o editor de consultas no CQD. Esses filtros são usados para reduzir o número de registros retornados pela CQD, minimizando assim o tamanho geral do relatório e os tempos de consulta. Isso é especialmente útil para filtrar redes não gerenciadas. Os filtros listados na tabela a seguir usam expressões regulares (RegEx).


| Filter         | Descrição          | Exemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Nenhum valor em branco   | Alguns filtros não têm a opção de filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e defina o filtro para igual ou não igual, dependendo das suas necessidades.      | Segundo nome da compilação \<\> \^ \\ s\*\$                       |
| Excluir sub-redes comuns | Sem um arquivo de construção válido para separar o gerenciamento de redes não gerenciadas, as redes domésticas serão incluídas nos relatórios. Essas sub-redes residenciais estão fora do escopo do controle de ti e podem ser rapidamente excluídas de um relatório. As sub-redes comuns, conforme definido neste guia, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Exibir somente dentro  | Usado para filtrar um relatório para gerenciado (interno) ou não gerenciado (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.       | Segunda interna Corp = Inside        |

## <a name="report-filters"></a>Filtros de relatório

Use CQD filtros de relatório para restringir o foco de suas investigações. Use filtros de relatório adicionando um filtro ao relatório renderizado no editor de consultas ou diretamente no relatório. Os filtros de relatório a seguir são usados em todos os [modelos do CQD](https://aka.ms/QERtemplates).


| Filter     | Descrição                            | Exemplo de filtro de relatório CQD         |
|------------|----------------------------------------|-----------------------------------|
| Mensais      | Comece com o ano primeiro e, em seguida, mês. | 2017-10                           |
| Maiúscula | Filtros para qualquer caractere alfabético. | [a-z]                             |
| Alfanumérico    | Filtros para caracteres numéricos.    | [0-9]                             |
| Porcentual | Filtros para uma porcentagem.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9] [0-9]) |


### <a name="drill-down-filters"></a>Filtros de detalhamento

Os relatórios do CQD apresentam vários filtros de busca detalhada, que são ferramentas poderosas para restringir o foco das suas investigações de qualidade de chamada. Se você selecionar um campo de busca detalhada, o relatório abrirá automaticamente a guia apropriada e os filtros no valor selecionado. Se essa guia tiver seus próprios campos de drill-down e um estiver selecionado, ambos os conjuntos de filtros serão aplicados, restringindo progressivamente o conjunto de dados resultante.

![Fluxo de relatório de ilustrações de ilustrações de diagrama](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Adicionar e editar campos de drill-down

Ao editar um relatório, você tem a opção de especificar os campos de busca detalhada usando o editor de consultas.

Comece clicando em **..** . para o relatório que você deseja editar e, em seguida, selecione **Editar**.

![Captura de tela da edição de um campo de drill-down](media/qerguide-image-addeditdrilldownfields.png)

Selecione uma dimensão na lista no lado esquerdo do editor de consultas. Em seguida, clique na lista suspensa abaixo do botão **navegar para** etiquetar e selecione a guia e o grupo de expansores para os quais você deseja que a dimensão faça drill-through. Observação: no momento, a funcionalidade de busca detalhada só funciona ao navegar para guias diferentes. O suporte para análise detalhada para um expansor específico será adicionado mais tarde. Por fim, clique em **fechar** para salvar as alterações na dimensão e, em seguida, clique em **salvar** para salvar e fechar o editor de consultas.

![Captura de tela da seleção de uma dimensão no editor de consultas](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtros de seleção múltipla

Além da funcionalidade de busca detalhada, o CQD também oferece suporte à especificação de filtros com vários valores (ou filtros).

Para selecionar vários valores de filtro, comece adicionando um novo filtro ao relatório. Clique **+** ao lado do rótulo **filtros** , insira o nome da dimensão que você deseja usar e clique em **Adicionar**.

![Captura de tela da adição de um filtro de seleção múltipla](media/qerguide-image-addmultiselectfilter.png)

Em seguida, clique em **Pesquisar** (um ícone de lupa ao lado do novo filtro). Você verá um campo de texto e várias opções, incluindo **selecionar tudo** e **inverter**. Insira um valor e clique em **Pesquisar** ao lado desse campo para pesquisar. Você também pode deixar o campo de texto vazio e clicar em **Pesquisar** para exibir até as primeiras opções do 100.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo  

![Captura de tela da adição de um filtro de consulta](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtros em nível de painel
Certos relatórios do CQD têm filtros em nível de painel adicionados a eles, facilitando a filtragem por parâmetros comuns. Esses filtros são exibidos fora das guias relatório regular e logo abaixo do filtro de produto, e eles se aplicam a todos os filtros no painel.

![Captura de tela de um filtro de painel](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtros de URL

CQD dá suporte à adição de filtros à URL. Isso facilita o compartilhamento ou a marcação de uma consulta CQD. Você pode definir parâmetros na URL, como mês de tendências, ID de locatário ou idioma. Você também pode adicionar filtros de produto ou de nível de painel à URL.
Excluir dados federados dos relatórios do CQD é útil quando você está remediando prédios gerenciados ou redes nas quais pontos de extremidade federados podem influenciar seus relatórios.

Para adicionar um filtro, acrescente o seguinte ao final da URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Exemplo  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Para adicionar um filtro em nível de painel a uma URL, esse filtro deve existir no CQD como um filtro de produto ou de nível de painel. Adicione esses filtros à URL após o mês de tendência e antes dos parâmetros de URL:

`filter/DATA_MODEL_NAME|VALUE`

Por exemplo, para aplicar um valor de filtro de produto do Microsoft Teams, adicione o seguinte:

`filter/[AllStreams].[Is%20Teams]|[True]`

Sua URL inteira teria uma aparência semelhante a esta:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Para aplicar filtros de URL com valores de seleção múltipla, separe cada valor com um caractere de pipe (|). Por exemplo:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Se você especificar um nome ou um valor inválido, o filtro de URL não será aplicado.


Você pode usar um filtro de URL para filtrar cada relatório de uma dimensão específica. Os filtros de URL mais comuns são usados para filtrar relatórios e excluir telemetria de participantes federados ou se concentrar apenas em equipes ou no Skype for Business online. Excluir dados federados dos relatórios do CQD é útil quando você está remediando prédios gerenciados ou redes nas quais pontos de extremidade federados podem influenciar seus relatórios.

| Filter         | Descrição          | Exemplo de filtro de consulta CQD      |
|----------------|----------------------|-------------------------------|
| Nenhum valor em branco   | Alguns filtros não têm a opção de filtrar valores em branco. Para filtrar valores em branco manualmente, use a expressão em branco e defina o filtro para igual ou não igual, dependendo das suas necessidades.      | Segundo nome da compilação \<\> \^ \\ s\*\$                       |
| Excluir sub-redes comuns | Sem um arquivo de construção válido para separar o gerenciamento de redes não gerenciadas, as redes domésticas serão incluídas nos relatórios. Essas sub-redes residenciais estão fora do escopo do controle de ti e podem ser rapidamente excluídas de um relatório. As sub-redes comuns, conforme definido neste artigo, são 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Segunda sub-rede \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Exibir somente dentro  | Usado para filtrar um relatório para gerenciado (interno) ou não gerenciado (externo). O modelo CQD gerenciado já está pré-configurado com esses filtros.       | Segunda interna Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Como encontrar sua ID de locatário

A ID do locatário em CQD corresponde à ID do diretório no Azure. Se não souber a ID do diretório, você pode encontrá-la no portal do Azure:

1.  Entre no portal do Microsoft Azure: <https://portal.azure.com>

2.  Selecione **Azure Active Directory**.

3.  Em **gerenciar**, selecione **Propriedades**. A ID do locatário está na caixa **ID do diretório** .

Você também pode encontrar sua ID de locatário usando o PowerShell: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Comparar o Microsoft Teams e os dados do Skype for Business CQD

Mesmo dentro da versão mais recente do CQD (cqd.teams.microsoft.com), você verá diferenças nos dados entre o Teams e o Skype for Business. Alguns motivos:
- Diferenças nos mecanismos para garantir o desempenho e a confiabilidade:
  - O Microsoft Teams tem reconexão automática e roaming rápido. O Skype for Business não.
  - O Microsoft Teams tem gerenciamento dinâmico de largura de banda. O Skype for Business não.
- Diferenças em [intervalos de endereços IP](Office-365-URLs-IP-address-ranges.md) entre o Teams e o Skype for Business. Os intervalos de IP do teams são mais recentes, o que pode causar problemas de conectividade no firewall.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Abrir o CQD a partir do portal herdado do Skype for Business

![Um ícone do logotipo do Skype for Business ](media/sfb-logo-30x30.png) **usando o portal herdado do Skype for Business**

1. Entre em sua organização do Office 365 usando uma conta de administrador e, em seguida, selecione o bloco **administrador** para abrir o centro de administração.

2. No painel esquerdo, em **centros de administração**, selecione **Microsoft Teams** para abrir o centro de administração do teams.

3. No centro de administração do Teams, selecione **portal herdado** no painel esquerdo, selecione **ferramentas**e, em seguida, selecione **painel de qualidade de chamada do Skype for Business online**.

   ![Captura de tela: selecione o painel de qualidade da chamada](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Na página que é aberta, entre com sua conta de administrador global e forneça as credenciais da conta quando for solicitado.

Após a primeira vez que você se conectar, o CQD começará a coletar e processar dados. 

> [!IMPORTANT]
> A partir de dezembro de 2019, você ainda pode acessar a versão mais antiga do CQD (cqd.lync.com), embora o portal herdado forneça um link para o CQD mais recente (cqd.teams.microsoft.com). Por fim, a versão mais antiga do CQD será descomissionada. A partir de 1 ° de julho de 2020, a versão mais antiga do CQD acessa os dados do novo CQD ( https://CQD.teams.microsoft.com) , e você não pode mais exportar dados de criação e de relatório. Um dia no final de 2020, desativaremos o antigo CQD, e você não poderá mais acessá-lo.


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
