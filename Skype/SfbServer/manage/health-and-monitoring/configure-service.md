---
title: Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: Saiba mais sobre o serviço de mobilidade no Skype para Business Server.'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876405"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server
 
**Resumo:** Saiba mais sobre o serviço de mobilidade no Skype para Business Server.
  
> [!IMPORTANT]
> Este tópico se aplica somente ao Skype para Business Server Mobility Service (Mcx) e não se aplica para o API do Web de comunicações unificadas (UCWA), conforme entregues as atualizações cumulativas do Lync Server 2013: fevereiro de 2013. 
  
Quando você instala o serviço de mobilidade (Mcx) nos serviços de informações da Internet (IIS) 7.5, o instalador do Mobility Service configura algumas configurações de desempenho no servidor Front-End. Recomendamos usar IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações concomitantes de usuários e o número máximo de threads permitidos para o Mobility Service.
  
Aqui estão as configurações de desempenho:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configurações para Mcx no IIS 7.5

1. **maxConcurrentThreadsPerCPU** está definido como zero (0).
    
2. **maxConcurrentRequestsPerCPU** está definido como zero (0).
    
3. O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).
    
4. O limite de fila HTTP.sys está definido como 1.000 (por padrão).
    

