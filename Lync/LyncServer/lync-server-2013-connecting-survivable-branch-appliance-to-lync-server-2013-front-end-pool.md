---
title: Conectando Aparelho de Filial Persistente ao pool Front End do Lync Server 2013
description: Conexão de aparelho de filial persistente ao pool de front-ends do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef917d3db6a1d653ac716d6c078e1df240fb31d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571657"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="55289-103">Conectando Aparelho de Filial Persistente ao pool Front End do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55289-103">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55289-104">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="55289-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="55289-105">Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends, que funciona como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="55289-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="55289-106">Quando o pool de front-ends é atualizado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends enquanto o pool de front-ends é atualizado.</span><span class="sxs-lookup"><span data-stu-id="55289-106">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="55289-107">Após a atualização do pool de front-ends, o SBA pode ser associado ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="55289-107">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="55289-108">Isso envolve a exclusão do SBA da topologia no Construtor de Topologia e, então, adicionando o SBA novamente no Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="55289-108">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="55289-109">Os usuários hospedados no SBA devem ser movidos para outro pool de front-ends antes da remoção do SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="55289-109">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="55289-110">Depois que o SBA for adicionado novamente à topologia, tais usuários poderão ser movidos de volta ao SBA.</span><span class="sxs-lookup"><span data-stu-id="55289-110">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="55289-111">Essas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="55289-111">These steps are summarized below:</span></span>

1.  <span data-ttu-id="55289-112">Mover usuários de filial hospedados no SBA para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="55289-112">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="55289-113">Remova o SBA da sua topologia para desassociar o pool de front-ends existente como registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="55289-113">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="55289-114">Atualize o pool de front-ends para o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55289-114">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="55289-115">Adicione o SBA novamente à topologia.</span><span class="sxs-lookup"><span data-stu-id="55289-115">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="55289-116">Associe o novo pool de front-ends ao SBA como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="55289-116">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="55289-117">Mova os usuários da ramificação de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="55289-117">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="55289-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="55289-118">In This Section</span></span>

  - [<span data-ttu-id="55289-119">Adicionar site de filial de dispositivo de filial persistente do Lync Server 2013 à sua topologia</span><span class="sxs-lookup"><span data-stu-id="55289-119">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="55289-120">Adicionar site de filial de dispositivo de filial persistente do Lync Server 2010 à sua topologia</span><span class="sxs-lookup"><span data-stu-id="55289-120">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

