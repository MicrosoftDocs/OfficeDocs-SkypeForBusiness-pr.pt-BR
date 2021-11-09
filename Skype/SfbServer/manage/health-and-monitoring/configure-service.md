---
title: Configurar o Serviço de Mobilidade para alto desempenho em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: saiba mais sobre o Serviço de Mobilidade Skype for Business Server.'
ms.openlocfilehash: 4c07c1e487875a41da0d1ba3c0d8872d96a5ac70
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828784"
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
    

