---
title: Monitorar os limites de capacidade de memória do servidor no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumo: saiba como monitorar os limites de capacidade de memória do servidor no Skype for Business Server.'
ms.openlocfilehash: f089ab9b5be693872754691050133ad27e992896
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279820"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorar os limites de capacidade de memória do servidor no Skype for Business Server
 
**Resumo:** Saiba como monitorar os limites de capacidade de memória do servidor no Skype for Business Server.
  
> [!CAUTION]
> As informações neste tópico referem-se ao planejamento da capacidade refere-se somente aos clientes móveis do Lync 2010 e ao serviço de mobilidade (MCX). O planejamento de capacidade para a API da Web de comunicação unificada (UCWA), usado pelos clientes móveis do Lync 2013, é fornecido pela ferramenta de planejamento 2013 do Lync Server. 

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
Dois contadores de desempenho de mobilidade podem ajudar você a determinar o seu uso atual e a planejar a capacidade do Skype for Business Server Mobility Service (MCX), bem como monitorar o uso da memória para UCWA. Para o UCWA, a categoria Counter é **ls: Web-UCWA**. Para o Serviço de mobilidade (Mcx), os contadores estão sob a categoria **LS:WEB - Mobile Communication Service**. Os contadores para monitoramento são:
  
- **Contagem atual da sessão ativa com as assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de mobilidade ou UCWA que tem assinaturas de presença ativa (número de usuários móveis sempre conectados).
    
- **Contagem atual de sessão ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de Mobilidade ou UCWA.
    
Se a diferença entre **Contagem atual de sessão ativa com assinaturas de presença ativa** e **Contagem atual de sessão ativa** for pequena com o passar do tempo, isso significa que a maioria dos usuários de dispositivos móveis tem um dispositivo sempre conectado, como um dispositivo Android ou Nokia (somente para Mcx). Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android que executam clientes móveis do Lync 2013). Se **Contagem atual de sessão ativa** for muito maior que **Contagem atual de sessão ativa com assinaturas de presença ativa**, isso mostra que mais usuários estão usando um dispositivo de ponto de extremidade de plano de fundo, como um dispositivo Apple iOS ou um Windows Phone com Mcx. (O Windows Phone é o único cliente móvel do Lync 2013 que será registrado como este).
  
Você deve definir um limite na **contagem de sessões ativas atualmente com assinaturas de presença ativas** e contadores de desempenho de **contagem de sessões ativas no momento** com base no uso esperado, nos resultados de planejamento de capacidade e na monitoração contínua de Serviço de mobilidade e outros contadores de servidor front-end. Os limites que você definir devem permitir a avaliação da capacidade do servidor e emitir alertas quando a capacidade for excedida.
  
Para determinar os limites apropriados, você precisa primeiro determinar a quantidade de memória disponível no servidor front-end para o serviço de mobilidade. Monitore os contadores determinar quando você precisa planejar uma capacidade extra, de acordo com a fórmula a seguir:
  
Total de memória usada pelo serviço de mobilidade do MCX (MB) = 164 + (400 + 134)/1024 * **contagem de sessões ativas atualmente com assinaturas de presença ativas** + 400 **** - /1024 * (contagem de sessões ativas atualmente**ativas atualmente com Assinaturas de presença ativas**)
  
> [!IMPORTANT]
> A calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha preenchida previamente com todas as fórmulas que permitem que um planejador determine quais são os requisitos para os servidores do Skype for Business, incluindo CPU, memória e disco rígido. Você pode [baixar a planilha e um documento associado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
O servidor front-end precisa de memória suficiente disponível para dar suporte ao serviço de mobilidade em situações de failover. Você pode monitorar a memória atual disponível no servidor front-end usando o contador **Memory\Available Mbytes** ou usando a equação mencionada anteriormente para planejar a quantidade de memória que você espera que o serviço de mobilidade use.
  
Se a quantidade de memória disponível no servidor front-end for inferior a 1.500 MB ao planejar o número esperado de usuários da mobilidade, você precisará adicionar mais hardware para dar suporte ao serviço de mobilidade. Para obter mais detalhes, consulte [monitorar a mobilidade para desempenho no Skype for Business Server](monitor-mobility-performance.md) na documentação de operações.
  
## <a name="see-also"></a>Confira também

[Monitorar a mobilidade para desempenho no Skype for Business Server](monitor-mobility-performance.md)
