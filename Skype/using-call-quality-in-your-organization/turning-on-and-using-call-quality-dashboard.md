---
title: "Como ativar e usar o painel de qualidade de chamada para Teams Microsoft e Skype for Business Online"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.ToolsCallQualityDashboard
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
description: "See how to turn on and use the Skype for Business Online Call Quality Dashboard and get summary reports of quality of calls. "
---

# Como ativar e usar o painel de qualidade de chamada para Teams Microsoft e Skype for Business Online

Aprenda a configurar sua organização Office 365 para usar o painel de qualidade de chamada para monitorar a qualidade da chamada.
  
> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
O painel de qualidade de chamadas (CQD) para Microsoft Teams e Skype for Business Online permite que você obtenha ideias para a qualidade das chamadas feitas usando serviços Microsoft Teams e Skype for Business. Este tópico descreve as etapas que você precisará concluir para iniciar a coleta de dados.
  
> [!NOTE]
> no momento, os relatórios detalhados do CQD estão disponíveis na versão Tech Preview para todos os usuários. 
  
## Alterações e atualizações mais recentes

As alterações mais recentes para CQD são da seguinte maneira:
  
- Inclui dados Microsoft Teams além dos dados de Skype for Business Online.
    
- Relatórios de resumo incluem um filtro de produto para selecionar todos os dados, dados de Microsoft Teams ou Skype for Business Online dados.
    
Consulte este artigo para obter uma lista de [Dimensões e medidas disponíveis no chamar painel de controle de qualidade para Teams da Microsoft e o Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard-for-microsoft-teams.md).
  
