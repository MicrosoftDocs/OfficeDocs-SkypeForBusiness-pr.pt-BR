---
title: Estimando o uso de voz e o tráfego para Skype para Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/22/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Você pode usar a métrica a seguir para estimar o tráfego de usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.
ms.openlocfilehash: dffcfdf7dcf70162b2a9c9ce65ab56b9025a4db0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server-2015"></a><span data-ttu-id="cfc3d-103">Estimando o uso de voz e o tráfego para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cfc3d-103">Estimating voice usage and traffic for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cfc3d-104">Você pode usar a métrica a seguir para estimar o tráfego de usuário em cada local e o número de portas necessárias para dar suporte a esse tráfego.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="cfc3d-105">No caso de **Tráfego leve** (uma chamada PSTN por usuário por hora), calcula-se 15 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="cfc3d-106">No caso de **Tráfego médio** (duas chamadas PSTN por usuário por hora), calcula-se 10 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="cfc3d-107">No caso de **Tráfego pesado** (três ou mais chamadas PSTN por usuário por hora), calcula-se 5 usuários por porta.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="cfc3d-108">Por sua vez, o número de portas determina o número de servidores de mediação e gateways que serão necessários.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="cfc3d-109">Os gateways PSTN (rede) telefônica comutada pública que a maioria das organizações considera para implantação variam em tamanho de 2 portas a 960 portas.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="cfc3d-110">(Há gateways até maiores, mas esses são usados principalmente pelos provedores de serviços de telefonia).</span><span class="sxs-lookup"><span data-stu-id="cfc3d-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="cfc3d-p102">Por exemplo, uma organização com 10.000 usuários e tráfego médio exigiria 1000 portas. O número de gateways necessário seria igual o número total de portas necessárias, conforme determinado pela capacidade total dos gateways.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

