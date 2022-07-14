---
title: Instalar o Conector do Power BI para usar modelos de consulta CQD
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Instalar o Conector do Power BI para usar modelos de consulta CQD (Painel de Qualidade de Chamada)
ms.openlocfilehash: 80d1b39c6fbe26f04998b06b22fb527b60bbb6a0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789866"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Instalar o conector de Qualidade de Chamada da Microsoft para Power BI para usar modelos de consulta do Painel de Qualidade de Chamadas

Antes de usar os modelos de consulta do Power BI (arquivos PBIX) para o Painel de Qualidade de Chamadas do Microsoft Teams (CQD), você precisará instalar o conector de Qualidade de Chamada da Microsoft para Power BI, usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).

Leia [Use o Power BI para analisar dados do CQD para o Teams](CQD-Power-BI-query-templates.md) para saber mais sobre esses modelos.

Verifique se você tem a função de acesso [CQD correta](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para acessar os relatórios do Power BI.

> [!NOTE]
> O conector de Qualidade de Chamada da Microsoft dá suporte apenas ao DirectQuery no Power BI; Não há suporte para o modo de importação. 

## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para habilitar o uso do conector é descrito em detalhes na documentação [do Power BI](/power-bi/desktop-connector-extensibility). Para simplificar, aqui está uma explicação rápida:

1. Verifique se o computador já tem uma *pasta\[ Documents\]\\ Power BI Desktop\\ Custom Connectors*. Caso contrário, crie esta pasta. <sup>1</sup>

2. Baixe o arquivo do conector (um *\*arquivo .mez* *\*ou .pqx* ) e coloque-o no *diretório Conectores Personalizados* .

3. **Se o arquivo do conector for *\*um arquivo .mez* ,** você também precisará ajustar suas configurações de segurança, conforme descrito na documentação de configuração [do conector personalizado](/power-bi/desktop-connector-extensibility#data-extension-security).

Se uma nova versão do conector de Qualidade de Chamada da Microsoft for lançada, substitua o arquivo do conector antigo no diretório Conectores *Personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro você precisará se conectar à fonte de dados CQD. Siga as etapas abaixo para se conectar:

1. Na guia Página Inicial do Power BI Desktop, clique em *Obter Dados*.

    ![Obter dados no Conector do Power BI.](media/CQD-power-bi-connector1-resize.png)

2. A *janela Obter* Dados deve aparecer neste ponto. Navegue *até Serviços Online*, selecione *Qualidade de Chamada da Microsoft (Beta)* e clique em *Conectar*.

    ![Qualidade de Chamada da Microsoft no Conector do Power BI.](media/CQD-power-bi-connector2-resize.png)

3. Você será solicitado a entrar em seguida. Use as mesmas credenciais que você usa para o Painel de Qualidade de Chamadas. <sup>2</sup>

4. O próximo prompt fornecerá a opção entre dois *modos de Conectividade de Dados*. Selecione *DirectQuery e* pressione *OK*.

5. Por fim, você receberá um prompt final mostrando todo o modelo de dados para o Painel de Qualidade de Chamada. Nenhum dado ficará visível neste ponto, somente o modelo de dados para CQD. Selecione *Carregar* para concluir o processo de instalação.

6. Neste ponto, o Power BI carregará o modelo de dados no lado direito da janela. Caso contrário, a página permanecerá em branco e nenhuma consulta será carregada por padrão. **Prossiga para a criação de** consultas abaixo para criar uma consulta e retornar dados.

Se qualquer uma das etapas durante esse processo de instalação não estiver clara, uma explicação mais detalhada do processo poderá ser encontrada no Início Rápido: Conectar-se aos dados [no Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Criando consultas

Depois que a instalação for concluída, você deverá ver os nomes de várias centenas de dimensões e medidas carregadas no *painel* Campos. A construção de consultas reais daqui é simples, basta selecionar as dimensões e medidas desejadas para a consulta e, em seguida, arrastá-las e soltar na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1. Selecione a visualização que você deseja usar no *painel Visualizações* . Uma versão em branco dessa visualização deve aparecer na página. Para os fins deste exemplo, usaremos a visualização *tabela* .

    ![Painel Visualizações no Conector do Power BI.](media/CQD-power-bi-connector3-resize.png)

2. Determine quais dimensões e medidas (indicadas por um símbolo de agregação pelo nome) que você deseja usar para sua consulta e, em seguida, selecione-as manualmente e arraste-as para a visualização preta. Como alternativa, arraste-os para o campo *Valores* abaixo das opções de visualização.

    ! Consulta de visualizações no Conector do Power BI.] (media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > O Painel de Qualidade de Chamadas requer uma medida para que qualquer consulta seja executada. Se não adicionar uma medida a uma consulta, essa consulta falhará.

3. Em seguida, selecione as dimensões nas quais você deseja filtrar e arraste-as para os Filtros neste *campo visual* no *painel* Filtros. Atualmente, o conector de Qualidade de Chamada da Microsoft dá suporte à filtragem *Básica (selecione* valores de uma lista de possíveis valores de *dimensão), filtragem* avançada (especifique manualmente valores e operandos para filtrar, semelhante ao Painel de Qualidade da Chamada) e  filtragem de  data *relativa (disponível* somente para as dimensões Hora de Término e Hora de Início). Não há suporte para filtragem de acordo com o *Top N* no Painel de Qualidade de Chamadas.

    ![Filtros de visualizações no Conector do Power BI.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Os filtros só têm suporte quando aplicados a Dimensões. Não há suporte para filtragem nos valores de Medidas no Painel de Qualidade da Chamada.

4. Por fim, selecione *a guia* Formatar no painel *Visualizações* para estilizar e formatar sua consulta.

    > [!NOTE]
    > As consultas do Painel de Qualidade de Chamada exigem pelo menos uma medida para serem executadas. Se a consulta não for carregada, verifique duas vezes se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um relatório de detalhamento

[O detalhamento no Power BI](/power-bi/desktop-drillthrough) permite que você crie relatórios focados que você pode filtrar rapidamente usando os valores de outros relatórios como contexto. Depois de saber como criar sua primeira consulta com o conector de Qualidade de Chamada da Microsoft, a criação de um detalhamento é ainda mais simples.

1. Crie outra página para o relatório focado e adicione suas consultas a essa página.

2. Selecione a dimensão que você deseja usar como um filtro de detalhamento e arraste-as  para o campo Detalhamento no painel *Visualizações*.

    ![Detalhamento no Conector do Power BI.](media/CQD-power-bi-connector6-resize.png)

3. **É isso mesmo.\!** Qualquer outra consulta em outra página que usa essa dimensão agora pode detalhar essa página, aplicando automaticamente o valor da dimensão de detalhamento como um filtro.

    ![Filtro de detalhamento no Conector do Power BI.](media/CQD-power-bi-connector7-resize.png)

Ao contrário do Painel de Qualidade de Chamadas, o Power BI dá suporte ao detalhamento não sequencial. Se uma consulta incluir a dimensão necessária, ela poderá fazer drill-through para qualquer outra página.

### <a name="best-practice"></a>Prática recomendada

As consultas do conector de Qualidade de Chamada da Microsoft devem ser projetadas com a funcionalidade de detalhamento em mente. Em vez de tentar carregar todos os dados de uma vez e, em seguida, reduzir com filtros, comece com consultas mais amplas e de baixa cardinalidade e faça drill down para consultas de alta cardinalidade. Por exemplo, ao tentar diagnosticar quais sub-redes contribuem mais para problemas de qualidade, é útil primeiro identificar essas regiões e países que contribuem para o problema e, em seguida, fazer uma busca detalhada nas sub-redes nessa região ou país. Os modelos de conector de Qualidade de Chamada foram projetados dessa maneira para atuar como um exemplo.

## <a name="limitations"></a>Limitações

Apesar de usar o Power BI, nem todas as funcionalidades do Power BI são compatíveis com o conector de Qualidade de Chamada da Microsoft, seja como resultado de limitações no modelo de dados do Painel de Qualidade de Chamada ou em conectores DirectQuery em geral. A lista abaixo observa algumas das limitações mais importantes do Conector, mas essa lista não deve ser considerada exaustiva:

1. **Colunas Calculadas –** Os conectores do DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Algumas colunas calculadas podem funcionar com o Conector, que essas colunas são exceções. Como regra geral, as colunas calculadas não funcionam.

2. **Agregações –** O modelo de dados do Painel de Qualidade de Chamada é criado em um modelo de cubo, o que significa que as agregações já têm suporte na forma de medidas. Tentar adicionar agregações manualmente a dimensões diferentes ou alterar o tipo de agregação de uma medida não funcionará com o Conector e geralmente resultará em um erro.

3. **Visuais personalizados –** Embora o conector de Qualidade de Chamada da Microsoft funcione com uma variedade de visuais personalizados, não é possível garantir a compatibilidade com todos os visuais personalizados. Muitos visuais personalizados dependem do uso de colunas calculadas ou dados importados, nenhum dos quais é compatível com conectores DirectQuery.

4. **Referenciando dados armazenados em cache –** Atualmente, o Power BI não dá suporte à referência a dados armazenados em cache de um conector directQuery de nenhuma maneira. Qualquer tentativa de referenciar os resultados de uma consulta resultará em uma nova consulta.

5. **Filtragem de dados relativos –** Há suporte no conector de Qualidade de Chamada da Microsoft, mas apenas com as dimensões *Hora* de Início e *Hora de* Término. Embora a *dimensão Data* possa ser a escolha óbvia para filtragem de data *relativa, a* data não é armazenada como um objeto de data e hora e, portanto, não dá suporte à filtragem de data relativa no Power BI.

6. **Consultas somente de medida -** Não há suporte no momento no conector de Qualidade de Chamada da Microsoft. Ao criar uma visualização com três ou mais medidas e nenhuma dimensão, os dados da coluna serão transpostos. Para evitar isso, sempre inclua pelo menos uma dimensão (por exemplo: Mês Ano) em suas visualizações. Isso é agendado para ser resolvido em uma versão futura do conector de Qualidade de Chamada da Microsoft para o Power BI.

7. **Suporte do GCC (Government Community Cloud) –** Para clientes no ambiente GCC, o conector de Qualidade de Chamada da Microsoft funcionará ao usar Power BI Desktop somente. Atualmente, o conector de Qualidade de Chamada da Microsoft não é compatível com o serviço do Power BI para clientes GCC.

A maioria desses problemas são restrições ao design do conector DirectQuery no Power BI ou fundamentais para o design do modelo de dados CQD.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estou tentando usar a coluna Data como uma segmentação de data. Assim que eu converter o tipo de dados desta coluna em Data, eu receber esse erro

> **Não foi possível** carregar os dados deste visual: erro OLE DB ou ODBC: [Expression.Error] Não foi possível dobrar a expressão para a fonte de dados. Tente uma expressão mais simples.

Não há suporte para segmentações de dados com o conector de Qualidade de Chamada da Microsoft. Para especificar um intervalo de datas, aplique dois filtros ao relatório, especificando uma data menor que e maior que.

Como alternativa, se as datas que você deseja exibir forem recentes, aplique um filtro de data relativa para mostrar apenas os dados dos últimos N dias/semanas/meses.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Quando eu adicionar determinadas dimensões aos meus relatórios, o visual retornará imediatamente "Não foi possível carregar **os dados para este visual"**. Remover a dimensão corrige o visual. O que está acontecendo?

Esse é um problema conhecido no conector de Qualidade de Chamada da Microsoft; qualquer dimensão exposta como um número inteiro aparecerá no Power BI como uma coluna "agregação", em que o Power BI tentará uma ação de resumo padrão (normalmente 'Soma'). Em alguns casos, esse comportamento terá êxito ao somar os valores, mesmo que o resultado não seja útil, pois a "soma" de uma dimensão como o Segundo Canal WiFi não tem sentido. Em outros casos, essa ação de resumo falhará e causará erros no visual.

Para contornar esse problema, comece removendo a dimensão do visual. Selecione a dimensão na lista 'Campos', navegue até a guia 'Ferramentas de coluna' na faixa de opções, clique no menu suspenso 'Resumo' e selecione Não **resumir**. A dimensão agora pode ser adicionada ao visual novamente.


## <a name="error-codes"></a>Códigos de erro

Como o conector de Qualidade de Chamada da Microsoft para Power BI é menos restrito do que o aplicativo de navegador em termos de tipos de consultas que você pode construir, ocasionalmente, você pode encontrar vários erros ao criar suas consultas. Caso você receba uma mensagem de erro do tipo "CQDError. RunQuery – Erro de execução de consulta", consulte a lista abaixo com o número ErrorType fornecido para solucionar o possível problema com a consulta. A seguir estão os códigos de Tipo de Erro mais comuns que você pode encontrar com o CQD Power BI Connector:

- **ErrorType 1 – Erro de estrutura de consulta:** Um erro de estrutura de consulta normalmente é causado pela falha do Conector ao criar uma consulta formatada corretamente. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou visuais personalizados para essa consulta.

  - **ErrorType 2 – Erro de construção da consulta:** Um erro de criação de consulta é causado pelo conector de Qualidade de Chamada da Microsoft não conseguir analisar corretamente a consulta que você está tentando criar. Isso acontece com mais frequência ao usar a funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou visuais personalizados para essa consulta.

  - **ErrorType 5 – Tempo Limite de Execução:** A consulta atingiu o tempo de execução máximo possível antes do tempo limite. Tente adicionar mais filtros à consulta para limitar seu escopo. Restringir o intervalo de dados geralmente é a maneira mais eficaz de fazer isso.

  - **ErrorType 7 – Erro sem medidas:** As consultas do Painel de Qualidade de Chamada exigem uma medida para funcionar. Verifique se a consulta inclui medida. As medidas no conector de Qualidade de Chamada da Microsoft são indicadas pelo símbolo de agregação (soma) antes de seu nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do Painel de Qualidade de Chamada para que possamos ajudar a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Rodapé

**<sup>1</sup>** Determinados processos e aplicativos (por exemplo, OneDrive) podem fazer com que a pasta raiz documentos seja alterada; verifique se o diretório *Power BI Desktop\\ Conectores personalizados* está colocado dentro da pasta documentos da pasta raiz atual.

**<sup>2</sup>** As credenciais de logon que você usa para o Painel  de Qualidade de Chamada não precisam ser as mesmas que você usa para fazer logon Power BI Desktop aplicativo em si.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando o Conector do Power BI será atualizado do status "Beta"?

Apesar da marca Beta, o conector de Qualidade de Chamada da Microsoft (Beta) para Power BI é a primeira versão de "versão" do conector e foi oficialmente assinado pela equipe do Power BI para refletir isso. No momento da versão inicial do conector, a equipe do Power BI não pôde fornecer suporte e certificação mais ampla, mas ainda estava preparada para atestar a segurança, a autenticidade e a funcionalidade geral do conector de Qualidade de Chamada da Microsoft. Olhando para frente, estamos planejando investir no conector de Qualidade de Chamada da Microsoft para o Power BI em um futuro próximo.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Por que o conector parece mais lento em comparação com o Painel de Qualidade de Chamada no navegador? O que posso fazer para melhorar o desempenho?

O desempenho da consulta para os vários modelos é, na verdade, o mesmo no navegador e no conector.  Assim como qualquer outro aplicativo autônomo, o Power BI adiciona seu tempo de autenticação e renderização ao nosso desempenho. Além disso, a diferença ocorre no número de consultas simultâneas que estão sendo executadas. Como a versão no navegador do Painel de Qualidade de Chamadas tinha opções de visualização menos bem desenvolvidas e densas de informações, a maioria dos nossos relatórios estava limitada ao carregamento de 2 a 3 consultas por vez. Por outro lado, os modelos de conector geralmente exibem mais de 20 consultas simultâneas. Se você quiser criar relatórios que sejam tão responsivos quanto os mais antigos aos quais você estava acostumado, tente criar relatórios com no máximo 2 a 3 consultas por guia.

Para obter mais informações, consulte os seguintes artigos:

- [Guia de otimização para o Power BI](/power-bi/guidance/power-bi-optimization)
- [Diretrizes de modelo do DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Eu acho que eu rotineiramente encontro o limite de 10.000 linhas ao executar consultas. Como fazer com que o conector retorne mais de 10.000 linhas?

O limite de 10.000 linhas é realmente especificado no final da API e foi projetado para ajudar a melhorar significativamente o desempenho e reduzir o risco de erros de execução de consulta resultantes de condições de memória insuficiente.

Em vez de tentar aumentar a contagem de linhas de resultado, é melhor reestruturar seus relatórios de acordo com as práticas recomendadas do conector. Os modelos que incluímos foram projetados para demonstrar essas práticas recomendadas. Sempre que possível, comece examinando seus KPIs usando dimensões mais amplas e de cardinalidade mais baixa, como Mês, Ano, Data, Região, País, etc. A partir daí, você pode fazer drill down em dimensões de cardinalidade cada vez mais altas. O Helpdesk e Location-Enhanced relatórios fornecem bons exemplos desse fluxo de trabalho de busca detalhada.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados do CQD para o Teams](CQD-Power-BI-query-templates.md)
