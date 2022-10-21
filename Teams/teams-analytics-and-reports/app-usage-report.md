---
title: Relatório de uso de aplicativo do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso do aplicativo Teams no centro de administração do Teams para conhecer as equipes ativas e os usuários de um aplicativo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c907dc44ff7b76b3df94843d6e33f4a711b37721
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655877"
---
# <a name="microsoft-teams-app-usage-report"></a>Relatório de uso de aplicativo do Microsoft Teams

O relatório de uso do aplicativo Teams no centro de administração do Microsoft Teams fornece insights sobre quais aplicativos os usuários estão usando no Teams. Você pode obter insights sobre a atividade de aplicativos em sua organização para diferentes aplicativos microsoft (Viva learning, Shifts etc), terceiros (Polly, Trello etc.) & aplicativos do Teams de Linha de Negócios (LOB).   

Você pode usar este relatório para entender onde exatamente diferentes aplicativos estão sendo usados e aprofundar os dados de utilização por aplicativo.

Os dados representados neste relatório fornecem respostas para as seguintes perguntas:

-  Quantos aplicativos instalados os usuários em seu ambiente têm?
-  Quantos aplicativos têm pelo menos um usuário ativo em seu ambiente com base no tipo (Microsoft, terceiros e LOB)?
-  Quantos aplicativos estão sendo usados por plataforma (Windows, Mac, Web ou mobile)?
-  Quantos usuários ativos e equipes ativas estão usando um aplicativo?

> [!NOTE]
> O uso de aplicativos LOB **carregados** de lado não está incluído neste relatório.

Este artigo explica como acessar o relatório e exibir e interpretar as várias métricas dentro do relatório. 

## <a name="view-the-app-usage-report"></a>Exibir o relatório de uso do aplicativo

Você deve ser um administrador global, um leitor global ou um administrador de serviço do Teams para exibir os relatórios no centro de administração do Microsoft Teams. Veja [ Use funções de administrador Teams para gerenciar o Teams](../using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **Análise & relatórios** > **Relatórios de uso**. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de aplicativos**.

2. Em **Intervalo de datas**, selecione um intervalo e selecione **Executar relatório**.

:::image type="content" alt-text="Captura de tela do relatório de uso do aplicativo Teams no centro de administração do Teams com callouts." source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso do aplicativo pode ser exibido para tendências nos últimos 7, 30, 90 e 180 dias. |
|**2**   |Cada relatório tem uma data de geração. Os relatórios geralmente refletem uma latência de 24 a 48 horas do momento em que um aplicativo foi usado. Por exemplo, os dados de 10 de janeiro devem aparecer no relatório por volta de 12 de janeiro. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y é a contagem de itens.</li> </ul>Passe o mouse sobre o ponto que representa um item em uma determinada data para ver o número de instâncias desse item nessa data.|
|**4**   |Você pode filtrar o que vê no gráfico selecionando um item na legenda. Por exemplo, selecione **Aplicativos Ativos da Microsoft**, **Total de aplicativos instalados** e muito mais para ver apenas as informações relacionadas a cada um deles. Ao alterar esta seleção, as informações da tabela não são alteradas. <ul><li>**Aplicativos Microsoft ativos** são o número de aplicativos da Microsoft (por exemplo, aprendizado do Viva) usados em toda a sua organização. </li> <li>**Aplicativos de terceiros ativos** são o número de aplicativos de terceiros (por exemplo, Polly) usados em toda a sua organização.  </li> <li>**Os aplicativos LOB ativos** são o número de aplicativos de Linha de Negócios usados em toda a sua organização. </li><li>**O total de aplicativos ativos** é o número total de aplicativos usados em toda a sua organização. </li><li>**O total de aplicativos inativos** é o número de aplicativos não usados em sua organização. </li><li>**O total de aplicativos instalados** é o número total de aplicativos instalados em sua organização. A data de início de todas as métricas de instalação é outubro de 2021. Somente os aplicativos instalados após essa data serão contados.</li></ul> O gráfico mostra métricas agregadas em toda a organização em cada dia em um período selecionado. Por exemplo, se você selecionar 28 de janeiro e a métrica **Aplicativos de terceiros ativos**, o gráfico mostrará o número total de aplicativos de terceiros usados em 28 de janeiro em sua organização.  |
|**5**   |A tabela fornece uma divisão do uso por cada aplicativo. <ul><li>**A ID** do aplicativo é o identificador de aplicativo externo presente no manifesto do aplicativo. <br/>Mais informações sobre o aplicativo podem ser encontradas na [seção Gerenciar aplicativos no centro de administração do Teams](/microsoftteams/manage-apps) , referindo-se a ele usando essa ID de Aplicativo externa.</li> <li>**O nome** do aplicativo é o nome desse aplicativo como presente no manifesto do aplicativo. </li> <li>**O Publicador** é o editor desse aplicativo como presente no manifesto do aplicativo. Isso só está disponível para aplicativos publicados na Loja global.</li> <li>**O Teams que usa esse aplicativo** é o número de equipes distintas do Teams que têm pelo menos um usuário usando este aplicativo. </li><li>**Os usuários que usam esse aplicativo** são o número de usuários distintos em sua organização que estão usando este aplicativo.</li> <li>**Usado no Windows** indica se esse aplicativo foi usado no Windows por pelo menos um usuário em sua organização.</li><li>**Usado no Mac** indica se esse aplicativo foi usado no MAC por pelo menos um usuário em sua organização.</li><li>**Usado na Web** indica se esse aplicativo foi usado na Web por pelo menos um usuário em sua organização. </li> <li>**A última data usada** é a data em que esse aplicativo foi usado pela última vez por qualquer pessoa em sua organização. </li></ul> |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Exporte o relatório para um arquivo CSV para análise offline. Selecione o ícone **Exportar para Excel** e o relatório será baixado no navegador.|
|**8** |Os dados de série temporal representados no gráfico superior mostram diferentes métricas de uso agregadas para todo o locatário.|
|**9** |Os dados tabulares representados na metade inferior mostram diferentes métricas de uso agregadas por equipe.|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>Gerenciando aplicativos no centro de administração do Microsoft Teams

Para obter mais informações sobre como gerenciar seus aplicativos do Teams, consulte [Sobre aplicativos no Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Para vincular um aplicativo neste relatório à experiência Gerenciar Aplicativos no centro de administração do Microsoft Teams, você pode usar o seguinte:

- Nome do aplicativo
- ID do aplicativo externo

As IDs externas do aplicativo são equivalentes à ID na página Gerenciar aplicativos para aplicativos store. Para aplicativos LOB, a coluna **ID do aplicativo externo**  pode ser habilitada na seção Gerenciar aplicativos nas configurações de coluna do [centro de administração do Teams](/microsoftteams/manage-apps) . Você também pode exibi-lo na página de detalhes do aplicativo de um aplicativo LOB personalizado.

## <a name="related-articles"></a>Artigos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
