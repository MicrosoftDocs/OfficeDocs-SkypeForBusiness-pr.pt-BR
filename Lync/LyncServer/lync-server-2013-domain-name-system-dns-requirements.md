---
title: 'Lync Server 2013: requisitos de DNS (sistema de nomes de domínio)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ddbab6e4d0b1a0654c91027cbf0676ad6445f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501128"
---
# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="01b3e-102">Requisitos de DNS (sistema de nomes de domínio) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-102">Domain Name System (DNS) requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01b3e-103">_**Última modificação do tópico:** 2012-06-18_</span><span class="sxs-lookup"><span data-stu-id="01b3e-103">_**Topic Last Modified:** 2012-06-18_</span></span>

<span data-ttu-id="01b3e-104">Para implantar o Lync Server, você deve criar registros de DNS (sistema de nomes de domínio) que permitem a descoberta de clientes e servidores, e, opcionalmente, suporte para entrada automática de cliente se sua organização quiser oferecer suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="01b3e-104">To deploy Lync Server, you must create Domain Name System (DNS) records that enable the discovery of clients and servers, and, optionally, support for automatic client sign-in if your organization wants to support it.</span></span>

<span data-ttu-id="01b3e-105">O Lync Server usa o DNS das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="01b3e-105">Lync Server uses DNS in the following ways:</span></span>

  - <span data-ttu-id="01b3e-106">Para descobrir pools ou servidores internos para a comunicação entre servidores.</span><span class="sxs-lookup"><span data-stu-id="01b3e-106">To discover internal servers or pools for server-to-server communications.</span></span>

  - <span data-ttu-id="01b3e-107">Para permitir que os clientes descubram o pool de front-ends ou o servidor Standard Edition usado para várias transações SIP.</span><span class="sxs-lookup"><span data-stu-id="01b3e-107">To allow clients to discover the Front End pool or Standard Edition server used for various SIP transactions.</span></span>

  - <span data-ttu-id="01b3e-108">Para permitir que os dispositivos UC (comunicações unificadas) que não estão conectados descubram o pool de front-ends ou o servidor Standard Edition executando o serviço Web de atualização de dispositivo, obtenham atualizações e enviem logs.</span><span class="sxs-lookup"><span data-stu-id="01b3e-108">To allow unified communications (UC) devices that are not logged on to discover the Front End pool or Standard Edition server running Device Update Web Service, obtain updates, and send logs.</span></span>

  - <span data-ttu-id="01b3e-109">Para permitir que servidores e clientes externos se conectem aos servidores de borda ou ao proxy reverso HTTP para mensagens instantâneas (IM) ou de conferência.</span><span class="sxs-lookup"><span data-stu-id="01b3e-109">To allow external servers and clients to connect to Edge Servers or the HTTP reverse proxy for instant messaging (IM) or conferencing.</span></span>

  - <span data-ttu-id="01b3e-110">Para permitir que os dispositivos de UC externos se conectem ao serviço Web de atualização de dispositivo por meio de servidores de borda ou do proxy reverso HTTP e obtenham atualizações.</span><span class="sxs-lookup"><span data-stu-id="01b3e-110">To allow external UC devices to connect to Device Update Web service through Edge Servers or the HTTP reverse proxy and obtain updates.</span></span>

  - <span data-ttu-id="01b3e-111">Para permitir que clientes móveis descubram automaticamente os recursos dos Serviços Web sem exigir que os usuários insiram URLs manualmente nas configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="01b3e-111">To allow mobile clients to automatically discover Web Services resources without requiring users to manually enter URLs in device settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01b3e-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="01b3e-112">In This Section</span></span>

  - [<span data-ttu-id="01b3e-113">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-113">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="01b3e-114">Requisitos de DNS para pools de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-114">DNS requirements for Front End pools in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [<span data-ttu-id="01b3e-115">Requisitos de DNS para servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-115">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [<span data-ttu-id="01b3e-116">Requisitos de DNS para URLs simples no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-116">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="01b3e-117">Requisitos de DNS para entrada de cliente automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-117">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [<span data-ttu-id="01b3e-118">Requisitos de DNS para mobilidade com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-118">DNS requirements for mobility with Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-mobility.md)

  - [<span data-ttu-id="01b3e-119">Balanceamento de carga de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01b3e-119">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

