---
title: Relatório de usuários bloqueados da PSTN do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Use o relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams para obter uma visão geral dos usuários do Teams da sua organização que estão impedidos de fazer chamadas PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809331"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Relatório de usuários bloqueados da PSTN do Microsoft Teams

O relatório de usuários PSTN bloqueados no centro de administração do Microsoft Teams mostra os usuários em sua organização que estão impedidos de fazer chamadas PSTN no Teams. Você pode exibir mais informações sobre cada usuário bloqueado, incluindo seu número de telefone atribuído e o motivo pelo qual eles foram impedidos de fazer chamadas.

## <a name="view-the-pstn-blocked-users-report"></a>Exibir o relatório de usuários bloqueados PSTN

Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **usuários PSTN bloqueados** e clique em **Executar relatório**.

![Captura de tela do relatório de usuários bloqueados PSTN no centro de administração](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para quando ele foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |O eixo X é a data. O eixo Y é o número de usuários. <br>Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários bloqueados nessa data. |
|**3**   |A tabela fornece uma divisão de todos os usuários que estão impedidos de fazer chamadas PSTN.  Ele mostra todos os usuários que têm o Sistema de Telefonia ou Audioconferência atribuído e fornece mais informações sobre cada usuário. <ul><li>**Nome para** exibição é o nome de exibição do usuário. Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Centro de administração do Microsoft Teams. </li> <li>**O** telefone é o número atribuído ao usuário.</li> <li>**O motivo do** bloqueio é o motivo pelo qual o usuário é impedido de fazer chamadas.</li><li>**A ação**  bloqueada informa se o usuário está bloqueado ou impedido de fazer chamadas PSTN no Teams.</li> <li>**A hora bloqueada** é a data e a hora (UTC) que o usuário foi impedido de fazer chamadas.</li></li> </ul>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**4**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**5**   |Selecione **Tela inteira** para exibir o relatório no modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)