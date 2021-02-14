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
description: Instalar o Power BI Connector para usar modelos de consulta CQD (Painel de Qualidade de Chamada)
ms.openlocfilehash: c3812032f385a3428feec7f1126663e815af1b52
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611575"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar o Power BI Connector para usar modelos de consulta CQD

Antes de poder usar os modelos de consulta do Power BI (arquivos PBIX) para o Painel de Qualidade de Chamada do Microsoft Teams (CQD), você precisará instalar o Power BI Connector para Microsoft CQD, usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Leia [Use o Power BI para analisar dados CQD do Teams](CQD-Power-BI-query-templates.md) para saber mais sobre esses modelos.

Certifique-se de ter a função de [acesso CQD correta](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) para acessar os relatórios do Power BI.

> [!NOTE]
> O CQD Power BI Connector só é compatível com o DirectQuery no Power BI; Não há suporte para o modo de importação. 

## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para habilitar o uso do conector é descrito em detalhes na documentação [do Power BI.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility) Para o bem da simplicidade, aqui está uma explicação rápida:

1. Verifique se seu computador já tem uma pasta *\[ Documentos do Power BI Desktop \] \\ \\ Custom Connectors.* Caso não, crie esta pasta. <sup>1</sup>

2. Baixe o arquivo do conector (um *\* arquivo .mez* ou *\* .pqx)* e coloque-o no *diretório Conectores Personalizados.*

3. **Se o arquivo do conector for *\* um arquivo .mez,*** você também precisará ajustar suas configurações de segurança, conforme descrito na documentação de configuração [do conector personalizado.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)

Se uma nova versão deste Power BI Connector para Microsoft Teams for lançada, basta substituir o antigo arquivo do conector no diretório *Conectores Personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro você precisará se conectar à fonte de dados CQD. Siga as etapas abaixo para se conectar:

1. Na guia Página Home do Power BI Desktop, clique em *Obter Dados.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector1-resize.png)

2. A *janela Obter* Dados deve aparecer neste ponto. Navegue *até Os Serviços Online,* selecione Qualidade de Chamada da Microsoft *(Beta)* e clique em *Conectar.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector2-resize.png)

3. Você será solicitado a entrar em seguida. Use as mesmas credenciais que você usa para CQD. <sup>2</sup>

4. O próximo prompt lhe dará a opção entre dois modos *de Conectividade de Dados.* Selecione *DirectQuery* e clique em *OK.*

5. Por fim, você receberá um aviso final mostrando todo o modelo de dados do CQD. Nenhum dado ficará visível neste momento, somente o modelo de dados para CQD. Selecione *Carregar* para concluir o processo de configuração.

6. Neste ponto, o Power BI carregará o modelo de dados no lado direito da janela. Caso contrário, a página permanecerá em branco e nenhuma consulta será carregada por padrão. Vá para **a criação de consultas** abaixo para criar uma consulta e retornar dados.

Se qualquer uma das etapas durante esse processo de configuração não tiver sido totalmente clara, uma explicação mais detalhada sobre o processo poderá ser encontrada no Início Rápido: Conectar-se aos dados no [Power BI Desktop.](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>Criando consultas

Depois que a configuração for concluída, você verá os nomes das centenas de dimensões e medidas carregadas no *painel* Campos. Construir consultas reais a partir daqui é simples, basta selecionar as dimensões e medidas que você deseja para a sua consulta, em seguida, arraste-as e solte-as na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1. Selecione a visualização que você deseja usar no *painel* Visualizações. Uma versão em branco dessa visualização deve aparecer na página. Para os fins deste exemplo, vamos usar a visualização *tabela.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector3-resize.png)

2. Determine quais dimensões e medidas (anotadas por um símbolo de agregação pelo nome) que você deseja usar para sua consulta, selecione-as manualmente e arraste-as para a visualização preta. Como alternativa, arraste-os para o campo *Valores* abaixo das opções de visualização.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > O Painel de Qualidade da Chamada requer uma medida para que qualquer consulta seja executado. Se não adicionar uma medida a uma consulta, essa consulta falhará.

3. Em seguida, selecione as dimensões que você deseja filtrar e arraste-as para os Filtros neste *campo visual* no *painel* Filtros. O CQD Power BI Connector atualmente é compatível com filtragem básica (selecionar valores de uma lista de possíveis valores de dimensão), filtragem avançada (especificar manualmente valores  e operands para filtrar, semelhante ao CQD Avançado) e filtragem de data relativa *(disponível* somente para as dimensões Hora de Término e Hora de Início).    A filtragem de acordo com *o N* superior não é suportada pelo CQD.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector5-resize.png)

