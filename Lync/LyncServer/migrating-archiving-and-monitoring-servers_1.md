---
title: Migrando servidores de arquivamento e monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67896576fce21eea630533a5826bbcbc53392fa0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="61629-102">Migrando servidores de arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="61629-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61629-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="61629-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="61629-104">Se você implantou o servidor de arquivamento e o Monitoring Server no Office Communications Server 2007 R2, pode implantar esses servidores em seu ambiente do Lync Server 2013 após migrar seus pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="61629-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="61629-105">Se as funcionalidades de arquivamento e monitoração forem cruciais para a organização, no entanto, você deverá adicionar o Arquivamento e Monitoramento ao pool piloto antes de migrar, de forma que a funcionalidade fique disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="61629-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="61629-106">Se você deseja as funcionalidades de arquivamento e monitoração durante a migração e a fase de coexistência, lembre-se das considerações a seguir:</span><span class="sxs-lookup"><span data-stu-id="61629-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="61629-107">Os dados de arquivamento e de monitoramento não são movidos para a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61629-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="61629-108">Os dados que você fez backup antes de encerrar o ambiente herdado serão seu histórico de atividades no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="61629-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="61629-109">A versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server só podem ser associadas a um pool de front-ends do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="61629-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="61629-110">No Lync Server 2013, o arquivamento e o monitoramento não são mais funções de servidor, mas os serviços integrados ao pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61629-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="61629-111">Durante o tempo em que suas implantações herdadas do Lync Server 2013 coexistem, a versão do Office Communications Server 2007 R2 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados em pools do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="61629-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="61629-112">A versão do Lync Server 2013 do servidor de arquivamento e o Monitoring Server reúnem dados para usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="61629-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61629-113">Durante a fase de migração quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Lync Server 2013, a versão do Office Communications Server 2007 R2 do servidor de arquivamento continua a coletar dados para usuários hospedados no Office Communications Server 2007 Os pools R2 e a versão do Lync Server 2013 do servidor de arquivamento coleta dados para usuários hospedados no Lync Server 2013 pools.</span><span class="sxs-lookup"><span data-stu-id="61629-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="61629-114">Se você usar uma solução de arquivamento e monitoramento de terceiros junto com o servidor de arquivamento e o servidor de monitoramento, converse com seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61629-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

