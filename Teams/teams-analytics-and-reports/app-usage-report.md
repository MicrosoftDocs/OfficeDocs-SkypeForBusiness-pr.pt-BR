---
title: Relatório de uso de aplicativos do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-quhur
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
ms.openlocfilehash: 6fb738bc1b1fd068196d1b7c3238c139426eac73
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825675"
---
# <a name="microsoft-teams-app-usage-report"></a>Relatório de uso de aplicativos do Microsoft Teams

O relatório de uso do aplicativo Teams no centro de administração do Microsoft Teams fornece informações sobre quais aplicativos os usuários estão usando no Teams.  

## <a name="view-the-app-usage-report"></a>Exibir o relatório uso do aplicativo

1. No painel de navegação esquerdo do centro de administração, <https://admin.teams.microsoft.com>clique em **Análise & relatórios** > **de uso**.<br><br>![Captura de tela do item de menu Relatórios de Uso.](media/app-usage-report1.png "Captura de tela do item de menu Relatórios de Uso.")
2. Na guia **Exibir relatórios** , em **Relatório**, selecione **Uso de Aplicativos**.

3. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**. O relatório de uso dos Aplicativos do Teams pode ser exibido para ver tendências nos últimos 7, 30 ou 90 dias.<br><br>![Captura de tela do relatório Uso de Aplicativos.](media/app-usage-report2.png "Captura de tela do relatório Uso de Aplicativos.")


## <a name="interpret-the-report"></a>Interpretar relatório

:::image type="content" alt-text="Captura de tela do relatório de uso do aplicativo Teams no Centro de administração do Teams com textos explicativo." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

Cada relatório tem uma data no canto superior esquerdo que mostra quando o relatório foi criado. Os relatórios geralmente refletem uma latência de 24 horas a partir do momento em que um aplicativo foi aberto.

O eixo Y no gráfico é o número de usuários que, para a data selecionada passando o mouse sobre o gráfico, são considerados usuários ativos porque abriram um aplicativo pelo menos uma vez.

O eixo X no gráfico é o intervalo de datas selecionado para o relatório.

Passe o mouse sobre o ponto (4) que representa o uso de um aplicativo em qualquer data para ver o número total de usuários ativos desse aplicativo nessa data.

Para selecionar outros aplicativos, no canto superior direito, clique  no ícone Filtro (5), selecione ou digite novos critérios e clique em **Aplicar**.

A tabela na parte inferior do relatório (6) mostra usuários ativos e equipes pelo nome do aplicativo.

   - **O nome do** aplicativo é o nome de exibição do aplicativo usado no Teams.
   - **Usuários ativos** são o número de usuários que abriram o aplicativo pelo menos uma vez durante o período de tempo especificado.
   - **O tipo** de aplicativo é um valor estático de "Microsoft" ou "Terceiros".
   - **Equipes** ativas são o número de equipes que abriram o aplicativo por pelo menos um membro da equipe e durante os períodos de tempo especificados.
   - **O Publisher** é o editor de software do aplicativo.
   - **A** versão é a versão de software do aplicativo, do editor de aplicativos.

   > [!NOTE]
   > **Os usuários ativos** **e as equipes** ativas são calculados apenas para aplicativos usados em canais.

Para adicionar ou remover colunas na tabela, no canto superior direito, clique no ícone Editar **colunas** (7), na guia Editar colunas, selecione novos **critérios** e clique em **Aplicar**.

Para exportar o relatório para um arquivo CSV para análise offline, no canto superior direito, selecione o ícone Exportar para **Excel** (8) e, na guia **Downloads** , em **Status**, clique em **Baixar**.

   :::image type="content" alt-text="Captura de tela do painel Downloads." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

Ao exibir o relatório no Excel, você também verá uma coluna **de ID** , que representa a ID do aplicativo, normalmente uma cadeia de caracteres alfanumérica. Se a **ID** for **\n**, isso significa que um usuário solicitou que suas informações sejam excluídas.

   ![Captura de tela do relatório baixado do Excel.](media/app-usage-report8.png "Captura de tela do relatório baixado do Excel.")

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
