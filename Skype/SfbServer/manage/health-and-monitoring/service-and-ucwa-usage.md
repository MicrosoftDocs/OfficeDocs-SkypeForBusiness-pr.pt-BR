---
title: Monitorar o uso do Serviço de Mobilidade e do UCWA Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o Serviço de Mobilidade (Mcx) e a UCWA (Unified Communications Web API) no Skype for Business Server.'
ms.openlocfilehash: 6139ab53e964bd7c880a83a7af252fe2da71a152
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835249"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorar o uso do Serviço de Mobilidade e do UCWA Skype for Business Server
 
**Resumo:** Gerencie o Serviço de Mobilidade (Mcx) e a API Web de Comunicações Unificadas (UCWA) no Skype for Business Server.

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
Em uma base contínua, você deve monitorar a CPU e a memória que é usada pelo Serviço Skype for Business Server Mobility (Mcx) e pela UCWA (Unified Communications Web API). Para monitorar o uso, você pode usar o seguinte:
  
 **Para a UCWA (Unified Communications Web API):**
  
- O **processo de trabalho do LyncUcwa** no Serviços de Informações da Internet (IIS) Manager. No painel **Processos de** Trabalho, confira as colunas **CPU %** e **Bytes Particulares (KB)** (memória).
    
- Os **contadores de** desempenho da CPU **e** do processador.
    
Para a maioria das implantações, o uso da CPU do UCWA deve estar abaixo de 15% em média. O uso da memória deve estar dentro dos limites descritos em [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).
  
Além dos contadores de uso de CPU e memória, você pode usar os seguintes contadores de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **LS:WEB - Throttling and Authentication\WEB - Total de** Solicitações no Processamento , que indica o número de solicitações da Web pendentes no servidor. Quando esse contador atingir 10.000, as solicitações subsequentes falharão, com a mensagem de erro "503 - Serviço Indisponível".
    
- **ASP.NET\Solicitações enluadas** (sempre deve ser zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, deverá revisitar e re computar seu planejamento de capacidade para o cálculo correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web. 
  
 **Para o Serviço de Mobilidade (Mcx):**
  
- Os processos de trabalho **CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador Serviços de Informações da Internet (IIS). No painel **Processos de** Trabalho, confira as colunas **CPU %** e **Bytes Particulares (KB)** (memória).
    
- Os **contadores de** desempenho da CPU **e** do processador.
    
Para a maioria das implantações, o uso da CPU do Mobility Service deve estar abaixo de 15%, em média. O uso da memória deve estar dentro dos limites descritos em [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).
  
Além dos contadores de uso de CPU e memória, você pode usar os seguintes contadores ASP.NET de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **ASP.NET v2.0.50727\Solicitações Atuais**, que indica o número de solicitações da Web pendentes no servidor. Quando esse contador atingir 5.000, as solicitações subsequentes falharão com a mensagem de erro " 503 - Serviço Indisponível".
    
- **ASP.NET\Solicitações enluadas** (sempre deve ser zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, você deverá revisitar e recompuir seu planejamento de capacidade para o corretamente de recolhimento de CPU, número de núcleos e memória para os computadores que hospedam os serviços Web. 

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
## <a name="see-also"></a>Confira também

[Monitorar os limites de capacidade de memória do servidor Skype for Business Server](server-memory-capacity-limits.md)
