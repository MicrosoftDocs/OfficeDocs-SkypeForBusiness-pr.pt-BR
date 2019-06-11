---
title: Preparando para instalação de servidores na rede de perímetro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8474ea56062a89952001850b1a78fd86f5843cc1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="6d301-102">Preparando para instalação de servidores na rede de perímetro para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d301-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6d301-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6d301-104">Antes de configurar componentes do servidor de borda, você precisa garantir que os computadores que você está configurando atendam aos requisitos do sistema e concluam outras etapas de pré-requisito necessárias para a implantação de componentes do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="6d301-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="6d301-105">Antes de começar, examine os detalhes nos tópicos a seguir na documentação de planejamento da arquitetura de referência que você deseja implantar:</span><span class="sxs-lookup"><span data-stu-id="6d301-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="6d301-106">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="6d301-107">Única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6d301-108">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="6d301-109">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="6d301-110">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d301-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6d301-111">In This Section</span></span>

  - [<span data-ttu-id="6d301-112">Configurar DNS para suporte à borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="6d301-113">Configurar balanceadores de carga de hardware para topologias de borda em escala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="6d301-114">Configurar firewalls e portas para acesso de usuários externos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="6d301-115">Determinar firewall A/V externo e requisitos de porta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="6d301-116">Solicitar certificados para componentes de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d301-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

