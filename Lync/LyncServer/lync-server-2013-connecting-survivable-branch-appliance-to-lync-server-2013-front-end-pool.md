---
title: Conectando Aparelho de Filial Persistente ao pool Front-End do Lync Server 2013
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
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="b95fc-102">Conectando Aparelho de Filial Persistente ao pool Front-End do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b95fc-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b95fc-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="b95fc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="b95fc-104">Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end, que atua como um registrador de backup para o SBA.</span><span class="sxs-lookup"><span data-stu-id="b95fc-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="b95fc-105">Quando o pool de front-ends é atualizado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends enquanto o pool de front-end é atualizado.</span><span class="sxs-lookup"><span data-stu-id="b95fc-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="b95fc-106">Depois que o pool de front-ends é atualizado, o SBA pode ser associado novamente ao pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="b95fc-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="b95fc-107">Isso envolve excluir o SBA da topologia no construtor de topologias e, em seguida, adicionar SBA, novamente, ao construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b95fc-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="b95fc-108">Os usuários hospedados no SBA devem ser movidos para outro pool de front-end antes da remoção do SBA da topologia.</span><span class="sxs-lookup"><span data-stu-id="b95fc-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="b95fc-109">Depois que o SBA é adicionado novamente à topologia, esses usuários podem retornar ao SBA.</span><span class="sxs-lookup"><span data-stu-id="b95fc-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="b95fc-110">Estas etapas estão resumidas abaixo:</span><span class="sxs-lookup"><span data-stu-id="b95fc-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="b95fc-111">Mova os usuários da ramificação hospedados no SBA para outro pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="b95fc-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="b95fc-112">Remova o SBA da sua topologia para desassociar o pool de front-end existente como registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="b95fc-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="b95fc-113">Atualize o pool de front-ends para o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b95fc-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="b95fc-114">Adicione SBA de volta à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b95fc-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="b95fc-115">Associe o novo pool de front-ends ao SBA como um registrador de backup.</span><span class="sxs-lookup"><span data-stu-id="b95fc-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="b95fc-116">Mova os usuários da ramificação de volta para o SBA.</span><span class="sxs-lookup"><span data-stu-id="b95fc-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b95fc-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b95fc-117">In This Section</span></span>

  - [<span data-ttu-id="b95fc-118">Adicionar Aparelho de Filial Persistente do Lync Server 2013 a sua topologia</span><span class="sxs-lookup"><span data-stu-id="b95fc-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="b95fc-119">Adicionar site de Aparelho de Filial Persistente do Lync Server 2010 a sua topologia</span><span class="sxs-lookup"><span data-stu-id="b95fc-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

