---
title: 'Lync Server 2013: Suporte a protocolo IP e de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a35395c9bb7eb8d90e5618ba6afde17defdbbcfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="cf392-102">Suporte a protocolo IP e de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf392-102">IP and networking protocol support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf392-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cf392-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cf392-104">O Lync Server 2013 dá suporte aos seguintes protocolos de IP e de rede:</span><span class="sxs-lookup"><span data-stu-id="cf392-104">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="cf392-105">**Protocolos IP.**    O Lync Server 2013 oferece suporte ao IP versão 4 (IPv4) ou IP versão 6 (IPv6) para a rede do servidor.</span><span class="sxs-lookup"><span data-stu-id="cf392-105">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf392-106">O Lync Server 2013 pode funcionar em uma rede com a pilha de IP duplo habilitada.</span><span class="sxs-lookup"><span data-stu-id="cf392-106">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="cf392-107">**Protocolos de transporte SIP.**    Em geral, o SIP pode usar pelo menos três tipos de transporte: protocolo UDP, protocolo de controle de transmissão (TCP) e Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="cf392-107">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="cf392-108">Na configuração de transporte SIP padrão, o TLS é executado sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="cf392-108">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="cf392-109">O TLS é usado na rede do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf392-109">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="cf392-110">Na borda da rede, o Lync Server 2013 pode interoperar via TCP.</span><span class="sxs-lookup"><span data-stu-id="cf392-110">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="cf392-111">O Lync Server 2013 não é compatível com o UDP para transporte SIP porque ele não atende aos padrões mínimos de segurança, confiabilidade e escalabilidade de comunicação corporativa.</span><span class="sxs-lookup"><span data-stu-id="cf392-111">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="cf392-112">Para obter detalhes, consulte o artigo sobre o blog NextHop, "para UDP ou não para UDP, que é a pergunta" [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)em.</span><span class="sxs-lookup"><span data-stu-id="cf392-112">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf392-113">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="cf392-113">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

