---
title: 'Lync Server 2013: regiões de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a93e4bda396cb684ee15e5ee8dcd2c90ae09542
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="b508c-102">Regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b508c-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b508c-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b508c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b508c-104">*Regiões de rede* são hubs de rede ou backbones usados na configuração do serviço de controle de admissão de chamadas, E9-1-1 e desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="b508c-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="b508c-105">Use os procedimentos a seguir para visualizar, criar ou modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="b508c-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="b508c-106">Por exemplo, se você já criou regiões de rede para um recurso de Voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="b508c-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="b508c-107">Porém, talvez seja necessário modificar uma definição de região de rede existente para aplicar configurações específicas ao recurso.</span><span class="sxs-lookup"><span data-stu-id="b508c-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="b508c-108">Por exemplo, se você cria regiões de rede para o E9-1-1 (que não exige um local central associado) e depois implanta o controle de admissão de chamadas, precisará modificar as definições de região de rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="b508c-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="b508c-109">Para obter detalhes, consulte [Configure Network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="b508c-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b508c-110">Quaisquer requisitos específicos ao recurso para definições de região de rede são documentados nos tópicos de Implantação do recurso.</span><span class="sxs-lookup"><span data-stu-id="b508c-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b508c-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b508c-111">In This Section</span></span>

  - [<span data-ttu-id="b508c-112">Exibindo informações de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b508c-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="b508c-113">Criar ou modificar regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b508c-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="b508c-114">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b508c-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="b508c-115">Referência</span><span class="sxs-lookup"><span data-stu-id="b508c-115">Reference</span></span>

[<span data-ttu-id="b508c-116">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b508c-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

