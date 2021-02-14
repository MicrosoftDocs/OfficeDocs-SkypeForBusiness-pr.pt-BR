---
title: Monitorar os limites de capacidade de memória do servidor no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumo: Saiba como monitorar os limites de capacidade da memória do servidor no Skype for Business Server.'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814291"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorar os limites de capacidade de memória do servidor no Skype for Business Server
 
**Resumo:** Saiba como monitorar os limites de capacidade de memória do servidor no Skype for Business Server.
  
> [!CAUTION]
> As informações neste tópico que se referem ao Planejamento de Capacidade pertencem apenas aos clientes do Lync 2010 Mobile e ao Mobility Service (Mcx). O Planejamento de capacidade para a Unified Communications Web API (UCWA), usado pelos clientes do Lync 2013 Mobile, é fornecido pela Ferramenta de Planejamento do Lync Server 2013. 

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
Dois contadores de desempenho de mobilidade podem ajudá-lo a determinar seu uso atual e a planejar a capacidade para o Serviço de Mobilidade do Skype for Business Server (Mcx), bem como monitorar o uso de memória para o UCWA. Para UCWA, a categoria de contador **é LS:WEB - UCWA**. Para o Mobility Service (Mcx), os contadores estão sob a categoria **LS:WEB - Mobile Communication Service**. Os contadores a monitorar são:
  
- Contagem atual de sessão ativa com **assinaturas** de presença ativa , que é o número atual de pontos de extremidade registrados por meio de UCWA ou o Serviço de Mobilidade (Mcx) que têm assinaturas de presença ativa (número de usuários móveis sempre conectados)
    
- **Contagem de sessões ativas** no momento, que é o número atual de pontos de extremidade registrados por meio do UCWA ou do Mobility Service
    
Se a diferença entre a Contagem atual de  sessão ativa com **assinaturas** de presença ativa e contagem de sessão ativa no momento for pequena ao longo do tempo, isso significa que a maioria dos usuários de dispositivo móvel tem um dispositivo sempre conectado, como um dispositivo móvel Android ou Nokia (somente para Mcx). Os dispositivos sempre conectados ao UCWA incluem dispositivos Apple e Android executando clientes do Lync 2013 Mobile). Se  a contagem de sessão ativa no momento for muito maior do que a contagem atual de sessão ativa com **assinaturas** de presença ativa , isso indica que mais usuários estão usando um dispositivo de ponto de extremidade em segundo plano, como um dispositivo Apple iOS ou Windows Phone em Mcx. (O Windows Phone é o único cliente Lync 2013 Mobile que se registrará desta forma).
  
Você deve definir um limite na Contagem atual de  sessão ativa com **assinaturas** de presença ativa e contadores de desempenho de contagem de sessão ativa no momento com base em seu uso esperado, resultados de planejamento de capacidade e monitoramento contínuo do Mobility Service e outros contadores do Servidor front-end. Os limites definidos devem permitir que você avalie a capacidade do servidor e eleva alertas quando a capacidade é excedida.
  
Para determinar os limites apropriados, você precisa primeiro determinar quanta memória está disponível no Servidor front-end para o Serviço de Mobilidade. Monitore os contadores para determinar quando você precisa planejar capacidade extra, de acordo com a seguinte fórmula:
  
Memória total usada pelo Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * Contagem atual de sessão ativa com **assinaturas** de presença ativa + 400 / 1024 * **(** Contagem atual de sessão ativa contagem de sessão atualmente ativa com  -  **assinaturas** de presença ativa )
  
> [!IMPORTANT]
> A Calculadora de Capacidade do Microsoft Lync Server 2010 é uma planilha pré-populada com todas as fórmulas que permitem que um planejador determine quais serão os requisitos para os servidores do Skype for Business, incluindo CPU, memória e disco rígido. Você pode [baixar a planilha e um documento associado.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
O Servidor front-end precisa de memória suficiente disponível para dar suporte ao Serviço de Mobilidade em situações de failover. Você pode monitorar a memória disponível atual no Servidor front-end usando o contador **Memory\Available Mbytes** ou usando a equação mencionada anteriormente para planejar a quantidade de memória que você espera que o Mobility Service use.
  
Se a quantidade de memória disponível no Servidor front-end for menor que 1.500 MB ao planejar o número esperado de usuários de mobilidade, você precisará adicionar mais hardware para dar suporte ao Serviço de Mobilidade. Para obter mais detalhes, [consulte Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) in the Operations documentation.
  
## <a name="see-also"></a>Confira também

[Monitorar a mobilidade para desempenho no Skype for Business Server](monitor-mobility-performance.md)