4. Por fim, selecione *a guia Formatar* no painel *Visualizações* para estilo e formatação da consulta.

    > [!NOTE]
    > As consultas CQD exigem pelo menos uma medida para ser executado. Se a consulta não carregar, verifique se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um Relatório Drillthrough

[Drillthrough in Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context. Depois que você sabe como criar sua primeira consulta com o CQD Connector, criar um drillthrough é ainda mais simples.

1. Crie outra página para o relatório com foco e adicione suas consultas a essa página.

2. Selecione a dimensão que você deseja usar como um filtro drillthrough e arraste-os para o campo *Drillthrough* no painel *Visualizações.*

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector6-resize.png)

3. **É isso\!** Qualquer outra consulta em outra página que usa essa dimensão agora pode fazer drillthrough nessa página, aplicando automaticamente o valor da dimensão drillthrough como um filtro.

    ![Captura de tela: Conector do Power BI](media/CQD-power-bi-connector7-resize.png)

Ao contrário do CQD Avançado, o Power BI oferece suporte a drillthrough não sequencial. Desde que uma consulta inclua a dimensão necessária, ela pode fazer drillthrough para qualquer outra página.

### <a name="best-practice"></a>Práticas práticas práticas

As consultas de conector de Qualidade de Chamada devem ser projetadas com a funcionalidade drillthrough em mente. Em vez de tentar carregar todos os dados de uma vez e, em seguida, cortar com filtros, comece com consultas mais amplas e de baixa cardinalidade e faça drill down para consultas de alta cardinalidade. Por exemplo, ao tentar diagnosticar quais sub-redes contribuem mais com problemas de qualidade, é útil primeiro identificar as regiões e países que contribuem com o problema e, em seguida, fazer uma busca drill down nas sub-redes nessa região ou país. Os modelos de conector de Qualidade de Chamada foram projetados dessa maneira para atuar como exemplo.

## <a name="limitations"></a>Limitações

Apesar de fazer uso do Power BI, nem todas as funcionalidades do Power BI são compatíveis com o CQD Connector, seja como resultado de limitações no modelo de dados CQD ou nos conectores do DirectQuery em geral. A lista a seguir observa algumas das limitações mais significativas do Conector, mas essa lista não deve ser considerada completa:

1. **Colunas Calculadas –** Os conectores do DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Embora algumas colunas calculadas possam funcionar com o Conector, elas devem ser consideradas exceções. Como regra geral, as colunas calculadas não funcionarão.

2. **Agregação –** O modelo de dados CQD é criado em um modelo de cubo, o que significa que as agregação já têm suporte na forma de medidas. Tentar adicionar agregações manualmente a dimensões diferentes ou alterar o tipo de agregação de uma medida não funcionará com o Conector, e isso geralmente resultará em um erro.

3. **Elementos visuais personalizados –** Embora o Conector CQD funcione com uma variedade de elementos visuais personalizados, não é possível garantir a compatibilidade com todos os elementos visuais personalizados. Muitos elementos visuais personalizados dependem do uso de colunas calculadas ou dados importados, nem dos quais são suportados por conectores do DirectQuery.

4. **Fazendo referência a dados armazenados em cache –** Atualmente, o Power BI não dá suporte a referência a dados armazenados em cache de um conector Do DirectQuery de nenhuma maneira. Qualquer tentativa de referência aos resultados de uma consulta resultará em uma nova consulta.

5. **Filtragem de Dados Relativos –** Tem suporte no Conector CQD, mas  somente com as dimensões Hora de Início e *Hora de* Término. Embora a *dimensão* Data possa ser a opção óbvia para filtragem de data *relativa,* a data não é armazenada como um objeto de data e hora e, portanto, não dá suporte à filtragem de data relativa no Power BI.

6. **Suporte a GCC (Government Community Cloud) –** Para clientes no ambiente GCC, o CQD Power BI Connector funcionará ao usar o Power BI Desktop. No momento, o conector do CQD Power BI não é compatível com o serviço Power BI para clientes GCC.

A maioria desses problemas são restrições ao design do conector DirectQuery no Power BI ou fundamentais para o design do modelo de dados CQD.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estou tentando usar a coluna Data como uma slicer de data. Assim que converter o tipo de dados desta coluna em Data, receberemos este erro

> **Não foi consegui carregar** os dados para este erro visual: OLE DB ou ODBC: [Expression.Error] Não foi consegui dobrar a expressão para a fonte de dados. Tente uma expressão mais simples.

Não há suporte para as slicers de data com o Power BI Connector. Para especificar um intervalo de datas, aplique dois filtros ao relatório, especificando um menor que e maior que a data.

Como alternativa, se as datas que você deseja exibir são recentes, aplique um filtro de data relativo para mostrar apenas os dados dos últimos N dias/semanas/meses.

