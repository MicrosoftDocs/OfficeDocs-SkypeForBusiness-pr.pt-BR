---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: Notificação de chamada de roteamento direto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a031af6a7bdfedfebd6d666b717d03259d92f56c
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074603"
---
# <a name="manage-call-notifications"></a>Gerenciar notificações de chamadas

Este artigo descreve como gerenciar notificações de chamada para seus usuários. Você pode configurar pontos de extremidade de chamada para as duas equipes e para um PBX ou um controlador de borda de sessão (SBC) ou um controlador de borda de sessão (SBC) de terceiros.  Isso é útil, por exemplo, se você quiser enviar uma chamada para telefones celulares e de mesa de um usuário ao mesmo tempo.   

No diagrama a seguir, o usuário Irena tem dois pontos de extremidade:

- Um ponto de extremidade do teams
- Um telefone SIP conectado a um SBC de terceiros

Quando chega uma chamada, o SBC bifurca a chamada entre o roteamento direto do sistema telefônico e o SBC de terceiros.


![Diagrama mostrando pontos de extremidade de equipes bifurcadas](media/direct-routing-call-notification-1.png)

Se a chamada for aceita na bifurcação 2 (pelo SBC de terceiros), o Teams irá gerar uma notificação de "chamada perdida".  

Você pode impedir a notificação de "chamada perdida" Configurando o SBC para enviar um cancelamento na bifurcação 1 da seguinte maneira:

MOTIVO: SIP; causa = 200; texto "chamada concluída em outro lugar" 

Observe que a chamada não será registrada nos registros de detalhes da chamada do sistema de telefonia da Microsoft como uma chamada bem-sucedida. A chamada será registrada como uma "tentativa" com o código SIP final "487", subcódigo final da Microsoft "540200" e a frase de código SIP final "chamada concluída".   (Para exibir os registros de detalhes da chamada, vá para o portal de administração do Teams, análises e relatórios, relatórios de uso e selecione uso de PSTN.)


O diagrama a seguir ilustra a escada SIP para a bifurcação 1, explica o fluxo de chamadas e o motivo esperado na mensagem de cancelamento. 

![Diagrama mostrando pontos de extremidade de equipes bifurcadas](media/direct-routing-call-notification-2.png)
