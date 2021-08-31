---
title: Microsoft Teams Relatório de usuários bloqueados PSTN
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
MS.collection:
- M365-voice
description: Use o relatório de usuários bloqueados PSTN no centro de administração Microsoft Teams para obter uma visão geral dos usuários Teams da sua organização que estão bloqueados para fazer chamadas PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1f703c672859c68d79a56af754dc087f68407c1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733090"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Microsoft Teams Relatório de usuários bloqueados PSTN

O relatório de usuários bloqueados PSTN no centro de administração Microsoft Teams mostra os usuários em sua organização que estão impedidos de fazer chamadas PSTN em Teams. Você pode exibir mais informações sobre cada usuário bloqueado, incluindo o número de telefone atribuído e o motivo pelo qual eles foram impedidos de fazer chamadas.

## <a name="view-the-pstn-blocked-users-report"></a>Exibir o relatório de usuários bloqueados PSTN

Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **Usuários bloqueados PSTN** e clique em **Executar relatório**.

![Captura de tela do relatório de relatório de usuários bloqueados PSTN no centro de administração.](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de tela do relatório de usuários bloqueados do PSTN no centro de administração Microsoft Teams com callouts numerados")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |O eixo X é a data. O eixo Y é o número de usuários. <br>Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários bloqueados nessa data. |
|**3**   |A tabela fornece uma divisão de todos os usuários que estão impedidos de fazer chamadas PSTN.  Ele mostra todos os usuários que Sistema de Telefonia ou Audioconferência atribuídas e fornece mais informações sobre cada usuário. <ul><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Microsoft Teams de administração. </li> <li>**Telefone** é o número atribuído ao usuário.</li> <li>**O motivo bloqueado** é o motivo pelo qual o usuário é impedido de fazer chamadas.</li><li>**A ação bloqueada** informa se o usuário está bloqueado ou não bloqueado para fazer chamadas PSTN em Teams.</li> <li>**A hora bloqueada** é a data e a hora (UTC) que o usuário foi impedido de fazer chamadas.</li></li> </ul>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**4**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**5**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)