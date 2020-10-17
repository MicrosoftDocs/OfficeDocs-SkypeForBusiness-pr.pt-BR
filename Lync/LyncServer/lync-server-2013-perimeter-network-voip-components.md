---
title: 'Lync Server 2013: componentes VoIP da rede de perímetro'
description: 'Lync Server 2013: componentes VoIP da rede de perímetro.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a416838b2ccec969e2990d492029486b6f2c72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557207"
---
# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="07da7-103">Componentes VoIP da rede de perímetro do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07da7-103">Perimeter network VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07da7-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="07da7-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="07da7-105">Os chamadores externos que usam clientes de comunicação unificada para chamadas individuais ou de conferência dependem do servidor de borda para comunicação por voz com colegas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07da7-105">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="07da7-106">Em um servidor de borda, o serviço de borda de acesso fornece sinalização SIP para chamadas de usuários do Lync que estão fora do firewall da sua organização.</span><span class="sxs-lookup"><span data-stu-id="07da7-106">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="07da7-107">O Serviço de Borda A/V permite o percurso de mídia de NAT e firewalls.</span><span class="sxs-lookup"><span data-stu-id="07da7-107">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="07da7-108">Um chamador que usa um cliente UC (comunicações unificadas) de fora do firewall corporativo depende do serviço de Borda A/V para chamadas individuais e de conferência.</span><span class="sxs-lookup"><span data-stu-id="07da7-108">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="07da7-p102">O serviço de Autenticação A/V está colocado no serviço de Borda A/V e fornece a este serviços de autenticação. Os usuários externos que tentam se conectar ao serviço de Borda A/V necessitam um token de autenticação fornecido pelo Serviço de Autenticação A/V, antes que suas chamadas possam ser feitas.</span><span class="sxs-lookup"><span data-stu-id="07da7-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

