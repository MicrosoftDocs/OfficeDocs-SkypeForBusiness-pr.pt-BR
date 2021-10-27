---
title: Microsoft Teams de uso do aplicativo
author: SerdarSoysal
ms.author: serdars
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
description: Saiba como usar o relatório de uso Teams aplicativo no centro de administração Microsoft Teams de usuário.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7679652f0cb93e445e72af80307803b1e3197992
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "60596208"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams de uso do aplicativo

O Teams de uso do aplicativo no centro de administração Microsoft Teams fornece informações sobre quais aplicativos os usuários estão usando Teams.  

## <a name="view-the-app-usage-report"></a>Exibir o relatório de uso do aplicativo

1. Na navegação à esquerda do centro de administração em <https://admin.teams.microsoft.com> , clique em Análise & **relatórios**  >  **de uso.**<br><br>![Captura de tela do item de menu Relatórios de Uso.](media/app-usage-report1.png "Captura de tela do item de menu Relatórios de Uso.")
2. Na guia **Exibir relatórios,** em **Relatório**, selecione **Uso de Aplicativos**.

3. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**. O Teams de uso de Aplicativos pode ser exibido para tendências nos últimos 7, 30 ou 90 dias.<br><br>![Captura de tela do relatório uso de aplicativos.](media/app-usage-report2.png "Captura de tela do relatório uso de aplicativos.")


## <a name="interpret-the-report"></a>Interpretar relatório

:::image type="content" alt-text="Captura de tela do relatório Teams uso do aplicativo no centro de administração Teams com explicações explicativas." source="media/app-usage-report5.png" lightbox="media/app-usage-report5.png":::

1. Cada relatório tem uma data na parte superior esquerda que mostra quando o relatório foi criado. Os relatórios geralmente refletem uma latência de 24 horas a partir do momento em que um aplicativo foi aberto.

2. O eixo Y no gráfico é o número de usuários que para a data selecionada ao passar o mouse sobre o gráfico são considerados usuários ativos porque abriram um aplicativo pelo menos uma vez.

3. O eixo X no gráfico é o intervalo de datas selecionado para o relatório.

4. Passe o mouse sobre o ponto que representa o uso de um aplicativo em qualquer data para ver o número total de usuários ativos desse aplicativo nessa data.

5. Para selecionar outros aplicativos, na  parte superior direita, clique no ícone Filtro, selecione ou digite novos critérios e clique em **Aplicar**.

6. A tabela na parte inferior do relatório mostra usuários ativos e equipes pelo nome do aplicativo.

   - **Nome do** aplicativo é o nome de exibição do aplicativo usado Teams.
   - **Usuários ativos** é o número de usuários que abriram o aplicativo pelo menos uma vez durante o período especificado.
   - **Tipo de** aplicativo é um valor estático de "Microsoft" ou "Terceiros".
   - **Equipes** ativas é o número de equipes que abriram o aplicativo por pelo menos um membro da equipe e durante os períodos de tempo especificados.
   - **Publisher** é o editor de software do aplicativo.
   - **Version** é a versão de software do aplicativo, do editor de aplicativos.

   > [!NOTE]
   > **Usuários ativos** **e equipes ativas** são calculados para aplicativos usados apenas em canais.

7. Para adicionar ou remover colunas na tabela, na parte superior direita, clique no ícone Editar **colunas,** na guia Editar **colunas,** selecione novos critérios e clique em **Aplicar**.

8. Para exportar o relatório para um arquivo CSV para análise offline, na parte superior direita, selecione o ícone Exportar para Excel e, em seguida, **na** guia **Downloads** em **Status**, clique em **Baixar**.

   :::image type="content" alt-text="Captura de tela do painel Downloads." source="media/app-usage-report7.png" lightbox="media/app-usage-report7.png":::

9. Quando você exibir o relatório Excel, você também verá uma coluna **de Id,** que representa a ID do aplicativo, normalmente uma cadeia de caracteres alfanumérico. Se a **ID** for **\n**, isso significa que um usuário solicitou que suas informações sejam excluídas.

   ![Captura de tela do relatório Excel baixado.](media/app-usage-report8.png "Captura de tela do relatório Excel baixado.")

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
