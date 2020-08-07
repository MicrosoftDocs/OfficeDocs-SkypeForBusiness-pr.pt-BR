---
title: Relatório de uso do aplicativo Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso do aplicativo Teams no centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91af37ed9c19a1d3e8d32cdf296cf32e90818564
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583790"
---
# <a name="microsoft-teams-app-usage-report"></a>Relatório de uso do aplicativo Microsoft Teams

O relatório de uso do aplicativo Teams no centro de administração do Microsoft Teams fornece informações sobre quais aplicativos os usuários estão usando no Teams.  

## <a name="view-the-app-usage-report"></a>Exibir o relatório de uso do aplicativo

1.  Na navegação à esquerda do centro de administração <https://admin.teams.microsoft.com> , clique em relatórios de **análise & relatórios** de \> **uso**. Na guia **exibir relatórios** , em **relatório**, selecione **uso do aplicativo**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de tela do item de menu relatórios de uso":::

2.  Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Captura de tela do relatório de uso de aplicativos":::

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O relatório de uso de aplicativos Teams pode ser exibido para obter tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 horas a partir do momento em que um aplicativo foi aberto. <br><br>![Captura de tela do relatório de uso de aplicativos mostrando intervalos de datas](media/app-usage-report3.png)|
|**3**    | <ul><li>O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico.</li><li>O eixo Y é o número de usuários com o qual o dia passa o passar o mouse sobre o gráfico, esses usuários abriram um aplicativo pelo menos uma vez e, ao fazer isso, são considerados um usuário ativo e se acumulam em direção ao total visto sobre o mouse sobre o cursor.</li></ul>|
|**4**   |Passe o mouse sobre o ponto que representa o uso de um aplicativo em uma determinada data para ver o número de instâncias do total de usuários ativos do aplicativo nessa determinada data.  |
|**5**   |Todos os aplicativos serão incluídos, mas ao escolher o ícone de filtro, outros filtros estarão disponíveis.  |
|**6**   |A tabela oferece uma divisão de usuários ativos e equipes pelo nome do aplicativo.<br><ul><li>**Nome do aplicativo** é o nome de exibição do aplicativo usado no Teams.</li><li>**Usuários ativos** é o número de usuários que abriram o aplicativo pelo menos uma vez durante o período de tempo especificado.</li><li>O **tipo de aplicativo** é um valor estático de "Microsoft" ou "terceiros".</li><li>**Active** Teams é o número de equipes que abriram o aplicativo por pelo menos um membro da equipe e durante os períodos de tempo especificados.</li><li>O **Publisher** é o fornecedor do software do aplicativo.</li><li>**Version** é a versão do software do aplicativo, do fornecedor do aplicativo.</li></ul><br>![Captura de tela de um relatório de uso de aplicativos](media/app-usage-report4.png)  |
|**7**  |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.<br><br>![Captura de tela da página Editar colunas](media/app-usage-report5.png)  |
|**8**  |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique em **exportar para o Excel**e, na guia **downloads** , clique em **baixar** para baixar o relatório quando ele estiver pronto.<br>![Captura de tela da página de downloads](media/app-usage-report7.png)  |
|**9**   |Ao visualizar o relatório no Excel, você também verá uma coluna **ID** , que representa a ID do aplicativo. Uma ID de equipe geralmente é uma cadeia de caracteres alfanumérica. Se a coluna **ID** aparecer como * * \n * * * *, isso significará que o usuário solicitou as informações a serem excluídas.<br>![Captura de tela do relatório do Excel baixado](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)