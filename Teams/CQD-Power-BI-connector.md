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
ms.openlocfilehash: 534103fc2bec48566a1d0a57eeb390ed6ae0606c
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774746"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Instalar o conector de qualidade de chamada da Microsoft para o Power BI para usar modelos de consulta do Painel de Qualidade de Chamada

Antes de poder usar os modelos de consulta do Power BI (arquivos PBIX) para o CQD (Microsoft Teams Call Quality Dashboard), você precisará instalar o conector de Qualidade de Chamada da Microsoft para o Power BI, usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download](https://www.microsoft.com/download/details.aspx?id=102291).

Leia [Usar o Power BI para analisar dados CQD do Teams](CQD-Power-BI-query-templates.md) para saber mais sobre esses modelos.

Verifique se você tem a [função de acesso CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) correta para acessar os relatórios do Power BI.

> [!NOTE]
> O conector de Qualidade de Chamada da Microsoft só dá suporte ao DirectQuery no Power BI; Não há suporte para o modo de importação. 

## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para habilitar o uso do conector é descrito em detalhes na [documentação do Power BI](/power-bi/desktop-connector-extensibility). Por uma questão de simplicidade, aqui está uma explicação rápida:

1. Verifique se o computador já tem uma *\[pasta Documentos\]\\ Power BI Desktop\\ Custom Connectors*. Caso contrário, crie essa pasta. <sup>1</sup>

2. Baixe o arquivo do conector (um *\*arquivo .mez* ou *\*.pqx* ) e coloque-o no diretório *Conectores Personalizados* .

3. **Se o arquivo do conector for um *\*arquivo .mez* ,** você também precisará ajustar suas configurações de segurança, conforme descrito na [documentação de configuração do conector personalizado](/power-bi/desktop-connector-extensibility#data-extension-security).

Se uma nova versão do conector de Qualidade de Chamada da Microsoft for lançada, substitua o arquivo do conector antigo no diretório *Conectores Personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro você precisará se conectar à fonte de dados do CQD. Siga as etapas abaixo para se conectar:

1. Na guia Página Inicial do Power BI Desktop, clique em *Obter Dados*.

    ![Obtenha dados no Conector do Power BI.](media/CQD-power-bi-connector1-resize.png)

2. A janela *Obter Dados* deve ser exibida neste momento. Navegue até *Serviços Online*, selecione *Qualidade de Chamada da Microsoft (Beta)* e clique *em Conectar*.

    ![Qualidade de chamada da Microsoft no Conector do Power BI.](media/CQD-power-bi-connector2-resize.png)

3. Você será solicitado a entrar em seguida. Use as mesmas credenciais que você usa para o Painel de Qualidade de Chamada. <sup>2</sup>

4. O próximo prompt lhe dará a opção entre dois *modos de conectividade de dados*. Selecione *DirectQuery* e clique *em OK*.

5. Por fim, você receberá um prompt final mostrando todo o modelo de dados do Painel de Qualidade de Chamada. Nenhum dado ficará visível neste momento, apenas o modelo de dados para CQD. Selecione *Carregar* para concluir o processo de instalação.

6. Neste ponto, o Power BI carregará o modelo de dados no lado direito da janela. A página permanecerá em branco e nenhuma consulta será carregada por padrão. Prossiga para **Criar Consultas** abaixo para criar uma consulta e retornar dados.

Se alguma das etapas durante esse processo de instalação não estiver clara, uma explicação mais detalhada do processo poderá ser encontrada no [Início Rápido: conectar-se aos dados em Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Criando consultas

Depois que a configuração for concluída, você deverá ver os nomes de várias centenas de dimensões e medidas carregadas no painel *Campos* . A construção de consultas reais a partir daqui é simples, basta selecionar as dimensões e as medidas desejadas para sua consulta e arrastá-las e soltá-las na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1. Selecione a visualização que você deseja usar no painel *Visualizações* . Uma versão em branco dessa visualização deve ser exibida na página. Para fins deste exemplo, usaremos a visualização *tabela* .

    ![Painel visualizações no Conector do Power BI.](media/CQD-power-bi-connector3-resize.png)

2. Determine quais dimensões e medidas (denotadas por um símbolo de agregação pelo nome) você deseja usar para sua consulta e selecione-as manualmente e arraste-as para a visualização em preto. Como alternativa, arraste-os para o campo *Valores* abaixo das opções de visualização.

    ! Consulta de visualizações no Conector do Power BI.] (mídia/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Chamar o Painel de Qualidade requer uma medida para que qualquer consulta seja executada. A falha em adicionar uma medida a uma consulta fará com que essa consulta falhe.

3. Em seguida, selecione todas as dimensões nas quais você deseja filtrar e arraste-as para os *Filtros neste campo visual* no painel *Filtros* . Atualmente, o conector de Qualidade de Chamada da Microsoft dá suporte à *filtragem básica* (selecione valores de uma lista de valores de dimensão possíveis), *filtragem avançada* (especifique manualmente valores e operandos para filtrar, semelhante ao Painel de Qualidade de Chamada) e *Filtragem de data relativa* (disponível apenas para as dimensões *Hora de Término* e *Hora de Início* ). A filtragem de acordo com o *Top N* não é compatível com o Painel de Qualidade de Chamada.

    ![Filtros de visualizações no Conector do Power BI.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Os filtros só têm suporte quando aplicados a Dimensões. Não há suporte para filtragem nos valores das Medidas no Painel de Qualidade de Chamada.

4. Por fim, selecione a guia *Formatar* no painel *Visualizações* para estilizar e formatar sua consulta.

    > [!NOTE]
    > As consultas do Painel de Qualidade de Chamada exigem pelo menos uma medida para serem executadas. Se a consulta não for carregada, verifique se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um relatório de detalhamento

[O detalhamento no Power BI](/power-bi/desktop-drillthrough) permite criar relatórios focados que podem ser filtrados rapidamente usando os valores de outros relatórios como contexto. Depois de saber como criar sua primeira consulta com o conector de Qualidade de Chamada da Microsoft, a criação de um detalhamento é ainda mais simples.

1. Crie outra página para o relatório focado e adicione suas consultas a essa página.

2. Selecione a dimensão que você deseja usar como um filtro de detalhamento e arraste-os para o campo *Drillthrough* no painel *Visualizações* .

    ![Detalhamento no Conector do Power BI.](media/CQD-power-bi-connector6-resize.png)

3. **É isso.\!** Qualquer outra consulta em outra página que usa essa dimensão agora pode fazer drill through nessa página, aplicando automaticamente o valor da dimensão drillthrough como um filtro.

    ![Filtro de detalhamento no Conector do Power BI.](media/CQD-power-bi-connector7-resize.png)

Ao contrário do Painel de Qualidade de Chamada, o Power BI dá suporte a detalhamento não sequencial. Se uma consulta incluir a dimensão necessária, ela poderá percorrer qualquer outra página.

### <a name="best-practice"></a>Prática recomendada

As consultas do conector de Qualidade de Chamada da Microsoft devem ser projetadas com a funcionalidade de detalhamento em mente. Em vez de tentar carregar todos os dados de uma só vez e cortar com filtros, comece com consultas mais amplas e de baixa cardinalidade e faça consultas de alta cardinalidade. Por exemplo, ao tentar diagnosticar quais sub-redes contribuem mais para problemas de qualidade, é útil primeiro identificar as regiões e países que contribuem para o problema e, em seguida, detalhar as sub-redes nessa região ou país. Os modelos de conector de Qualidade de Chamada foram projetados dessa maneira para atuar como um exemplo.

## <a name="limitations"></a>Limitações

Apesar de usar o Power BI, nem todas as funcionalidades do Power BI são compatíveis com o conector de Qualidade de Chamada da Microsoft, seja como resultado de limitações no modelo de dados do Painel de Qualidade de Chamada ou nos conectores do DirectQuery em geral. A lista abaixo observa algumas das limitações mais notáveis do Conector, mas essa lista não deve ser considerada exaustiva:

1. **Colunas calculadas –** Os conectores DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Algumas colunas calculadas podem funcionar com o Conector, que essas colunas são exceções. Como regra geral, as colunas calculadas não funcionam.

2. **Agregações–** O modelo de dados do Painel de Qualidade de Chamada é criado em um modelo de cubo, o que significa que as agregações já têm suporte na forma de medidas. Tentar adicionar agregações manualmente a diferentes dimensões ou alterar o tipo de agregação de uma medida não funcionará com o Conector e, geralmente, resultará em um erro.

3. **Visuais personalizados –** Embora o conector de Qualidade de Chamada da Microsoft funcione com um intervalo de visuais personalizados, não é possível garantir a compatibilidade com todos os visuais personalizados. Muitos visuais personalizados dependem do uso de colunas calculadas ou dados importados, nenhum dos quais é compatível com conectores DirectQuery.

4. **Referenciando dados armazenados em cache –** Atualmente, o Power BI não dá suporte a referenciar dados armazenados em cache de um conector do DirectQuery de forma alguma. Qualquer tentativa de fazer referência aos resultados de uma consulta resultará em uma nova consulta.

5. **Filtragem de dados relativos –** Há suporte no conector de Qualidade de Chamada da Microsoft, mas somente com as dimensões *Hora de Início* e *Hora de Término* . Embora a dimensão *Date* possa ser a opção óbvia para filtragem de data relativa, *Date* não é armazenado como um objeto de data e, portanto, não dá suporte à filtragem de data relativa no Power BI.

6. **Consultas somente de medição –** Não há suporte neste momento no conector de Qualidade de Chamada da Microsoft. Ao criar uma visualização com três ou mais medidas e nenhuma dimensão, os dados da coluna serão transpostos. Para evitar isso, inclua sempre pelo menos uma dimensão (por exemplo: Ano De Mês) em suas visualizações. Isso está previsto para ser resolvido em uma próxima versão do conector de Qualidade de Chamada da Microsoft para o Power BI.

7. **Suporte ao GCC (Government Community Cloud) –** Para clientes no ambiente de GCC, o conector de Qualidade de Chamada da Microsoft funcionará somente ao usar Power BI Desktop. O conector de Qualidade de Chamada da Microsoft não é atualmente compatível com o serviço do Power BI para clientes GCC.

A maioria desses problemas são restrições ao design do conector DirectQuery no Power BI ou fundamentais para o design do modelo de dados CQD.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estou tentando usar a coluna Date como uma segmentação de data. Assim que eu converter o tipo de dados desta coluna em Date, recebo este erro

> **Não foi possível carregar os dados para este visual**: erro OLE DB ou ODBC: [Expression.Error] Não foi possível dobrar a expressão para a fonte de dados. Tente uma expressão mais simples.

Não há suporte para segmentações de data com o conector de Qualidade de Chamada da Microsoft. Para especificar um intervalo de datas, aplique dois filtros ao relatório, especificando um menor e maior que a data.

Como alternativa, se as datas que você deseja exibir forem recentes, aplique um filtro de data relativo para mostrar apenas os dados dos últimos N dias/semanas/meses.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Quando adiciono determinadas dimensões aos meus relatórios, o visual retorna imediatamente **"Não foi possível carregar os dados para este visual"**. Remover a dimensão corrige o visual .

Esse é um problema conhecido no conector de Qualidade de Chamada da Microsoft; qualquer dimensão exposta como um número inteiro será exibida no Power BI como uma coluna 'agregada', em que o Power BI tentará uma ação de resumo padrão (normalmente 'Soma'). Em alguns casos, esse comportamento terá êxito em resumir os valores, embora o resultado não seja útil, já que a "soma" de uma dimensão como o Segundo Canal wi-fi não tem sentido. Em outros casos, essa ação de resumo falhará e causará erros no visual.

Para contornar esse problema, comece removendo a dimensão do visual. Selecione a dimensão na lista 'Campos', navegue até a guia 'Ferramentas de coluna' na faixa de opções, clique no menu suspenso 'Resumir' e selecione **Não resumir**. A dimensão agora pode ser adicionada ao visual novamente.


## <a name="error-codes"></a>Códigos de erro

Como o conector de Qualidade de Chamada da Microsoft para Power BI é menos restrito do que o aplicativo do navegador em termos de tipos de consultas que você pode construir, você pode ocasionalmente encontrar uma série de erros ao criar suas consultas. No caso de você receber uma mensagem de erro do tipo "CQDError. RunQuery – Erro de Execução de Consulta", faça referência à lista abaixo com o número ErrorType fornecido para solucionar problemas possíveis com a consulta. A seguir estão os códigos de tipo de erro mais comuns que você pode encontrar com o Conector do Power BI do CQD:

- **ErrorType 1 – Erro da estrutura de consulta:** Um erro de estrutura de consulta normalmente é causado pela falha do Conector em criar uma consulta formatada corretamente. Isso acontece com mais frequência ao usar funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou visuais personalizados para essa consulta.

  - **ErrorType 2 – Erro de construção de consulta:** Um erro de criação de consulta é causado pelo conector de Qualidade de Chamada da Microsoft não conseguir analisar corretamente a consulta que você está tentando criar. Isso acontece com mais frequência ao usar funcionalidade sem suporte, conforme especificado nas Limitações acima. Verifique se você não está usando colunas calculadas ou visuais personalizados para essa consulta.

  - **ErrorType 5 – Tempo limite de execução:** A consulta atingiu o máximo de tempo de execução possível antes do tempo limite. Tente adicionar mais filtros à consulta para limitar seu escopo. Restringir o intervalo de dados geralmente é a maneira mais eficaz de conseguir isso.

  - **ErrorType 7 – Sem erro de medidas:** As consultas do Painel de Qualidade de Chamada exigem uma medida para funcionar. Verifique se a consulta inclui medida. As medidas no conector de Qualidade de Chamada da Microsoft são denotadas pelo símbolo de agregação (soma) antes de seu nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do Painel de Qualidade de Chamada para que possamos ajudar a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Rodapé

**<sup>1</sup>** Determinados processos e aplicativos (por exemplo, OneDrive) podem fazer com que sua pasta raiz Documentos seja alterada; verifique se o *diretório Power BI Desktop\\ Custom Connectors* é colocado dentro da pasta raiz atual Documentos.

**<sup>2</sup>** As credenciais de logon que você usa para o Painel de Qualidade de Chamada *não* precisam ser as mesmas credenciais que você usa para fazer logon no próprio aplicativo Power BI Desktop.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando o Conector do Power BI será atualizado do status "Beta"?

Apesar da marca Beta, o conector Beta (Qualidade de Chamada da Microsoft) para Power BI é a primeira versão de "versão" do conector e foi oficialmente assinado pela equipe do Power BI para refletir isso. No momento da versão inicial do conector, a equipe do Power BI não pôde fornecer suporte e certificação mais ampla, mas ainda estava preparada para atestar a segurança, a autenticidade e a funcionalidade geral do conector de Qualidade de Chamada da Microsoft. Olhando para frente, estamos planejando investir no conector de Qualidade de Chamada da Microsoft para o Power BI em um futuro próximo.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Por que o conector parece mais lento em comparação com o Painel de Qualidade de Chamada no navegador? O que posso fazer para melhorar o desempenho?

O desempenho da consulta para os vários modelos é, na verdade, o mesmo no navegador e no conector.  Assim como qualquer outro aplicativo autônomo, o Power BI adiciona seu tempo de autenticação e renderização ao nosso desempenho. Além disso, a diferença vem no número de consultas simultâneas que estão sendo executadas. Como a versão no navegador do Painel de Qualidade de Chamada tinha opções de visualização menos bem desenvolvidas e densas de informações, a maioria dos nossos relatórios estava limitada ao carregamento de consultas 2-3 por vez. Por outro lado, os modelos de conector geralmente exibem mais de 20 consultas simultâneas. Se você quiser criar relatórios tão responsivos quanto os mais antigos aos quais você estava acostumado, tente criar relatórios com no máximo 2 a 3 consultas por guia.

Para obter mais informações, confira os seguintes artigos:

- [Guia de otimização do Power BI](/power-bi/guidance/power-bi-optimization)
- [Diretrizes de modelo do DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Acho que corro rotineiramente para o limite de 10.000 linhas ao executar consultas. Como fazer com que o conector retorne mais de 10.000 linhas?

O limite de 10.000 linhas é realmente especificado no final da API e foi projetado para ajudar a melhorar significativamente o desempenho e reduzir o risco de erros de execução de consulta resultantes de baixas condições de memória.

Em vez de tentar aumentar a contagem de linhas de resultados, é melhor reestruturar seus relatórios de acordo com as melhores práticas do conector. Os modelos que incluímos foram projetados para demonstrar essas práticas recomendadas. Sempre que possível, comece examinando seus KPIs usando dimensões mais amplas e de menor cardinalidade, como Mês, Ano, Data, Região, País etc. A partir daí, você pode detalhar em dimensões cada vez mais altas de cardinalidade. Os Relatórios de Helpdesk e Location-Enhanced fornecem bons exemplos desse fluxo de trabalho de detalhamento.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados do CQD para o Teams](CQD-Power-BI-query-templates.md)
