---
title: Usar o Painel de Qualidade de Chamada para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 'Resumo: Saiba como usar o Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 5647622a04cbe449f426ae38b7d207fcbe2858e9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398825"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>Usar o Painel de Qualidade de Chamada para Skype for Business Server

**Resumo:** Saiba como usar o Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.

O Painel de Qualidade de Chamada (CQD) permite que os profissionais de IT usem dados agregados para identificar problemas de criação de problemas de qualidade de mídia comparando estatísticas para grupos de usuários para identificar tendências e padrões. O CQD não se concentra na solução de problemas de chamada individuais, mas na identificação de problemas e soluções que se aplicam a muitos usuários.

## <a name="call-quality-dashboard-user-guide"></a>Guia do usuário do Painel de Qualidade de Chamada

O CQD é um portal da Web para criar e organizar relatórios rapidamente com base nos dados de QoE (Qualidade da Experiência). O CQD implanta um cubo SSAS para agregar os dados no banco de dados de Métricas de QoE e permite aos administradores criar e modificar relatórios ou fazer investigações em tempo real. Embora seja possível usar o Excel para se conectar diretamente ao cubo, o portal é otimizado para vários fluxos de trabalho envolvendo dados de QoE. Os dados incluem:

- Dados de relatório armazenados em cache para acesso rápido
- Links profundos para relatar páginas para compartilhamento e publicação de informações
- Edição e criação de relatório simplificados e metadados editáveis para descrições de relatório.

Além disso, o CQD expõe APIs da Web que dão aos usuários acesso programático aos dados do cubo para uso em painéis personalizados.

### <a name="feature-overview"></a>Visão geral dos Recursos

Ao visitar o Painel de Qualidade de Chamada, você verá a seguinte tela:

