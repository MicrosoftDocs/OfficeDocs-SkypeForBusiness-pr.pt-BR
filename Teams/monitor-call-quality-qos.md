---
title: Implementar QoS e Monitorar a análise de chamada no Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: Use as configurações de qualidade do serviço (QoS) e, em seguida, faça a análise de chamada e painel de qualidade da chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19e97053120f5f28dcd634fd2047fed0abd2dd57
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573385"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementar QoS e monitorar a qualidade das chamadas no Microsoft Teams

## <a name="get-started"></a>Comece a usar

À medida que seus usuários começarem a usar o Microsoft Teams para fazer chamadas e participar de reuniões, eles poderão enfrentar a voz de um usuário que está decompondo ou travando uma chamada ou reunião. O vídeo compartilhado pode congelar ou ser pixel ou falhar completamente. Isso ocorre devido aos pacotes de IP que representam o tráfego de voz e vídeo que está encontrando o congestionamento da rede e que chega fora de sequência. Há maneiras de identificar esses problemas quando eles fazem a superfície e impedem o retorno, principalmente a QoS (qualidade de serviço).

A **QoS (qualidade de serviço)** é uma maneira de permitir o tráfego de rede em tempo real (como fluxos de voz ou de vídeo) sensíveis a atrasos na rede para "recortar linha" na frente do tráfego que é menos confidencial (como baixar um novo aplicativo, onde um segundo adicional para baixar Não é um negócio importante). A QoS identifica e marca todos os pacotes em fluxos em tempo real usando objetos de política de grupo do Windows e um recurso de roteamento chamado de listas de controle de acesso baseado em porta, o que, em seguida, ajuda sua rede a fornecer voz, vídeo e compartilhamento de tela para transmitir suas próprias partes exclusivas de largura de banda de rede.

 Por enquanto, vamos dizer que é muito parecido com o envio de uma carta por meio do email: se você enviar a tarifa do livro de ti, ele fica lá logo e isso é bom o suficiente, se você enviá-lo para a primeira classe, ele se torna muito mais rápido e se você enviar emails de prioridade de ti , ele chega dentro de dois dias. De redes de curso são executados mais rapidamente do que o e-mail, mas ele ainda é válido para que a velocidade seja crítica para alguns aplicativos e não é tão importante para outras pessoas. Este assunto é inerentemente detalhado e difícil de entender em primeiro lugar, mas faz uma grande diferença na experiência do usuário para que ele valha a pena investir tempo e energia antecipadamente. Leia [implementar qualidade de serviço (QoS) no Microsoft Teams](QoS-in-Teams.md) para obter uma discussão mais detalhada.

O ideal é que você implementasse a QoS na sua rede interna enquanto configurou o Microsoft Teams, mas se for pequeno o suficiente pode ser opcional. Isso permite que o tráfego de voz e vídeo sensível à atraso seja priorizado antes do outro tráfego. Você faria essa priorização em todos os [dispositivos cliente](QoS-in-Teams-clients.md), no centro de [Administração do Microsoft Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), bem como nos switches e roteadores da sua rede.

O [**painel de análise de chamadas e o painel de qualidade de chamada**](difference-between-call-analytics-and-call-quality-dashboard.md) são usados para localizar e solucionar problemas que surgem durante a operação em andamento.  

A **análise de chamadas** mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados a ***chamadas e reuniões específicas*** para cada usuário em uma conta do Microsoft Teams ou do Skype for Business. Se você for um administrador do Office 365, poderá usar a análise de chamadas para solucionar problemas com a qualidade da chamada e a conexão com experiência em uma chamada específica. Isso pode ajudá-lo a identificar e eliminar problemas.

O **painel de qualidade de chamada (CQD)** foi projetado para ajudar administradores e engenheiros de rede a otimizar sua ***rede***, não analisar e solucionar problemas de uma única chamada. CQD muda o foco de usuários específicos para ver as informações agregadas de uma organização inteira. Isso também pode ajudá-lo a identificar e eliminar problemas.

## <a name="related-topics"></a>Tópicos Relacionados

[Implementar a QoS (qualidade de serviço) no Microsoft Teams](QoS-in-Teams.md)

[Vídeo: visão geral da qualidade da chamada](https://aka.ms/teams-quality)

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativando e usando o Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md)

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)