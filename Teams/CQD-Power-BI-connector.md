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
description: Instalar o conector do Power BI para usar modelos de consulta CQD
ms.openlocfilehash: c9987d05c5b057adf55791ffb2105d9ddb252722
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559359"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar o conector do Power BI para usar modelos de consulta CQD

Antes de poder usar os modelos de consulta do Power BI para CQD (arquivos PBIX), você precisará instalar o conector do Power BI para Microsoft CQD usando o arquivo *MicrosoftCallQuality. pqx* incluído no [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Leia [use o Power bi para analisar os dados do CQD para](CQD-Power-BI-query-templates.md) que as equipes aprendam sobre esses modelos.


## <a name="installation"></a>Instalação

O processo para instalar um conector personalizado e ajustar a segurança para permitir o uso do conector é descrito em detalhes na [documentação do Power bi](https://docs.microsoft.com/power-bi/desktop-connector-extensibility). Para simplificar, veja a seguir uma explicação rápida:

1.  Verifique se o seu computador já tem uma pasta * \[de\]\\conectores\\* personalizados da área de trabalho do Power bi desktop. Caso contrário, crie essa pasta. <sup>1</sup>

2.  Baixe o arquivo do conector (um * \*arquivo. Mez* ou * \*. pqx* ) e coloque-o no diretório de *conectores personalizados* .

3.  **Se o arquivo do conector for * \*um arquivo. Mez* ,** você também precisará ajustar as configurações de segurança conforme descrito na [documentação de instalação do conector personalizado](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security).

Se uma nova versão deste conector do Power BI para Microsoft Teams for lançada, basta substituir o arquivo de conector antigo no diretório de *conectores personalizados* pelo novo arquivo.

## <a name="setup"></a>Instalação

Para criar um relatório e executar consultas, primeiro será necessário se conectar à fonte de dados CQD. Siga as etapas abaixo para conectar-se:

1.  Na guia página inicial do Power BI desktop, clique em *obter dados*.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector1.png)

2.  A janela *obter dados* deve aparecer neste ponto. Navegue até *serviços online*e, em seguida, selecione *qualidade da chamada do Microsoft (beta)* e clique em *conectar*.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector2.png)

3.  Você será solicitado a entrar em Login. Use as mesmas credenciais usadas para o CQD. <sup>2</sup>

4.  O próximo prompt oferecerá a opção entre dois *modos de conectividade de dados*. Selecione *DirectQuery* e clique em *OK*.

5.  Por fim, você receberá um prompt final mostrando todo o modelo de dados para CQD. Nenhum dado estará visível nesse ponto, apenas o modelo de dados para CQD. Selecione *carregar* para concluir o processo de configuração.

6.  Nesse ponto, o Power BI carregará o modelo de dados no lado direito da janela. A página permanecerá em branco de outra forma, e nenhuma consulta será carregada por padrão. Vá para **criando consultas** abaixo para criar uma consulta e retornar dados.

Se qualquer uma das etapas durante este processo de configuração não fosse completamente clara, uma explicação mais detalhada sobre o processo pode ser encontrada [aqui](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Criando consultas

Depois que a instalação for concluída, você verá os nomes de várias centenas de dimensões e medidas de carga no painel *campos* . A criação de consultas reais aqui é simples, basta selecionar as dimensões e medidas desejadas para a sua consulta e, em seguida, arrastar e solte-os na página. Aqui está uma explicação mais detalhada, com um exemplo simples:

1.  Selecione a visualização que você deseja usar no painel *visualizações* . Uma versão em branco dessa visualização deve aparecer na página. Para os fins deste exemplo, usaremos a visualização de *tabela* .

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector3.png)

2.  Determine quais dimensões e medidas (denotadas por um símbolo de agregação pelo nome) você deseja usar para a sua consulta, selecione-as manualmente e arraste-as para a visualização preta. Como alternativa, arraste-os para o campo *valores* abaixo das opções de visualização.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector4.png)

**Observação importante:** O painel de qualidade da chamada requer uma medida para que qualquer consulta seja executada. Falha ao adicionar uma medida a uma consulta causará falha na consulta.

3.  Em seguida, selecione as dimensões que deseja filtrar e arraste-as para o campo *filtros nesse Visual* no painel *filtros* . No momento, o conector do Power BI do CQD dá suporte a *filtragem básica* (selecione valores em uma lista de possíveis valores de dimensão), *filtragem avançada* (especifique manualmente valores e operandos para filtrar, de forma semelhante ao CQD avançado) e *à filtragem de data relativa* (disponível somente para as dimensões de *hora de término* e hora de *início* ). A filtragem de acordo com a *N superior* não é suportada pela CQD.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector5.png)

4.  Por fim, selecione a guia *formato* no painel *visualizações* para estilizar e formatar sua consulta.

**Observação:** As consultas CQD exigem pelo menos uma medida para serem executadas. Se a sua consulta não carregar, verifique novamente se você incluiu uma medida na consulta.

## <a name="creating-a-drillthrough-report"></a>Criando um relatório detalhado

O [detalhamento do Power bi](https://docs.microsoft.com/power-bi/desktop-drillthrough) permite criar relatórios direcionados que você pode filtrar rapidamente usando os valores de outros relatórios como contexto. Depois que você sabe como criar sua primeira consulta com o conector CQD, criar um detalhamento é ainda mais simples.

1.  Crie outra página para o relatório prioritário e, em seguida, adicione suas consultas a essa página.

2.  Selecione a dimensão que você deseja usar como um filtro detalhado e arraste-os para o campo *Drillthrough* em no painel *visualizações* .

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector6.png)

