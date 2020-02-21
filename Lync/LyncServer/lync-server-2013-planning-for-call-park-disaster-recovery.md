---
title: 'Lync Server 2013: planejamento para recuperação de desastre de estacionamento de chamadas'
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
ms.openlocfilehash: 1ae06a3d0e3e404781e2f51ef18e1ba2ca76d72b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="dba12-102">Planejamento para recuperação de desastre de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dba12-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dba12-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="dba12-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="dba12-104">Esta seção descreve algumas maneiras de preparar o aplicativo de estacionamento de chamada para recuperação de desastres e algumas considerações para o processo de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="dba12-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="dba12-105">Preparando para recuperação de desastre de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="dba12-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="dba12-106">Considere o seguinte ao preparar e realizar os procedimentos de recuperação de desastres:</span><span class="sxs-lookup"><span data-stu-id="dba12-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="dba12-107">Planeje a recuperação de desastres ao realizar o planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="dba12-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="dba12-108">Para a capacidade de recuperação de desastres, cada pool em um pool emparelhado deve ser capaz de lidar com as cargas de trabalho dos serviços de estacionamento de chamadas nos dois pools.</span><span class="sxs-lookup"><span data-stu-id="dba12-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="dba12-109">Para obter detalhes sobre o planejamento de capacidade de estacionamento de chamada, consulte [Capacity Planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="dba12-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="dba12-110">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o serviço Estacionamento de Chamada executado no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="dba12-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="dba12-111">Portanto, o suporte para estacionamento de chamadas durante a recuperação de desastres exige que o aplicativo de estacionamento de chamada seja implantado e habilitado no pool primário e no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="dba12-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="dba12-112">Cada pool deve ter um intervalo válido de números de órbita para ser utilizado pelos usuários hospedados no pool a fim de estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="dba12-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="dba12-113">Mantenha sempre uma cópia de backup separada de qualquer música personalizada em espera que tenha sido carregada para estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="dba12-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="dba12-114">Não é feito backup desses arquivos como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="dba12-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="dba12-115">Considerações de recuperação de desastre de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="dba12-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="dba12-116">Você pode definir apenas um conjunto de definições de configuração do aplicativo de estacionamento de chamada e um arquivo de áudio de música em espera personalizado por pool.</span><span class="sxs-lookup"><span data-stu-id="dba12-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="dba12-117">Essas configurações incluem o tempo limite máximo, a música em espera, o número máximo de tentativas de recebimento de chamadas e o tempo limite de URI.</span><span class="sxs-lookup"><span data-stu-id="dba12-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="dba12-118">Para exibir essas configurações, execute o cmdlet **Get-CsCpsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="dba12-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="dba12-119">Para obter detalhes sobre o cmdlet **Get-CsCpsConfiguration** , consulte [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="dba12-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="dba12-120">Durante a recuperação de desastre, o estacionamento de chamadas usa o aplicativo de estacionamento de chamada no pool de backup, de modo que não seja feito backup das configurações do pool principal.</span><span class="sxs-lookup"><span data-stu-id="dba12-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="dba12-121">Se o pool primário não puder ser recuperado e você implantar um novo pool para substituir o pool principal, as configurações do pool primário serão perdidas e você precisará reconfigurar as configurações de estacionamento de chamada e qualquer arquivo de áudio de música em espera personalizado no novo pool.</span><span class="sxs-lookup"><span data-stu-id="dba12-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="dba12-122">Se você implantar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente para substituir o pool primário, precisará reatribuir todos os intervalos de órbita de estacionamento de chamada que foram associados ao pool primário ao FQDN do novo pool.</span><span class="sxs-lookup"><span data-stu-id="dba12-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="dba12-123">Para reatribuir intervalos de órbita ao novo pool, você pode usar o painel de controle do Lync Server ou o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="dba12-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="dba12-124">Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="dba12-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

