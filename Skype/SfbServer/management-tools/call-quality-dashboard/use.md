---
title: Usar o painel de qualidade da chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Resumo: saiba como usar o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 09eb8bdae508ff9a5fe39fec67b0f440859efad0
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774701"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usar o painel de qualidade da chamada para o Skype for Business Server

**Resumo:** Saiba mais sobre como usar o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.

O painel de qualidade de chamada (CQD) permite que os profissionais de ti usem dados agregados para identificar problemas relacionados à criação de problemas de qualidade de mídia comparando estatísticas de grupos de usuários para identificar tendências e padrões. O CQD não se concentra em solucionar problemas de chamada individuais, mas para identificar problemas e soluções que se aplicam a muitos usuários.

## <a name="call-quality-dashboard-user-guide"></a>Guia do Usuário do Painel de Qualidade da Chamada

O CQD é um portal da Web para criar e organizar relatórios rapidamente com base em dados de qualidade da experiência (QoE). O CQD implanta um cubo de SSAS para agregar os dados no banco de dados métricas de QoE e permite que os administradores criem e modifiquem relatórios ou façam investigações em tempo real. Embora seja possível usar o Excel para se conectar diretamente ao cubo, o portal é otimizado para diversos fluxos de trabalho que envolvem dados de QoE. Os dados incluem:

- Dados de relatório em cache para acesso rápido
- Links profundo para páginas de relatório para compartilhamento e publicação de informações
- Edição e criação de relatórios otimizadas e metadados editáveis para descrições de relatórios.

Além disso, CQD expõe APIs da Web que dão aos usuários acesso programático aos dados do cubo para uso em painéis personalizados.

### <a name="feature-overview"></a>Visão geral do recurso

Ao visitar o painel de qualidade da chamada, você verá a seguinte tela:

