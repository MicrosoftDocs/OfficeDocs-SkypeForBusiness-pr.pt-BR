---
title: 'Lync Server 2013: suporte à infraestrutura de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5ede9d6af8c9f912a207c602c225c19c3dd1f38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="cfbbb-102">Suporte à infraestrutura de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfbbb-102">DNS infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfbbb-103">_**Última modificação do tópico:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="cfbbb-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="cfbbb-104">O Lync Server 2013 requer o DNS (sistema de nomes de domínio) e o utiliza das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="cfbbb-104">Lync Server 2013 requires Domain Name System (DNS) and uses it in the following ways:</span></span>

  - <span data-ttu-id="cfbbb-105">Para descobrir pools ou servidores internos para a comunicação entre servidores.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-105">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="cfbbb-106">Para permitir que os clientes descubram o pool de front-ends ou o servidor Standard Edition usado em diversas transações SIP.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-106">To enable clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="cfbbb-107">Para associar URLs simples de conferências com os servidores que as hospedam.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-107">To associate the simple URLs for conferences with the servers hosting those conferences.</span></span>

  - <span data-ttu-id="cfbbb-108">Para permitir que os servidores e clientes externos se conectem aos servidores de borda ou ao proxy reverso HTTP para fazer uso de IM (mensagens instantâneas) ou conferências.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-108">To enable external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="cfbbb-109">Para permitir que os dispositivos de UC (comunicações unificadas) que não estejam conectados descubram o pool de front-ends ou o servidor Standard Edition que está executando o serviço Web de atualização de dispositivo obtenham atualizações e enviem logs.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-109">To enable unified communications (UC) devices that are not logged in to discover the Front End pool or Standard Edition server running Device Update Web service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="cfbbb-110">Para permitir que os clientes móveis descubram automaticamente os recursos dos serviços Web, sem exigir que os usuários insiram as URLs manualmente nas configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-110">To enable mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

  - <span data-ttu-id="cfbbb-111">Para o balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-111">For DNS load balancing.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cfbbb-112">O Lync Server 2013 não suporta nomes de domínio internacionalizados (IDNs).</span><span class="sxs-lookup"><span data-stu-id="cfbbb-112">Lync Server 2013 does not support internationalized domain names (IDNs).</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cfbbb-113">O nome que você especifica deve ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-113">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="cfbbb-114">Por padrão, o nome de um computador que não esteja em um domínio é curto e não um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="cfbbb-114">By default, the computer name of a computer that is not joined to a domain is a short name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="cfbbb-115">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-115">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="cfbbb-116">Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-116">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="cfbbb-117"><STRONG>Use somente caracteres padrão</STRONG> (inclusive A–Z, a–z, 0–9 e hifens) quando atribuir FQDNs de seus Lync Servers, servidores de borda e pools.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-117"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="cfbbb-118">Não use caracteres Unicode ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="cfbbb-118">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="cfbbb-119">Os caracteres incompatíveis em um FQDN frequentemente não são suportados no DNS externo e CAs públicos (isto é, quando o FQDN deve ser atribuído ao SN no certificado).</span><span class="sxs-lookup"><span data-stu-id="cfbbb-119">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

