---
title: 'Fase 10: encerrar o site herdado'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c306f79bf1e9f2d136472419b1c57465a2d71bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="9be91-102">Fase 10: encerrar o site herdado</span><span class="sxs-lookup"><span data-stu-id="9be91-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be91-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="9be91-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="9be91-104">Os tópicos a seguir fornecem orientações sobre como encerrar pools e como desativar e remover servidores e pools de uma implantação herdada do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9be91-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="9be91-105">Nem todos os procedimentos listados nesta seção são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="9be91-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="9be91-106">Leia as informações de cada tópico para determinar qual procedimento de desprogramação deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="9be91-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9be91-107">Se você importou diretórios de conferência para conferência discada para o Lync Server 2013, é importante fazer a transição da Propriedade do diretório de conferência para o Lync Server 2013 antes de começar a encerrar seus pools.</span><span class="sxs-lookup"><span data-stu-id="9be91-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="9be91-108">Se você encerrar um pool sem antes fazer a transição da propriedade de diretório de conferência, o recurso de discagem para todas as reuniões migradas deixará de funcionar.</span><span class="sxs-lookup"><span data-stu-id="9be91-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="9be91-109">Você deve executar a etapa para fazer a transição da propriedade uma vez para cada diretório de conferência no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="9be91-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9be91-110">Para obter informações sobre a migração e atualização de aplicativos do Microsoft Unified Communications Managed API (UCMA), antes de encerrar seu ambiente herdado, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="9be91-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9be91-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9be91-111">In This Section</span></span>

  - [<span data-ttu-id="9be91-112">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="9be91-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="9be91-113">Atualizar registros SRV DNS</span><span class="sxs-lookup"><span data-stu-id="9be91-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="9be91-114">Encerrar servidores e pools</span><span class="sxs-lookup"><span data-stu-id="9be91-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="9be91-115">Remover BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="9be91-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

