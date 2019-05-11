---
title: Estimando o uso de voz e o tráfego para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Você pode usar a métrica a seguir para estimar o tráfego de usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
ms.openlocfilehash: 711ba624baa19531f49b137458d692a0f60229bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910711"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a>Estimando o uso de voz e o tráfego para Skype para Business Server
 
Você pode usar a métrica a seguir para estimar o tráfego de usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
  
> No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.
> 
> No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.
> 
> No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.
    
Por sua vez, o número de portas determina o número de servidores de mediação e gateways que serão necessários. Os gateways PSTN (rede) telefônica comutada pública que a maioria das organizações considera para implantação variam em tamanho de 2 portas a 960 portas. (Há gateways até maiores, mas esses são usados principalmente pelos provedores de serviços de telefonia).
  
Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.
  

