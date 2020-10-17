---
title: Lync Server 2013 experiência do usuário durante falha do pool
description: Lync Server 2013 experiência do usuário durante falha do pool.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569787"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="3c4ce-103">Experiência do usuário durante falha do pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c4ce-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c4ce-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3c4ce-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3c4ce-105">Se um pool falhar, todos os usuários do pool afetado serão forçados a sair e entrar no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="3c4ce-106">Para um breve período, os usuários que entram no pool de backup podem estar no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="3c4ce-107">No modo resiliência, os usuários não podem executar tarefas que poderiam causar uma alteração persistente no Lync Server, como adicionar um contato.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="3c4ce-108">Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="3c4ce-109">Todas as sessões que um usuário tem quando o pool falha são interrompidas, e o usuário deve restabelecer essas sessões após o failover para continuar.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="3c4ce-110">Os usuários não são hospedados durante o failover ou o failback.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-110">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="3c4ce-111">Os usuários hospedados em um pool que falharão serão temporariamente atendidos pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-111">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="3c4ce-112">Quando o pool inicial é restaurado, o administrador pode fazer o failback desses usuários para serem atendidos pelo pool inicial original.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-112">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="3c4ce-113">Observação no Lync 2013, o banco de dados do local Information Server não é replicado para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="3c4ce-114">Para obter uma prática recomendada, o administrador deve fazer o backup do banco de dados LIS regularmente e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup após o failover.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="3c4ce-115">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="3c4ce-115">User Experience During Failover</span></span>

<span data-ttu-id="3c4ce-116">Quando um usuário está em um pool que falha, o usuário está desconectado. Qualquer sessão ponto a ponto na qual o usuário estava participando foi encerrada, assim como as conferências organizadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-116">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="3c4ce-117">O usuário não pode fazer logon novamente até que o timer de resiliência do registrador expire ou o administrador inicie procedimentos de failover, o que vier primeiro.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-117">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="3c4ce-118">Quando o usuário fizer logon novamente, ele fará logon no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-118">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="3c4ce-119">Se eles fizerem logon antes da conclusão do failover, eles estarão no modo de resiliência até que o failover seja concluído.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-119">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="3c4ce-120">Somente o usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-120">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="3c4ce-121">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-121">User Experience During Failback</span></span>

<span data-ttu-id="3c4ce-122">O failback do pool pode acontecer enquanto um usuário afetado está conectado ao pool de backup e o usuário permanece conectado e funcionando durante o failback.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-122">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="3c4ce-123">O processo de failback leva vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-123">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="3c4ce-124">Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-124">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="3c4ce-125">As tabelas a seguir mostram mais detalhes sobre como um usuário com um cliente do Lync 2013 ou o Microsoft Lync 2010 é afetado durante e após o failback, e também como os usuários em outros pools vêem e interagem com um usuário em um pool que está sendo reprovado.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="3c4ce-126">Os usuários com o Microsoft Office Communicator 2007 R2 clients não podem entrar até que o pool de front-ends tenha falhado completamente novamente.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="3c4ce-127">O termo *usuário afetado* refere-se a qualquer usuário que tenha falhado do pool local e está sendo atendido pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-127">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="3c4ce-128">Por definição, qualquer usuário hospedado originalmente no pool de backup não é um usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-128">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="3c4ce-129">Experiência do usuário para um usuário afetado em um pool de failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c4ce-130">Estado ou tarefa do usuário</span><span class="sxs-lookup"><span data-stu-id="3c4ce-130">User state or task</span></span></th>
<th><span data-ttu-id="3c4ce-131">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-131">During failback</span></span></th>
<th><span data-ttu-id="3c4ce-132">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-133">Estado do usuário já conectado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-134">O usuário permanece conectado e conectado ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-134">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="3c4ce-135">Em algum momento, o usuário será desconectado e entrará novamente no pool local original, no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-135">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-136">O usuário permanece conectado e entra no modo normal.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-137">Novo logon de usuário</span><span class="sxs-lookup"><span data-stu-id="3c4ce-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-138">O usuário pode entrar no pool de Home no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-139">O usuário pode entrar no pool local original no modo normal.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-140">Conferências em andamento organizadas pelo usuário afetado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-141">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-141">All modalities of conference are terminated.</span></span> <span data-ttu-id="3c4ce-142">O botão reingressar será exibido, mas nenhum usuário poderá se reingressar enquanto o usuário afetado estiver no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-142">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-143">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-143">All modalities now work.</span></span> <span data-ttu-id="3c4ce-144">Todo participante precisa clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-144">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-145">Conferências em andamento organizadas pelo usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-146">A conferência continua e o usuário afetado pode permanecer na conferência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-146">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="3c4ce-147">O usuário afetado está restrito ao que ele pode fazer no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-147">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-148">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sai do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-149">Agendando ou modificando reuniões agendadas, criando conferências ad-hoc</span><span class="sxs-lookup"><span data-stu-id="3c4ce-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-150">Não é possível enquanto o usuário está no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-151">Disponível para todas as modalidades.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-152">Presença como vista por outros usuários no mesmo pool</span><span class="sxs-lookup"><span data-stu-id="3c4ce-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-153">Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-154">Mostra o último estado de presença definido pelo usuário e as alterações de presença serão refletidas agora.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-155">Disponibilidade de serviço de catálogo de endereços e lista de contatos</span><span class="sxs-lookup"><span data-stu-id="3c4ce-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-156">Não disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-157">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-158">Todas as sessões e modalidades ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="3c4ce-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-159">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-159">Available</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-160">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="3c4ce-161">Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool</span><span class="sxs-lookup"><span data-stu-id="3c4ce-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c4ce-162">Tarefa do usuário</span><span class="sxs-lookup"><span data-stu-id="3c4ce-162">User task</span></span></th>
<th><span data-ttu-id="3c4ce-163">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-163">During failback</span></span></th>
<th><span data-ttu-id="3c4ce-164">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="3c4ce-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-165">Exibindo a presença do usuário afetado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-166">Mostra o último estado de presença definido pelo usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-167">Trabalhando.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-167">Working.</span></span> <span data-ttu-id="3c4ce-168">Usuários não afetados Confira as atualizações feitas por usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-168">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-169">Conferências em andamento organizadas pelo usuário afetado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-170">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-171">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-171">All modalities now work.</span></span> <span data-ttu-id="3c4ce-172">Todo participante precisa clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-172">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c4ce-173">Conferências em andamento organizadas pelo usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="3c4ce-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-174">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-175">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="3c4ce-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c4ce-176">Todas as sessões e modalidades ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="3c4ce-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-177">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-177">Available</span></span></p></td>
<td><p><span data-ttu-id="3c4ce-178">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c4ce-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

