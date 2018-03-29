---
title: Monitorar desempenho de mobilidade no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba sobre o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas em Skype para Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Monitorar desempenho de mobilidade no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas no Skype para Business Server 2015.
  
O Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA) aumentar a carga nos servidores Front-End, pools de Front-End. Dispositivos móveis que mantêm uma conexão ao servidor, mesmo quando o aplicativo móvel estiver minimizado, como Android e Nokia dispositivos que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerrar sua conexão ao servidor quando o aplicativo móvel estiver minimizado. Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.
  
Vários limites influenciam o desempenho da mobilidade: 
  
- Memória disponível
    
- Limite da fila de solicitações
    
- Conexões concorrentes
    
- Tamanho da fila do IIS
    
Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.
  
## <a name="in-this-section"></a>Nesta seção

- [Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server 2015](server-memory-capacity-limits.md)
    
- [Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server 2015](service-and-ucwa-usage.md)
    
- [Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server 2015](configure-service.md)
    
- [Monitoramento do IIS solicitar os arquivos de log de rastreamento em Skype para Business Server 2015](iis-request-tracing-log-files.md)
    
- [Contadores de desempenho de mobilidade no Skype para Business Server 2015](performance-counters.md)
    

