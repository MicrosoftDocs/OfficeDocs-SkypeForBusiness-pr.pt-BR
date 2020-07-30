---
title: Instalar o conector do Power BI para usar modelos de consulta CQD
ms.author: lolaj
author: LolaJacobsen
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
description: Instalar o conector do Power BI para usar modelos de consulta do painel de qualidade de chamada (CQD)
ms.openlocfilehash: 1c315dc0214ee0540ddce25fb8f0a1dc1794048f
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506164"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar o conector do Power BI para usar modelos de consulta CQD

Antes de poder usar os modelos de consulta do Power BI (arquivos PBIX) para o Microsoft Teams Call Quality Dashboard (CQD), você precisará instalar o conector do Power BI para Microsoft CQD, usando o arquivo *MicrosoftCallQuality. pqx* incluído no [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).

Leia [use o Power bi para analisar os dados do CQD para](CQD-Power-BI-query-templates.md) que as equipes aprendam sobre esses modelos.

Verifique se você tem a [função de acesso CQD](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) certa para acessar os relatórios do Power bi.

## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para permitir o uso do conector é descrito em detalhes na [documentação do Power bi](https://docs.microsoft.com/power-bi/desktop-connector-extensibility). Para simplificar, veja a seguir uma explicação rápida:

1. Verifique se o seu computador já tem uma pasta de * \[ \] \\ \\ conectores personalizados da área de trabalho do Power bi desktop*   . Caso contrário, crie essa pasta. <sup>1</sup>

2. Baixe o arquivo do conector (um arquivo * \* . Mez* ou * \* . pqx* ) e coloque-o no diretório de *conectores personalizados* .

3. **Se o arquivo do conector for um arquivo * \* . Mez* ,** você também precisará ajustar as configurações de segurança conforme descrito na [documentação de instalação do conector personalizado](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security).

Se uma nova versão deste conector do Power BI para Microsoft Teams for lançada, basta substituir o arquivo de conector antigo no diretório de *conectores personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro será necessário se conectar à fonte de dados CQD. Siga as etapas abaixo para conectar-se:

1. Na guia página inicial do Power BI desktop, clique em *obter dados*.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector1-resize.png)

2. A janela *obter dados* deve aparecer neste ponto. Navegue até *serviços online*e, em seguida, selecione *qualidade da chamada do Microsoft (beta)* e clique em *conectar*.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector2-resize.png)

3. Você será solicitado a entrar em Login. Use as mesmas credenciais usadas para o CQD. <sup>2</sup>

4. O próximo prompt oferecerá a opção entre dois *modos de conectividade de dados*. Selecione *DirectQuery* e clique em *OK*.

5. Por fim, você receberá um prompt final mostrando todo o modelo de dados para CQD. Nenhum dado estará visível nesse ponto, apenas o modelo de dados para CQD. Selecione *carregar* para concluir o processo de configuração.

6. Nesse ponto, o Power BI carregará o modelo de dados no lado direito da janela. A página permanecerá em branco de outra forma, e nenhuma consulta será carregada por padrão. Vá para **criando consultas** abaixo para criar uma consulta e retornar dados.

Se qualquer uma das etapas durante este processo de configuração não fosse completamente clara, uma explicação mais detalhada sobre o processo pode ser encontrada [aqui](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Criando consultas

Depois que a instalação for concluída, você verá os nomes de várias centenas de dimensões e medidas de carga no painel *campos* . A criação de consultas reais aqui é simples, basta selecionar as dimensões e medidas desejadas para a sua consulta e, em seguida, arrastar e solte-os na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1. Selecione a visualização que você deseja usar no painel *visualizações* . Uma versão em branco dessa visualização deve aparecer na página. Para os fins deste exemplo, usaremos a visualização de *tabela* .

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector3-resize.png)

2. Determine quais dimensões e medidas (denotadas por um símbolo de agregação pelo nome) você deseja usar para a sua consulta, selecione-as manualmente e arraste-as para a visualização preta. Como alternativa, arraste-os para o campo *valores* abaixo das opções de visualização.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > O painel de qualidade da chamada requer uma medida para que qualquer consulta seja executada. Falha ao adicionar uma medida a uma consulta causará falha na consulta.

3. Em seguida, selecione as dimensões que deseja filtrar e arraste-as para o campo *filtros nesse Visual* no painel *filtros* . No momento, o conector do Power BI do CQD dá suporte a *filtragem básica* (selecione valores em uma lista de possíveis valores de dimensão), *filtragem avançada* (especifique manualmente valores e operandos para filtrar, de forma semelhante ao CQD avançado) e *à filtragem de data relativa* (disponível somente para as dimensões de *hora de término* e hora de *início* ). A filtragem de acordo com a *N superior* não é suportada pela CQD.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector5-resize.png)

