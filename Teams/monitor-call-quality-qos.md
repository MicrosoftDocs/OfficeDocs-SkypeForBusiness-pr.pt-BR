---
title: Implementar QoS e Monitorar a Análise de Chamada no Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: Use configurações de qualidade de serviço (QoS) e análise de chamada e painel de controle de qualidade de chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 505409ac51552a99fabc4eb41801a1f19a737877
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742946"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementação QoS e monitorar a qualidade de chamada no equipes da Microsoft

## <a name="get-started"></a>Guia de Introdução

Como os usuários começam a usar as equipes para fazer chamadas e reter as reuniões, eles podem achar alto-falantes ups quebra ou talhar e sair de uma chamada ou reunião. Vídeo compartilhado pode congelar ou pixellate, ou reprovação todo. Isso acontece devido à que representam o tráfego de voz e vídeo encontrando congestionamento da rede e que chegam fora de sequência ou não em todos os pacotes IP. Há maneiras para impedir isso e identificar outros problemas quando eles desvendar, principalmente Quality of Service (QoS).

[**Qualidade de serviço (QoS)**](monitor-call-quality-qos.md) é uma maneira de identificar os pacotes que são sensíveis a atrasos e congestionamento e forneça os pacotes com tratamento preferencial para que eles encontrem é muito menor congestionamento. No momento, vamos dizer apenas que ele é muito parecido com o envio de uma carta pelo correio: se você enviá-la chegar lá muito breve e que é bom, se você enviar primeira classe chegar lá muito mais rapidez, e se você enviar o email de prioridade de taxa de catálogo , chegar lá dentro de dois dias. Obviamente redes executado mais rapidamente do que o email, mas ainda executa true que velocidade é fundamental para alguns aplicativos e não é tão crítica para outras pessoas. Esse assunto é naturalmente detalhadas e complicado compreender em um primeiro momento, mas ele faz com que uma enorme diferença no usuário experiência para que ele tenha a pena investir tempo e energia antecipadamente.

Idealmente, você poderia implementar QoS em sua rede interna durante a configuração de equipes, mas se você estiver pequeno suficiente é opcional. Isso permite que o atraso confidenciais tráfego de voz e vídeo para obter priorizados antes dos outros tráfegos. Você deseja fazer esta priorização em todos os dispositivos de cliente, bem como sobre os switches e roteadores em sua rede.

[**Análise de chamada e o painel de controle de qualidade de chamada**](difference-between-call-analytics-and-call-quality-dashboard.md) são usados para encontrar e solucionar problemas que surgem durante a operação em andamento.  

Análise de chamada mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados à chamadas específicas e reuniões para cada usuário em um Microsoft Teams ou Skype para a conta de negócios. Se você for um administrador do Office 365, você pode usar a análise de chamada para solucionar problemas de qualidade e conexão de chamada enfrentou em uma chamada específica. Isso pode ajudar a identificar e eliminar os problemas.

Painel de controle de qualidade de chamada (CQD) foi projetado para ajudar os administradores e os engenheiros de rede otimizam uma **rede**, não analisar e resolver problemas de uma única chamada. CQD alterna o foco de usuários específicos, examine as informações agregadas para uma organização inteira. Isso também pode ajudar a identificar e eliminar os problemas.

## <a name="related-topics"></a>Tópicos Relacionados

[Vídeo: Visão geral de qualidade de chamada](https://aka.ms/teams-quality)

[Configurar a análise de chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Ativando e usando o painel de controle de qualidade de chamada](turning-on-and-using-call-quality-dashboard.md)

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no Painel de Qualidade de Chamadas](stream-classification-in-call-quality-dashboard.md)