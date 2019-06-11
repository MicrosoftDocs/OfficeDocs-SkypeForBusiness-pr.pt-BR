---
title: 'Lync Server 2013: alta disponibilidade de compartilhamento de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="1f985-102">Alta disponibilidade de compartilhamento de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f985-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f985-103">_**Tópico da última modificação:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="1f985-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="1f985-104">Para garantir alta disponibilidade para o compartilhamento de arquivos do Lync Server em um único Data Center, você pode usar o sistema de arquivos distribuídos (DFS).</span><span class="sxs-lookup"><span data-stu-id="1f985-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="1f985-105">O DFS suporta failover de um servidor de arquivos para outro dentro do mesmo data center.</span><span class="sxs-lookup"><span data-stu-id="1f985-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="1f985-106">Para uma implantação de larga escala, recomendamos usar servidores de arquivos dedicados, emparelhados com o uso do DFS.</span><span class="sxs-lookup"><span data-stu-id="1f985-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="1f985-107">Dependendo do tamanho da sua rede e da quantidade de resiliência desejada, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou usar um par por pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="1f985-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="1f985-108">O DFSS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="1f985-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="1f985-109">O failover entre os servidores DFS deve ser concluído rapidamente, mas o atraso na replicação de dados pode impedir que os usuários possam continuar trabalhando em andamento quando o failover ocorrer.</span><span class="sxs-lookup"><span data-stu-id="1f985-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="1f985-110">Se você usar o DFS e o repositório de dados no compartilhamento for essencial, será preciso fazer backup dos compartilhamentos de arquivos com frequência, como cada 4 a 8 horas.</span><span class="sxs-lookup"><span data-stu-id="1f985-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="1f985-111">Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.</span><span class="sxs-lookup"><span data-stu-id="1f985-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

