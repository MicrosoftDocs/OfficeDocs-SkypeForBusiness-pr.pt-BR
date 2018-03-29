---
title: Componentes obrigatórios para Enterprise Voice no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 2c5df4c0d580d767693717cf48585ceb0d4c7365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="c57cc-103">Componentes obrigatórios para Enterprise Voice no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c57cc-103">Components required for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c57cc-104">Um resumo dos componentes do Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c57cc-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="c57cc-105">Para implantar o Enterprise Voice, os seguintes componentes são necessários na sua topologia.</span><span class="sxs-lookup"><span data-stu-id="c57cc-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="c57cc-106">Um ou mais servidores de mediação, que convertem a sinalização e, em algumas configurações, mídia entre seu Skype interno para Business Server, a infraestrutura do Enterprise Voice e um gateway PSTN (rede) telefônica comutada pública ou um protocolo de iniciação de sessão Tronco (SIP).</span><span class="sxs-lookup"><span data-stu-id="c57cc-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="c57cc-107">Os servidores de mediação são o componente mais crucial na sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c57cc-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="c57cc-108">Para obter mais informações, consulte [componente de servidor de mediação em Skype para Business Server 2015](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="c57cc-108">For more information, see [Mediation Server component in Skype for Business Server 2015](mediation-server.md).</span></span>
    
    <span data-ttu-id="c57cc-109">Servidores de mediação podem ser colocados com servidores Front-End ou instalados como servidores autônomos.</span><span class="sxs-lookup"><span data-stu-id="c57cc-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="c57cc-110">Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN gateways.</span><span class="sxs-lookup"><span data-stu-id="c57cc-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="c57cc-111">Para obter mais informações, consulte [componentes de conectividade PSTN em Skype para Business Server 2015](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c57cc-111">For more information, see [PSTN connectivity components in Skype for Business Server 2015](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="c57cc-112">Servidores de borda, que permite o uso dos recursos do Enterprise Voice pelos usuários quando eles estão fora do firewall da organização.</span><span class="sxs-lookup"><span data-stu-id="c57cc-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="c57cc-113">O serviço de borda de acesso oferece sinalização SIP para chamadas do Skype para usuários comerciais que estão fora do firewall da organização.</span><span class="sxs-lookup"><span data-stu-id="c57cc-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="c57cc-114">O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls.</span><span class="sxs-lookup"><span data-stu-id="c57cc-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="c57cc-115">Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.</span><span class="sxs-lookup"><span data-stu-id="c57cc-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="c57cc-p104">O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.</span><span class="sxs-lookup"><span data-stu-id="c57cc-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="c57cc-118">Além disso, alguns componentes do Enterprise Voice executados nos servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="c57cc-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="c57cc-119">Para obter detalhes sobre esses componentes, consulte [componentes de VoIP de servidor Front End para Skype para Business Server 2015](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="c57cc-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server 2015](front-end-server-voip.md)</span></span>
    

