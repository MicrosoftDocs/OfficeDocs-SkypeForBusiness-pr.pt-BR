---
title: Estimando o uso e o tráfego de voz para Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Você pode usar a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.
ms.openlocfilehash: 470590baf8ce5735b77576292fc6558d916dd3a7173b95c113b74d42f35c5224
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318834"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimando o uso e o tráfego de voz para Skype for Business Server
 
Você pode usar a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.
  
> Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta
> 
> Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta
> 
> Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta
    
O número de portas, por sua vez, determina o número de Servidores de Mediação e gateways que serão necessários. Os gateways PSTN (rede telefônica pública comutado) que a maioria das organizações considera implantar no intervalo de tamanho de duas portas para até 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  

