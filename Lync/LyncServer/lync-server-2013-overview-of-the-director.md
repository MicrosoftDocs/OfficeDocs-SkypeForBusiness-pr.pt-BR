---
title: 'Lync Server 2013: Visão Geral do Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51ee90020be9d23384c5ed90ca1f8095156eaf56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="b2ae1-102">Visão Geral do Diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2ae1-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2ae1-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b2ae1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b2ae1-104">Um diretor é um servidor que executa o Lync Server 2013 que autentica solicitações do usuário, mas não hospeda nenhuma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="b2ae1-105">Opcionalmente, você pode implantar um diretor nos dois cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="b2ae1-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="b2ae1-106">Se você habilitar o acesso por usuários externos implantando servidores de borda, também deverá implantar um diretor.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="b2ae1-107">Nesse cenário, o diretor autentica os usuários externos e, em seguida, passa o tráfego deles para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="b2ae1-108">Quando um diretor é usado para autenticar usuários externos, ele libera os servidores de pool de front-end da sobrecarga de execução de autenticação desses usuários.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="b2ae1-109">Também ajuda a proteger pools de front-end internos contra tráfego mal-intencionado, como ataques de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="b2ae1-110">Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, esse tráfego terminará no diretor.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="b2ae1-111">Se você implantar vários pools de front-end em um site central, adicionando um diretor ao site, você pode simplificar solicitações de autenticação e melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="b2ae1-112">Nesse cenário, todas as solicitações entram primeiro no director, que, em seguida, as roteia para o pool de front-end correto.</span><span class="sxs-lookup"><span data-stu-id="b2ae1-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

