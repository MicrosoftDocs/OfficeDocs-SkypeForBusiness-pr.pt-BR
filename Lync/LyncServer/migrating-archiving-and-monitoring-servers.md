---
title: Migrar servidores de Arquivamento e de Monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="fe7ad-102">Migrar servidores de Arquivamento e de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="fe7ad-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe7ad-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fe7ad-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fe7ad-104">Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente do Lync Server 2010, poderá implantar esses servidores no ambiente do Lync Server 2013 após migrar seus pools front-ends.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="fe7ad-105">No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para a sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Lync Server 2013 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="fe7ad-106">Se você quiser a funcionalidade de arquivamento e monitoramento durante o processo de migração, tenha em mente as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="fe7ad-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="fe7ad-107">O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="fe7ad-108">Os dados que você deve fazer backup antes de descomissionar o ambiente herdado serão o seu histórico de atividades no ambiente do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="fe7ad-109">A versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server podem ser associadas apenas a um pool de front-end do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="fe7ad-110">No Lync Server 2013, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="fe7ad-111">Durante o tempo em que suas implantações do Lync Server e do Lync Server 2013 coexistem, a versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server coletam dados para os usuários hospedados nos pools do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="fe7ad-112">O arquivamento e o monitoramento no Lync Server 2013 coletam dados para usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe7ad-113">Durante a fase de migração quando você ainda estiver usando o servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do servidor de arquivamento do Lync Server 2010 continua a coletar dados para os usuários hospedados no Lync Server 2010 pools e o arquivamento no Lync Server 2013 reúne dados para os usuários hospedados nos pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="fe7ad-114">Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o arquivamento e o monitoramento no Lync Server 2013, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe7ad-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