> [!NOTE]
> Para ver informações sobre atualizações e alterações no painel, clique em **Boas notícias!** no painel. Você pode ir para o[Painel de Qualidade da Chamada](https://aka.ms/CQDOnline). 
  
## Ativar os relatórios de resumo de Dashboard (CQD) de qualidade de chamada da Microsoft

Antes de começar a usar o CQD, você precisará ativá-lo para a sua organização de Office 365.
  
1. Entrar em sua organização de Office 365 usando uma conta de administrador e, em seguida, selecione o bloco de **administrador** para abrir o Centro de administração.
    
2. No painel esquerdo, em **centros de administração**, selecione o **Skype for Business** para abrir o Centro de administração do Skype for Business.
    
3. No Centro de administração do Skype for Business, selecione **Ferramentas** no painel esquerdo e selecione **Skype for Business Online chamar qualidade Dashboard**.
    
     ![Skype for Business tools](../images/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. Na página que é aberta, faça logon com sua conta de Administrador Global e fornecer as credenciais da conta quando solicitado.
    
     ![CQD Login](../images/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
Após efetuar logon, uma vez ativado, o CQD começará a coletando e o processamento de dados.
  
> [!NOTE]
> Pode levar algumas horas para processar dados suficientes para exibir resultados significativos nos relatórios. 
  
## Recursos do painel de qualidade de chamada do Skype for Business Online
<a name="BKMK_FeaturesOfTheCQD"> </a>

Os relatórios resumidos do CQD fornecem um subconjunto dos recursos planejados para relatórios detalhados. As diferenças entre as duas edições estão resumidas aqui:
  
|**Recurso**|**Relatórios resumidos**|**Relatórios detalhados**|
|:-----|:-----|:-----|
|Métrica de compartilhamento de aplicativos  <br/> |Não  <br/> |Sim  <br/> |
|Suporte a informações de criação do cliente  <br/> |Sim  <br/> |Sim  <br/> |
|Suporte para análise detalhada  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de confiabilidade de mídia  <br/> |Não  <br/> |Sim  <br/> |
|Relatórios de fora da caixa  <br/> |Sim  <br/> |Sim  <br/> |
|Relatórios de visão geral  <br/> |Sim  <br/> |Sim  <br/> |
|Conjunto de relatórios por usuário  <br/> |Não  <br/> |Sim  <br/> |
|Personalização do conjunto de relatórios (adicionar, excluir, modificar relatórios)  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de compartilhamento de tela baseado em vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Métricas de vídeo  <br/> |Não  <br/> |Sim  <br/> |
|Volume de dados disponíveis  <br/> |Últimos seis meses  <br/> |Últimos seis meses  <br/> |
|Dados de Teams da Microsoft  <br/> |Sim  <br/> |Sim  <br/> |
   
### Relatórios de fora da caixa

As duas edições do CQD oferecem uma-de-prontos experiência, dando a você chamar métricas de qualidade sem a necessidade de criar todos os novos relatórios. Depois que os dados são processados no back-end, você pode começar vendo dados de qualidade da chamada nos relatórios.
  
### Relatórios de visão geral

Ambas as edições do CQD fornecem um ponto de entrada de alto nível para informações gerais de qualidade da chamada, mas a forma como as informações são apresentadas nos relatórios resumidos é diferente daquela dos relatórios detalhados.
  
Os relatórios resumidos fornecem uma visualização simplificada do relatório em uma página com guias que permite aos usuários procurar e entender rapidamente o status e as tendências gerais de qualidade das chamadas.
  
As quatro guias incluem:
  
- **Qualidade da chamada geral** - fornece informações sobre todos os fluxos, que é uma agregação de fluxos de servidor-cliente e fluxos de cliente, bem como cliente de servidor separado e fluxos de cliente, na forma de tendências diárias e mensais.
    
- **Servidor - Cliente** - fornece mais detalhes sobre os fluxos entre os pontos de extremidade de Servidor e Cliente.
    
- **Cliente - Cliente** - fornece mais detalhes sobre os fluxos entre dois pontos de extremidade de Cliente.
    
- **SLA de qualidade de voz** - fornece informações sobre chamadas que estão incluídos no Skype for Business Online SLA de qualidade de voz.
    
### Guia Qualidade Geral da Chamada

Use os dados nesta guia para avaliar o status de qualidade de chamada e tendências examinando o fluxo contagens e porcentagens má. A legenda no canto superior direito mostra quais cor e elementos visuais representam essas métricas.
  
![CQD Data key](../images/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Fluxos são classificados em três grupos: BOM, ruim e não classificados. Há também são calculadas  *% má*  valores que fornecem você a proporção da fluxos classificados como * má*  à contagem total fluxo classificados. Desde que *má % = fluxos má / (má fluxos + fluxos de boas) * 100*  , isso tornará o *% má*  afetadas pela presença com vários fluxos de *Unclassified*  . Para o que é usado para classificar um fluxo como má ou boa, consulte[https://aka.ms/cqd_quality_thresholds](https://aka.ms/cqd_quality_thresholds).
  
Utilize a escala existente à esquerda para medir os valores de contagem de chamadas.
  
![CQD data count](../images/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Utilize a escala existente na esquerda para medir os valores de % insatisfatória.
  
![CQD data per cent](../images/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
Você também pode obter valores numéricos reais passando com o mouse sobre uma barra.
  
> [!NOTE]
> O exemplo a seguir é de um conjunto de dados de exemplo muito pequeno, e os valores não são realistas para uma implantação real. 
  
![CQD Data numeric](../images/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
O volume geral de fluxo é um fator importante para determinar a relevância dos percentuais de fluxos ruins calculados. Quanto menor o volume geral de fluxo, menos confiáveis são os valores de percentuais de fluxos ruins relatados.
  
### Guia de servidor-cliente e as guias de cliente

Essas duas guias fornecem mais detalhes sobre os fluxos que ocorrem em cenários de um ponto de extremidade a outro. As duas guias têm quatro seções, que representam os quatro cenários pelos quais os fluxos de mídia percorrem.
  
- Com fio interno
    
- Com fio externo
    
- Sem fio interno
    
- Sem fio externo
    
#### Teste interno

Durante o processamento, back-end do CQD classifica um fluxo como  *dentro*  ou *fora*  usando informações de construção, se ele existir. Pontos de extremidade de cada fluxo estão associados um endereço de sub-rede. Se a sub-rede estiver na lista das sub-redes nas informações de construção carregadas, ele é considerado dentro. Se informações do edifício não ainda foi carregada, em seguida, teste dentro sempre classificará os fluxos como *fora*  . Observe que dentro de teste para o cenário de servidor-cliente considera somente o ponto de extremidade do cliente. Como os servidores são sempre fora da perspectiva de um usuário, isso não é considerado no teste.
  
#### Wired versus wifi

Como os nomes indicam, este é um critério de classificação com base no tipo de conexões de cliente. Novamente, o servidor está sempre com fio e não é incluído no cálculo.
  
> [!NOTE]
> Considerando um fluxo, se um dos dois pontos de extremidade está conectado a uma rede Wifi, em seguida, ele é classificado como Wifi no CQD. 
  
## Selecionar dados de produto para ver em relatórios
<a name="BKMK_FeaturesOfTheCQD"> </a>

Em Resumo da e localização avançada relatórios, você pode usar na lista suspensa do **Filtro de produto** para mostrar todos os dados de produto, somente os dados de Microsoft Teams ou apenas os dados de Skype for Business Online.
  
![Screenshot shows the Product Filter control with options for All, Microsoft Teams, and Skype for Business.](../images/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Em relatórios detalhados, você pode usar a dimensão de equipes para filtrar os dados para os dados de Microsoft Teams ou Skype for Business Online como parte da definição de relatório.
  
## Carregar informações de criação
<a name="BKMK_FeaturesOfTheCQD"> </a>

O painel de relatórios de resumo de CQD inclui uma página **Para carregar dados locatário**, acessada selecionando **Locatário para carregar dados** no menu configurações no canto superior direito. Esta página é usada para administradores de carregar suas próprias informações, como o mapeamento de endereço IP e informações geográficas, mapeamento de cada ponto de acesso sem fio e seu endereço MAC, etc.
  
![CQD Dashboard](../images/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. Na página de **Carregamento de dados de Inquilino**, use o menu suspenso para escolher um tipo de arquivo de dados para carregar. O tipo de dados do arquivo indica o conteúdo do arquivo (por exemplo, "Construção" se refere ao mapeamento de endereço IP e criando bem como outras informações geográficas). Suporte no momento podemos são apenas o tipo de dados de "Construção". Alguns tipos de dados mais serão adicionados com versões posteriores.
    
2. Após selecionar o tipo de dados do arquivo, clique em **Procurar** para escolher um arquivo de dados.
    
  - O arquivo de dados deve ser um arquivo. tsv (valores separados por tabulações) ou um arquivo do. csv (valores separados por vírgula). Se usando um arquivo. csv, qualquer campo que contém uma vírgula deve conter aspas ou ter a vírgula removida. Por exemplo, se o nome de construção é NY, NY, no arquivo. csv-deve ser inserida como "Nova York, NY".
    
  - O arquivo de dados deve ter, no máximo, 50 MB.
    
  - Para cada arquivo de dados, cada coluna do arquivo deve corresponder a um tipo de dados predefinido, descrito posteriormente neste tópico.
    
3. Depois de selecionar um arquivo de dados, especifique a **Data de início** e, opcionalmente, **Especifique uma data de término**.
    
4. Após a seleção de **Data de início**, selecione **Upload** para fazer upload do arquivo para o servidor do CQD.
    
    Para que o arquivo é carregado, ele é validado primeiro. Uma vez validada, ela é armazenada em um blob do Microsoft Azure. Se o arquivo ou falha de validação falhará sejam armazenados em um blob Azure, uma mensagem de erro é exibida solicitando uma correção para o arquivo. A imagem a seguir mostra um erro que ocorrem quando o número de colunas no arquivo de dados está incorreto.
    
     ![CQD Example upload validation error](../images/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. Se nenhum erro ocorrer durante o processo de validação, o carregamento do arquivo será bem-sucedido. Assim, você poderá ver o arquivo de dados carregado na tabela **Meus uploads**, que mostra a lista completa de todos os arquivos carregados para o locatário atual na parte inferior da página.
    
    Cada registro mostra um locatário carregados arquivo de dados, com o tipo de arquivo, hora da última atualização, período de tempo, descrição, remover e um ícone de download. Para remover um arquivo, selecione o ícone de Lixeira Lixeira na tabela. Para baixar um arquivo, selecione o ícone de download na coluna **Download** da tabela.
    
     ![CQD My Uploads table](../images/4168a883-bbea-461a-80b1-42eedf2e7732.png)
  
### Formato de arquivo de dados de usuário e estrutura do arquivo de dados de criação
<a name="BKMK_TenantDataFile"> </a>

O formato do arquivo de dados que você carrega precisa atender aos seguintes requisitos para passar na verificação de validação antes do upload.
  
- O arquivo deve ser um arquivo. tsv, o que significa que, em cada linha, as colunas são separadas por uma tabulação, ou um arquivo. csv com cada coluna separada por vírgula.
    
- O conteúdo do arquivo de dados não inclui os cabeçalhos da tabela. Que significa que a primeira linha do arquivo de dados deve ser dados reais, cabeçalhos não gostam "Rede", etc.
    
- Para cada coluna, o tipo de dados só pode ser Bool, número ou cadeia de caracteres. Se ele for o número, o valor deve ser um valor numérico; Se for Bool, o valor deve ser 0 ou 1.
    
- Para cada coluna, se o tipo de dados for cadeia, os dados podem estar vazios (mas ainda devem ser separados por um delimitado apropriado (ou seja, uma tabulação ou vírgula). Isso apenas atribui nesse campo um valor de cadeia de caracteres vazia.
    
- Deve haver 14 colunas para cada linha. Cada coluna deve ter o tipo de dados a seguir, e as colunas devem estar na ordem listada na seguinte tabela:
    
|**Nome da Coluna**|**Tipo de dados**|**Exemplo**|
|:-----|:-----|:-----|
|Rede  <br/> |String  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |String  <br/> |USA/Seattle/SEATTLE-SEA-1  <br/> |
|NetworkRange  <br/> |Número  <br/> |26  <br/> |
|BuildingName  <br/> |String  <br/> |SEATTLE-SEA-1  <br/> |
|OwnershipType  <br/> |String  <br/> |Contoso  <br/> |
|BuildingType  <br/> |String  <br/> |Terminação de TI  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |Engenharia  <br/> |
|Cidade  <br/> |String  <br/> |Seattle  <br/> |
|ZipCode  <br/> |String  <br/> |98001  <br/> |
|País  <br/> |Cadeia de caracteres  <br/> |US  <br/> |
|Estado  <br/> |Cadeia de caracteres  <br/> |WA  <br/> |
|Região  <br/> |Cadeia de caracteres  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> o intervalo de rede pode ser usado para representar uma super-rede (combinação de várias sub-redes com um único prefixo de roteamento). Será verificado se há intervalos sobrepostos em todas as novas criações carregadas. Se você já carregou um arquivo de criação, deve baixar o arquivo atual e recarregá-lo para identificar sobreposições e corrigir o problema antes de carregá-lo novamente. Qualquer sobreposição em arquivos carregados anteriormente pode resultar no mapeamento incorreto de sub-redes para criações nos relatórios. > Determinadas implementações VPN não relatar precisamente as informações de sub-rede. É recomendável que ao adicionar uma sub-rede VPN para o arquivo de construção, em vez de uma entrada da sub-rede, entradas separadas são adicionadas para cada endereço na sub-rede VPN como uma rede de 32 bits separada. Cada linha pode ter os mesmos metadados de construção. Por exemplo, em vez de uma linha para 172.16.18.0/24, você deve ter 256 linhas, com uma linha para cada endereço entre 172.16.18.0/32 e 172.16.18.255/32, inclusive. 
  
## Seleção do tipo de mídia nos relatórios detalhados
<a name="BKMK_FeaturesOfTheCQD"> </a>

Os relatórios detalhados suportam olhando confiabilidade mídia e qualidade de áudio, vídeo, compartilhamento de aplicativos e tipos de mídia de compartilhamento de tela de baseados em vídeo. Dimensões, medidas e filtros que são específicos para um tipo de mídia único tem "Áudio", "Vídeo", "AppSharing" ou "VBSS" como um prefixo.
  
![Call Quality Dashboard Dimensions.](../images/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
Se você quiser exibir as dimensões e medidas para um tipo de mídia único, a nova dimensão de tipo de mídia e o filtro podem ser necessárias. Por exemplo, para que um relatório que mostra que o total da sessão contagens entre diferentes tipos de mídia, inclua a dimensão de tipo de mídia.
  
![Call Quality Dashboard Total Stream Count.](../images/21d5d0dc-2321-415e-8ef2-cea06165601c.png)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

