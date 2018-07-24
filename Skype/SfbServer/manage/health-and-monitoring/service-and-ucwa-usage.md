---
title: Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975946"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server
 
**Resumo:** Gerencie o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.

> [!NOTE]
> Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual.
  
Em uma base contínua, você deve monitorar a CPU e memória que é usada pelo Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA). Para monitorar o uso, você pode usar uma das opções a seguir:
  
 **Para Unified Communications Web API (UCWA):**
  
- O processo de trabalho **LyncUcwa** no Gerenciador de serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.
    
- Os contadores de desempenho da **CPU** e do **Processador**.
    
Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média. Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md).
  
Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **LS:WEB - limitação e Authentication\WEB - Total de solicitações no processamento**, que indica o número de solicitações da web no servidor pendentes. Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".
    
- **ASP.NET \requests Queued** (deve ser sempre zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web. 
  
 **Para o Mobility Service (Mcx):**
  
- Os processos de trabalho do **CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador de serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.
    
- Os contadores de desempenho da **CPU** e do **Processador**.
    
Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média. Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md).
  
Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **ASP.NET v2.0.50727\Requests atual**, que indica o número de solicitações da web no servidor pendentes. Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".
    
- **ASP.NET \requests Queued** (deve ser sempre zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web. 

> [!NOTE]
> Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual.
  
## <a name="see-also"></a>Consulte também

[Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md)