![Usar CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. O "painel de resumo" é onde o contexto do "conjunto de relatórios" (à direita) pode ser encontrado.
2. Clique em "Editar" na PaneReport de resumo para definir as propriedades de nível (incluindo a altura do eixo Y).
3. O breadcrumb ajuda você a identificar sua localização atual na hierarquia de conjuntos de relatórios.
4. Os relatórios com sub-relatórios são exibidos com um link azul. Clique no link para fazer buscas detalhadas nos relatórios filho.

Mova o mouse sobre os gráficos de barras e linhas de tendências para mostrar valores detalhados. O relatório que tem o foco mostra o menu Ação: "Editar", "clonar", "excluir" e "download".

### <a name="default-reports"></a>Relatórios Padrão

Quando você acessa pela primeira vez o portal do painel de qualidade da chamada, um conjunto padrão de relatórios é criado automaticamente. Esses relatórios são, por vezes, chamados de relatórios do sistema. Você pode modificar ou excluir livremente esses relatórios ou estendê-los criando novos relatórios irmãos e filho.

No nível superior, o relatório "tendências mensais de fluxos de áudio" mostra a tendência mensal para todos os fluxos de áudio. Mova o mouse sobre as barras em um gráfico de barras para mostrar um modo de exibição mais detalhado dos dados representados pelo gráfico de barras. Clique no título do relatório de tendências mensais de fluxos de áudio para navegar até o relatório "fluxos de áudio gerenciados vs não gerenciados", em que os relatórios são divididos entre chamadas gerenciadas e não gerenciadas. As chamadas gerenciadas são aquelas feitas de dentro do firewall corporativo por conexões com fio. As chamadas não gerenciadas incluem chamadas feitas de fora do firewall corporativo e todas as chamadas feitas por Wi-Fi.

O outro relatório de nível superior é chamado de histograma de classificação de qualidade de chamada reportado pelo usuário. As classificações de qualidade da chamada são os números fornecidos pelos usuários do Skype for Business ao fim de uma chamada para indicar a qualidade da chamada. Os números de classificação variam de 1 a 5, 1 é o pior e 5 é o melhor. O histograma mostra o número de chamadas de áudio que tiveram a classificação indicada em um mês.

Clique no título de qualquer um dos relatórios para navegar em relatórios com mais filtros nos dados. Nos relatórios do sistema, cada relatório filho exibe um subconjunto dos dados disponíveis em seu relatório pai. O modelo de solução de problemas é simples: investigue qual subrelatório os dados ou a tendência em sugestão de um problema é refinado para e reduz gradualmente o espaço do problema. A capacidade de criar sub-relatórios permite que você investigue seus próprios palpites sobre a causa de tendências de dados específicas.

### <a name="create-and-edit-reports"></a>Criar e editar relatórios

Clique em "Editar" no menu Ação de um relatório para ver o editor de relatórios. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O editor de relatórios ajuda você a editar essas consultas e as opções de exibição do relatório. Ao abrir o editor de relatórios, você verá:

![Usar CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensões, medidas e filtros são escolhidos no painel esquerdo. Passe o mouse sobre um dos valores existentes para mostrar um botão "x" que permite que o valor seja removido. Clique no botão "mais" ao lado de um título para abrir a caixa de diálogo onde você pode adicionar uma nova dimensão, medida ou filtro.
2. As opções para a personalização de gráficos são exibidas na parte superior.
3. Uma visualização do relatório está disponível no Editor de Relatório. 
4. Uma descrição de relatório detalhada pode ser criada com a caixa de edição na parte inferior.

### <a name="sparklines-in-tables"></a>Minigráficos em tabelas

Quando StartDate.Month é adicionado como uma dimensão e os dados são processados como tendência na forma de tabela, gráficos de barras e minigráficos podem ser mostrados dentro das células da tabela. Mova o ponteiro do mouse sobre o gráfico de barras e os minigráficos para mostrar os valores de meses individuais.

![Usar CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Para que os gráficos de barras e os minigráficos sejam exibidos, a caixa de seleção "mostrar minigráficos" na parte superior do editor de relatório deve estar marcada. Isso seleciona a opção tendência e move o mês para baixo para ser a última dimensão, que também pode ser realizada clicando em mês e usando as setas para cima e para baixo para mover StartDate. mês para cima ou para baixo.

### <a name="settings"></a>Configurações

O menu configurações contém links para páginas úteis, como a saúde do sistema e sobre as páginas, e está localizado no canto superior direito do painel.

![Usar CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Se devem ser exibidas descrições e carimbos de data/hora em usuários individuais, essas configurações afetam somente a versão individual do painel e não modificam o conjunto de relatórios ou o que os outros usuários vêem. A limpeza do cache faz com que todas as consultas Recarreguem os dados do cubo, enquanto restaurar os padrões exclui todos os relatórios criados ou modificados pelo usuário e recria o conjunto de relatórios do sistema, o que o usuário veria ao entrar pela primeira vez.

O Link do Painel de Usuários mostra uma página onde os usuários podem visualizar outros usuários do CQD e navegar em seus relatórios. Para compartilhar um conjunto de relatórios, copie o link na barra de URL e compartilhe-o com outro usuário do CQD. Esse link é o mesmo link que outros usuários veriam na página do link do painel usuários sob o nome de usuário do usuário.

### <a name="supplying-subnet-information"></a>Fornecer informações da sub-rede

Informações adicionais podem ser reveladas se informações específicas do site forem inseridas no banco de dados de arquivo para fornecer informações de mapeamento de sub-rede para construção (por exemplo, qualidade de chamada sem fio/sem fio criando).

No mínimo, conclua as seguintes tabelas para criar esses relatórios:

- CqdBuilding
- CqdNetwork

Informações adicionais podem ser fornecidas nas tabelas CqdBuildingType e CqdBuildingOwnershipType para permitir mais filtragem e busca detalhada. 

Os dados usados para essas tabelas são definidos da seguinte maneira:

**CqdBuilding**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |Não |Chave primária da tabela CqdBuilding. |
|BuildingName |varchar(80) |Não |Nome do edifício. |
|BuildingShortName |varchar(10) |Não |Versão abreviada do nome do edifício. |
|OwnershipTypeId |int |Não |Chave estrangeira corresponde a uma das entradas na tabela CqdBuildingOwners. |
|BuildingTypeId |int |Não |Chave estrangeira corresponde a uma das entradas na tabela CqdBuildingType. |
|Liberdade |float |Sim |Latitude do edifício. |
|Longitude |float |Sim |Longitude do edifício. |
|CityName |varchar(30) |Sim |Nome da cidade onde o edifício está localizado. |
|ZipCode |varchar(25) |Sim |CEP do local do edifício. |
|CountryShortCode |varchar(2) |Sim |Códigos ISO 3166-1 alpha-2 do país onde o edifício está localizado. |
|StateProvinceCode |varchar(3) |Sim |Abreviação de três letras para o estado/província onde a construção está localizada. |
|InsideCorp |bit |Sim |Bit indica se a construção faz parte da rede corporativa. |
|BuildingOfficeType |nvarchar(150) |Sim |Descrição do tipo de escritório do edifício. |
|Região |varchar(25) |Sim |Região onde o edifício está localizado. |
|||||

**CqdNetwork**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|Rede |varchar(25) |Não |Endereço da sub-rede. |
|NetworkRange |tinyint |Sim |Máscara de sub-rede. |
|NetworkNameID |int |Sim |Mapeia opcionalmente para uma linha da tabela CqdNetworkName. |
|BuildingKey |int |Sim |Chave estrangeira corresponde a uma das entradas na tabela CqdBuilding. |
|UpdatedDate |datetime |Não |Data e hora da última atualização da entrada. |
||||||

Por padrão, essa próxima tabela tem uma entrada (0, "desconhecido").

**CqdBuildingType**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |Não |Chave primária da tabela CqdBuildingType. |
|BuildingTypeDesc |char(18) |Não |Descrição do tipo de edifício. |
|||||

Por padrão, essa próxima tabela tem uma entrada (0, "desconhecido", 0, nulo).

**CqdBuildingOwnershipType**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |Não |Chave primária da tabela CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |Não |Descrição do tipo de propriedade. |
|LeaseInd |tinyint |Sim |Índice que faz referência a outra linha da tabela CqdBuildingOwnershipType, usada para identificar edifícios com concessão. |
|Proprietário |varchar(50) |Sim |Proprietário do edifício. |
|||||

Por padrão, essa próxima tabela tem uma entrada (0, "desconhecido", 0, nulo).

**CqdBssid**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|bss |nvarchar(50) |Não |Chave primária da tabela CqdBssid. É o BSSID do ponto de acesso WiFi. |
|ess |nvarchar(50) |Sim |Informações do Controlador do Ponto de Acesso Wi-Fi. |
|phy |nvarchar(50) |Sim |Informações de phy. |
|ap |nvarchar(50) |Sim |Nome do Ponto de Acesso Wi-Fi. |
|Edifício |nvarchar(500) |Sim |O nome da construção em que o ponto de acesso WiFi está localizado. |
||||

## <a name="cqd-streams"></a>Fluxos de CQD

Um fluxo de CQD é considerado bom, ruim ou não classificado. O CQM 1.5 agora usa a seguinte definição de CQD:

- Um fluxo ruim é qualquer combinação de métricas de chamadas deficientes além do limite.
- Quando um fluxo em uma chamada é ruim, os dois fluxos da chamada são ruins. Em conferências, cada participante é contado como uma chamada exclusiva e é reportado de forma independente de todos os outros.
- Fluxos não classificados são fluxos sem métricas de qualidade (ou seja, transações sintéticas ou chamadas curtas).
- Fluxos válidos = clientes não móveis
- O classificador não pode ser modificado

**Classificador/definição de chamada ruim**

|Métrica|Limite|
|:-----|:-----|
|DegradationAvg |Maior que 1,0 (-1 MOS de rede) |
|RoundTrip |Maior que 500  |
|PacketLossRate |Maior do que 0,1 (10%) |
|JitterInterArrival |Maior que 30  |
|RatioConcealedSamplesAvg |Maior do que 0, 7 |
|||

Definição de JPDR = Definição de chamada ruim menos RatioConcealedSamplesAvg 

## <a name="where-is-callercallee"></a>Onde está o Chamador/Autor da Chamada?

O CQD não usa os campos Caller/Callee, em vez disso, ele usa "First" e "Second" porque há etapas intervenientes entre o chamador e o receptor.

 **Primeira vez** Será sempre o ponto de extremidade do servidor (por exemplo, AV MCU ou servidor de mediação) se um servidor estiver envolvido no fluxo.

 **Segundo** Será sempre o ponto de extremidade do Cliente, a menos que seja um fluxo Servidor–Servidor. 

**Exemplo de classificação Primeiro e Segundo**

|UAType do Ponto de Extremidade 1 |UUAType do Ponto de Extremidade 2 |Primeiro|Segundo|
|:-----|:-----|:-----|:-----|
|2 (AVMCU)  |4 (Skype for Business)  |Ponto de Extremidade 1 |Ponto de Extremidade 2 |
|2 (AVMCU)  |1 (mMediationServer)  |Ponto de Extremidade 2 |Ponto de Extremidade 1 |
|4 (Skype for Business) |4 (Skype for Business)  |O Chamador em MediaLine  |O Autor da Chamada em MMediaLine  |
|||||

Se os dois pontos de extremidade forem do mesmo tipo, o CQD faz a entrada do chamador primeiro e o receptor do outro. Para obter mais informações sobre nomes de ponto de extremidade, consulte [este blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).

## <a name="accounting-for-vpn"></a>Justificar a VPN

Se a solução VPN for conhecida para definir precisamente o sinalizador de VPN, tudo estará definido. Caso contrário, use um dos seguintes métodos:

- Crie um Tipo de Rede chamado VPN (preferencial), depois Associe Sub-redes de VPN a esse novo NetworkType de VPN.
- Crie um edifício chamado VPN, depois Associe Sub-redes de VPN a esse edifício. 

## <a name="query-fundamentals"></a>Fundamentos da consulta

Uma consulta bem formada contém todos estes três parâmetros: 

- Medição
- Dimensão
- Filtro

Um exemplo de uma consulta bem formada seria "Mostrar-me Fluxos Ruins [Medição] por Sub-rede [Dimensão] para o Edifício 6 [Filtro]".

## <a name="what-does-union-do"></a>O que UNION faz?

O recurso Union permite que você filtre condições com o operador AND. Há cenários em que você pode combinar várias condições de filtro para obter um resultado semelhante a uma operação ou.

Exemplo: para obter todos os fluxos de um edifício, UNION fornece uma exibição distinta do DataSet mesclado. Para usar o parâmetro UNION, insira texto comum no campo UNION nas duas condições de filtro que você deseja unir.

## <a name="default-report-breakdown"></a>Divisão padrão dos relatórios

Se a conexão Sem Fio é gerenciada internamente, você pode recriar os relatórios de conexão Sem Fio no bucket Gerenciado. 

![Divisão de relatório CQD](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processos operacionais

Revisar e corrigir os fluxos gerenciados primeiro. A qualidade nessa área deve ser de 100% dentro do seu controle e, portanto, mais fácil de corrigir.

### <a name="managed-streams"></a>Fluxos Gerenciados 

Examine e corrija os fluxos gerenciados na seguinte ordem: 

1. Servidor-Servidor 
2.  Servidor-Com Fio-Dentro
3. Com Fio-Com Fio-Dentro 

### <a name="unmanaged-streams"></a>Fluxos Não Gerenciados

Examine e corrija os fluxos não gerenciados na seguinte ordem: 

1. Servidor-Wi-Fi-Dentro
2. Servidor-Com Fio-Fora
3. Servidor-Wi_Fi-Fora
4. Com Fio-Fora-Direto
5. Com Fio-Fora-Retransmissão
6. Outros Não Gerenciados
