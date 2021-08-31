---
title: 'Teams: Gerenciar notificações de chamada'
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
ms.localizationpriority: medium
ms.openlocfilehash: 80c7c5487d61447a38852ca30328126b19c0499b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725920"
---
# <a name="manage-call-notifications"></a>Gerenciar notificações de chamadas

Este artigo descreve como gerenciar notificações de chamada para seus usuários. Você pode configurar pontos de extremidade de chamada para Teams e para um PbX (Private Branch Exchange) de terceiros ou Controlador de Borda de Sessão (SBC).  Essa configuração é útil, por exemplo, se você quiser enviar uma chamada para os telefones móveis e de mesa de um usuário ao mesmo tempo.   

No diagrama a seguir, a Irena do usuário tem dois pontos de extremidade:

- Um Teams ponto de extremidade
- Um telefone SIP conectado a um SBC de terceiros

Quando uma chamada chega, o SBC bifurca a chamada entre Sistema de Telefonia Roteamento Direto e o SBC de terceiros.


![Diagrama mostrando pontos Teams pontos de extremidade bifurcados.](media/direct-routing-call-notification-1.png)

Se a chamada for aceita no Fork 2 (pelo SBC de terceiros), Teams gerará uma notificação de "Chamada Perdida".  

Você pode impedir a notificação de "Chamada Perdida" configurando o SBC para enviar um Cancelamento no Bifurcação 1 da seguinte forma:

MOTIVO: SIP; cause=200;text"Call completed elsewhere" 

A chamada não será registrada nos registros de detalhes de chamada do Telefone Microsoft System como uma chamada bem-sucedida. A chamada será registrada como uma "Tentativa" com o Código SIP Final "487", o subcodigo final da Microsoft "540200" e a frase de código SIP final "Chamada concluída em outro lugar".  (Para exibir os registros de detalhes da chamada, acesse o portal de administração do Teams, Análise e Relatórios, Relatórios de Uso e selecione Uso de PSTN.)


O diagrama a seguir ilustra a escala SIP do Fork 1, explica o fluxo de chamada e o MOTIVO esperado na mensagem Cancelar. 

![O diagrama mostra pontos Teams pontos de extremidade bifurcados.](media/direct-routing-call-notification-2.png)
