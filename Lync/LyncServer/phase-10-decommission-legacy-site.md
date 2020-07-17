---
title: 'Fase 10: encerrar o site herdado'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d40c988822a27a34f148e4e1e7893a077965fcd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="57033-102">Fase 10: encerrar o site herdado</span><span class="sxs-lookup"><span data-stu-id="57033-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57033-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="57033-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="57033-104">Os tópicos a seguir fornecem orientações sobre como encerrar pools e como desativar e remover servidores e pools de uma implantação herdada do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="57033-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="57033-105">Nem todos os procedimentos listados nesta seção são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="57033-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="57033-106">Leia as informações de cada tópico para determinar qual procedimento de desprogramação deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="57033-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="57033-107">Se você importou diretórios de conferência para conferência discada para o Lync Server 2013, é importante fazer a transição da Propriedade do diretório de conferência para o Lync Server 2013 antes de começar a encerrar seus pools.</span><span class="sxs-lookup"><span data-stu-id="57033-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="57033-108">Se você encerrar um pool sem antes fazer a transição da propriedade de diretório de conferência, o recurso de discagem para todas as reuniões migradas deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="57033-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="57033-109">Você deve executar a etapa para fazer a transição da propriedade uma vez para cada diretório de conferência no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="57033-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57033-110">Para obter informações sobre a migração e atualização de aplicativos do Microsoft Unified Communications Managed API (UCMA), antes de encerrar seu ambiente herdado, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="57033-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57033-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="57033-111">In This Section</span></span>

  - [<span data-ttu-id="57033-112">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="57033-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="57033-113">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="57033-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="57033-114">Encerrar servidores e pools</span><span class="sxs-lookup"><span data-stu-id="57033-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="57033-115">Remover BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="57033-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

