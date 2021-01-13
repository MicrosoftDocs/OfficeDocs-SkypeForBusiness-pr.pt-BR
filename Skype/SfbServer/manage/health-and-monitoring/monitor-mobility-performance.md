---
title: Monitorar a mobilidade para desempenho no Skype for Business Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: saiba mais sobre o Mobility Service (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816831"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorar a mobilidade para desempenho no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Mobility Service (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.
  
O Serviço de Mobilidade do Skype for Business Server (Mcx) e o Unified Communications Web API (UCWA) aumentam a carga em servidores front-end e pools de front-end. Dispositivos móveis que mantêm uma conexão com o servidor mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia executando o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerram sua conexão com o servidor quando o aplicativo móvel é minimizado. À medida que o uso da mobilidade aumenta, você deve monitorar o desempenho da mobilidade para determinar quando precisa aumentar sua capacidade.

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
Vários limites influenciam o desempenho da mobilidade: 
  
- Memória disponível
    
- Limite da fila de solicitações
    
- Conexões concorrentes
    
- Tamanho da fila do IIS
    
Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de 12 logins simultâneos, autenticações, renovações de sessão e encerramentos. Esses máximos não precisam ser modificados para a maioria das implantações.
  
## <a name="in-this-section"></a>Nesta seção

- [Monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurar o Serviço de Mobilidade para alto desempenho no Skype for Business Server](configure-service.md)
    
- [Monitorando arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contadores de desempenho de mobilidade no Skype for Business Server](performance-counters.md)
    

