---
title: Migrar servidores de Arquivamento e de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="d45ef-102">Migrar servidores de Arquivamento e de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="d45ef-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d45ef-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d45ef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d45ef-104">Se você implantou o servidor de arquivamento e monitorando o servidor no Office Communications Server 2007 R2, poderá implantar esses servidores no ambiente do Lync Server 2013 depois de migrar seus pools front-ends.</span><span class="sxs-lookup"><span data-stu-id="d45ef-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="d45ef-105">No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="d45ef-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="d45ef-106">Se você quiser a funcionalidade de arquivamento e monitoramento durante a fase de migração e de coexistência, tenha em mente as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="d45ef-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="d45ef-107">O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d45ef-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="d45ef-108">Os dados que você reproduzem antes de descomissionar o ambiente herdado serão seu histórico de atividades no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d45ef-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="d45ef-109">A versão do Office Communications Server 2007 R2 do servidor de arquivamento e Monitoring Server somente pode ser associada a um pool de front-end do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d45ef-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="d45ef-110">No Lync Server 2013, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d45ef-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="d45ef-111">Durante o tempo em que suas implantações do Lync Server e do Lync Server 2013 coexistem, a versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server reúne dados para os usuários hospedados no Office Communications Server 2007 R2 pools.</span><span class="sxs-lookup"><span data-stu-id="d45ef-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="d45ef-112">A versão do Lync Server 2013 do servidor de arquivamento e o Monitoring Server coletam dados para os usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="d45ef-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d45ef-113">Durante a fase de migração, quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do Office Communications Server 2007 R2 do servidor de arquivamento continua a coletar dados para os usuários hospedados no Office Communications Server 2007 Os pools R2 e a versão do Lync Server 2013 do servidor de arquivamento coletam dados para os usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="d45ef-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="d45ef-114">Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o servidor de arquivamento e monitoração do servidor, fale com o fornecedor sobre quando e como você precisa integrar a solução de terceiros ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d45ef-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

