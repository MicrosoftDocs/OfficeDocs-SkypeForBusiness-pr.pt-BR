---
title: Suporte ao armazenamento de arquivos do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc2250020b7456515f06bcb308ca4cea4430a56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="7030f-102">Suporte ao armazenamento de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7030f-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7030f-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7030f-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7030f-104">O Lync Server 2013 usa o mesmo repositório de arquivos para todo o armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7030f-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="7030f-105">O suporte ao armazenamento de arquivos inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7030f-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="7030f-106">Um compartilhamento de arquivos no DAS (armazenamento de conexão direta) ou uma rede de área de armazenamento (SAN), incluindo o sistema de arquivos distribuídos (DFS) e um conjunto redundante de discos independentes (RAID) para repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7030f-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="7030f-107">Para obter detalhes sobre os requisitos de armazenamento, consulte [requisitos técnicos para servidores front-end, mensagens instantâneas e presença no Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) e [requisitos de hardware e software para o diretor no Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7030f-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="7030f-108">Para obter detalhes sobre o sistema operacional do DFS para Windows Server 2008, consulte o guia passo a passo do DFS para o Windows [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)Server 2008 em.</span><span class="sxs-lookup"><span data-stu-id="7030f-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="7030f-109">Um cluster compartilhado para o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7030f-109">A shared cluster for the file share.</span></span> <span data-ttu-id="7030f-110">Se você usar um cluster compartilhado, deverá usar servidores de cluster executando o Windows Server 2008 ou o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7030f-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="7030f-111">O uso de servidores de cluster executando uma versão mais antiga do Windows pode resultar em problemas de permissão que impedem a disponibilidade de alguns recursos.</span><span class="sxs-lookup"><span data-stu-id="7030f-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="7030f-112">Use o Administrador de cluster para criar compartilhamentos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7030f-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="7030f-113">Para obter detalhes sobre como usar o administrador de cluster, consulte o artigo 284838 da base de dados de conhecimento da Microsoft, "como criar um compartilhamento de [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)arquivo de cluster de servidor com cluster. exe" em.</span><span class="sxs-lookup"><span data-stu-id="7030f-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

