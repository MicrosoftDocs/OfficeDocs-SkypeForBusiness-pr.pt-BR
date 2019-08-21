---
title: Ativando e usando o Painel de Qualidade de Chamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Veja como ativar e usar o painel de qualidade de chamada do Skype for Business Online e obter relatórios resumidos de qualidade das chamadas. '
ms.openlocfilehash: cf937a159eba723ee4ac7fc2ae01aa733e57170f
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483765"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Ativar e usar o painel de qualidade da chamada para Microsoft Teams e Skype for Business Online

Saiba como configurar sua organização do Office 365 para usar o painel de qualidade da chamada para monitorar a qualidade da chamada.
  
O painel de qualidade de chamada (CQD) para Microsoft Teams e o Skype for Business Online permite que você obtenha ideias sobre a qualidade das chamadas feitas usando o Microsoft Teams e os serviços do Skype for Business. Este tópico descreve as etapas que você precisará concluir para começar a coleta de dados.
  
  
## <a name="latest-changes-and-updates"></a>Alterações e atualizações mais recentes

As alterações mais recentes no CQD são as seguintes:
  
- Inclui dados do Microsoft Teams além dos dados do Skype for Business online.
    
- Os relatórios de resumo incluem um filtro de produto para selecionar todos os dados, dados do Microsoft Teams ou dados do Skype for Business online.

- A lógica de classificação de qualidade do fluxo de vídeo e VBSS foi atualizada. Consulte [classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md) para obter as definições mais recentes do classificador.

