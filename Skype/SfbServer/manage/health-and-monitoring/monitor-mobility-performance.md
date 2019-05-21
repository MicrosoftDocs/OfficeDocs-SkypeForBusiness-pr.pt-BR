---
title: Monitorar a mobilidade para desempenho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279918"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorar a mobilidade para desempenho no Skype for Business Server
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.
  
O serviço Skype for Business Server Mobility (MCX) e a API da Web de comunicação unificada (UCWA) aumentam a carga em servidores front-end e em pools front-end. Dispositivos móveis que mantêm uma conexão com o servidor, mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple que executam o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que Termine a conexão com o servidor quando o aplicativo móvel estiver minimizado. Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
Vários limites influenciam o desempenho da mobilidade: 
  
- Memória disponível
    
- Limite da fila de solicitações
    
- Conexões concorrentes
    
- Tamanho da fila do IIS
    
Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.
  
## <a name="in-this-section"></a>Nesta seção

- [Monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorar o uso do serviço de mobilidade e do UCWA no Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurar o serviço de mobilidade para alto desempenho no Skype for Business Server](configure-service.md)
    
- [Monitorar arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contadores de desempenho de mobilidade no Skype for Business Server](performance-counters.md)
    

