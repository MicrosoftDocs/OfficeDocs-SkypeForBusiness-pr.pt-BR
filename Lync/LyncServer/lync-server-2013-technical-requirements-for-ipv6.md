---
title: Requisitos técnicos do Lync Server 2013 para IPv6
description: Requisitos técnicos do Lync Server 2013 para IPv6.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559457"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="9d7a5-103">Requisitos técnicos para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d7a5-103">Technical requirements for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d7a5-104">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="9d7a5-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="9d7a5-105">Se você planeja configurar o Lync Server 2013 para IPv6, tenha em mente os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="9d7a5-105">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="9d7a5-106">Para usar endereços IPv6 com o Lync Server, você precisa criar registros de DNS (sistema de nomes de domínio) para registros que devem ser descobertos e resolvidos para um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-106">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="9d7a5-107">O DNS IPv6 usa um registros de host AAAA (quad-A).</span><span class="sxs-lookup"><span data-stu-id="9d7a5-107">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="9d7a5-108">Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-108">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="9d7a5-109">Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-109">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="9d7a5-110">É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-110">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="9d7a5-111">Se o cliente ou servidor não usar IPv6, o registro não será referenciado.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-111">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="9d7a5-112">As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-112">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="9d7a5-113">Cada endereço IPv6 possui um escopo.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-113">Each IPv6 address has a scope.</span></span> <span data-ttu-id="9d7a5-114">Os três escopos que você pode usar para o endereçamento IPv6 são endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhantes aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante aos endereços IP privados automáticos no Windows Server para IPv4).</span><span class="sxs-lookup"><span data-stu-id="9d7a5-114">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="9d7a5-115">Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-115">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9d7a5-116">O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribui no nível do servidor do Windows e no nível do Lync Server 2013 funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-116">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="9d7a5-117">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="9d7a5-117">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d7a5-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="9d7a5-118">See Also</span></span>


[<span data-ttu-id="9d7a5-119">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="9d7a5-119">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="9d7a5-120">Formato de endereço de unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="9d7a5-120">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="9d7a5-121">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="9d7a5-121">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

