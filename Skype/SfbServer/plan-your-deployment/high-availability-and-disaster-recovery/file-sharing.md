---
title: Alta disponibilidade de compartilhamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Saiba mais sobre como garantir alta disponibilidade de seus compartilhamentos de arquivos no Skype for Business Server, usando DFS.
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093089"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="69938-103">Alta disponibilidade de compartilhamento de arquivos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="69938-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="69938-104">Saiba mais sobre como garantir alta disponibilidade de seus compartilhamentos de arquivos no Skype for Business Server, usando DFS.</span><span class="sxs-lookup"><span data-stu-id="69938-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="69938-105">Para garantir alta disponibilidade para compartilhamento de arquivos em sua implantação do Skype for Business Server, você pode usar o DFS (Sistema de Arquivos Distribuídos).</span><span class="sxs-lookup"><span data-stu-id="69938-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="69938-106">O DAS oferece suporte a failover de um servidor de arquivos para outro no mesmo data Center.</span><span class="sxs-lookup"><span data-stu-id="69938-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="69938-107">Para uma implantação em grande escala, nós recomendamos que você use servidores de arquivos dedicados emparelhados usando DAS.</span><span class="sxs-lookup"><span data-stu-id="69938-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="69938-108">Para obter mais informações sobre o DFS no Windows Server 2012, consulte [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) .</span><span class="sxs-lookup"><span data-stu-id="69938-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).</span></span> <span data-ttu-id="69938-109">Para obter informações sobre o DFS no Windows Server 2008, consulte [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .</span><span class="sxs-lookup"><span data-stu-id="69938-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)).</span></span>
  
<span data-ttu-id="69938-110">Dependendo do tamanho da rede e da quantidade de resiliência desejada, você pode usar um par de servidores para hospedar todos os compartilhamentos de arquivos em um site ou usar um par por pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="69938-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="69938-111">O DAS é o melhor mecanismo de replicação de arquivos, sem objetivo de tempo recuperado (RTO) publicado ou compromisso de objetivo de ponto de recuperação (RPO).</span><span class="sxs-lookup"><span data-stu-id="69938-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="69938-112">Um failover entre servidores DFS deve ser concluído rapidamente, mas o atraso na replicação de dados pode impedir que os usuários possam continuar a trabalhar em andamento quando o failover acontece.</span><span class="sxs-lookup"><span data-stu-id="69938-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="69938-113">Se você usar o DFS e o armazenamento de dados no compartilhamento de arquivos for fundamental, você deve fazer o back up dos compartilhamentos de arquivos com frequência, como a cada 4 a 8 horas.</span><span class="sxs-lookup"><span data-stu-id="69938-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="69938-114">Quando um compartilhamento de arquivos cai e a replicação não está atualizada, é possível usar o backup para recuperar o conteúdo no servidor com falha para o outro servidor emparelhado com o que está indisponível.</span><span class="sxs-lookup"><span data-stu-id="69938-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
