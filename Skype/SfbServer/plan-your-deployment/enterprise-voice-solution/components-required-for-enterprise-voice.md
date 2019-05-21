---
title: Componentes necessários para o Enterprise Voice no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Um resumo dos componentes Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277003"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="39b91-103">Componentes necessários para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39b91-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="39b91-104">Um resumo dos componentes Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="39b91-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="39b91-105">Para implantar o Enterprise Voice, os seguintes componentes são necessários na sua topologia.</span><span class="sxs-lookup"><span data-stu-id="39b91-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="39b91-106">Um ou mais servidores de mediação, que convertem a sinalização e, em algumas configurações, mídia entre o Skype for Business Server interno, a infraestrutura do Enterprise Voice e um gateway PSTN (rede telefônica pública comutada) ou um protocolo de inicialização de sessão (SIP) trunk.</span><span class="sxs-lookup"><span data-stu-id="39b91-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="39b91-107">Os servidores de mediação são os componentes mais cruciais na sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="39b91-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="39b91-108">Para obter mais informações, consulte [componente do servidor de mediação no Skype for Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="39b91-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="39b91-109">Os servidores de mediação podem ser posicionados com servidores front-end ou instalados como servidores autônomos.</span><span class="sxs-lookup"><span data-stu-id="39b91-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="39b91-110">Componentes de conectividade PSTN, que podem incluir troncos SIP ou gateways PSTN gateways.</span><span class="sxs-lookup"><span data-stu-id="39b91-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="39b91-111">Para obter mais informações, consulte [componentes de conectividade PSTN no Skype for Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="39b91-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="39b91-112">Servidores de borda, que permitem o uso de recursos do Enterprise Voice pelos seus usuários quando eles estão fora do firewall da sua organização.</span><span class="sxs-lookup"><span data-stu-id="39b91-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="39b91-113">O serviço de borda de acesso fornece sinalização de SIP para chamadas de usuários do Skype for Business que estão fora do firewall da sua organização.</span><span class="sxs-lookup"><span data-stu-id="39b91-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="39b91-114">O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls.</span><span class="sxs-lookup"><span data-stu-id="39b91-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="39b91-115">Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.</span><span class="sxs-lookup"><span data-stu-id="39b91-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="39b91-p104">O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.</span><span class="sxs-lookup"><span data-stu-id="39b91-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="39b91-118">Além disso, alguns componentes do Enterprise Voice são executados em servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="39b91-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="39b91-119">Para obter detalhes sobre esses componentes, consulte [componentes de VoIP do servidor front-end para o Skype for Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="39b91-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