![Use CQD.](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. O "Painel de Resumo" é onde o contexto do "Conjunto de Relatório" (à direita) pode ser encontrado.
2. Clique em "Editar" no Painel de ResumoReport para definir propriedades de nível (incluindo a altura do eixo Y).
3. O Breadcrumb ajuda você a identificar sua localização atual dentro da hierarquia de conjunto de relatório.
4. Relatórios com sub-relatórios são mostrados com um link azul. Clique no link para detalhar os relatórios filho.

Mova o mouse sobre os gráficos de barras e linhas de tendência para mostrar valores detalhados. O relatório que tem foco mostra o menu de ação: "Edit", "Clone", "Delete" e "Download".

### <a name="default-reports"></a>Relatórios padrão

Quando você acessa pela primeira vez o portal do Painel de Qualidade de Chamada, um conjunto padrão de relatórios é criado automaticamente. Esses relatórios às vezes são chamados de relatórios do sistema. Você pode modificar ou excluir esses relatórios livremente ou ampliá-los criando novos relatórios irmãos e filhos.

No nível superior, o relatório "Audio Fluxos Tendência Mensal" mostra a tendência mensal para todos os fluxos de áudio. Mova o mouse sobre as barras em um gráfico de barras para mostrar uma exibição mais detalhada dos dados representados pelo gráfico de barras. Clique no título do relatório de tendência mensal de áudio Fluxos para navegar até o relatório "Managed vs Unmanaged Audio Fluxos", onde os relatórios são divididos entre chamadas gerenciadas e não gerenciadas. Chamadas gerenciadas são chamadas feitas de dentro do firewall corporativo por conexões com fio. As chamadas não realizadas incluem chamadas feitas de fora do firewall corporativo e todas as chamadas feitas por Wi-Fi.

O outro relatório de nível superior é chamado de "Histograma de classificação de qualidade de chamada relatado pelo usuário". Classificações de Qualidade de Chamada são os números Skype for Business usuários no final de uma chamada para indicar a qualidade da chamada. Os números de classificação variam de 1 a 5, 1 é o pior e 5 é o melhor. O histograma mostra o número de chamadas de áudio que tiveram a classificação indicada em um mês.

Clique no título de qualquer um dos relatórios para navegar em relatórios com mais filtros nos dados. Nos relatórios do sistema, cada relatório filho exibe um subconjunto dos dados disponíveis em seu relatório pai. O modelo de solução de problemas é simples: investigar a qual sub-re-porte os dados ou tendência sugerindo um problema está limitado e restringir gradualmente o espaço do problema. A capacidade de criar sub-reportes permite que você investigue suas próprias suposições sobre a causa das tendências de dados específicas.

### <a name="create-and-edit-reports"></a>Criar e editar relatórios

Clique em "Editar" no menu ação de um relatório para ver o Editor de Relatório. Cada relatório é respaldado por uma consulta no cubo. Um relatório é uma visualização dos dados retornados por sua consulta. O Editor de Relatório ajuda você a editar essas consultas e as opções de exibição do relatório. Ao abrir o Editor de Relatório, você verá:

![Use CQD.](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. Dimensões, medidas e filtros são escolhidos no painel esquerdo. Passe o mouse sobre um dos valores existentes para mostrar um botão "x" que permite que o valor seja removido. Clique no botão "mais" ao lado de um título para abrir a caixa de diálogo onde você pode adicionar uma nova dimensão, medida ou filtro.
2. As opções de personalização do gráfico são exibidas na parte superior.
3. Uma visualização do relatório está disponível no Editor de Relatório.
4. Uma descrição detalhada do relatório pode ser criada com a caixa de edição na parte inferior.

### <a name="sparklines-in-tables"></a>Sparklines in Tables

Quando StartDate.Month é adicionado como uma dimensão e os dados são renderizados como uma tendência no formato de tabela, gráficos de barras e sparklines podem ser mostrados dentro das células da tabela. Mova o ponteiro do mouse sobre o gráfico de barras e os sparklines para mostrar os valores de meses individuais.

![Use CQD.](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

Para que os gráficos de barras e os sparklines apareçam, a caixa de seleção "Mostrar sparklines" na parte superior do Editor de Relatório deve ser verificada. Isso seleciona a opção Tendência e move Mês para baixo para ser a última dimensão, que também pode ser realizada clicando em Mês e usando as setas para cima e para baixo para mover StartDate.Month para cima ou para baixo.

### <a name="settings"></a>Settings

O menu configurações contém links para páginas úteis, como as páginas Sobre e Saúde do Sistema, e está localizado no canto superior direito do painel.

![Use CQD.](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

Se para mostrar descrições e carimbos de data/hora, essas configurações só afetam a versão individual do painel e não modificam o conjunto de relatório ou o que outros usuários veem. Limpar o cache faz com que todas as consultas recarregem seus dados do cubo, enquanto a restauração de padrões exclui todos os relatórios criados pelo usuário ou modificados e recria o conjunto de relatórios do sistema — o que um usuário verá quando fizer logoff pela primeira vez.

O Link do Painel de Usuários mostra uma página em que os usuários podem exibir outros usuários do CQD e procurar seus relatórios. Para compartilhar um conjunto de relatório, copie o link na barra de URL e compartilhe-o com outro usuário CQD. Esse link é o mesmo link que outros usuários veriam na página Link do Painel de Usuários sob o nome de usuário do usuário.

### <a name="supplying-subnet-information"></a>Fornecendo informações de sub-rede

Informações adicionais podem ser reveladas se informações específicas do site são inseridas no banco de dados De arquivo morto para fornecer informações de mapeamento de sub-rede para construção (por exemplo, qualidade de chamada com fio/sem fio criando).

No mínimo, conclua as tabelas a seguir para criar esses relatórios:

- CqdBuilding
- CqdNetwork

Informações adicionais podem ser fornecidas nas tabelas CqdBuildingType e CqdBuildingOwnershipType para permitir mais filtragem e detalhamento.

Os dados usados para essas tabelas são definidos da seguinte forma:

**CqdBuilding**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |Não |Chave primária para a tabela CqdBuilding. |
|BuildingName |varchar(80) |Não |Nome do edifício. |
|BuildingShortName |varchar(10) |Não |Versão mais curta do nome do edifício. |
|OwnershipTypeId |int |Não |Chave estrangeira, corresponde a uma das entradas na tabela CqdBuildingOwners. |
|BuildingTypeId |int |Não |Chave estrangeira, corresponde a uma das entradas na tabela CqdBuildingType. |
|Latitude |flutuação |Sim |Latitude do edifício. |
|Longitude |flutuação |Sim |Longitude do edifício. |
|CityName |varchar(30) |Sim |Nome da cidade onde o edifício está localizado. |
|ZipCode |varchar(25) |Sim |CEP onde o edifício está localizado. |
|CountryShortCode |varchar(2) |Sim |Códigos alfa-2 iso 3166-1 para o país onde o edifício está localizado. |
|StateProvinceCode |varchar(3) |Sim |Abreviação de três letras para o Estado/Província onde o edifício está localizado. |
|InsideCorp |bit |Sim |Bit indica se o edifício faz parte da rede corporativa. |
|BuildingOfficeType |nvarchar(150) |Sim |Descrição do tipo de escritório de construção. |
|Região |varchar(25) |Sim |Região onde o edifício está localizado. |


**CqdNetwork**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|Rede |varchar(25) |Não |Endereço de sub-rede. |
|NetworkRange |tinyint |Sim |Máscara de sub-rede. |
|NetworkNameID |int |Sim |Opcionalmente, mapeia para uma linha na tabela CqdNetworkName. |
|BuildingKey |int |Sim |Chave estrangeira, corresponde a uma das entradas na tabela CqdBuilding. |
|UpdatedDate |datetime |Não |Datetime for when the entry was last updated. |


Por padrão, esta próxima tabela tem uma entrada (0, 'Unknown').

**CqdBuildingType**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |Não |Chave primária para a tabela CqdBuildingType. |
|BuildingTypeDesc |char(18) |Não |Descrição do tipo de construção. |


Por padrão, esta próxima tabela tem uma entrada (0, 'Unknown', 0, null).

**CqdBuildingOwnershipType**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |Não |Chave primária para a tabela CqdBuildingOwnershipType. |
|OwnershipTypeDesc |varchar(25) |Não |Descrição do tipo de propriedade. |
|LeaseInd |tinyint |Sim |Index fazendo referência a outra linha na tabela CqdBuildingOwnershipType, usada para identificar edifícios arrendados. |
|Proprietário |varchar(50) |Sim |Proprietário do edifício. |


Por padrão, esta próxima tabela tem uma entrada (0, 'Unknown', 0, null).

**CqdBssid**

|Coluna|Tipo de dados|Permitir Nulos?|Detalhes|
|:-----|:-----|:-----|:-----|
|bss |nvarchar (50) |Não |Chave primária para a tabela CqdBssid. É o BSSID do Ponto de Acesso WiFi. |
|ess |nvarchar (50) |Sim |Informações do Controlador de Ponto de Acesso Wifi. |
|phy |nvarchar (50) |Sim |Informações de phy. |
|ap |nvarchar (50) |Sim |Nome do Ponto de Acesso Wifi. |
|Construção |nvarchar(500) |Sim |O Nome da Construção em que o Ponto de Acesso WiFi está localizado. |


## <a name="cqd-streams"></a>CQD Fluxos

Um fluxo CQD é considerado bom, ruim ou não classificado. O CQM 1.5 agora usa a seguinte definição de CQD:

- Um fluxo ruim é qualquer combinação das métricas de chamada ruins além do limite.
- Quando um fluxo em uma chamada é ruim, ambos os fluxos da chamada são sinalizados como ruins. Em conferências, cada participante é contado como uma chamada exclusiva e é relatado independentemente de todos os outros.
- Fluxos não classificados são fluxos sem métricas de qualidade (ou seja, Transações Sintéticas ou chamadas curtas).
- Válido Fluxos = clientes não móveis
- Classificador não pode ser modificado

**Definição/classificador de chamada ruim**

|Indicador|Limite|
|:-----|:-----|
|DegradationAvg |Maior que 1,0 (-1 MOS de rede) |
|RoundTrip |Maior que 500 |
|PacketLossRate |Maior que 0,1 (10%) |
|JitterInterArrival |Maior que 30 |
|RatioConcealedSamplesAvg |Maior que 0,07 |


Definição JPDR = Definição de chamada ruim menos RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>Onde está Chamador/Chamador?

O CQD não usa campos Chamador/Chamador, em vez disso, usa "First" e "Second" porque há etapas intermediárias entre o chamador e o chamador.

 **Primeiro** Sempre será o ponto de extremidade servidor (por exemplo, AV MCU ou Servidor de Mediação) se um Servidor estiver envolvido no fluxo.

 **Segundo** Sempre será o ponto de extremidade Cliente, a menos que seja um Server-Server stream.

**Exemplo de primeira e segunda classificação**

|Endpoint 1 UAType|Endpoint 2 UUAType|Primeiro|Segundo|
|:-----|:-----|:-----|:-----|
|2 (AVMCU) |4 (Skype for Business) |Ponto de extremidade 1 |Ponto de extremidade 2 |
|2 (AVMCU) |1 (mMediationServer) |Ponto de extremidade 2 |Ponto de extremidade 1 |
|4 (Skype for Business) |4 (Skype for Business) |O chamador em MediaLine |O Chamador no MMediaLine |


Se ambos os pontos de extremidade são do mesmo tipo, o CQD torna a entrada do Chamador primeiro e a segunda chamada. Para obter mais informações sobre nomes de pontos de extremidade, consulte [este blog](/archive/blogs/jenstr/call-quality-dashboard-tips-and-tricks).

## <a name="accounting-for-vpn"></a>Contabilidade para VPN

Se a solução VPN for conhecida por definir com precisão o sinalizador VPN, você está definido. Caso contrário, use um dos seguintes métodos:

- Crie um Tipo de Rede chamado VPN (preferencial) e associe sub-redes VPN a este novo NetworkType VPN.
- Crie um edifício chamado VPN e associe sub-redes VPN a esse edifício.

## <a name="query-fundamentals"></a>Fundamentos da consulta

Uma consulta bem formada contém todos os três parâmetros:

- Medida
- Dimensão
- Filter

Um exemplo de uma consulta bem formada seria "Show me Poor Fluxos [Measurement] by Subnet [Dimension] for Building 6 [Filter]".

## <a name="what-does-union-do"></a>O que a UNION faz?

A União permite filtrar as condições com o operador AND. Há cenários em que você pode combinar várias condições de Filtro para obter um resultado semelhante a uma operação or.

Exemplo: para obter todos os fluxos de um edifício, o UNION fornece uma exibição distinta do conjuntos de dados mesclados. Para usar o UNION, insira texto comum no campo UNION nas duas condições de filtro que você deseja UNION.

## <a name="default-report-breakdown"></a>Divisão de relatório padrão

Se o Wireless for gerenciado internamente, você poderá recriar os relatórios sem fio no bucket gerenciado.

![CQD Report Breakdown.](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>Processos Operacionais

Revisar e remediar o managed Fluxos primeiro. A qualidade nessa área deve estar 100% dentro do seu controle e, portanto, mais fácil de ser remediada.

### <a name="managed-streams"></a>Gerenciada Fluxos

Revise e remediar fluxos gerenciados na seguinte ordem:

1. Server-Server
2. Server-Wired-Inside
3. Wired-Wired-Inside

### <a name="unmanaged-streams"></a>Sem gestão Fluxos

Revise e remedia fluxos nãomanejados na seguinte ordem:

1. Server-Wifi-Inside
2. Server-Wired-Outside
3. Server-Wifi-Outside
4. Wired-Outside-Direct
5. Retransmissão com fio externo
6. Outros Não-amanados