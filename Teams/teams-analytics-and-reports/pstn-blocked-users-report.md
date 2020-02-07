---
title: Relatório de usuários bloqueados PSTN do Microsoft Teams
author: LanaChin
ms.author: v-lanac
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
description: Saiba como usar o relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams para obter uma visão geral dos usuários do teams em sua organização que estão bloqueados para fazer chamadas PSTN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ef4dfbab2b32b088c8e2f8b38b55c15a66eb32
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827339"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a>Relatório de usuários bloqueados PSTN do Microsoft Teams

O relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams mostra os usuários em sua organização que estão bloqueados da realização de chamadas PSTN no Teams. Você pode ver mais informações sobre cada usuário bloqueado, incluindo o número de telefone atribuído a ele e o motivo pelo qual eles foram bloqueados para fazerem chamadas.

## <a name="view-the-report"></a>Exibir o relatório

Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios. Na guia **exibir relatórios** , em **relatório**, selecione **usuários bloqueados PSTN**e clique em **executar relatório**.

![Captura de tela do relatório de relatório de usuários bloqueados PSTN no centro de administração](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de tela do relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams com textos explicativos numerados")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |Cada relatório tem uma data para o momento em que foi gerado. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**2**   |O eixo X é a data. O eixo Y é o número de usuários. <br>Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários bloqueados nessa data. |
|**3**   |A tabela fornece uma divisão de todos os usuários que estão bloqueados para fazerem chamadas PSTN.  Ele mostra todos os usuários que têm o sistema de telefonia ou a conferência de áudio atribuída e fornece mais informações sobre cada usuário. <ul><li>**Nome para exibição** é o nome de exibição do usuário. Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams. </li> <li>**Telefone** é o número atribuído ao usuário.</li> <li>**Motivo bloqueado** é o motivo pelo qual o usuário está bloqueado para fazerem chamadas.</li><li>**Ação bloqueada** informa se o usuário está bloqueado ou desbloqueado da realização de chamadas PSTN no Teams.</li> <li>**Tempo bloqueado** é a data e a hora (UTC) em que o usuário foi bloqueado para fazerem chamadas.</li></li> </ul>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**4**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**5**   |Selecione **tela inteira** para exibir o relatório em modo de tela inteira.|

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)