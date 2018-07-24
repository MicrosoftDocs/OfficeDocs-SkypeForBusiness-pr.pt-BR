---
title: Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Saiba mais sobre a garantir a alta disponibilidade de seus compartilhamentos de arquivo no Skype para Business Server, o uso do DFS.
ms.openlocfilehash: 645aa70ffc0c42cddb6941c9766cb91bed898dc8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989906"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="b3799-103">Alta disponibilidade de compartilhamento de arquivos no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b3799-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="b3799-104">Saiba mais sobre a garantir a alta disponibilidade de seus compartilhamentos de arquivo no Skype para Business Server, o uso do DFS.</span><span class="sxs-lookup"><span data-stu-id="b3799-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="b3799-105">Para garantir a alta disponibilidade para o compartilhamento de arquivo no seu Skype para implantação de servidor de negócios, você pode usar o sistema de arquivos distribuídos (DFS).</span><span class="sxs-lookup"><span data-stu-id="b3799-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="b3799-106">O DFS suporta failover de um servidor de arquivos para outro dentro do mesmo data center.</span><span class="sxs-lookup"><span data-stu-id="b3799-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="b3799-107">Para uma implantação de larga escala, recomendamos usar servidores de arquivos dedicados, emparelhados com o uso do DFS.</span><span class="sxs-lookup"><span data-stu-id="b3799-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="b3799-108">Para obter mais informações sobre o DFS no Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="b3799-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="b3799-109">Para obter informações sobre o DFS no Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="b3799-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="b3799-110">Dependendo do tamanho da sua rede e a quantidade de resiliência desejado, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou use um par por pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="b3799-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="b3799-111">O DFSS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="b3799-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="b3799-112">Um failover entre servidores DFS deve ser concluído rapidamente, mas o atraso de replicação de dados pode impedir que os usuários consigam continuar o trabalho em andamento quando ocorre o failover.</span><span class="sxs-lookup"><span data-stu-id="b3799-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="b3799-p103">Se você usa o DFS e o armazenamento de dados no compartilhamento de arquivos for importante, você deve efetuar o backup de compartilhamentos de arquivos frequentemente, como a cada 4 a 8 horas. Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.</span><span class="sxs-lookup"><span data-stu-id="b3799-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