## <a name="error-codes"></a>Códigos de Erro

Como o CQD Power BI Connector é menos restrito do que o aplicativo do navegador em termos de tipos de consultas que você pode construir, ocasionalmente você pode encontrar uma série de erros ao criar suas consultas. Caso você receba uma mensagem de erro do tipo "CQDError. RunQuery – Erro de Execução de Consulta", consulte a lista abaixo com o número ErrorType fornecido para solucionar o possível problema com a consulta. Veja a seguir os códigos de Tipo de Erro mais comuns que você pode encontrar com o Conector do Power BI CQD:

- **ErrorType 1 - Erro de Estrutura de Consulta:** Um erro de estrutura de consulta geralmente é causado pela falha do Conector ao criar uma consulta formatada corretamente. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 2 - Erro de construção de consulta:** Um erro de construção de consulta é causado pelo conector CQD não conseguir analisar corretamente a consulta que você está tentando criar. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 5 – Tempo de Execução:** A consulta atingiu o tempo de execução máximo possível antes do intervalo. Tente adicionar mais filtros à consulta para limitar seu escopo. Restringir o intervalo de dados geralmente é a maneira mais eficaz de conseguir isso.

  - **ErrorType 7 - No Measurements Error:** As consultas CQD exigem uma medida para funcionar. Verifique se sua consulta inclui medida. As medidas no Conector CQD são anotadas pelo símbolo de agregação (soma) antes do nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do CQD para que possamos ajudar a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Rodapé

**<sup>1</sup>** Determinados processos e aplicativos (por exemplo, o OneDrive) podem fazer com que a pasta raiz Documentos seja alterada; Certifique-se de que o *diretório Conectores \\ Personalizados* da Área de Trabalho do Power BI seja colocado dentro da pasta raiz atual Da pasta Documentos.

**<sup>2</sup>** As credenciais de logon  que você usa para o CQD não precisam ser as mesmas que você usa para fazer logon no próprio aplicativo da área de trabalho do Power BI.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando o Conector do Power BI será atualizado a partir do status "Beta"

Apesar da marca Beta, o Conector de Qualidade de Chamada para Power BI é a versão de lançamento do conector e foi oficializado como segurança assinada pela equipe do Power BI para refletir isso. O processo de certificação para remover essa marca Beta é extenso e requer um compromisso da equipe do Power BI para fornecer suporte direto ao conector também. Devido a restrições de tempo, a equipe do Power BI não consegue fornecer suporte e certificação mais ampla, mas ainda está preparado para atestar a segurança, a autenticidade e a funcionalidade geral do conector de Qualidade de Chamada da Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Por que o conector parece mais lento em comparação com o CQD Avançado no navegador? O que posso fazer para melhorar o desempenho

Na verdade, o desempenho da consulta para os vários modelos é o mesmo no navegador e no conector.  Assim como qualquer outro aplicativo autônomo, o Power BI adiciona seu tempo de autenticação e renderização ao nosso desempenho. Além disso, a diferença vem no número de consultas simultâneas que estão sendo executados. Como a versão no navegador do CQD tinha opções de visualização menos bem desenvolvidas e desdoarmada de informações, a maioria dos nossos relatórios estava limitada ao carregamento de consultas de 2 a 3 por vez. Por outro lado, os modelos de conector geralmente exibem mais de 20 consultas simultâneas. Se você quiser criar relatórios que sejam tão responsivos quanto os mais antigos, tente criar relatórios com no máximo 2 a 3 consultas por guia.

Para obter mais informações, consulte os seguintes artigos:

- [Guia de otimização do Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [Diretrizes de modelo do DirectQuery](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Acho que encontro rotineiramente o limite de 10.000 linhas ao executar consultas. Como faço para que o conector retorne mais de 10.000 linhas

O limite de 10.000 linhas na verdade é especificado no final da API e foi projetado para ajudar a melhorar significativamente o desempenho e reduzir o risco de erros de execução de consulta resultantes de condições de memória baixa.

Em vez de tentar aumentar a contagem de linhas de resultados, é melhor reestruture seus relatórios de acordo com as práticas recomendadas do conector. Os modelos que incluímos foram projetados para demonstrar essas práticas recomendadas. Sempre que possível, comece olhando para seus KPIs usando dimensões mais amplas e de menor cardinalidade, como Mês, Ano, Data, Região, País etc. A partir daí, você pode fazer uma drill down em dimensões cada vez mais altas de cardinalidade. Os Relatórios de Ajuda e Location-Enhanced fornecem bons exemplos desse fluxo de trabalho de drill down.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados CQD para o Teams](CQD-Power-BI-query-templates.md)
