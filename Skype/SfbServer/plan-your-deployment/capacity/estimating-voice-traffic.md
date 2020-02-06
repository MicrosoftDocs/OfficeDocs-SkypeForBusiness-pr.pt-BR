---
title: Estimando o uso de voz e o tráfego do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816060"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="be6c0-103">Estimando o uso de voz e o tráfego do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="be6c0-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="be6c0-104">Você pode usar a métrica a seguir para estimar o tráfego do usuário em cada site e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="be6c0-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="be6c0-105">No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="be6c0-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="be6c0-106">No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="be6c0-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="be6c0-107">No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="be6c0-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="be6c0-108">O número de portas, por sua vez, determina o número de servidores e gateways de mediação que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="be6c0-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="be6c0-109">Os gateways de rede telefônica pública comutada (PSTN) que a maioria das organizações considera implantando o tamanho de duas portas para até 960 portas.</span><span class="sxs-lookup"><span data-stu-id="be6c0-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="be6c0-110">(Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)</span><span class="sxs-lookup"><span data-stu-id="be6c0-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="be6c0-p102">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="be6c0-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

