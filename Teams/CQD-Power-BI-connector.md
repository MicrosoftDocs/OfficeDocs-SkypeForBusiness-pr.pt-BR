---
title: Instalar o Power BI Connector para usar modelos de consulta CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Instalar o Power BI Connector para usar modelos de consulta do Painel de Qualidade de Chamada (CQD)
ms.openlocfilehash: 188e030d4f1ef6eaff21bef83a09c22d29bb51c5
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875031"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar o Power BI Connector para usar modelos de consulta CQD

Antes de usar os modelos de consulta do Power BI (arquivos PBIX) para o CQD (Painel de Qualidade de Chamadas do Microsoft Teams), você precisará instalar o Conector do Power BI para Microsoft CQD, usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).

Leia [Use o Power BI para analisar dados do CQD para o Teams](CQD-Power-BI-query-templates.md) para saber mais sobre esses modelos.

Certifique-se de ter a função de acesso [CQD correta](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) para acessar os relatórios do Power BI.

> [!NOTE]
> O Conector do CQD Power BI só dá suporte ao DirectQuery no Power BI; O modo de importação não é suportado. 

## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para habilitar o uso do conector é descrito em detalhes na documentação [do Power BI.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility) Para simplificar, aqui está uma explicação rápida:

1. Verifique se o computador já tem uma pasta *\[ Conectores \] \\ \\ Personalizados* da Área de Trabalho do Power BI. Caso não seja, crie essa pasta. <sup>1</sup>

2. Baixe o arquivo do conector (um *\* arquivo .mez* ou *\* .pqx)* e coloque-o no *diretório Conectores Personalizados.*

3. **Se o arquivo do conector for *\* um arquivo .mez,*** você também precisará ajustar suas configurações de segurança, conforme descrito na documentação de instalação [do conector personalizado.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)

Se uma nova versão desse Conector do Power BI para o Microsoft Teams for lançada, basta substituir o arquivo do conector antigo no diretório *Conectores Personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro você precisará se conectar à fonte de dados CQD. Siga as etapas abaixo para se conectar:

1. Na guia Página Base da Área de Trabalho do Power BI, clique em *Obter Dados.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector1-resize.png)

2. A *janela Obter Dados* deve aparecer neste ponto. Navegue *até Serviços Online,* selecione *Qualidade de Chamada da Microsoft (Beta)* e clique em *Conectar*.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector2-resize.png)

3. Você será solicitado a entrar em seguida. Use as mesmas credenciais que você usa para CQD. <sup>2</sup>

4. O próximo prompt dará a opção entre dois modos *de Conectividade de Dados.* Selecione *DirectQuery* e clique em *OK*.

5. Por fim, você receberá um prompt final mostrando todo o modelo de dados para CQD. Nenhum dado será visível neste ponto, apenas o modelo de dados para CQD. Selecione *Carregar* para concluir o processo de instalação.

6. Neste ponto, o Power BI carregará o modelo de dados no lado direito da janela. A página permanecerá em branco, e nenhuma consulta será carregada por padrão. **Prossiga para a** criação de consultas abaixo para criar uma consulta e retornar dados.

Se qualquer uma das etapas durante esse processo de instalação não tiver sido completamente clara, uma explicação mais detalhada sobre o processo poderá ser encontrada em Início Rápido: Conectar-se aos dados na Área de [Trabalho do Power BI.](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>Criando consultas

Depois que a instalação for concluída, você deverá ver os nomes de várias centenas de dimensões e medidas carregadas no painel *Campos.* A construção de consultas reais a partir daqui é simples, basta selecionar as dimensões e medidas que você deseja para sua consulta e arraste e solte-as na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1. Selecione a visualização que você deseja usar no painel *Visualizações.* Uma versão em branco dessa visualização deve aparecer na página. Para os fins deste exemplo, vamos usar a visualização *tabela.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector3-resize.png)

2. Determine quais dimensões e medidas (denotadas por um símbolo de agregação pelo nome) que você deseja usar para sua consulta e selecione-as manualmente e arraste-as para a visualização em preto. Como alternativa, arraste-os para o campo *Valores* abaixo das opções de visualização.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > O Painel de Qualidade de Chamada requer uma medida para que qualquer consulta seja executado. A falha ao adicionar uma medida a uma consulta fará com que essa consulta falhe.

3. Em seguida, selecione as dimensões que você deseja filtrar e arraste-as para o *Filtros* neste campo visual no painel *Filtros.* O CQD Power BI Connector atualmente dá suporte à filtragem básica (selecione valores de uma lista de valores de dimensão possíveis), filtragem avançada (especificar manualmente  valores  e operands para filtrar, semelhante ao CQD avançado) e filtragem de data relativa *(disponível* apenas para as dimensões Hora de Término e Hora de Início).   A filtragem de acordo *com o Top N* não é suportada pelo CQD.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector5-resize.png)

