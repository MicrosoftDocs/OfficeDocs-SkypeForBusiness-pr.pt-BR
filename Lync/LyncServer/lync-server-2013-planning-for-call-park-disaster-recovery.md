---
title: 'Lync Server 2013: planejamento para recuperação de desastre de estacionamento de chamadas'
description: 'Lync Server 2013: planejamento para recuperação de desastre de estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554277"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="c6caa-103">Planejamento para recuperação de desastre de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6caa-103">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6caa-104">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c6caa-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c6caa-105">Esta seção descreve algumas maneiras de preparar o aplicativo de estacionamento de chamada para recuperação de desastres e algumas considerações para o processo de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="c6caa-105">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="c6caa-106">Preparando para recuperação de desastre de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="c6caa-106">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="c6caa-107">Considere o seguinte ao preparar e realizar os procedimentos de recuperação de desastres:</span><span class="sxs-lookup"><span data-stu-id="c6caa-107">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="c6caa-108">Planeje a recuperação de desastres ao realizar o planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="c6caa-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="c6caa-109">Para a capacidade de recuperação de desastres, cada pool em um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de estacionamento de chamadas nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="c6caa-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="c6caa-110">Para obter detalhes sobre o planejamento de capacidade de estacionamento de chamada, consulte [Capacity Planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="c6caa-110">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="c6caa-111">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o serviço Estacionamento de Chamada executado no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c6caa-111">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="c6caa-112">Portanto, o suporte para estacionamento de chamadas durante a recuperação de desastres exige que o aplicativo de estacionamento de chamada seja implantado e habilitado no pool primário e no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c6caa-112">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="c6caa-113">Cada pool deve ter um intervalo válido de números de órbita para ser utilizado pelos usuários hospedados no pool a fim de estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="c6caa-113">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="c6caa-114">Mantenha sempre uma cópia de backup separada de qualquer música personalizada em espera que tenha sido carregada para estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="c6caa-114">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="c6caa-115">Não é feito backup desses arquivos como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="c6caa-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="c6caa-116">Considerações de recuperação de desastre de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="c6caa-116">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="c6caa-117">Você pode definir apenas um conjunto de definições de configuração do aplicativo de estacionamento de chamada e um arquivo de áudio de música em espera personalizado por pool.</span><span class="sxs-lookup"><span data-stu-id="c6caa-117">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="c6caa-118">Essas configurações incluem o tempo limite máximo, a música em espera, o número máximo de tentativas de recebimento de chamadas e o tempo limite de URI.</span><span class="sxs-lookup"><span data-stu-id="c6caa-118">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="c6caa-119">Para exibir essas configurações, execute o cmdlet **Get-CsCpsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c6caa-119">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="c6caa-120">Para obter detalhes sobre o cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c6caa-120">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="c6caa-121">Durante a recuperação de desastre, o estacionamento de chamadas usa o aplicativo de estacionamento de chamada no pool de backup, de modo que não seja feito backup das configurações do pool principal.</span><span class="sxs-lookup"><span data-stu-id="c6caa-121">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="c6caa-122">Se o pool primário não puder ser recuperado e você implantar um novo pool para substituir o pool principal, as configurações do pool primário serão perdidas e você precisará reconfigurar as configurações de estacionamento de chamada e qualquer arquivo de áudio de música em espera personalizado no novo pool.</span><span class="sxs-lookup"><span data-stu-id="c6caa-122">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="c6caa-123">Se você implantar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente para substituir o pool primário, precisará reatribuir todos os intervalos de órbita de estacionamento de chamada que foram associados ao pool primário ao FQDN do novo pool.</span><span class="sxs-lookup"><span data-stu-id="c6caa-123">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="c6caa-124">Para reatribuir intervalos de órbita ao novo pool, você pode usar o painel de controle do Lync Server ou o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="c6caa-124">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="c6caa-125">Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="c6caa-125">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

