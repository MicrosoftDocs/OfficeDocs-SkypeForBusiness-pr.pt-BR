---
title: Configurar o Serviço de Mobilidade para alto desempenho no Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: saiba mais sobre o Serviço de Mobilidade no Skype for Business Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817031"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Configurar o Serviço de Mobilidade para alto desempenho no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Serviço de Mobilidade no Skype for Business Server.
  
> [!IMPORTANT]
> Este tópico se aplica somente ao Serviço de Mobilidade do Skype for Business Server (Mcx) e não se aplica à Unified Communications Web API (UCWA), conforme fornecido nas Atualizações Cumulativas do Lync Server 2013: fevereiro de 2013. 
  
Quando você instala o Mobility Service (Mcx) no Internet Information Services (IIS) 7.5, o instalador do Mobility Service define algumas configurações de desempenho no Servidor front-end. Recomendamos o uso do IIS 7.5 para mobilidade. As configurações afetam o número máximo de solicitações de usuário simultâneas e o número máximo de segmentos permitidos para o Serviço de Mobilidade.
  
Aqui estão as configurações de desempenho:
  
### <a name="settings-for-mcx-on-iis-75"></a>Configurações para Mcx no IIS 7.5

1. **maxConcurrentThreadsPerCPU** está definido como zero (0).
    
2. **maxConcurrentRequestsPerCPU** está definido como zero (0).
    
3. O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).
    
4. O limite de fila HTTP.sys está definido como 1.000 (por padrão).
    

