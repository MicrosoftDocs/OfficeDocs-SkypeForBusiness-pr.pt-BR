---
title: Configurar o serviço de mobilidade para alto desempenho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: Saiba mais sobre o serviço de mobilidade no Skype for Business Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305840"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar o serviço de mobilidade para alto desempenho no Skype for Business Server
 
**Resumo:** Saiba mais sobre o serviço de mobilidade no Skype for Business Server.
  
> [!IMPORTANT]
> Este tópico se aplica somente ao serviço Skype for Business Server Mobility (MCX) e não se aplica à API da Web de comunicação unificada (UCWA), conforme entregue nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro. 
  
Quando você instala o serviço de mobilidade (MCX) em serviços de informações da Internet (IIS) 7,5, o instalador do serviço de mobilidade configura algumas configurações de desempenho no servidor front-end. Recomendamos usar IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações concomitantes de usuários e o número máximo de threads permitidos para o Mobility Service.
  
Aqui estão as configurações de desempenho:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configurações para Mcx no IIS 7.5

1. **maxConcurrentThreadsPerCPU** está definido como zero (0).
    
2. **maxConcurrentRequestsPerCPU** está definido como zero (0).
    
3. O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).
    
4. O limite de fila HTTP.sys está definido como 1.000 (por padrão).
    

