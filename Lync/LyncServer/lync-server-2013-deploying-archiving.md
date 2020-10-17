---
title: 'Lync Server 2013: Implantando arquivamento'
description: 'Lync Server 2013: Implantando arquivamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ba38b7dcde0c72469e361f59ade7cb7f6ebb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558497"
---
# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="7236e-103">Implantando o arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-103">Deploying Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7236e-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7236e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7236e-105">O Lync Server 2013 oferece uma solução para o arquivamento de comunicações de mensagens instantâneas e de conferência no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7236e-105">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="7236e-106">Você pode implementar o suporte ao arquivamento integrando o armazenamento de arquivamento com o armazenamento do Exchange 2013, usando os bancos de dados do SQL Server para armazenamento de dados de arquivamento do Lync Server 2013 ou usando o armazenamento do Lync Server 2013 e do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7236e-106">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="7236e-107">Você controla como os dados são arquivados usando configurações de política e arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7236e-107">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="7236e-108">Para obter detalhes, consulte [Planning for Archiving in Lync server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento e [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="7236e-108">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="7236e-109">Você pode usar as informações nesta seção para definir e configurar  inicialmente o Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7236e-109">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="7236e-110">Após a implantação, você pode alterar as configurações de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="7236e-110">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="7236e-111">Para obter detalhes sobre como implementar o suporte de arquivamento para o gerenciamento de dia-a-dia ou para atender aos novos requisitos em sua organização, consulte [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="7236e-111">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7236e-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7236e-112">In This Section</span></span>

  - [<span data-ttu-id="7236e-113">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-113">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="7236e-114">Lista de verificação de implantação para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-114">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="7236e-115">Configurando sistemas e infraestrutura para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-115">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="7236e-116">Adicionando bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-116">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="7236e-117">Configurando o suporte para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7236e-117">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

