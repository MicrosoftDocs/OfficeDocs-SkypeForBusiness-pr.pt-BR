---
title: 'Lync Server 2013: visão geral do diretor'
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
ms.openlocfilehash: 2ac09f5ca7ed67b078b3d5313982cff4af38e835
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="45c66-102">Visão geral do diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c66-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45c66-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="45c66-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="45c66-104">Um diretor é um servidor executando o Lync Server 2013 que autentica solicitações do usuário, mas não hospeda contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="45c66-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="45c66-105">Opcionalmente, você pode implantar um diretor nos dois cenários a seguir:</span><span class="sxs-lookup"><span data-stu-id="45c66-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="45c66-106">Se você habilitar o acesso por usuários externos implantando servidores de borda, também deverá implantar um diretor.</span><span class="sxs-lookup"><span data-stu-id="45c66-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="45c66-107">Neste cenário, o diretor autentica os usuários externos e, em seguida, passa o tráfego para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="45c66-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="45c66-108">Quando um diretor é usado para autenticar usuários externos, ele alivia os servidores do pool de front-ends da sobrecarga de execução de autenticação desses usuários.</span><span class="sxs-lookup"><span data-stu-id="45c66-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="45c66-109">Também ajuda a isolar pools de front-ends internos de tráfego mal-intencionado, como ataques de negação de serviço.</span><span class="sxs-lookup"><span data-stu-id="45c66-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="45c66-110">Se a rede é preenchida com tráfego externo inválido em tal ataque, este tráfego termina no Diretor.</span><span class="sxs-lookup"><span data-stu-id="45c66-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="45c66-111">Se você implantar vários pools de front-ends em um site central, adicionando um diretor a esse site, você poderá simplificar as solicitações de autenticação e melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="45c66-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="45c66-112">Neste cenário, todas as solicitações vão primeiro para o diretor, que as direciona para o pool de front-ends correto.</span><span class="sxs-lookup"><span data-stu-id="45c66-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