3.  **Isso é\!** Qualquer outra consulta em outra página que use essa dimensão agora pode detalhar essa página, aplicando automaticamente o valor da dimensão de detalhamento como um filtro.

    ![Captura de tela: conector do Power BI](media/CQD-power-bi-connector7.png)

Ao contrário do CQD avançado, o Power BI dá suporte ao detalhamento não sequencial. Desde que uma consulta inclua a dimensão necessária, ela pode detalhar qualquer outra página.

## <a name="limitations"></a>Relacionadas

Apesar de fazer uso do Power BI, nem toda a funcionalidade do Power BI é compatível com o conector CQD, seja como resultado de limitações no modelo de dados CQD ou nos conectores DirectQuery em geral. A lista abaixo observa algumas das limitações mais importantes do conector, mas esta lista não deve ser considerada exaustiva:

1.  **Colunas calculadas –** Os conectores DirectQuery em geral têm suporte limitado para colunas calculadas no Power BI. Embora algumas colunas calculadas possam funcionar com o conector, elas devem ser consideradas exceções. Como regra geral, as colunas calculadas não funcionarão.

2.  **Agregações –** O modelo de dados CQD é criado em um modelo de cubo, o que significa que as agregações já têm suporte na forma de medidas. A tentativa de adicionar agregações manualmente a dimensões diferentes ou alterar o tipo de agregação de uma medida não funcionará com o conector, e isso geralmente resultará em um erro.

3.  **Elementos visuais personalizados-** Embora o conector CQD funcione com uma variedade de elementos visuais personalizados, não podemos garantir a compatibilidade com todos os elementos visuais personalizados. Muitos elementos visuais personalizados dependem do uso de colunas calculadas ou de dados importados, nenhum ou que são suportados pelos conectores DirectQuery.

4.  **Fazendo referência a dados armazenados em cache –** Atualmente, o Power BI não oferece suporte a referências a dados armazenados em cache de um conector DirectQuery de maneira alguma. Qualquer tentativa de fazer referência aos resultados de uma consulta resultará em uma nova consulta.

5.  **Filtragem de dados relativa –** É compatível com o conector CQD, mas somente com as dimensões *hora de início* e hora de *término* . Embora a dimensão de *Data* possa ser a opção óbvia para a filtragem de data relativa, a *Data* não é armazenada como um objeto de data/hora e, portanto, não oferece suporte a filtragem de data relativa no Power bi.

Observe que, embora o conector esteja em visualização, essas limitações provavelmente não mudarão com a versão final do conector. A maioria desses problemas é uma restrição do design do conector DirectQuery no Power BI ou fundamental para o design do modelo de dados CQD.

## <a name="error-codes"></a>Códigos de erro

Como o conector do Power BI do CQD é menos restrito do que o aplicativo do navegador em termos de tipos de consultas que você pode construir, ocasionalmente você pode encontrar vários erros ao criar suas consultas. No caso de receber uma mensagem de erro do tipo "CQDError. RunQuery – erro de execução de consulta ", consulte a lista abaixo com o número de ErrorType fornecido para solucionar o problema possível com a consulta. Estes são os códigos de tipo de erro mais comuns que você pode encontrar com o conector do Power BI do CQD:

  - **ErrorType 1-erro de estrutura de consulta:** Geralmente, um erro de estrutura de consulta é causado pelo conector que não consegue criar uma consulta formatada corretamente. Isso ocorre com mais frequência ao usar funcionalidades sem suporte, conforme especificado nas limitações acima. Verifique novamente se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 2-erro ao criar consulta:** Um erro de construção de consulta é causado pelo conector CQD não pode analisar corretamente a consulta que você está tentando compilar. Isso ocorre com mais frequência ao usar funcionalidades sem suporte, conforme especificado nas limitações acima. Verifique novamente se você não está usando colunas calculadas ou elementos visuais personalizados para essa consulta.

  - **ErrorType 5-tempo limite de execução:** A consulta atingiu o tempo de execução máximo possível antes do tempo limite. Tente adicionar mais filtros à consulta para limitar o escopo. Restringir o intervalo de dados é geralmente a maneira mais eficiente de conseguir isso.

  - **ErrorType 7-erro de medições:** As consultas CQD exigem uma medida para funcionar. Verifique novamente se a sua consulta inclui medida. As medidas no conector CQD são indicadas pelo símbolo de agregação (Sum) antes do nome.

Se você encontrar erros adicionais fora desse escopo, notifique a equipe do CQD para que possamos ajudá-lo a solucionar o problema e atualizar a documentação conforme apropriado.

## <a name="footnotes"></a>Notas

**<sup>1</sup>** alguns processos e aplicativos (por exemplo, o onedrive) podem fazer com que a pasta raiz dos seus documentos seja alterada; Verifique se o diretório de *conectores\\personalizados da área de trabalho do Power bi* está colocado dentro da pasta de documentos da pasta raiz atual.

**<sup>2</sup>** as credenciais de logon que você usa para o CQD *não* precisam ter as mesmas credenciais que você usa para fazer logon no próprio aplicativo da área de trabalho do Power bi.



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados do CQD para Teams](CQD-Power-BI-query-templates.md)