4. Por fim, selecione a guia *Formatar* no painel *Visualizações* para estilizar e formatar sua consulta.

    > [!NOTE]
    > As consultas CQD exigem pelo menos uma medida para ser executado. Se a consulta não for carregada, verifique duas vezes se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um relatório passo a passo

[O drillthrough no Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) permite que você crie relatórios focados que você pode filtrar rapidamente usando os valores de outros relatórios como contexto. Depois de saber como criar sua primeira consulta com o Conector CQD, criar um drillthrough é ainda mais simples.

1. Crie outra página para o relatório focado e adicione suas consultas a essa página.

2. Selecione a dimensão que você deseja usar como um filtro passo a passo e arraste-os para o campo *Drillthrough* no painel *Visualizações.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector6-resize.png)

3. **É isso.\!** Qualquer outra consulta em outra página que use essa dimensão agora pode ser passo a passo nessa página, aplicando automaticamente o valor da dimensão drillthrough como um filtro.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector7-resize.png)

Ao contrário do CQD avançado, o Power BI oferece suporte a drillthrough não sequencial. Desde que uma consulta inclua a dimensão necessária, ela pode ser passo a passo para qualquer outra página.

### <a name="best-practice"></a>Prática prática prática

As consultas do conector de qualidade de chamada devem ser projetadas com a funcionalidade drillthrough em mente. Em vez de tentar carregar todos os dados de uma só vez e cortar com filtros, comece com consultas mais amplas e de baixa cardinalidade e faça uma pesquisa até consultas de alta cardinalidade. Por exemplo, ao tentar diagnosticar quais sub-redes contribuem mais para problemas de qualidade, é útil primeiro identificar essas regiões e países que contribuem para o problema e, em seguida, detalhar as sub-redes nessa região ou país. Os modelos de conector de Qualidade de Chamada foram projetados dessa maneira para atuar como um exemplo.

## <a name="limitations"></a>Limitações

Apesar de usar o Power BI, nem todas as funcionalidades do Power BI são compatíveis com o Conector CQD, seja como resultado de limitações no modelo de dados CQD ou em conectores DirectQuery em geral. A lista abaixo observa algumas das limitações mais notáveis do Conector, mas essa lista não deve ser considerada exaustiva:

1. **Colunas Calculadas –** Os conectores do DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Embora algumas colunas calculadas possam funcionar com o Conector, elas devem ser consideradas exceções. Como regra geral, as colunas calculadas não funcionarão.

2. **Agregaçãos –** O modelo de dados CQD é criado em um modelo de cubo, o que significa que as agregação já têm suporte na forma de medidas. A tentativa de adicionar agregação manualmente a dimensões diferentes ou alterar o tipo de agregação de uma medida não funcionará com o Conector, e isso geralmente resultará em um erro.

3. **Elementos visuais personalizados –** Embora o Conector CQD funcione com uma variedade de elementos visuais personalizados, não é possível garantir a compatibilidade com todos os elementos visuais personalizados. Muitos elementos visuais personalizados dependem do uso de colunas calculadas ou dados importados, nem que são suportados por conectores do DirectQuery.

4. **Fazendo referência a dados armazenados em cache –** No momento, o Power BI não dá suporte a fazer referência a dados armazenados em cache de um conector DirectQuery de qualquer maneira. Qualquer tentativa de referenciar os resultados de uma consulta resultará em uma nova consulta.

5. **Filtragem de Dados Relativos –** Tem suporte no Conector CQD, mas somente com as dimensões *Hora* de Início e Hora *de* Término. Embora a *dimensão Date* possa ser a escolha óbvia para filtragem de data relativa, *Date* não é armazenada como um objeto de data e, portanto, não dá suporte à filtragem de data relativa no Power BI.

6. Suporte à Nuvem da Comunidade Governamental **(GCC) –** Para clientes no ambiente GCC, o Conector do CQD Power BI funcionará ao usar a Área de Trabalho do Power BI. O conector do CQD Power BI é compatível com o serviço Power BI para clientes GCC.

A maioria desses problemas são restrições ao design do conector DirectQuery no Power BI ou fundamentais para o design do modelo de dados CQD.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estou tentando usar a coluna Data como uma slicer Date. Assim que eu converter o tipo de dados dessa coluna em Data, eu receber esse erro

> **Não foi necessário** carregar os dados para este visual : erro OLE DB ou ODBC: [Expressão.Erro] Não foi foi conseguida dobrável a expressão para a fonte de dados. Tente uma expressão mais simples.

As slicers de data não são suportadas com o Power BI Connector. Para especificar um intervalo de datas, aplique dois filtros ao relatório, especificando uma data menor do que e maior do que a data.

