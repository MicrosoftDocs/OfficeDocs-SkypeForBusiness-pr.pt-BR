---
title: 'Lync Server 2013: Configurar Entrada Automática de Cliente para usar o Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a6d9090796b2c6c2271025ed4d17a134943c11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="e6d20-102">Configurar Entrada Automática de Cliente para usar o Diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6d20-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6d20-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e6d20-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e6d20-104">Ao implantar um aplicativo do Lync Server 2013, diretor ou um pool de diretores, recomendamos que você use a entrada automática do cliente como prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="e6d20-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="e6d20-105">Para obter detalhes sobre como configurar servidores DNS para a entrada automática do cliente, confira [requisitos de DNS para entrada automática do cliente no Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e6d20-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="e6d20-106">Se você já tiver implantado a entrada automática do cliente, consulte as seções a seguir para configurá-lo em seu (s) director (es).</span><span class="sxs-lookup"><span data-stu-id="e6d20-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="e6d20-107">Instância do diretor único</span><span class="sxs-lookup"><span data-stu-id="e6d20-107">Single Director Instance</span></span>

<span data-ttu-id="e6d20-108">Se você já tiver o recurso de entrada automática do cliente implantado e ele estiver apontando para um servidor front-end ou um pool de front-end, será necessário alterar o registro SRV DNS para apontar para o diretor.</span><span class="sxs-lookup"><span data-stu-id="e6d20-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="e6d20-109">Pool de diretor</span><span class="sxs-lookup"><span data-stu-id="e6d20-109">Director Pool</span></span>

<span data-ttu-id="e6d20-110">Se você já tiver o recurso de entrada automática do cliente implantado e ele estiver apontando para um servidor front-end ou um pool de front-end, será necessário alterar o registro SRV DNS para apontar para o pool diretor.</span><span class="sxs-lookup"><span data-stu-id="e6d20-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

