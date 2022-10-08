---
title: Relatório de uso de aplicativos do Microsoft Teams
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
description: Saiba como usar o relatório de uso do aplicativo Teams no Centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9db5378a439061639298b8bc3b48f4d3ef26c50b
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68376959"
---
# <a name="microsoft-teams-app-usage-report"></a>Relatório de uso de aplicativos do Microsoft Teams

O relatório de uso do aplicativo Teams no centro de administração do Microsoft Teams fornece informações sobre quais aplicativos os usuários estão usando no Teams. Você pode obter insights sobre a atividade de aplicativos do Teams em sua organização. Este artigo explica como acessar o relatório e exibir e interpretar as várias métricas dentro do relatório. 

## <a name="view-the-app-usage-report"></a>Exibir o relatório uso do aplicativo

1. No painel de navegação esquerdo do Centro de administração do Teams, selecione **Relatórios de uso &** > **[análise.](https://admin.teams.microsoft.com/analytics/reports)**

   :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de tela do item de menu Relatórios de Uso.":::

1. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de Aplicativos**.

1. Em **Intervalo de datas**, selecione um intervalo e, em seguida, **selecione Executar relatório**. Você pode exibir o relatório uso de aplicativos do Teams para tendências nos últimos 7, 30, 90 e 180 dias.

   :::image type="content" source="media/app-usage-report2-trimmed.png" alt-text="Captura de tela da interface de relatório uso de aplicativos." lightbox="media/app-usage-report2.png":::

## <a name="interpret-the-report"></a>Interpretar relatório

:::image type="content" alt-text="Captura de tela do relatório de uso do aplicativo Teams no Centro de administração do Teams com textos explicativo." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Cada relatório tem uma data no canto superior esquerdo que mostra quando o relatório foi criado. Os relatórios geralmente refletem uma latência de 24 a 48 horas a partir do momento em que um aplicativo foi aberto.

Administração central fornece um gráfico dos usuários ativos e as datas. Usuários ativos são o número de usuários que abriram um aplicativo pelo menos uma vez durante o período de tempo selecionado.

Passe o mouse sobre o ponto (4) que representa o uso de um aplicativo em qualquer data para ver o número total de usuários ativos desse aplicativo nessa data.

Para selecionar outros aplicativos, no canto superior direito, selecione  o ícone Filtro (5), selecione ou digite novos critérios e, em seguida, **selecione Aplicar**.

A tabela na parte inferior do relatório (6) mostra usuários ativos e equipes pelo nome do aplicativo.

   - **O nome do** aplicativo é o nome de exibição do aplicativo usado no Teams.
   - **Usuários ativos** são o número de usuários que abriram o aplicativo pelo menos uma vez durante o período de tempo especificado.
   - **O tipo** de aplicativo é um valor estático de "Microsoft" ou "Terceiros".
   - **Equipes** ativas são o número de equipes que abriram o aplicativo por pelo menos um membro da equipe e durante os períodos de tempo especificados.
   - **O Publisher** é o desenvolvedor de software do aplicativo.
   - **A** versão é a versão de software do aplicativo, do desenvolvedor do aplicativo.

   > [!NOTE]
   > **Os usuários ativos** **e as equipes** ativas são calculados apenas para aplicativos usados em canais.

Para adicionar ou remover colunas na tabela, no canto superior direito, selecione o ícone Editar **colunas** (7), na guia Editar colunas, selecione novos **critérios** e, em seguida, selecione **Aplicar**.

Para exportar o relatório para um arquivo CSV para análise offline, no canto superior direito, selecione o ícone Exportar para **Excel** (8) e, na guia **Downloads** , em **Status**, selecione **Baixar**.

   :::image type="content" alt-text="Captura de tela do painel Downloads." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Ao exibir o relatório no Microsoft Excel, você também verá uma coluna, que representa a `Id` ID do aplicativo, normalmente uma cadeia de caracteres alfanumérica. Se o valor do valor for `Id` **\n**, isso significa que um usuário solicitou que suas informações sejam excluídas.

   :::image type="content" source="media/app-usage-report8.png" alt-text="Captura de tela do relatório baixado do Excel.":::

## <a name="related-articles"></a>Artigos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
