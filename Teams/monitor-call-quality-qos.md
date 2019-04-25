---
title: Implementar QoS e Monitorar a análise de chamada no Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: Use configurações de qualidade de serviço (QoS) e análise de chamada e painel de controle de qualidade de chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228419"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementação QoS e monitorar a qualidade de chamada no equipes da Microsoft

## <a name="get-started"></a>Guia de Introdução

Como os usuários começam a usar as equipes para fazer chamadas e reter as reuniões, eles podem enfrentar voz de um chamador separação ou talhar e sair de uma chamada ou reunião. Shared maio vídeo congelamento ou Pixelizar, ou reprovação todo. Isso acontece devido à que representam o tráfego de voz e vídeo encontrando congestionamento da rede e que chegam fora de sequência ou não em todos os pacotes IP. Há maneiras para identificar esses problemas quando eles desvendar e impedem o retorno, principalmente Quality of Service (QoS).

**Qualidade de serviço (QoS)** é uma maneira para permitir o tráfego de rede em tempo real (como fluxos de voz ou vídeo) sensível a atrasos de rede "cortar na linha" na frente de tráfego menos confidencial (como fazer o download de um novo aplicativo, onde um segundo extra para baixar não é importante). QoS identifica e marca todos os pacotes de fluxos em tempo real usando objetos de diretiva de grupo do Windows e um recurso de roteamento chamado porta-based Access Control Lists, que então ajuda a sua rede para dar a voz, vídeo e compartilhamento de tela transmite suas próprias partes dedicados de largura de banda de rede.

 No momento, vamos dizer apenas que ele é muito parecido com o envio de uma carta pelo correio: se você enviá-la chegar lá muito breve e que é bom, se você enviar primeira classe chegar lá muito mais rapidez, e se você enviar o email de prioridade de taxa de catálogo , chegar lá dentro de dois dias. Obviamente redes executado mais rapidamente do que o email, mas ainda executa true que velocidade é fundamental para alguns aplicativos e não é tão crítica para outras pessoas. Esse assunto é naturalmente detalhadas e complicado compreender em um primeiro momento, mas ele faz com que uma enorme diferença no usuário experiência para que ele tenha a pena investir tempo e energia antecipadamente. Leia [Implementar Quality of Service (QoS) em equipes da Microsoft](QoS-in-Teams.md) para obter uma discussão mais detalhada.

Idealmente, você poderia implementar QoS em sua rede interna durante a configuração de equipes, mas se você estiver pequeno suficiente é opcional. Isso permite que o atraso confidenciais tráfego de voz e vídeo para obter priorizados antes dos outros tráfegos. Você deseja fazer esta priorização em todos os [dispositivos cliente](QoS-in-Teams-clients.md), no [Centro de administração de equipes da Microsoft](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), bem como sobre os switches e roteadores em sua rede.

[**Análise de chamada e o painel de controle de qualidade de chamada**](difference-between-call-analytics-and-call-quality-dashboard.md) são usados para encontrar e solucionar problemas que surgem durante a operação em andamento.  

**Análise de chamada** mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionadas a ***reuniões e chamadas específicas*** para cada usuário em um Microsoft Teams ou Skype para a conta de negócios. Se você for um administrador do Office 365, você pode usar a análise de chamada para solucionar problemas de qualidade e conexão de chamada enfrentou em uma chamada específica. Isso pode ajudar a identificar e eliminar os problemas.

**Painel de controle de qualidade de chamada (CQD)** foi projetado para ajudar os administradores e os engenheiros de rede otimizam sua ***rede***, não analisar e resolver problemas de uma única chamada. CQD alterna o foco de usuários específicos, examine as informações agregadas para uma organização inteira. Isso também pode ajudar a identificar e eliminar os problemas.

## <a name="related-topics"></a>Tópicos Relacionados

[Implementar a qualidade do serviço (QoS) em equipes da Microsoft](QoS-in-Teams.md)

[Vídeo: Visão geral de qualidade de chamada](https://aka.ms/teams-quality)

[Configurar Análise de Chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativando e usando o Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md)

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)