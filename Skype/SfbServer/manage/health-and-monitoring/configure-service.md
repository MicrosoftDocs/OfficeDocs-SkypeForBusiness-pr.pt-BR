---
title: Configurar alto desempenho do Serviço de Mobilidade no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: Saiba mais sobre o serviço de mobilidade no Skype para Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Configurar alto desempenho do Serviço de Mobilidade no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o serviço de mobilidade no Skype para Business Server 2015.
  
> [!IMPORTANT]
> Este tópico se aplica somente ao Skype para Business Server 2015 Mobility Service (Mcx) e não se aplica para o API do Web de comunicações unificadas (UCWA), conforme entregues as atualizações cumulativas do Lync Server 2013: fevereiro de 2013. 
  
Quando você instala o serviço de mobilidade (Mcx) nos serviços de informações da Internet (IIS) 7.5, o instalador do Mobility Service configura algumas configurações de desempenho no servidor Front-End. Recomendamos usar IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações concomitantes de usuários e o número máximo de threads permitidos para o Mobility Service.
  
Aqui estão as configurações de desempenho:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configurações para Mcx no IIS 7.5

1. **maxConcurrentThreadsPerCPU** está definido como zero (0).
    
2. **maxConcurrentRequestsPerCPU** está definido como zero (0).
    
3. O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).
    
4. O limite de fila HTTP.sys está definido como 1.000 (por padrão).
    