Como alternativa, se as datas que você deseja exibir são recentes, aplique um filtro de data relativa para mostrar apenas os dados dos últimos N dias/semanas/meses.

## <a name="error-codes"></a>Códigos de erro

Como o Conector do CQD Power BI é menos restrito do que o aplicativo do navegador em termos de tipos de consultas que você pode construir, você pode ocasionalmente encontrar vários erros ao criar suas consultas. Caso você receba uma mensagem de erro do tipo "CQDError. RunQuery – Erro de Execução de Consulta", consulte a lista abaixo com o número ErrorType fornecido para solucionar o possível problema com a consulta. Veja a seguir os códigos de Tipo de Erro mais comuns que você pode encontrar com o Conector do Power BI do CQD:

- **ErrorType 1 - Erro de Estrutura de Consulta:** Um erro de estrutura de consulta geralmente é causado pela falha do Conector ao criar uma consulta formatada corretamente. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique duas vezes se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 2 - Erro de construção de consulta:** Um erro de construção de consulta é causado pelo conector CQD não poder analisar corretamente a consulta que você está tentando criar. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique duas vezes se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 5 - Tempo de execução:** A consulta atingiu o tempo de execução máximo possível antes do tempo limite. Tente adicionar mais filtros à consulta para limitar seu escopo. Restringir o intervalo de dados geralmente é a maneira mais eficaz de fazer isso.

  - **ErrorType 7 - Nenhum erro de medição:** As consultas CQD exigem uma medida para funcionar. Verifique se sua consulta inclui medida. As medidas no Conector CQD são anotadas pelo símbolo de agregação (soma) antes de seu nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do CQD para que possamos ajudar a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Notas de rodapé

**<sup>1</sup>** Determinados processos e aplicativos (por exemplo, OneDrive) podem fazer com que a pasta raiz documentos seja mudada; certifique-se de que o *diretório Conectores \\ Personalizados* da Área de Trabalho do Power BI seja colocado dentro da pasta raiz atual Documentos.

**<sup>2</sup>** As credenciais de logon  que você usa para o CQD não precisam ser as mesmas que você usa para fazer logon no próprio aplicativo da Área de Trabalho do Power BI.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando o Conector do Power BI será atualizado a partir do status "Beta"

Apesar da marca Beta, o Conector de Qualidade de Chamada para Power BI é a versão de lançamento do conector e foi oficialmente assinado pela equipe do Power BI para refletir isso. O processo de certificação para remover essa marca Beta é abrangente e requer um compromisso da equipe do Power BI para fornecer suporte direto ao conector também. Devido às restrições de tempo, a equipe do Power BI não consegue fornecer esse suporte e uma certificação mais ampla, mas ainda está preparada para atestar a segurança, a autenticidade e a funcionalidade geral do conector de Qualidade de Chamada da Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Por que o conector parece mais lento em comparação com o CQD avançado no navegador? O que posso fazer para melhorar o desempenho

O desempenho da consulta para os vários modelos é, na verdade, o mesmo no navegador e no conector.  Assim como qualquer outro aplicativo autônomo, o Power BI adiciona seu tempo de autenticação e renderização ao nosso desempenho. Além disso, a diferença vem no número de consultas simultâneas sendo executados. Como a versão no navegador do CQD tinha opções de visualização menos desenvolvidas e densas de informações, a maioria dos nossos relatórios estava limitada ao carregamento de consultas de 2 a 3 por vez. Por outro lado, os modelos de conector geralmente exibem mais de 20 consultas simultâneas. Se você deseja criar relatórios que sejam tão responsivos quanto os mais antigos aos quais você estava acostumado, tente criar relatórios com no máximo 2 a 3 consultas por guia.

Para obter mais informações, consulte os seguintes artigos:

- [Guia de otimização do Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [Diretrizes do modelo DirectQuery](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Eu acho que eu corro rotineiramente para o limite de 10.000 linhas ao executar consultas. Como fazer com que o conector retorne mais de 10.000 linhas

O limite de 10.000 linhas é realmente especificado no final da API e foi projetado para ajudar a melhorar significativamente o desempenho e reduzir o risco de erros de execução de consulta resultantes de condições de memória baixa.

Em vez de tentar aumentar a contagem de linhas de resultados, é melhor reestruturar seus relatórios de acordo com as práticas recomendadas do conector. Os modelos que incluímos foram projetados para demonstrar essas práticas recomendadas. Sempre que possível, comece olhando para seus KPIs usando dimensões mais amplas e de menor cardinalidade, como Mês, Ano, Data, Região, País, etc. A partir daí, você pode detalhar as dimensões cada vez mais elevadas. O Helpdesk e Location-Enhanced relatórios fornecem bons exemplos desse fluxo de trabalho de detalhamento.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados CQD para o Teams](CQD-Power-BI-query-templates.md)
