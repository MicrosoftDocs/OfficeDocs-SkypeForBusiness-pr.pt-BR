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
ms.openlocfilehash: f58634bea7a2846e35ddc4dbc8da0be13396e616
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046007"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams de uso do aplicativo

O Teams de uso do aplicativo no centro de administração Microsoft Teams fornece informações sobre quais aplicativos os usuários estão usando Teams.  

## <a name="view-the-app-usage-report"></a>Exibir o relatório de uso do aplicativo

1.  Na navegação à esquerda do centro de administração em <https://admin.teams.microsoft.com> , clique em Análise & **relatórios** \> **de uso.** Na guia **Exibir relatórios,** em **Relatório**, selecione **Uso de Aplicativos**.

     :::image type="content" source="media/app-usage-report1.png" alt-text="Captura de tela do item de menu Relatórios de Uso.":::

2.  Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

      :::image type="content" source="media/app-usage-report2.png" alt-text="Captura de tela do relatório uso de aplicativos.":::

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O Teams de uso de Aplicativos pode ser exibido para tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data para quando o relatório foi gerado. Os relatórios geralmente refletem uma latência de 24 horas a partir do momento em que um aplicativo foi aberto. <br><br>![Captura de tela do relatório uso de aplicativos mostrando intervalos de datas.](media/app-usage-report3.png)|
|**3**    | <ul><li>O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico.</li><li>O eixo Y é o número de usuários que, durante o determinado dia, pairam sobre o gráfico, esses usuários abriram um aplicativo pelo menos uma vez e, fazendo isso, são considerados um Usuário Ativo e acumulam-se em direção ao total visto no mouse passar o mouse.</li></ul>|
|**4**   |Passe o mouse sobre o ponto que representa um Uso de Aplicativos em uma determinada data para ver o número de instâncias do Total de Usuários Ativos desse aplicativo nessa determinada data.  |
|**5**   |Todos os aplicativos serão incluídos, mas escolhendo o ícone Filtro, filtros adicionais estão disponíveis.  |
|**6**   |A tabela fornece uma divisão de usuários ativos e equipes pelo nome do aplicativo.<br><ul><li>**Nome do** aplicativo é o nome de exibição do aplicativo usado Teams.</li><li>**Usuários ativos** é o número de usuários que abriram o aplicativo pelo menos uma vez durante o período especificado.</li><li>**Tipo de** aplicativo é um valor estático de "Microsoft" ou "Terceiros".</li><li>**Equipes** ativas é o número de equipes que abriram o Aplicativo por pelo menos um membro da equipe e durante os períodos de tempo especificados.</li><li>**Publisher** é o editor de software do aplicativo.</li><li>**Version** é a versão de software do aplicativo, do editor de aplicativos.</li></ul><b> Observação :</b> Atualmente, 'Usuários ativos' e 'Equipes ativas' são calculados para aplicativos usados apenas em canais.     
<br>![Captura de tela de um relatório de uso de aplicativos.](media/app-usage-report4.png)|
|**7**  |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.<br><br>![Captura de tela da página Editar colunas.](media/app-usage-report5.png)  |
|**8**  |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando estiver pronto.<br>![Captura de tela da página Downloads.](media/app-usage-report7.png)  |
|**9**   |Quando você exibir o relatório Excel, você também verá uma **coluna de Id,** que representa a ID do aplicativo. Uma ID de equipe normalmente é uma cadeia de caracteres alfanumérico. Se a **coluna Id** mostrar como **\n****,isso significa que um usuário solicitou que suas informações sejam excluídas.<br>![Captura de tela do relatório Excel baixado.](media/app-usage-report8.png)  |

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)