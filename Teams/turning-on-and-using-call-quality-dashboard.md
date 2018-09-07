---
title: Ativando e usando o Painel de Qualidade de Chamadas
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: 'Consulte como ativar e usar o Skype para Business Online chamada qualidade Dashboard e obter relatórios de resumo de qualidade de chamadas. '
ms.openlocfilehash: 4e6ef7fc8358d75c5043ec8cc34615db0a4dfe23
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23870481"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Ativando e usando o painel de controle de qualidade de chamada para Teams da Microsoft e Skype para Business Online

Aprenda a configurar sua organização do Office 365 para usar o painel de controle de qualidade de chamada para monitorar a qualidade da chamada.
  
O painel de qualidade de chamada (CQD) for Microsoft Teams e Skype para Business Online permite que você adquira ideias sobre a qualidade das chamadas feitas usando o Microsoft Teams e Skype para serviços corporativos. Este tópico descreve as etapas que você precisará concluir para iniciar a coleta de dados.
  
> [!NOTE]
> O CQD detalhada relatórios estão atualmente disponíveis como Tech Preview, mas disponível para todos os clientes. 
  
## <a name="latest-changes-and-updates"></a>As alterações mais recentes e atualizações

As alterações mais recentes para CQD são:
  
- Inclui os dados do Microsoft Teams além do Skype para dados corporativos on-line.
    
- Relatórios de resumo incluem um filtro de produto para selecionar todos os dados, os dados de Teams da Microsoft ou Skype para dados corporativos on-line.

- Lógica de classificação de qualidade stream de vídeo e VBSS foi atualizada. Consulte a [Classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md) para as definições de classificador mais recentes.

