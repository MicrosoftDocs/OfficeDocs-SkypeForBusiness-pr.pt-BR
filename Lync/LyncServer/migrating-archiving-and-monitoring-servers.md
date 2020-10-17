---
title: Migrar servidores de Arquivamento e de Monitoramento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba32bf2b35a0d2e8b0048ebb9c62aac09cb6eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527404"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="eb8df-102">Migrar servidores de Arquivamento e de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="eb8df-102">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb8df-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eb8df-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eb8df-104">Se você implantou o servidor de arquivamento e o Monitoring Server no seu ambiente do Lync Server 2010, pode implantar esses servidores no seu ambiente do Lync Server 2013 após migrar seus pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="eb8df-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="eb8df-105">No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Lync Server 2013 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="eb8df-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="eb8df-106">Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:</span><span class="sxs-lookup"><span data-stu-id="eb8df-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="eb8df-107">Os dados de arquivamento e de monitoramento não são movidos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb8df-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="eb8df-108">Os dados submetidos ao backup antes de desprogramar o ambiente de legado serão seu histórico da atividade no ambiente do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="eb8df-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="eb8df-109">A versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server só podem ser associadas a um pool de front-ends do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="eb8df-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="eb8df-110">No Lync Server 2013, o arquivamento e o monitoramento não são mais funções de servidor, mas os serviços integrados ao pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb8df-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="eb8df-111">Durante o tempo em que suas implantações herdadas do Lync Server 2013 coexistem, a versão do Lync Server 2010 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados no Lync Server 2010 pools.</span><span class="sxs-lookup"><span data-stu-id="eb8df-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="eb8df-112">Arquivamento e monitoramento no Lync Server 2013 coletar dados para usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="eb8df-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb8df-113">Durante a fase de migração quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do servidor de arquivamento do Lync Server 2010 continua a coletar dados para usuários hospedados no Lync Server 2010 pools e o arquivamento no Lync Server 2013 coleta dados para usuários hospedados em pools do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb8df-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="eb8df-114">Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com arquivamento e monitoramento no Lync Server 2013, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb8df-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

