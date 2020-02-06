---
title: Monitorar o uso do serviço de mobilidade e do UCWA no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: gerenciar o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817680"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Monitorar o uso do serviço de mobilidade e do UCWA no Skype for Business Server
 
**Resumo:** Gerenciar o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
Continuamente, você deve monitorar a CPU e a memória usadas pelo serviço Skype for Business Server Mobility (MCX) e pela API da Web de comunicação unificada (UCWA). Para monitorar o uso, você pode usar uma das opções a seguir:
  
 **Para Unified Communications Web API (UCWA):**
  
- O processo de trabalho do **LyncUcwa** no Gerenciador dos serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.
    
- Os contadores de desempenho da **CPU** e do **Processador**.
    
Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média. O uso da memória deve ficar dentro dos limites descritos em [monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md).
  
Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **Ls: Web-throttling e Authentication\WEB-total de solicitações em processamento**, que indica o número de solicitações de Web pendentes no servidor. Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".
    
- **ASP.NET\Requests Queued** (deve ser sempre zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web. 
  
 **Para o Mobility Service (Mcx):**
  
- Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador dos serviços de informações da Internet (IIS). No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.
    
- Os contadores de desempenho da **CPU** e do **Processador**.
    
Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média. O uso da memória deve ficar dentro dos limites descritos em [monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md).
  
Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:
  
- **ASP.NET v2.0.50727\Requests Current**, que indica o número de solicitações Web pendentes no servidor. Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".
    
- **ASP.NET\Requests Queued** (deve ser sempre zero).
    
> [!NOTE]
> Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web. 

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
## <a name="see-also"></a>Confira também

[Monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md)