Consulte este artigo para obter uma lista de [dimensões e medidas disponíveis no painel de controle de qualidade de chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
> [!NOTE]
> Informações sobre as atualizações e alterações ao painel podem ser encontradas clicando no link do **boa notícia!** Banner quando ele é exibido no painel.
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>Ativar os relatórios de resumo de painel (CQD) de qualidade de chamada da Microsoft

Antes de começar a usar o CQD, você precisará ativá-lo para sua organização do Office 365.
 
![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
 
1. Entrar em sua organização do Office 365 usando uma conta de administrador e selecione os blocos de **administrador** para abrir o Centro de administração.
    
2. No painel esquerdo, em **Administração centrais**, selecione **Skype for Business** para abrir o Skype para centro de administração de negócios.
    
3. No Skype para centro de administração de negócios, selecione **Ferramentas** no painel esquerdo e selecione **Skype para Business Online chamada qualidade Dashboard**.
    
     ![Skype para as ferramentas de negócios](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Na página que é aberta, entrar com sua conta de Administrador Global e, em seguida, forneça as credenciais da conta quando solicitado.
    
     ![CQD Login](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Depois de entrar, uma vez ativado, o CQD começará a coletando e o processamento de dados.
  
> [!NOTE]
> Pode levar algumas horas para processar dados suficientes para exibir resultados significativos nos relatórios. 
  
## <a name="features-of-the-call-quality-dashboard-for-skype-for-business-online"></a>Recursos do painel de qualidade de chamada do Skype para negócios Online
<a name="BKMKFeaturesOfTheCQD"> </a>

Relatórios de resumo de CQD fornecem um subconjunto dos recursos planejados para relatórios detalhados. As diferenças entre as duas edições estão resumidas aqui:
  
|**Recurso**|**Relatórios de resumo**|**Relatórios detalhados**|
|:-----|:-----|:-----|
|Métrica de compartilhamento de aplicativo  <br/> |Não  <br/> |Sim  <br/> |
|Criando o suporte de informações do cliente  <br/> |Sim  <br/> |Sim  <br/> |
|Suporte à análise de detalhamento  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de confiabilidade de mídia  <br/> |Não  <br/> |Sim  <br/> |
|Relatórios de caixa  <br/> |Sim  <br/> |Sim  <br/> |
|Visão geral de relatórios  <br/> |Sim  <br/> |Sim  <br/> |
|Conjunto de relatório por usuário  <br/> |Não  <br/> |Sim  <br/> |
|Relatório definido personalização (Adicionar, excluir, modificar relatórios)  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de compartilhamento de tela com base em vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Quantidade de dados disponíveis  <br/> |Últimos seis meses  <br/> |Últimos seis meses  <br/> |
|Dados de Teams da Microsoft  <br/> |Sim  <br/> |Sim  <br/> |
   
### <a name="out-of-the-box-reports"></a>Relatórios de caixa

As duas edições do CQD oferecem uma-de-imediata métricas de qualidade sem a necessidade de criar todos os novos relatórios de chamada de experiência, dando a você. Quando os dados são processados no back-end, você poderá começar a ver dados de qualidade da chamada nos relatórios.
  
### <a name="overview-reports"></a>Visão geral de relatórios

As duas edições do CQD fornecem um ponto de entrada de alto nível para as informações de qualidade de chamada geral, mas a maneira como as informações são apresentadas em relatórios de resumo é diferente do relatórios detalhados.
  
Relatórios de resumo fornecem um modo de exibição de relatório de página com guias simplificado que permite aos usuários navegar rapidamente e entender o status de qualidade de chamada e as tendências gerais.
  
As quatro guias incluem:
  
- **Qualidade da chamada geral** - fornece informações sobre todos os fluxos, que é uma agregação de fluxos de servidor-cliente e fluxos de cliente, bem como servidor-cliente separado e fluxos de cliente, na forma de tendências mensais e diárias.
    
- **Servidor - cliente** - fornece detalhes adicionais para os fluxos entre pontos de extremidade do cliente e servidor.
    
- **Client - Client** - fornece detalhes adicionais para os fluxos entre dois pontos de extremidade do cliente.
    
- **SLA de qualidade de voz** - fornece informações sobre as chamadas que estão incluídos no Skype para negócios Online SLA de qualidade de voz.
    
### <a name="overall-call-quality-tab"></a>Guia geral de qualidade da chamada

Use os dados nesta guia para avaliar o status de qualidade de chamada e as tendências examinando as contagens de fluxo e porcentagens ruins. A legenda no canto superior direito mostra quais cor e elementos visuais representam esses indicadores.
  
![Chave CQD dados](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Fluxos são classificados em três grupos: BOM, ruim e não classificados. Há também são calculadas *% ruim* valores que fornecem a você a proporção entre fluxos classificada como *ruim* à contagem total stream classificados. Desde que *% ruim = ruins fluxos / (baixa fluxos + fluxos boa) * 100* , isso torna o *ruim %* não afetado pela presença com vários fluxos de *Unclassified* . Para o que é usado para classificar um stream como ruim ou BOM, consulte a [Classificação de fluxo no painel de qualidade de chamada](stream-classification-in-call-quality-dashboard.md).
  
Use a escala à esquerda para medir os valores de contagem de stream.
  
![Contagem de dados CQD](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Use a escala da direita para medir os valores de baixa %.
  
![Dados CQD por cent](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Você também pode obter os valores numéricos reais passando o mouse sobre uma barra.
  
> [!NOTE]
> O exemplo a seguir é um pequena amostra no conjunto de dados, e os valores não realistas para uma implantação real. 
  
![Numérico CQD dados](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
O volume total do fluxo é um fator importante na determinação relevantes como os percentuais de baixo calculados são. Menor será o volume dos fluxos gerais, menos confiáveis são os valores de porcentagem baixa reportados.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Guia de servidor-cliente e as guias do cliente

Essas duas guias fornecem detalhes adicionais para os fluxos que foram realizadas em seus cenários de-a-ponto de extremidade. Ambas as guias possuem quatro seções recolhidas, representando as quatro cenários sob a qual seriam fluxo de fluxos de mídia.
  
- Com fio dentro
    
- Com fio fora
    
- WiFi Inside
    
- Fora de WiFi
    
#### <a name="inside-test"></a>Teste interior

Durante o processamento, CQD back-end classifica um stream como *dentro* ou *externo* usando informações de construção, se ela existir. Pontos de extremidade de cada fluxo estão associados um endereço de sub-rede. Se a sub-rede estiver na lista das sub-redes marcado InsideCorp as informações de construção carregado, ele é considerado *dentro*. Se informações sobre o edifício ainda não foram carregou, em seguida, dentro do teste será sempre classificar os fluxos como *externo*. Observe que o teste de dentro do cenário de servidor-cliente considera apenas o ponto de extremidade do cliente. Como os servidores são sempre fora da perspectiva de um usuário, isso não é contabilizado no teste.
  
#### <a name="wired-vs-wifi"></a>Com fio versus wifi

Como o nome indica, esse é um critério de classificação com base no tipo de conexões de cliente. Novamente, sempre é por fio server e ele não está incluído no cálculo.
  
> [!NOTE]
> Dado um fluxo, se um dos dois pontos de extremidade estiver conectado a uma rede Wifi, em seguida, ele é classificado como Wifi no CQD. 
  
## <a name="selecting-product-data-to-see-in-reports"></a>Selecionando os dados de produto para ver em relatórios
<a name="BKMKFeaturesOfTheCQD"> </a>

No resumo e relatórios aprimorada de local, você pode usar na lista suspensa **Filtro do produto** para mostrar todos os dados do produto, somente os dados de Teams da Microsoft, ou apenas Skype para dados corporativos Online.
  
![Captura de tela mostra o controle de filtro de produto com opções para todos, Teams da Microsoft e Skype para negócios.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Em relatórios detalhados, você pode usar a dimensão de **Equipes é** para filtrar os dados para o Microsoft Teams ou Skype para dados corporativos Online como parte da definição de relatório.
  
## <a name="upload-building-information"></a>Informações de construção de carregamento
<a name="BKMKFeaturesOfTheCQD"> </a>

O painel de relatórios de resumo de CQD inclui uma página de **Carregamento de dados de Inquilino** , acessada selecionando o **Carregamento de dados de Inquilino** no menu Configurações, no canto superior direito. Esta página é usada para os administradores para carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.
  
![Painel CQD](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Na página de **Carregamento de dados de Inquilino** , use o menu suspenso para escolher um tipo de arquivo de dados para carregar. O tipo de dados de arquivo denota o conteúdo do arquivo (por exemplo, "Edifício" se refere ao mapeamento de endereço IP e a compilação bem como outras informações geográficas). Atualmente, somente suporte para o tipo de dados "Building". Alguns tipos de dados mais serão adicionados com versões subsequentes.
    
2. Depois de selecionar o tipo de dados de arquivo, clique em **Procurar** para escolher um arquivo de dados.
    
  - O arquivo de dados deve ser um arquivo. tsv (valores separados por tabulações) ou arquivos. csv (valores separados por vírgulas). Se estiver usando um arquivo. csv, qualquer campo que contém uma vírgula deve ser circundados por aspas ou ter a vírgula removida. Por exemplo, se o seu nome de construção é Nova York, NY, no arquivo. csv ele deve ser inserido como "Nova York, NY".
    
  - O arquivo de dados deve ser maior do que 50MB em tamanho.
    
  - Para cada arquivo de dados, cada coluna no arquivo deve corresponder a um tipo de dados predefinidos, discutido posteriormente neste tópico.
    
3. Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, **Especifique uma data de término**.
    
4. Depois de selecionar a **Data de início**, selecione **carregar** para carregar o arquivo para o servidor CQD.
    
    Antes do arquivo for carregado, primeiro é validada. Depois da validação, ele é armazenado em um blob Azure. Se a validação falhar ou o arquivo falhará a serem armazenados em um blob Azure, uma mensagem de erro é exibida solicitando uma correção para o arquivo. A imagem a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.
    
     ![Erro de validação de carregamento de exemplo CQD](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se nenhum erro ocorrer durante a validação, o carregamento de arquivo terá êxito. Em seguida, você pode ver o arquivo de dados carregados na **Minhas carregamentos de** tabela, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.
    
    Cada registro mostra locatário carregado de um arquivo de dados, com o tipo de arquivo, hora da última atualização, período, descrição e um ícone de remover um ícone de download. Para remover um arquivo, selecione o ícone de bandeja de Lixeira na tabela. Para baixar um arquivo, selecione o ícone de download na coluna **Baixar** da tabela.
    
     ![Tabela CQD meu carrega](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### <a name="tenant-data-file-format-and-building-data-file-structure"></a>Formato de arquivo de dados de Inquilino e estrutura do arquivo de dados de construção
<a name="BKMKTenantDataFile"> </a>

O formato do arquivo de dados que você carrega deve atender o seguinte procedimento para passar a verificação de validação antes de carregar.
  
- O arquivo deve ser um arquivo. tsv, o que significa que, em cada linha, colunas são separadas por uma guia, ou um arquivo. csv com cada coluna separado por uma vírgula.
    
- O conteúdo do arquivo de dados não inclui os cabeçalhos de tabela. Que significa que a primeira linha do arquivo de dados deve ser dados reais, não cabeçalhos like "Rede", etc.
    
- Para cada coluna, o tipo de dados só pode ser cadeia de caracteres, número ou Bool. Se ele for um número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.
    
- Para cada coluna, se o tipo de dados é a cadeia de caracteres, os dados podem estar vazios (mas ainda devem ser separados por um delimitador apropriado (ou seja, uma tabulação ou vírgula). Isso simplesmente atribui esse campo um valor de cadeia de caracteres vazia.
    
- Deve haver 14 colunas para cada linha, cada coluna deve ter os seguintes dados tipo e as colunas devem estar na ordem listada na tabela a seguir:
    
|**Nome da coluna**|**Tipo de dados**|**Exemplo**|
|:-----|:-----|:-----|
|Rede  <br/> |Cadeia de caracteres  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |Cadeia de caracteres  <br/> |EUA/Seattle/SEATTLE-mar-1  <br/> |
|NetworkRange  <br/> |Número  <br/> |26  <br/> |
|BuildingName  <br/> |Cadeia de caracteres  <br/> |SEATTLE-MAR-1  <br/> |
|OwnershipType  <br/> |Cadeia de caracteres  <br/> |Contoso  <br/> |
|BuildingType  <br/> |Cadeia de caracteres  <br/> |Terminação de IT  <br/> |
|BuildingOfficeType  <br/> |Cadeia de caracteres  <br/> |Engenharia  <br/> |
|Cidade  <br/> |Cadeia de caracteres  <br/> |Seattle  <br/> |
|CEP  <br/> |Cadeia de caracteres  <br/> |98001  <br/> |
|País  <br/> |Cadeia de caracteres  <br/> |CONOSCO  <br/> |
|Estado  <br/> |Cadeia de caracteres  <br/> |WA  <br/> |
|Região  <br/> |Cadeia de caracteres  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> O intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um prefixo de roteamento único). Todos os novos carregamentos de construção serão verificados para todos os intervalos de sobreposição. Se você carregou anteriormente um arquivo de construção, você deve baixar o arquivo atual e reenvie-lo para qualquer sobreposições de identificar e corrigir o problema antes de carregar novamente. Qualquer sobreposição nos arquivos carregados anteriormente pode resultar em mapeamentos de sub-redes aos prédios nos relatórios errados. Determinadas implementações de VPN com precisão não informam as informações de sub-rede. É recomendável que ao adicionar uma sub-rede VPN para o arquivo de construção, em vez de uma entrada para a sub-rede, entradas separadas são adicionadas para cada endereço na sub-rede VPN como uma rede separada de 32 bits. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive. 
  
## <a name="selecting-media-type-in-detailed-reports"></a>Selecionar o tipo de mídia em relatórios detalhados
<a name="BKMKFeaturesOfTheCQD"> </a>

Os relatórios detalhados suportam olhando confiabilidade de qualidade e a mídia de áudio, vídeo, compartilhamento de aplicativos e tipos de mídia de compartilhamento de tela de vídeo-based. Filtros que são específicos para um tipo de mídia único, medidas e dimensões tem "Áudio", "Vídeo", "AppSharing" ou "VBSS" como um prefixo.
  
![Dimensões do painel de controle de qualidade de chamada.](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Se você deseja exibir as dimensões e medidas para um tipo de mídia único, a nova dimensão MediaType e o filtro podem ser necessários. Por exemplo, para que um relatório que mostra que o total de sessões contagens entre diferentes tipos de mídia, inclua a dimensão de MediaType.
  
![Contagem de Stream Total do painel de qualidade de chamada.](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>Tópicos relacionados
[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Análise de uso chamada solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 