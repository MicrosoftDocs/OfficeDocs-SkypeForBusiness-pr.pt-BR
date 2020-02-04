---
title: 'Lync Server 2013: Requisitos técnicos para IPv6'
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
ms.openlocfilehash: e0688319a1b37dbd609a2f2051b3b8c6dfc6a2d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="6bdaf-102">Requisitos técnicos para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bdaf-102">Technical requirements for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bdaf-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="6bdaf-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="6bdaf-104">Se você planeja configurar o Lync Server 2013 para IPv6, tenha em mente os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="6bdaf-104">If you plan to configure Lync Server 2013 for IPv6, keep the following requirements in mind:</span></span>

  - <span data-ttu-id="6bdaf-105">Para usar endereços IPv6 com o Lync Server, você precisa criar registros de sistema de nomes de domínio (DNS) para registros que devem ser descobertos e resolvidos para um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-105">To use IPv6 addresses with Lync Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="6bdaf-106">O DNS IPv6 usa um registros de host AAAA (quad-A).</span><span class="sxs-lookup"><span data-stu-id="6bdaf-106">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="6bdaf-107">Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-107">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="6bdaf-108">Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-108">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="6bdaf-p102">É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-p102">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>

  - <span data-ttu-id="6bdaf-112">Cada endereço IPv6 possui um escopo.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-112">Each IPv6 address has a scope.</span></span> <span data-ttu-id="6bdaf-113">Os três escopos que você pode usar para endereçamento IPv6 são endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), endereços locais exclusivos do IPv6 (semelhantes aos intervalos de endereços IPv4 particulares) e endereços de conexão local IPv6 (semelhantes a endereços IP privados particulares no Windows Server para IPv4).</span><span class="sxs-lookup"><span data-stu-id="6bdaf-113">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="6bdaf-114">Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-114">All the servers within a pool should have IPv6 addresses with the same scope.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6bdaf-115">O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribuir no nível do servidor do Windows e no nível do Lync Server 2013 funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-115">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Lync Server 2013 level work as expected.</span></span> <span data-ttu-id="6bdaf-116">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="6bdaf-116">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bdaf-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="6bdaf-117">See Also</span></span>


[<span data-ttu-id="6bdaf-118">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="6bdaf-118">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="6bdaf-119">Formato de endereço de difusão ponto a ponto global IPv6</span><span class="sxs-lookup"><span data-stu-id="6bdaf-119">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="6bdaf-120">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="6bdaf-120">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

