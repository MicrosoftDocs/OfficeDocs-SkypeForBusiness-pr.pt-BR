---
title: Monitorar a mobilidade de desempenho no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990634"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorar a mobilidade de desempenho no Skype para Business Server
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) e de comunicação unificada Web API (UCWA) no Skype para Business Server.
  
O Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA) aumentar a carga nos servidores Front-End, pools de Front-End. Dispositivos móveis que mantêm uma conexão ao servidor, mesmo quando o aplicativo móvel estiver minimizado, como Android e Nokia dispositivos que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerrar sua conexão ao servidor quando o aplicativo móvel estiver minimizado. Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.

> [!NOTE]
> Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual.
  
Vários limites influenciam o desempenho da mobilidade: 
  
- Memória disponível
    
- Limite da fila de solicitações
    
- Conexões concorrentes
    
- Tamanho da fila do IIS
    
Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.
  
## <a name="in-this-section"></a>Nesta seção

- [Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md)
    
- [Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server](service-and-ucwa-usage.md)
    
- [Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server](configure-service.md)
    
- [Monitoramento de arquivos de log do Skype de rastreamento para o Business Server de solicitação do IIS](iis-request-tracing-log-files.md)
    
- [Contadores de desempenho de mobilidade no Skype para Business Server](performance-counters.md)
    

