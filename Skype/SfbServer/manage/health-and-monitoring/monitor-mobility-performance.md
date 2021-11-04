---
title: Monitorar mobilidade para desempenho em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: saiba mais sobre o Serviço de Mobilidade (Mcx) e a UCWA (Unified Communications Web API) no Skype for Business Server.'
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746917"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Monitorar mobilidade para desempenho em Skype for Business Server
 
**Resumo:** Saiba mais sobre o Serviço de Mobilidade (Mcx) e a API Web de Comunicações Unificadas (UCWA) no Skype for Business Server.
  
O Skype for Business Server Mobility Service (Mcx) e a UCWA (Unified Communications Web API) aumentam a carga em servidores front-end e pools de front-end. Dispositivos móveis que mantêm uma conexão com o servidor mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia executando o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerram sua conexão com o servidor quando o aplicativo móvel é minimizado. À medida que seu uso de mobilidade aumenta, você deve monitorar o desempenho da mobilidade para determinar quando você precisa aumentar sua capacidade.

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
Vários limites influenciam o desempenho da mobilidade: 
  
- Memória disponível
    
- Limite da fila de solicitações
    
- Conexões concorrentes
    
- Tamanho da fila do IIS
    
Outros limites em servidores que podem influenciar o desempenho da mobilidade são, no máximo, 12 insussões simultâneas, autenticações, renovações de sessão e terminações. Esses máximos não precisam ser modificados para a maioria das implantações.
  
## <a name="in-this-section"></a>Nesta seção

- [Monitorar os limites de capacidade de memória do servidor Skype for Business Server](server-memory-capacity-limits.md)
    
- [Monitorar o uso do Serviço de Mobilidade e do UCWA Skype for Business Server](service-and-ucwa-usage.md)
    
- [Configurar o Serviço de Mobilidade para alto desempenho em Skype for Business Server](configure-service.md)
    
- [Monitorando arquivos de log de rastreamento de solicitação do IIS Skype for Business Server](iis-request-tracing-log-files.md)
    
- [Contadores de desempenho de mobilidade Skype for Business Server](performance-counters.md)
    

