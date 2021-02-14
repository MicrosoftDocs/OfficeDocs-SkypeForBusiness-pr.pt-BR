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
f1.keywords:
- NOCSH
description: Notificação de chamada de Roteamento Direto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341800"
---
# <a name="manage-call-notifications"></a>Gerenciar notificações de chamadas

Este artigo descreve como gerenciar notificações de chamada para seus usuários. Você pode configurar pontos de extremidade de chamada para o Teams e para um PBX (Private Branch Exchange) de terceiros ou controlador de borda de sessão (SBC).  Isso é útil, por exemplo, se você quiser enviar uma chamada para os celulares e telefones de mesa de um usuário ao mesmo tempo.   

No diagrama a seguir, o usuário Inn tem dois pontos de extremidade:

- Um ponto de extremidade do Teams
- Um telefone SIP conectado a um SBC de terceiros

Quando uma chamada chega, o SBC faz a chamada entre o Roteamento Direto do Sistema telefônico e o SBC de terceiros.


![Diagrama mostrando pontos de extremidade empilhados do Teams](media/direct-routing-call-notification-1.png)

Se a chamada for aceita no Fork 2 (pelo SBC de terceiros), o Teams gerará uma notificação de "Chamada Perdida".  

Você pode impedir a notificação de "Chamada Perdida" configurando o SBC para enviar um Cancelamento no Fork 1 da seguinte forma:

MOTIVO: SIP; cause=200;texto "Chamada concluída em outro lugar" 

Observe que a chamada não será registrada nos registros de detalhes da chamada do Microsoft Phone System como uma chamada bem-sucedida. A chamada será registrada como uma "Tentativa" com o Código SIP Final "487", o subcódigo final da Microsoft "540200" e a frase de código SIP final "Chamada concluída em outro lugar".  (Para exibir os registros de detalhes da chamada, acesse o portal de administração do Teams, análise e relatórios, relatórios de uso e selecione Uso de PSTN.)


O diagrama a seguir ilustra o esquema SIP do Fork 1, explica o fluxo de chamada e o MOTIVO esperado na mensagem Cancelar. 

![Diagrama mostrando pontos de extremidade empilhados do Teams](media/direct-routing-call-notification-2.png)
