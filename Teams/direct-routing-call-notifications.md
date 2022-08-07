---
title: Gerenciar notificações de chamada para Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Notificação de chamada de Roteamento Direto
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268426"
---
# <a name="manage-call-notifications"></a>Gerenciar notificações de chamadas

Este artigo descreve como gerenciar notificações de chamada para seus usuários de Roteamento Direto. Você pode configurar pontos de extremidade de chamada para o Teams e para um PBX (Private Branch Exchange) ou SBC (Controlador de Borda de Sessão) de terceiros. Essa configuração é útil, por exemplo, se você quiser enviar uma chamada para os telefones móveis e de mesa de um usuário ao mesmo tempo.   

No diagrama a seguir, o usuário Irena tem dois pontos de extremidade:

- Um ponto de extremidade do Teams
- Um telefone SIP conectado a um SBC de terceiros

Quando uma chamada chega, o SBC bifurca a chamada entre o Roteamento Direto e o SBC de terceiros.


![Diagrama mostrando pontos de extremidade bifurcados do Teams.](media/direct-routing-call-notification-1.png)

Se a chamada for aceita no Fork 2 (pelo SBC de terceiros), o Teams gerará uma notificação de "Chamada Perdida".  

Você pode impedir a notificação de "Chamada Perdida" configurando o SBC para enviar um Cancelamento no Fork 1 da seguinte maneira:

MOTIVO: SIP; cause=200;text"Call completed elsewhere" 

A chamada não será registrada nos registros de detalhes da chamada do Sistema de Telefonia do Teams como uma chamada bem-sucedida. A chamada será registrada como uma "Tentativa" com o Código SIP Final "487", o subcódigo final da Microsoft "540200" e a Frase de Código SIP Final "Chamada concluída em outro lugar".  (Para exibir os registros de detalhes da chamada, acesse o centro de Administração teams -> **Relatórios** ->  de Uso de Relatórios e Análise e selecione **Uso de PSTN**.)


O diagrama a seguir ilustra a escada SIP para Fork 1, explica o fluxo de chamada e o MOTIVO esperado na mensagem Cancelar. 

![O diagrama mostra pontos de extremidade bifurcados do Teams.](media/direct-routing-call-notification-2.png)
