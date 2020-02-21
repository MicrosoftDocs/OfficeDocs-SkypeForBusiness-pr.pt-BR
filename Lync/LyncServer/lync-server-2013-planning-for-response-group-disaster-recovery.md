---
title: 'Lync Server 2013: planejamento para recuperação de desastre do grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab630dae949d1972d9e5077035d88d91964034f1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="aa774-102">Planejamento para recuperação de desastre do grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa774-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa774-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aa774-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aa774-104">Essa seção descreve algumas maneiras de preparar respostas de grupo para recuperação de desastres e fornece uma visão geral do processo de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="aa774-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="aa774-105">Preparando para recuperação de desastre do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="aa774-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="aa774-106">Lembre-se, ao se preparar para e executar procedimentos de recuperação de desastres, das coisas a seguir.</span><span class="sxs-lookup"><span data-stu-id="aa774-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa774-107">Em um ambiente de coexistência, somente os grupos de resposta do Lync Server 2013 têm suporte para os procedimentos de recuperação de desastre descritos neste documento.</span><span class="sxs-lookup"><span data-stu-id="aa774-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="aa774-108">Planeje para recuperação de desastres ao fazer seu planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="aa774-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="aa774-109">Para capacidade de recuperação de desastres, cada pool em um pool pareado deve ser capaz de lidar com as cargas de trabalho de todos os grupos de resposta em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="aa774-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="aa774-110">Para obter detalhes sobre o planejamento de capacidade de grupo de resposta, consulte [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="aa774-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="aa774-111">Faça cópias de backup regulares de todas as configurações do grupo de resposta em todos os pools de front-ends onde você implantou o aplicativo grupo de resposta usando o procedimento de exportação descrito neste documento.</span><span class="sxs-lookup"><span data-stu-id="aa774-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="aa774-112">Para obter detalhes, consulte [Response Group Disaster Recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="aa774-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="aa774-113">Mantenha as cópias de backup em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="aa774-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="aa774-114">Mantenha uma cópia de backup separada de todos os arquivos de áudio originais usados para o aplicativo de grupo de resposta, incluindo quaisquer gravações e arquivos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="aa774-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="aa774-115">Mantenha os arquivos de backup em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="aa774-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="aa774-116">Para a recuperação de desastres do Lync Server 2013, todas as configurações do grupo de resposta devem ter nomes exclusivos em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="aa774-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="aa774-117">Esse requisito se aplica a fluxos de trabalho, filas, grupos de agente, conjuntos de feriados e horários comerciais.</span><span class="sxs-lookup"><span data-stu-id="aa774-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="aa774-118">Você deve verificar se este requisito é atendido quando os pools primário e de backup ainda estão ativos, e antes de precisar iniciar qualquer procedimento de failover.</span><span class="sxs-lookup"><span data-stu-id="aa774-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="aa774-119">Caso encontre conflitos de nome ao importar dados de grupo de resposta ao pool de backup, a importação falha.</span><span class="sxs-lookup"><span data-stu-id="aa774-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="aa774-120">Para completar o procedimento de importação e failover, você deve solucionar os conflitos de nome, renomeando o objeto de grupo de resposta no pool de backup, ou usando o cmdlet **Import-CsRgsConfiguration** com o parâmetro –ResolveNameConflicts para solucionar automaticamente o conflito anexando um número de identificação exclusivo ao objeto de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="aa774-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="aa774-p105">No geral, recomendamos que você execute backups diários, mas caso possua um volume alto de alterações, você pode querer programar backups mais frequentes. a quantidade de informações que você pode perder em caso de desastre depende da frequência de seus backups, como também da frequência e volume de alterações.</span><span class="sxs-lookup"><span data-stu-id="aa774-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="aa774-123">É possível importar grupos de resposta a um pool de backup antes que ocorra uma operação de failover ou desastre.</span><span class="sxs-lookup"><span data-stu-id="aa774-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="aa774-124">A importação de grupos de resposta com antecedência reduz o tempo de inatividade, pois o serviço do grupo de resposta do Lync Server pode ser restaurado no pool de backup assim que as chamadas são roteadas para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa774-125">O aplicativo grupo de resposta não pode alcançar nenhum agente hospedado em um pool inativo até que o failover seja concluído.</span><span class="sxs-lookup"><span data-stu-id="aa774-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="aa774-126">Durante esse tempo, o aplicativo de grupo de resposta processa chamadas como se esses agentes não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="aa774-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="aa774-127">Processo de Recuperação de Disastre de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="aa774-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="aa774-128">No caso de um desastre, você pode recuperar grupos de resposta usando qualquer uma das seguintes abordagens de recuperação:</span><span class="sxs-lookup"><span data-stu-id="aa774-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="aa774-129">Failover para um pool de backup e então failback para o pool original.</span><span class="sxs-lookup"><span data-stu-id="aa774-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="aa774-130">Failover para um pool de backup, criar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente e então importar os grupos de resposta ao novo pool.</span><span class="sxs-lookup"><span data-stu-id="aa774-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="aa774-p108">Durante a fase de failover da recuperação de desastre, os grupos de resposta são hospedados em vários pools: no pool primário (que está indisponível) e no pool de backup. Os grupos de resposta em ambos os pools possuem o mesmo nome e proprietário (o pool primário), mas pais diferentes.</span><span class="sxs-lookup"><span data-stu-id="aa774-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="aa774-133">Ao recuperar criando um novo pool com um FQDN diferente, você deve atribuir ao novo pool a propriedade dos grupos de resposta, ao importá-los.</span><span class="sxs-lookup"><span data-stu-id="aa774-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="aa774-134">A propriedade dos grupos de resposta permanece com o pool original a menos que, ou até que, você explicitamente reatribua a propriedade usando o parâmetro –OverwriteOwner com o cmdlet **Import-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="aa774-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa774-135">Você também precisará usar o parâmetro – OverwriteOwner se reconstruído o pool durante a recuperação (ou seja, o banco de dados do grupo de resposta está vazio), se você usa ou não o mesmo FQDN.</span><span class="sxs-lookup"><span data-stu-id="aa774-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="aa774-136">Você não precisa usar o parâmetro –OverwriteOwner caso não tenha reconstruído o pool, mas é permitido que use este parâmetro a qualquer momento em que você importar grupos de resposta de volta ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="aa774-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="aa774-137">Você pode definir apenas um conjunto de definições de configuração de grupo de resposta no nível do aplicativo por pool.</span><span class="sxs-lookup"><span data-stu-id="aa774-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="aa774-138">Estas definições incluem a configuração de música de espera padrão, o arquivo de áudio música de espera padrão, o período de carência de retorno de toque e a configuração de contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="aa774-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="aa774-139">Para visualizar essas definições de configuração, execute o cmdlet **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="aa774-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="aa774-140">Para obter detalhes sobre o cmdlet **Get-CsRgsConfiguration** , consulte [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="aa774-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="aa774-141">Você pode transferir estas definições de nível de aplicativo de um pool para outro usando o cmdlet **Import-CsRgsConfiguration** com o parâmetro –ReplaceExistingSettings, mas fazer isso substitui as definições no pool de destino.</span><span class="sxs-lookup"><span data-stu-id="aa774-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aa774-p112">Essa limitação sobre a transferência de definições para outro pool é verdadeira apenas para as definições de nível de aplicativo e o arquivo de música de espera padrão. Ela não se aplica a grupos de agentes, filas, fluxos de trabalho, horários comerciais e conjutnos de feriados.</span><span class="sxs-lookup"><span data-stu-id="aa774-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="aa774-p113">Caso não queira substituir as definições de nível de aplicativo no pool de backup durante um desastre e o pool primário não possa ser recuperado, as definições de nível de aplicativo do pool primário serão perdidas. Caso precise criar um novo pool para substituir o pool primário durante a recuperação, seja com o mesmo FQDN ou com um diferente, você não pode recuperar as definições de nível de aplicativo originais. Neste caso, você precisa configurar o novo poool com essas definições e incluir o arquivo de áudio de música de espera.</span><span class="sxs-lookup"><span data-stu-id="aa774-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="aa774-147">Caso decisa usar o cmdlet **Import-CsRgsConfiguration** para transferir definições de nível de aplicativo do pool primário ao pool de backup durante um desastre, você então pode transferir as definições do pool de backup ao novo pool durante a recuperação, do mesmo modo que você as transferia do pool primário ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="aa774-148">A tabela a seguir é uma visão geral das etapas envolvidas na recuperação de grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="aa774-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="aa774-149">Para obter detalhes sobre como executar essas etapas, consulte [Response Group Disaster Recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="aa774-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="aa774-150">Etapas de Recuperação de Disastre de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="aa774-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa774-151">Fase</span><span class="sxs-lookup"><span data-stu-id="aa774-151">Phase</span></span></th>
<th><span data-ttu-id="aa774-152">Etapas</span><span class="sxs-lookup"><span data-stu-id="aa774-152">Steps</span></span></th>
<th><span data-ttu-id="aa774-153">Grupos e funções necessários</span><span class="sxs-lookup"><span data-stu-id="aa774-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa774-154">Antes da interrupção</span><span class="sxs-lookup"><span data-stu-id="aa774-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="aa774-155">Com base em rotina, execute o cmdlet <strong>Export-CsRgsConfiguration</strong> para criar backups de todas as configurações de grupo de resposta em todos os pools de front-ends onde o aplicativo de grupo de resposta é implantado.</span><span class="sxs-lookup"><span data-stu-id="aa774-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="aa774-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aa774-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aa774-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="aa774-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa774-158">Durante a interrupção</span><span class="sxs-lookup"><span data-stu-id="aa774-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="aa774-159">Execute o cmdlet <strong>Import-CsRgsConfiguration</strong> para importar a configuração do serviço grupo de resposta do Lync Server de backup do pool primário para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="aa774-160">Use o parâmetro – ReplaceExistingSettings se você quiser substituir as configurações do grupo de resposta no nível do aplicativo no pool de backup com as configurações do pool primário.</span><span class="sxs-lookup"><span data-stu-id="aa774-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="aa774-161">Se você não transferir as definições de nível de aplicativo do pool primário ao pool de backup, e o pool primário não possa ser recuperado, você perderá as definições do pool primário.</span><span class="sxs-lookup"><span data-stu-id="aa774-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="aa774-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aa774-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aa774-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="aa774-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa774-164">Após importar</span><span class="sxs-lookup"><span data-stu-id="aa774-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="aa774-165">Execute cmdlets do grupo de resposta com o parâmetro – ShowAll (para exibir todos os grupos de resposta) ou o parâmetro – Owner (para exibir apenas grupos de resposta importados) para verificar se todas as configurações do grupo de resposta foram importadas para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="aa774-166">Caso não use nenhum dos parâmetros –ShowAll ou –Owner, os grupos de resposta que você importou ao pool de backup não serão listados nos resultados retornados pelos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="aa774-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="aa774-167">Execute os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="aa774-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa774-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aa774-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aa774-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aa774-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="aa774-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa774-175">Após o failover</span><span class="sxs-lookup"><span data-stu-id="aa774-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="aa774-176">Realize uma chamada de teste a um grupo de resposta que foi importado ao pool de backup e verifique se a chamada é atendida corretamente.</span><span class="sxs-lookup"><span data-stu-id="aa774-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="aa774-177">Todos os operadores formais devem entrar novamente em seus grupos formais no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="aa774-178">Gerencie alterações de configuração:</span><span class="sxs-lookup"><span data-stu-id="aa774-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="aa774-179">Grupos de resposta no pool de backup, sejam importados ao pool de backup, ou de propriedade do pool de backup, podem ser modificados normalmente durante a interrupção.</span><span class="sxs-lookup"><span data-stu-id="aa774-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="aa774-180">Você deve usar o Shell de gerenciamento do Lync Server para gerenciar os grupos de resposta importados para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="aa774-181">Você não pode usar o painel de controle do Lync Server para gerenciar esses grupos de resposta enquanto eles estão no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="aa774-182">Não disponível</span><span class="sxs-lookup"><span data-stu-id="aa774-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa774-183">Após recuperação, antes de failback</span><span class="sxs-lookup"><span data-stu-id="aa774-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="aa774-184">Execute o cmdlet <strong>Export-CsRgsConfiguration</strong> especificando o parâmetro -Source como o pool de backup, e o parâmetro –Owner como o pool primário para exportar os grupos de resposta de propriedade do pool primário, a partir do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="aa774-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aa774-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aa774-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="aa774-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa774-187">Após failback</span><span class="sxs-lookup"><span data-stu-id="aa774-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="aa774-188">Execute o cmdlet <strong>Import-CsRgsConfiguration</strong> para importar os grupos de resposta de volta ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="aa774-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="aa774-p116">Caso o pool primário não possa ser recuperado e você implante um novo pool para substituí-lo, use o parâmetro -ReplaceExistingSettings para transferir as definições de nível de aplicativo do pool de backup ao novo pool. Caso não transfira as configurações do pool de backup, o novo pool usará as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="aa774-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="aa774-191">Execute os cmdlets a seguir com o parâmetro –ShowAll (para exibir todos os grupos de resposta) ou o parâmetro –Owner (para exibir apenas grupos de resposta importados) para verificar se todas as configurações de grupo de resposta foram importados com sucesso de volta ao pool primário:</span><span class="sxs-lookup"><span data-stu-id="aa774-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="aa774-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="aa774-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="aa774-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="aa774-197">Realize uma chamada de teste a um grupo de resposta que foi importado de volta ao pool primário e verifique se a chamada é atendida corretamente.</span><span class="sxs-lookup"><span data-stu-id="aa774-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="aa774-198">Execute, opcionalmente, o cmdlet <strong>Export-CsRgsConfiguration</strong> no pool de backup com o parâmetro –RemoveExportedConfiguration para remover os grupos de resposta pertencentes ao pool primário, a partir do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="aa774-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aa774-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aa774-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aa774-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="aa774-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