4. Por fim, selecione a guia *formato* no painel *visualizações* para estilizar e formatar sua consulta.

    > [!NOTE]
    > As consultas CQD exigem pelo menos uma medida para serem executadas. Se a sua consulta não carregar, verifique novamente se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um relatório detalhado

O [detalhamento do Power bi](https://docs.microsoft.com/power-bi/desktop-drillthrough) permite criar relatórios direcionados que você pode filtrar rapidamente usando os valores de outros relatórios como contexto. Depois que você sabe como criar sua primeira consulta com o conector CQD, criar um detalhamento é ainda mais simples.

1. Crie outra página para o relatório prioritário e, em seguida, adicione suas consultas a essa página.

2. Selecione a dimensão que você deseja usar como um filtro detalhado e arraste-os para o campo *Drillthrough* em no painel *visualizações* .

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector6-resize.png)

3. **Isso é\!** Qualquer outra consulta em outra página que use essa dimensão agora pode detalhar essa página, aplicando automaticamente o valor da dimensão de detalhamento como um filtro.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector7-resize.png)

Ao contrário do CQD avançado, o Power BI dá suporte ao detalhamento não sequencial. Desde que uma consulta inclua a dimensão necessária, ela pode detalhar qualquer outra página.

### <a name="best-practice"></a>Prática recomendada

As consultas do conector de qualidade da chamada devem ser projetadas com a funcionalidade de detalhamento. Em vez de tentar carregar todos os dados de uma vez e, em seguida, aplicar uma fatia abaixo com os filtros, comece com consultas de baixa e pouca cardinalidade e faça drill down até consultas de alta cardinalidade. Por exemplo, ao tentar diagnosticar quais subredes contribuem da maioria dos problemas de qualidade, é útil primeiro identificar as regiões e os países que contribuem para o problema e, em seguida, fazer uma busca detalhada nas sub-redes dessa região ou do país. Os modelos do conector de qualidade da chamada foram projetados dessa maneira para atuar como exemplo.

## <a name="limitations"></a>Relacionadas

Apesar de fazer uso do Power BI, nem toda a funcionalidade do Power BI é compatível com o conector CQD, seja como resultado de limitações no modelo de dados CQD ou nos conectores DirectQuery em geral. A lista abaixo observa algumas das limitações mais importantes do conector, mas esta lista não deve ser considerada exaustiva:

1. **Colunas calculadas –** Os conectores DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Embora algumas colunas calculadas possam funcionar com o conector, elas devem ser consideradas exceções. Como regra geral, as colunas calculadas não funcionarão.

2. **Agregações –** O modelo de dados CQD é criado em um modelo de cubo, o que significa que as agregações já têm suporte na forma de medidas. A tentativa de adicionar agregações manualmente a dimensões diferentes ou alterar o tipo de agregação de uma medida não funcionará com o conector, e isso geralmente resultará em um erro.

3. **Elementos visuais personalizados-** Embora o conector CQD funcione com uma variedade de elementos visuais personalizados, não podemos garantir a compatibilidade com todos os elementos visuais personalizados. Muitos elementos visuais personalizados dependem do uso de colunas calculadas ou de dados importados, nenhum ou que são suportados pelos conectores DirectQuery.

4. **Fazendo referência a dados armazenados em cache –** Atualmente, o Power BI não oferece suporte a referências a dados armazenados em cache de um conector DirectQuery de maneira alguma. Qualquer tentativa de fazer referência aos resultados de uma consulta resultará em uma nova consulta.

5. **Filtragem de dados relativa –** É compatível com o conector CQD, mas somente com as dimensões *hora de início* e hora de *término* . Embora a dimensão de *Data* possa ser a opção óbvia para a filtragem de data relativa, a *Data* não é armazenada como um objeto de data/hora e, portanto, não oferece suporte a filtragem de data relativa no Power bi.

6. **Suporte para a nuvem da Comunidade governamental (GCC) do governo-** Para os clientes no ambiente GCC, o conector do Power BI do CQD funcionará com o uso da área de trabalho do Power BI. O conector do Power BI CQD não é compatível no momento com o serviço do Power BI para clientes GCC.

A maioria desses problemas é uma restrição do design do conector DirectQuery no Power BI ou fundamental para o design do modelo de dados CQD.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estou tentando usar a coluna data como uma segmentação de data. Assim que faço para converter o tipo de dados desta coluna em Date, recebo esse erro

> **Não foi possível carregar os dados para este Visual**: erro OLE DB ou ODBC: [Expression. Error] não foi possível dobrar a expressão na fonte de dados. Tente uma expressão mais simples.

Não há suporte para segmentações de dados com o conector do Power BI. Para especificar um intervalo de datas, aplique dois filtros ao relatório, especificando uma data menor que e maior que.

Como alternativa, se as datas que você deseja exibir forem recentes, aplique um filtro de data relativo para mostrar somente os dados dos últimos N dias/semanas/meses.

