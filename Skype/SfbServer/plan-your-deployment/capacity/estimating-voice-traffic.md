---
title: Estimando o uso e o tráfego de voz para o Skype for Business Server
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
description: Você pode usar a métrica a seguir para estimar o tráfego do usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827681"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="c6afa-103">Estimando o uso e o tráfego de voz para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c6afa-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="c6afa-104">Você pode usar a métrica a seguir para estimar o tráfego do usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="c6afa-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="c6afa-105">Para **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="c6afa-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="c6afa-106">Para **Tráfego médio**, (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="c6afa-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="c6afa-107">Para **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta</span><span class="sxs-lookup"><span data-stu-id="c6afa-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="c6afa-108">O número de portas, por sua vez, determina o número de Servidores de Mediação e gateways que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="c6afa-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="c6afa-109">Os gateways PSTN (rede telefônica pública comutado) que a maioria das organizações considera implantar variam de duas portas a até 960 portas.</span><span class="sxs-lookup"><span data-stu-id="c6afa-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="c6afa-110">(Há gateways ainda maiores, mas eles são usados principalmente por provedores de serviços de telefonia.)</span><span class="sxs-lookup"><span data-stu-id="c6afa-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="c6afa-p102">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="c6afa-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

