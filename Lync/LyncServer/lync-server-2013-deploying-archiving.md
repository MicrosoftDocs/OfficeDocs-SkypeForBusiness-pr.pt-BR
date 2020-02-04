---
title: 'Lync Server 2013: Implantando Arquivamento'
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
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="25bfd-102">Implantando Arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25bfd-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="25bfd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="25bfd-104">O Lync Server 2013 fornece uma solução para o arquivamento de comunicações de mensagens instantâneas (IM) e comunicações de conferência no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25bfd-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="25bfd-105">Você pode implementar o suporte para arquivamento integrando o armazenamento de arquivamento com o armazenamento do Exchange 2013, usando bancos de dados do SQL Server para armazenamento de dados de arquivamento do Lync Server 2013 ou usando o Lync Server 2013 e o armazenamento do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="25bfd-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="25bfd-106">Você controla como os dados são arquivados usando políticas e configurações de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="25bfd-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="25bfd-107">Para obter detalhes, consulte [planejando o arquivamento no Lync server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento e [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="25bfd-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="25bfd-108">Você pode usar as informações desta seção para configurar e configurar o arquivamento inicialmente.</span><span class="sxs-lookup"><span data-stu-id="25bfd-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="25bfd-109">Após a implantação, você pode alterar as configurações de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="25bfd-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="25bfd-110">Para obter detalhes sobre como implementar o suporte para arquivamento do gerenciamento do dia-a-dia ou atender aos novos requisitos em sua organização, consulte [Gerenciando o arquivamento do Lync Server 2013](lync-server-2013-managing-archiving.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="25bfd-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25bfd-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="25bfd-111">In This Section</span></span>

  - [<span data-ttu-id="25bfd-112">Como o arquivamento funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="25bfd-113">Lista de verificação da implantação para Arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="25bfd-114">Configurando sistemas e infraestrutura para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="25bfd-115">Adicionar bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="25bfd-116">Configurando o suporte para o arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25bfd-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

