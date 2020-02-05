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
ms.openlocfilehash: 4085b3c554429c960e6f9f558f82366d7b2b2532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="796e5-102">Regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796e5-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="796e5-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="796e5-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="796e5-104">*Regiões de rede* são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="796e5-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="796e5-105">Use os procedimentos a seguir para exibir, criar ou modificar regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="796e5-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="796e5-106">Por exemplo, se você já tiver criado regiões de rede para um recurso de voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="796e5-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="796e5-107">No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="796e5-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="796e5-108">Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="796e5-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="796e5-109">Para obter detalhes, consulte [configurar regiões de rede para o CAC no Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="796e5-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="796e5-110">Qualquer requisito específico de recurso para definições de região de rede está documentado nos tópicos de implantação do recurso.</span><span class="sxs-lookup"><span data-stu-id="796e5-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="796e5-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="796e5-111">In This Section</span></span>

  - [<span data-ttu-id="796e5-112">Exibir informações de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796e5-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="796e5-113">Criando ou modificando regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796e5-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="796e5-114">Excluindo regiões de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796e5-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="796e5-115">Referência</span><span class="sxs-lookup"><span data-stu-id="796e5-115">Reference</span></span>

[<span data-ttu-id="796e5-116">Implantação de recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796e5-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

