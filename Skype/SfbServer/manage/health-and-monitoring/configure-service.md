---
title: Configurar o Serviço de Mobilidade para alto desempenho em Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: saiba mais sobre o Serviço de Mobilidade Skype for Business Server.'
ms.openlocfilehash: ddf976d6adde4a8214a1a7ae1cc40930df421fd6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746983"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar o Serviço de Mobilidade para alto desempenho em Skype for Business Server
 
**Resumo:** Saiba mais sobre o Serviço de Mobilidade Skype for Business Server.
  
> [!IMPORTANT]
> Este tópico se aplica apenas ao Serviço de Mobilidade Skype for Business Server (Mcx) e não se aplica à UCWA (Unified Communications Web API), conforme fornecido nas Atualizações Cumulativas do Lync Server 2013: fevereiro de 2013. 
  
Quando você instala o Serviço de Mobilidade (Mcx) no Serviços de Informações da Internet (IIS) 7.5, o instalador do Mobility Service configura algumas configurações de desempenho no Servidor front-end. Recomendamos o uso do IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações de usuário simultâneas e o número máximo de segmentos permitidos para o Serviço de Mobilidade.
  
Aqui estão as configurações de desempenho:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configurações mcx no IIS 7.5

1. **maxConcurrentThreadsPerCPU** está definido como zero (0).
    
2. **maxConcurrentRequestsPerCPU** está definido como zero (0).
    
3. O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).
    
4. O limite de fila HTTP.sys está definido como 1.000 (por padrão).
    

