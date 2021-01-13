---
title: Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o Serviço de Mobilidade (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814241"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server
 
**Resumo:** Gerencie o Serviço de Mobilidade (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando o MCX precisarão atualizar para um cliente atual.
  
Você deve monitorar continuamente a CPU e a memória usada pelo Serviço de Mobilidade do Skype for Business Server (Mcx) e pela UNIFIED Communications Web API (UCWA). Para monitorar o uso, você pode usar o seguinte:
  
 **Para Unified Communications Web API (UCWA):**
  
- O processo de trabalho do **LyncUcwa** no Gerenciador do Serviços de Informações da Internet (IIS). No painel **Processos de** Trabalho, veja a % **da CPU** e as colunas **Bytes Particulares (KB)** (memória).
    
- Os **contadores** de desempenho **da** CPU e do processador.
    
Para a maioria das implantações, o uso da CPU do UCWA deve estar abaixo de 15% em média. O uso de memória deve estar dentro dos limites descritos no Monitor para limites de capacidade de memória do [servidor no Skype for Business Server.](server-memory-capacity-limits.md)
  
Além dos contadores de uso da CPU e da memória, você pode usar os seguintes contadores de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, que indica o número de solicitações web pendentes no servidor. Quando esse contador atingir 10.000, as solicitações subsequentes falharão, com a mensagem de erro "503 - Serviço Indisponível".
    
- **ASP.NET\Solicitações na Fila** (deve sempre ser zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, revisite e re compute seu planejamento de capacidade para o reavaliamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web. 
  
 **Para o Mobility Service (Mcx):**
  
- Os **processos de trabalho CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador do IIS (Serviços de Informações da Internet). No painel **Processos de** Trabalho, veja a % **da CPU** e as colunas **Bytes Particulares (KB)** (memória).
    
- Os **contadores** de desempenho **da** CPU e do processador.
    
Para a maioria das implantações, o uso da CPU do Mobility Service deve estar abaixo de 15%, em média. O uso de memória deve estar dentro dos limites descritos no Monitor para limites de capacidade de memória do [servidor no Skype for Business Server.](server-memory-capacity-limits.md)
  
Além dos contadores de uso da CPU e da memória, você pode usar os seguintes contadores ASP.NET de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **ASP.NET v2.0.50727\Solicitações** Atuais , que indica o número de solicitações da Web pendentes no servidor. Quando esse contador atingir 5.000, as solicitações subsequentes falharão com a mensagem de erro "503 - Serviço Indisponível".
    
- **ASP.NET\Solicitações na Fila** (deve sempre ser zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, revisite e recompute seu planejamento de capacidade para o reavaliamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web. 

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando o MCX precisarão atualizar para um cliente atual.
  
## <a name="see-also"></a>Confira também

[Monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md)