Consulte este artigo para obter uma lista de [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Informações sobre atualizações e alterações no painel podem ser encontradas clicando no link nas **boas notícias!** faixa quando ele é exibido no painel.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Ativar relatórios de resumo do Microsoft Call Quality Dashboard (CQD)

Antes de começar a usar o CQD, você precisará ativá-lo para a sua organização do Office 365.

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**
 
1. Entre em sua organização do Office 365 usando a conta de administrador do Microsoft Teams Service e, em seguida, selecione o bloco do **administrador** para abrir o centro de administração.
    
2. No painel esquerdo, em **centros de administração**, selecione **Microsoft Teams** para abrir o centro de administração do Microsoft Teams.
    
3. No centro de administração do Microsoft Teams, selecione **painel de qualidade de chamada** no painel esquerdo.
    
  
4. Na página que é aberta, entre com sua conta de administrador global ou com a conta de administrador do Microsoft Teams Service e forneça as credenciais da conta quando for solicitado.
    
     ![Captura de tela mostrando o prompt credenciais](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Depois de entrar, uma vez ativada, o CQD começará a coletar e processar dados.  
> [!NOTE]
> Pode levar algumas horas para processar dados suficientes para exibir resultados significativos nos relatórios. 

![Um ícone mostrando o logotipo](media/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**
 
1. Entre em sua organização do Office 365 usando uma conta de administrador e, em seguida, selecione o bloco **administrador** para abrir o centro de administração.
    
2. No painel esquerdo, em **centros de administração**, selecione **Skype for Business** para abrir o centro de administração do Skype for Business.
    
3. No centro de administração do Skype for Business, selecione **ferramentas** no painel esquerdo e, em seguida, selecione **painel de qualidade de chamada do Skype for Business online**.
    
     ![Captura de tela mostrando a seleção do painel de qualidade de chamada](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Na página que é aberta, entre com sua conta de administrador global e forneça as credenciais da conta quando for solicitado.
    
     ![Captura de tela mostrando o prompt credenciais](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Depois de entrar, uma vez ativada, o CQD começará a coletar e processar dados.


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Recursos do painel de qualidade de chamada do Microsoft Teams e do Skype for Business Online 
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD relatórios de resumo fornecem um subconjunto de recursos planejados para relatórios detalhados. As diferenças entre as duas edições são resumidas aqui:
  
|**Recurso**|**Relatórios de resumo**|**Relatórios detalhados**|
|:-----|:-----|:-----|
|Métrica de compartilhamento de aplicativos  <br/> |Não  <br/> |Sim  <br/> |
|Suporte a informações de prédio do cliente  <br/> |Sim  <br/> |Sim  <br/> |
|Suporte a informações de ponto de extremidade do cliente  <br/> |Somente no cqd.teams.microsoft.com  <br/> |Somente no cqd.teams.microsoft.com  <br/> |
|Suporte para análise detalhada  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de confiabilidade de mídia  <br/> |Não  <br/> |Sim  <br/> |
|Relatórios prontos da caixa  <br/> |Sim  <br/> |Sim  <br/> |
|Relatórios de visão geral  <br/> |Sim  <br/> |Sim  <br/> |
|Conjunto de relatórios por usuário  <br/> |Não  <br/> |Sim  <br/> |
|Personalização do conjunto de relatórios (adicionar, excluir, modificar relatórios)  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de compartilhamento de tela com base em vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Quantidade de dados disponíveis  <br/> |Últimos seis meses  <br/> |Últimos seis meses  <br/> |
|Dados do Microsoft Teams  <br/> |Sim  <br/> |Sim  <br/> |
   
### <a name="out-of-the-box-reports"></a>Relatórios prontos da caixa

Ambas as edições do CQD fornecem uma experiência inicial, oferecendo métricas de qualidade de chamada sem a necessidade de criar novos relatórios. Depois que os dados são processados no back-end, você pode começar a ver os dados de qualidade da chamada nos relatórios.
  
### <a name="overview-reports"></a>Relatórios de visão geral

Ambas as edições do CQD fornecem um ponto de entrada de alto nível para as informações gerais de qualidade da chamada, mas a maneira como as informações são apresentadas em relatórios de resumo é diferente da dos relatórios detalhados.
  
Os relatórios resumidos fornecem um modo de exibição de relatório de página com guias simplificado que permite aos usuários navegar e entender rapidamente o status e as tendências gerais de qualidade das chamadas.
  
As quatro guias incluem:
  
- **Qualidade de chamadas gerais** – fornece informações sobre todos os fluxos, que é uma agregação de fluxos de cliente de servidor e cliente-fluxo de cliente, além de fluxos de cliente/cliente e cliente separados, na forma de tendências mensal e diária.
    
- **Servidor-cliente** -fornece detalhes adicionais para os fluxos entre pontos de extremidade do servidor e do cliente.
    
- **Cliente-cliente** -fornece detalhes adicionais para os fluxos entre dois pontos de extremidade do cliente.
    
- **SLA de qualidade de voz** -fornece informações sobre chamadas incluídas no SLA de qualidade de voz do Skype for Business online.
    
### <a name="overall-call-quality-tab"></a>Guia qualidade geral da chamada

Use os dados desta guia para avaliar o status e as tendências da qualidade da chamada olhando para os números de fluxo e percentuais insatisfatórios. A legenda no canto superior direito mostra quais elementos visuais e de cor representam essas métricas.
  
![Captura de tela mostrando a guia qualidade da chamada](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Os fluxos são classificados em três grupos: satisfatório, fraco e não classificados. Também são calculados valores de *baixa qualidade* que proporcionam a taxa de fluxos classificados ** como deficientes para a contagem total de fluxos classificados. Como *baixa% = fluxos ruins/(fluxos de má qualidade + bom fluxo) * 100* , isso faz com que os *% deficientes* não afetados pela presença com vários fluxos não *classificados* . Para o que é usado para classificar um fluxo como ruim ou bom, consulte [classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md).
  
Use a escala à esquerda para medir os valores de contagem de fluxo.
  
![Captura de tela mostrando valores de contagem de fluxo](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use a escala à direita para medir os valores de baixa%.
  
![Captura de tela mostrando valores% deficientes](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Você também pode obter os valores numéricos reais passando o mouse sobre uma barra.
  
> [!NOTE]
> O exemplo a seguir é de um conjunto de dados de exemplo muito pequeno, e os valores não são realistas para uma implantação real. 
  
![Captura de tela mostrando o uso do mouse para acessar dados](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
O volume de fluxo geral é um fator importante na determinação da importância das porcentagens insatisfatórias calculadas. Quanto menor for o volume de fluxos gerais, menos confiável será a porcentagem dos valores de porcentagem deficientes reportados.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Guias servidor-cliente e cliente-cliente

Essas duas guias fornecem detalhes adicionais para os fluxos que ocorreram em seus cenários de ponto de extremidade a ponto de extremidade. A guia servidor-cliente tem quatro seções recolhíveis, representando quatro cenários em que os fluxos de mídia fluiriam.
  
- Com fio interno
    
- Com fio externo
    
- Sem fio dentro
    
- Sem fio externo

Da mesma forma, a guia cliente/cliente tem cinco seções recolhíveis:

- Com fio dentro de dentro

- Com fio interno-cabeado externo

- Com fio externo-conectado fora

- Com fio interno-WiFi dentro

- Com fio interno-WiFi externo
    
    
#### <a name="inside-test"></a>Teste interno

Durante o processamento, o back-end do CQD classifica um fluxo como *interno* ou *externo* usando as informações de construção, se houver. Os pontos de extremidade de cada fluxo estão associados a um endereço de sub-rede. Se a sub-rede estiver na lista das sub-redes marcadas InsideCorp nas informações de construção carregadas, ela será considerada *dentro*. Se as informações de construção ainda não tiverem sido carregadas, então dentro do teste sempre classificará os fluxos como *externos*. Observe que, dentro do teste para servidor-cliente, o cenário só considera o ponto de extremidade do cliente. Como os servidores estão sempre fora da perspectiva de um usuário, isso não é contabilizado no teste.
  
#### <a name="wired-vs-wifi"></a>Com fio versus WiFi

Como os nomes indicam, esse é um critério de classificação com base no tipo de conexões de cliente. Novamente, o servidor é sempre conectado e não está incluído no cálculo.
  
> [!NOTE]
> Dado um fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede WiFi, ele será classificado como WiFi no CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selecionando dados do produto para ver nos relatórios
<a name="BKMKProductFilter"></a>

Nos relatórios avançados de resumo e de localização, você pode usar o menu suspenso **filtro do produto** para mostrar todos os dados do produto, somente dados do Microsoft Teams ou somente dados do Skype for Business online.
  
![Captura de tela mostrando as opções de controle de filtro do produto](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Em relatórios detalhados, você pode usar a dimensão **is Teams** para filtrar os dados para o Microsoft Teams ou dados do Skype for Business online como parte da definição do relatório.
  
## <a name="upload-tenant-data-information"></a>Carregar informações de dados do locatário
<a name="BKMKTenantDataInformationUpload"></a>

O painel relatórios de resumo CQD inclui uma página de **carregamento de dados** de locatários, acessada selecionando **carregar dados do locatário** no menu configurações no canto superior direito. Esta página é usada para os administradores carregarem suas próprias informações, como o mapeamento de endereços IP e informações geográficas, o mapeamento de cada AP sem fio e seu endereço MAC, o mapeamento do ponto de extremidade para a marca/modelo/tipo de ponto de extremidade, etc.
  
![Captura de tela mostrando o painel de qualidade da chamada](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Na página de **carregamento de dados do locatário** , use o menu suspenso para escolher um tipo de arquivo de dados para carregar. O tipo de dados arquivo denota o conteúdo do arquivo (por exemplo, "edifício" refere-se ao mapeamento do endereço IP e à criação, bem como outras informações geográficas, "ponto de extremidade" refere-se ao mapeamento do nome do ponto de extremidade para tipo/modelo/tipo de ponto de extremidade... informações). Atualmente, damos suporte ao carregamento de tipos de dados "edifício" e "ponto de extremidade" para cqd.teams.microsoft.com (no estágio de visualização e ainda não disponível oficialmente), cqd.lync.com só permite carregar o tipo de dados "edifício". Mais alguns tipos de dados serão adicionados com versões subsequentes.
    
2. Depois de selecionar o tipo de dados do arquivo, clique em **procurar** para escolher um arquivo de dados.
    
   - O arquivo de dados deve ser um arquivo. TSV (valores separados por tabulação) ou um arquivo. csv (valor separado por vírgula). Se estiver usando um arquivo. csv, qualquer campo que contenha vírgula deve estar entre aspas ou ter a vírgula removida. Por exemplo, se o seu nome de edifício for NY, NY, no arquivo. csv, ele deverá ser inserido como "NY, NY".
    
   - O arquivo de dados não deve ter tamanho maior do que 50 MB.

   - Os arquivos carregados no cqd.teams.microsoft.com têm um limite de linha expandido de 1 milhão para manter o desempenho da consulta rápido. Também podemos impor esse limite ao cqd.lync.com.
    
   - Para cada arquivo de dados, cada coluna no arquivo deve corresponder a um tipo de dados predefinido, discutido posteriormente neste tópico.
    
3. Depois de selecionar um arquivo de dados, especifique **data de início** e, opcionalmente, **especifique uma data de término**.
    
4. Depois de selecionar **data de início**, selecione **carregar** para carregar o arquivo para o servidor do CQD.
    
    Antes de o arquivo ser carregado, ele é validado primeiro. Uma vez validada, ela é armazenada em um blob do Azure. Se ocorrer uma falha na validação ou o arquivo não for armazenado em um blob do Azure, uma mensagem de erro será exibida solicitando uma correção para o arquivo. A imagem a seguir mostra um erro que ocorre quando o número de colunas no arquivo de dados está incorreto.
    
     ![Captura de tela mostrando um erro de validação de carregamento](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se não ocorrerem erros durante a validação, o carregamento do arquivo será bem-sucedido. Em seguida, você pode ver o arquivo de dados carregado na tabela **My uploads** , que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.
    
    Cada registro mostra um arquivo de dados do locatário carregado, com o tipo de arquivo, a hora da última atualização, o período de tempo, a descrição, um ícone de remoção e um ícone de download. Para remover um arquivo, selecione o ícone de lixeira na tabela. Para baixar um arquivo, selecione o ícone baixar na coluna **baixar** da tabela.
    
     ![Captura de tela mostrando a tabela My uploads](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. Observe que, se você optar por usar vários arquivos de dados de construção ou vários arquivos de dados de ponto de extremidade, a velocidade da operação de alguns relatórios será mais lenta.

### <a name="tenant-data-file-format-and-structure"></a>Estrutura e formato de arquivo de dados do locatário
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>Criando arquivo de dados
O CQD usa a construção de arquivo de dados primeiramente, derivando que a coluna de sub-rede expanda a coluna Network + NetworkRange e, em seguida, ingressando na coluna subnet na primeira sub-rede/segunda sub-rede do registro de chamada, na coluna de construção/cidade/país/região... às. O formato do arquivo de dados que você carregar deve atender ao seguinte para passar na verificação de validação antes de carregar.
  
- O arquivo deve ser um arquivo. TSV, o que significa que, em cada linha, as colunas são separadas por uma TABULAção ou um arquivo. csv com cada coluna separada por uma vírgula.
    
- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Isso significa que a primeira linha do arquivo de dados deve ser dados reais, e não cabeçalhos como "rede" etc.
    
- Para cada coluna, o tipo de dados só pode ser String, Number ou bool. Se for núm, o valor deve ser um valor numérico; Se for bool, o valor deve ser 0 ou 1.
    
- Para cada coluna, se o tipo de dados for String, os dados podem ficar vazios (mas ainda devem ser separados por um delimitador adequado (ou seja, uma Tabulação ou vírgula). Isso apenas atribui um valor de cadeia de caracteres vazia a um campo.
    
- Deve haver 14 colunas para cada linha, cada coluna deve ter o tipo de dados a seguir, e as colunas devem estar na ordem listada na seguinte tabela:
    
|**Nome da coluna**|**Tipo de dados**|**Exemplo**|
|:-----|:-----|:-----|
|Rede  <br/> |Cadeia de caracteres  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |Cadeia de caracteres  <br/> |EUA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Número  <br/> |26  <br/> |
|BuildingName  <br/> |Cadeia de caracteres  <br/> |SEATTLE-SEA-1  <br/> |
|Propriedadetype  <br/> |Cadeia de caracteres  <br/> |Contoso.com  <br/> |
|Buildingtype  <br/> |Cadeia de caracteres  <br/> |Terminações  <br/> |
|BuildingOfficeType  <br/> |Cadeia de caracteres  <br/> |Engineer  <br/> |
|Cidade  <br/> |Cadeia de caracteres  <br/> |Seattle  <br/> |
|ZipCode  <br/> |Cadeia de caracteres  <br/> |98001  <br/> |
|País  <br/> |Cadeia de caracteres  <br/> |Junte  <br/> |
|Estado  <br/> |Cadeia de caracteres  <br/> |WA  <br/> |
|Região  <br/> |Cadeia de caracteres  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar um Supernet (combinação de várias sub-redes com um único prefixo de roteamento). Todos os novos carregamentos de construção serão verificados em busca de intervalos sobrepostos. Se você já carregou um arquivo de construção, baixe o arquivo atual e carregue-o novamente para identificar se há sobreposições e corrigir o problema antes de carregá-lo novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar em mapeamentos errados de sub-redes para prédios nos relatórios. Algumas implementações de VPN não reportam precisamente as informações de sub-rede. É recomendável que, ao adicionar uma sub-rede VPN ao arquivo de construção, em vez de uma entrada para a sub-rede, as entradas separadas sejam adicionadas para cada endereço na sub-rede VPN como uma rede de 32 bits separada. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive. 

### <a name="endpoint-data-file"></a>Arquivo de dados de ponto de extremidade
O CQD usa o arquivo de dados de ponto de extremidade ao ingressar na coluna EndpointName à primeira coluna nome do ponto de extremidade do cliente do registro/segundo nome do ponto de extremidade do cliente para mostrar informações de tipo/modelo/tipo de ponto de extremidade O formato do arquivo de dados que você carregar deve atender ao seguinte para passar na verificação de validação antes de carregar.

- O arquivo deve ser um arquivo. TSV, o que significa que, em cada linha, as colunas são separadas por uma TABULAção ou um arquivo. csv com cada coluna separada por uma vírgula.

- O conteúdo do arquivo de dados não inclui cabeçalhos de tabela. Isso significa que a primeira linha do arquivo de dados deve ser dados reais, e não cabeçalhos como "EndpointName," etc.

- Para cada coluna, o tipo de dados só pode ser cadeia de caracteres e ele não deve ter mais de 64 caracteres, o que é o comprimento máximo permitido.

- Para cada coluna, os dados podem ficar vazios (mas ainda devem ser separados por um delimitador adequado (ou seja, uma Tabulação ou vírgula). Isso apenas atribui um valor de cadeia de caracteres vazia a um campo.

- Deve haver 7 colunas para cada linha, e as colunas devem estar na ordem listada na tabela a seguir.

- EndpointName deve ser exclusivo o carregamento também falhará devido a uma linha duplicada, pois isso causará a junção incorreta.

-  EndpointLabel1, EndpointLabel2, EndpointLable3 são rótulos personalizáveis pelo usuário, eles podem ser cadeias de caracteres vazias ou valores que os usuários preferem, como "departamento de ti designado 2018 laptop", "marca do ativo 5678"... etc.

|**Nome da coluna**|**Tipo de dados**|**Exemplo**|
|:-----|:-----|:-----|
|EndpointName  <br/> |Cadeia de caracteres  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |Cadeia de caracteres  <br/> |Fabrikam Inc  <br/> |
|EndpointModel  <br/> |Cadeia de caracteres  <br/> |Fabrikam modelo 123  <br/> |
|EndpointType   <br/> |Cadeia de caracteres  <br/> |Laptop  <br/> |
|EndpointLabel1  <br/> |Cadeia de caracteres  <br/> |Ele designou 2018 laptop  <br/> |
|EndpointLabel2  <br/> |Cadeia de caracteres  <br/> |Marca de ativos 5678  <br/> |
|EndpointLabel3  <br/> |Cadeia de caracteres  <br/> |Comprar 2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>Selecionar o tipo de mídia em relatórios detalhados
<a name="BKMKMediaType"></a>

Os relatórios detalhados dão suporte à análise da confiabilidade de qualidade e mídia para tipos de mídia de compartilhamento de tela de áudio, vídeo, compartilhamento de aplicativos e com base em vídeo. As dimensões, medidas e filtros que são específicos para um único tipo de mídia têm "áudio", "vídeo", "compartilhamento" ou "VBSS" como prefixo.
  
![Captura de tela mostrando dimensões de painel de qualidade de chamada.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Se você quiser exibir as dimensões e medidas para um único tipo de mídia, a nova dimensão e o filtro de MediaType podem ser necessários. Por exemplo, para ter um relatório que mostra o número total de sessões em diferentes tipos de mídia, inclua a dimensão MediaType.
  
![Captura de tela mostrando a contagem total de fluxos do painel de qualidade da chamada.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Tópicos relacionados
[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a análise de chamadas para solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
