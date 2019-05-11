---
title: Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumo: Saiba como monitorar limites de capacidade de memória do servidor no Skype para Business Server.'
ms.openlocfilehash: fd299dc1108f8d7de1a884245448772f6623a940
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897447"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server
 
**Resumo:** Saiba como para o monitoramento de limites de capacidade de memória do servidor no Skype para Business Server.
  
> [!CAUTION]
> As informações neste tópico referente ao planejamento de capacidade refere-se somente a clientes móveis do Lync 2010 e o serviço de mobilidade (Mcx). Planejamento de capacidade para o Unified Communications Web API (UCWA), usado pelos clientes do Lync 2013 Mobile, é fornecido pelo Lync Server 2013, ferramenta de planejamento. 

> [!NOTE]
> Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.
  
Dois contadores de desempenho de mobilidade podem ajudá-lo a determinar seu uso atual e ajudá-lo a planejar a capacidade para o Skype Business Server Mobility Service (Mcx), bem como para monitorar o uso de memória para UCWA. Para UCWA, a categoria do contador é **LS:WEB - UCWA**. Para o Serviço de mobilidade (Mcx), os contadores estão sob a categoria **LS:WEB - Mobile Communication Service**. Os contadores para monitoramento são:
  
- **Contagem atual da sessão ativa com as assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de mobilidade ou UCWA que tem assinaturas de presença ativa (número de usuários móveis sempre conectados).
    
- **Contagem atual de sessão ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de Mobilidade ou UCWA.
    
Se a diferença entre **Contagem atual de sessão ativa com assinaturas de presença ativa** e **Contagem atual de sessão ativa** for pequena com o passar do tempo, isso significa que a maioria dos usuários de dispositivos móveis tem um dispositivo sempre conectado, como um dispositivo Android ou Nokia (somente para Mcx). Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android executando clientes do Lync 2013 Mobile). Se **Contagem atual de sessão ativa** for muito maior que **Contagem atual de sessão ativa com assinaturas de presença ativa**, isso mostra que mais usuários estão usando um dispositivo de ponto de extremidade de plano de fundo, como um dispositivo Apple iOS ou um Windows Phone com Mcx. (O Windows Phone é o único cliente do Lync 2013 Mobile que será registrado como isso).
  
Você deve definir um limite sobre os contadores de desempenho **Atualmente contagem de sessão ativa com assinaturas de presença ativa** e **Contagem de sessão ativa no momento** , com base em seu uso esperado, resultados de planejamento de capacidade e monitoramento contínuo de Serviço de mobilidade e outros contadores de servidor Front-End. Os limites que você definir devem permitir a avaliação da capacidade do servidor e emitir alertas quando a capacidade for excedida.
  
Para determinar os limites apropriados, você precisará primeiro determinar quanta memória está disponível no servidor Front-End para o serviço Mobility. Monitore os contadores determinar quando você precisa planejar uma capacidade extra, de acordo com a fórmula a seguir:
  
Total de memória usada pelo serviço de mobilidade Mcx (MB) = 164 + (400 + 134) / 1024 * **Atualmente contagem de sessão ativa com assinaturas de presença ativa** + 400 / 1024 * ( **Contagem de sessão ativa no momento** - **contagem de sessão ativa no momento com Assinaturas de presença ativa**)
  
> [!IMPORTANT]
> A Calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha que é pré-preenchido com todas as fórmulas que permitem que um planejador determinar quais serão os requisitos para o Skype para servidores de negócios, incluindo CPU, memória e disco rígido. Você pode [Baixar a planilha e um documento associado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
Servidor Front-End precisa memória suficiente disponível para suportar o serviço de mobilidade nas situações de failover. Você pode monitorar a memória disponível atual no servidor Front-End usando o contador **Memory\Available Mbytes** ou usando a equação mencionada anteriormente, planejar a quantidade de memória que você espera que o serviço de mobilidade para usar.
  
Se a quantidade de memória disponível no servidor Front-End for menor do que 1.500 MB ao planejar o número esperado de usuários de mobilidade, você precisa adicionar mais hardware para suportar o serviço de mobilidade. Para obter mais detalhes, consulte [mobility Monitor de desempenho no Skype para Business Server](monitor-mobility-performance.md) na documentação operações.
  
## <a name="see-also"></a>Confira também

[Monitorar a mobilidade de desempenho no Skype para Business Server](monitor-mobility-performance.md)