## <a name="error-codes"></a>Códigos de erro

Como o conector do Power BI do CQD é menos restrito do que o aplicativo do navegador em termos de tipos de consultas que você pode construir, ocasionalmente você pode encontrar vários erros ao criar suas consultas. No caso de receber uma mensagem de erro do tipo "CQDError. RunQuery – erro de execução de consulta ", consulte a lista abaixo com o número de ErrorType fornecido para solucionar o problema possível com a consulta. Estes são os códigos de tipo de erro mais comuns que você pode encontrar com o conector do Power BI do CQD:

- **ErrorType 1-erro de estrutura de consulta:** Geralmente, um erro de estrutura de consulta é causado pelo conector que não consegue criar uma consulta formatada corretamente. Isso ocorre com mais frequência ao usar funcionalidades sem suporte, conforme especificado nas limitações acima. Verifique novamente se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 2-erro ao criar consulta:** Um erro de construção de consulta é causado pelo conector CQD não pode analisar corretamente a consulta que você está tentando compilar. Isso ocorre com mais frequência ao usar funcionalidades sem suporte, conforme especificado nas limitações acima. Verifique novamente se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 5-tempo limite de execução:** A consulta atingiu o tempo de execução máximo possível antes do tempo limite. Tente adicionar mais filtros à consulta para limitar o escopo. Restringir o intervalo de dados é geralmente a maneira mais eficiente de conseguir isso.

  - **ErrorType 7-erro de medições:** As consultas CQD exigem uma medida para funcionar. Verifique novamente se a sua consulta inclui medida. As medidas no conector CQD são indicadas pelo símbolo de agregação (Sum) antes do nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do CQD para que possamos ajudá-lo a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Notas

**<sup>1</sup>** alguns processos e aplicativos (por exemplo, o onedrive) podem fazer com que a pasta raiz dos seus documentos seja alterada; Verifique se o diretório de * \\ conectores personalizados da área de trabalho do Power bi* está colocado dentro da pasta de documentos da pasta raiz atual.

**<sup>2</sup>** as credenciais de logon que você usa para o CQD *não* precisam ter as mesmas credenciais que você usa para fazer logon no próprio aplicativo da área de trabalho do Power bi.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando o conector do Power BI será atualizado do status "beta"

Apesar da marca beta, o conector de qualidade da chamada para o Power BI é a versão de lançamento do conector e tem a segurança oficialmente assinada pela equipe do Power BI para refletir isso. O processo de certificação para remover a marca beta é um processo extensivo e requer um compromisso da equipe do Power BI para fornecer suporte direto ao conector também. Devido a restrições de tempo, a equipe do Power BI atualmente não consegue fornecer esse suporte e certificação mais ampla, mas ainda está preparada para atestar a segurança, a autenticidade e a funcionalidade geral do conector de qualidade da chamada da Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Por que o conector parece mais lento quando o CQD avançado está no navegador? O que posso fazer para melhorar o desempenho

O desempenho da consulta para os vários modelos é realmente o mesmo no navegador e no conector.  Assim como qualquer outro aplicativo autônomo, o Power BI adiciona seu tempo de autenticação e renderização ao nosso desempenho. Além disso, a diferença se refere ao número de consultas simultâneas em execução. Como a versão do navegador do CQD tinha menos opções de visualização bem desenvolvidas e com informações de visualização, a maioria dos nossos relatórios limitava o carregamento de consultas do 2-3 de cada vez. Por outro lado, os modelos de conector geralmente exibem mais de 20 consultas simultâneas. Se você quiser criar relatórios que sejam tão responsivos quanto os antigos para os quais foi usado, tente criar relatórios sem mais de 2-3 consultas por guia.

Para obter mais informações, consulte os seguintes artigos:

- [Guia de otimização do Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [Diretrizes de modelo DirectQuery](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Acho que eu insiro rotineiramente o limite de linha de 10.000 ao executar consultas. Como posso obter o conector para retornar mais de 10.000 linhas

O limite de linha de 10.000 é realmente especificado no final da API, e ele foi projetado para ajudar a melhorar significativamente o desempenho e reduzir o risco de erros de execução de consulta resultantes de condições de memória insuficiente.

Em vez de tentar aumentar a contagem de linhas do resultado, é melhor reestruturar seus relatórios de acordo com as práticas recomendadas do conector. Os modelos incluídos foram projetados para demonstrar essas práticas recomendadas. Sempre que possível, comece examinando seus KPIs usando dimensões mais amplas e inferiores de cardinalidade, como mês, ano, data, região, país, etc. De lá, você pode fazer uma busca detalhada em dimensões de cardinalidade cada vez mais altos. Os relatórios de helpdesk e local-avançado fornecem bons exemplos de fluxo de trabalho de busca detalhada.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados do CQD para Teams](CQD-Power-BI-query-templates.md)
