---
title: 'Lync Server 2013: Suporte à infraestrutura de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa9670761e16032abf0c205bbb740cbe1f43c4a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="1ca10-102">Suporte à infraestrutura de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca10-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca10-103">_**Tópico da última modificação:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="1ca10-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="1ca10-104">O Lync Server 2013 requer o sistema de nomes de domínio (DNS) e o usa das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="1ca10-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="1ca10-105">Para descobrir servidores internos ou pools para comunicações entre servidores.</span><span class="sxs-lookup"><span data-stu-id="1ca10-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="1ca10-106">Para permitir que os clientes descubram o pool de front-end ou o servidor Standard Edition usado para várias transações SIP.</span><span class="sxs-lookup"><span data-stu-id="1ca10-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="1ca10-107">Associar as URLs simples para conferências com os servidores que hospedam essas conferências.</span><span class="sxs-lookup"><span data-stu-id="1ca10-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="1ca10-108">Para permitir que servidores e clientes externos se conectem a servidores de borda ou ao proxy reverso HTTP para mensagens instantâneas (IM) ou conferência.</span><span class="sxs-lookup"><span data-stu-id="1ca10-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="1ca10-109">Para habilitar dispositivos de comunicação unificada (UC) que não estão conectados para descobrir o pool de front-end ou o servidor Standard Edition executando o serviço Web de atualização de dispositivos, obtenha atualizações e envie logs.</span><span class="sxs-lookup"><span data-stu-id="1ca10-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="1ca10-110">Para permitir que os clientes móveis descubram automaticamente os recursos de serviços Web sem exigir que os usuários insiram manualmente URLs nas configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca10-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="1ca10-111">Para o balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="1ca10-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ca10-112">O Lync Server 2013 não é compatível com nomes de domínio internacionalizados (IDNs).</span><span class="sxs-lookup"><span data-stu-id="1ca10-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ca10-113">O nome especificado deve ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="1ca10-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="1ca10-114">Por padrão, o nome do computador de um computador que não tiver ingressado em um domínio deverá ser um nome curto, não um nome de domínio totalmente qualificado (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1ca10-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1ca10-115">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="1ca10-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="1ca10-116">Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio.</span><span class="sxs-lookup"><span data-stu-id="1ca10-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="1ca10-117"><STRONG>Use apenas caracteres padrão</STRONG> (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools.</span><span class="sxs-lookup"><span data-stu-id="1ca10-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="1ca10-118">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="1ca10-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="1ca10-119">Normalmente, caracteres não padrão no FQDN não são suportados por DNS externo e CAs públicas (ou seja, quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="1ca10-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

