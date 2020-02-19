---
title: Lync Server 2013 experiência do usuário durante falha do pool
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
ms.openlocfilehash: 65d33dad39527f64ba7b96ae6d75f8d6e11a2f04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="b0abc-102">Experiência do usuário durante falha do pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0abc-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0abc-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b0abc-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b0abc-104">Se um pool falhar, todos os usuários do pool afetado serão forçados a sair e entrar no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="b0abc-105">Para um breve período, os usuários que entram no pool de backup podem estar no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="b0abc-106">No modo resiliência, os usuários não podem executar tarefas que poderiam causar uma alteração persistente no Lync Server, como adicionar um contato.</span><span class="sxs-lookup"><span data-stu-id="b0abc-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="b0abc-107">Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="b0abc-108">Todas as sessões que um usuário tem quando o pool falha são interrompidas, e o usuário deve restabelecer essas sessões após o failover para continuar.</span><span class="sxs-lookup"><span data-stu-id="b0abc-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="b0abc-109">Os usuários não são hospedados durante o failover ou o failback.</span><span class="sxs-lookup"><span data-stu-id="b0abc-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="b0abc-110">Os usuários hospedados em um pool que falharão serão temporariamente atendidos pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="b0abc-111">Quando o pool inicial é restaurado, o administrador pode fazer o failback desses usuários para serem atendidos pelo pool inicial original.</span><span class="sxs-lookup"><span data-stu-id="b0abc-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="b0abc-112">Observação no Lync 2013, o banco de dados do local Information Server não é replicado para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="b0abc-113">Para obter uma prática recomendada, o administrador deve fazer o backup do banco de dados LIS regularmente e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup após o failover.</span><span class="sxs-lookup"><span data-stu-id="b0abc-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="b0abc-114">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="b0abc-114">User Experience During Failover</span></span>

<span data-ttu-id="b0abc-115">Quando um usuário está em um pool que falha, o usuário está desconectado. Qualquer sessão ponto a ponto na qual o usuário estava participando foi encerrada, assim como as conferências organizadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b0abc-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="b0abc-116">O usuário não pode fazer logon novamente até que o timer de resiliência do registrador expire ou o administrador inicie procedimentos de failover, o que vier primeiro.</span><span class="sxs-lookup"><span data-stu-id="b0abc-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="b0abc-117">Quando o usuário fizer logon novamente, ele fará logon no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="b0abc-118">Se eles fizerem logon antes da conclusão do failover, eles estarão no modo de resiliência até que o failover seja concluído.</span><span class="sxs-lookup"><span data-stu-id="b0abc-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="b0abc-119">Somente o usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b0abc-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="b0abc-120">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-120">User Experience During Failback</span></span>

<span data-ttu-id="b0abc-121">O failback do pool pode acontecer enquanto um usuário afetado está conectado ao pool de backup e o usuário permanece conectado e funcionando durante o failback.</span><span class="sxs-lookup"><span data-stu-id="b0abc-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="b0abc-122">O processo de failback leva vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="b0abc-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="b0abc-123">Como referência, espera-se que leve até 60 minutos para um pool de 20 mil usuários.</span><span class="sxs-lookup"><span data-stu-id="b0abc-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="b0abc-124">As tabelas a seguir mostram mais detalhes sobre como um usuário com um cliente do Lync 2013 ou o Microsoft Lync 2010 é afetado durante e após o failback, e também como os usuários em outros pools vêem e interagem com um usuário em um pool que está sendo reprovado.</span><span class="sxs-lookup"><span data-stu-id="b0abc-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="b0abc-125">Os usuários com o Microsoft Office Communicator 2007 R2 clients não podem entrar até que o pool de front-ends tenha falhado completamente novamente.</span><span class="sxs-lookup"><span data-stu-id="b0abc-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="b0abc-126">O termo *usuário afetado* refere-se a qualquer usuário que tenha falhado do pool local e está sendo atendido pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="b0abc-127">Por definição, qualquer usuário hospedado originalmente no pool de backup não é um usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="b0abc-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="b0abc-128">Experiência do usuário para um usuário afetado em um pool de failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0abc-129">Estado ou tarefa do usuário</span><span class="sxs-lookup"><span data-stu-id="b0abc-129">User state or task</span></span></th>
<th><span data-ttu-id="b0abc-130">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-130">During failback</span></span></th>
<th><span data-ttu-id="b0abc-131">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-132">Estado do usuário já conectado</span><span class="sxs-lookup"><span data-stu-id="b0abc-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="b0abc-133">O usuário permanece conectado e conectado ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="b0abc-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="b0abc-134">Em algum momento, o usuário será desconectado e entrará novamente no pool local original, no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-135">O usuário permanece conectado e entra no modo normal.</span><span class="sxs-lookup"><span data-stu-id="b0abc-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-136">Novo logon de usuário</span><span class="sxs-lookup"><span data-stu-id="b0abc-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="b0abc-137">O usuário pode entrar no pool de Home no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-138">O usuário pode entrar no pool local original no modo normal.</span><span class="sxs-lookup"><span data-stu-id="b0abc-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-139">Conferências em andamento organizadas pelo usuário afetado</span><span class="sxs-lookup"><span data-stu-id="b0abc-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="b0abc-140">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="b0abc-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="b0abc-141">O botão reingressar será exibido, mas nenhum usuário poderá se reingressar enquanto o usuário afetado estiver no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-142">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="b0abc-142">All modalities now work.</span></span> <span data-ttu-id="b0abc-143">Todo participante precisa clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-144">Conferências em andamento organizadas pelo usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="b0abc-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="b0abc-145">A conferência continua e o usuário afetado pode permanecer na conferência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="b0abc-146">O usuário afetado está restrito ao que ele pode fazer no modo resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-147">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam depois que o usuário sai do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-148">Agendando ou modificando reuniões agendadas, criando conferências ad-hoc</span><span class="sxs-lookup"><span data-stu-id="b0abc-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="b0abc-149">Não é possível enquanto o usuário está no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-150">Disponível para todas as modalidades.</span><span class="sxs-lookup"><span data-stu-id="b0abc-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-151">Presença como vista por outros usuários no mesmo pool</span><span class="sxs-lookup"><span data-stu-id="b0abc-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="b0abc-152">Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-153">Mostra o último estado de presença definido pelo usuário e as alterações de presença serão refletidas agora.</span><span class="sxs-lookup"><span data-stu-id="b0abc-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-154">Disponibilidade de serviço de catálogo de endereços e lista de contatos</span><span class="sxs-lookup"><span data-stu-id="b0abc-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="b0abc-155">Não disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="b0abc-156">Disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-157">Todas as sessões e modalidades ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="b0abc-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="b0abc-158">Disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-158">Available</span></span></p></td>
<td><p><span data-ttu-id="b0abc-159">Disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="b0abc-160">Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool</span><span class="sxs-lookup"><span data-stu-id="b0abc-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0abc-161">Tarefa do usuário</span><span class="sxs-lookup"><span data-stu-id="b0abc-161">User task</span></span></th>
<th><span data-ttu-id="b0abc-162">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-162">During failback</span></span></th>
<th><span data-ttu-id="b0abc-163">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="b0abc-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-164">Exibindo a presença do usuário afetado</span><span class="sxs-lookup"><span data-stu-id="b0abc-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="b0abc-165">Mostra o último estado de presença definido pelo usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="b0abc-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-166">Trabalhando.</span><span class="sxs-lookup"><span data-stu-id="b0abc-166">Working.</span></span> <span data-ttu-id="b0abc-167">Usuários não afetados Confira as atualizações feitas por usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="b0abc-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-168">Conferências em andamento organizadas pelo usuário afetado</span><span class="sxs-lookup"><span data-stu-id="b0abc-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="b0abc-169">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="b0abc-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-170">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="b0abc-170">All modalities now work.</span></span> <span data-ttu-id="b0abc-171">Todo participante precisa clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="b0abc-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0abc-172">Conferências em andamento organizadas pelo usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="b0abc-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="b0abc-173">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="b0abc-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="b0abc-174">A conferência continua e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="b0abc-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0abc-175">Todas as sessões e modalidades ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="b0abc-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="b0abc-176">Disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-176">Available</span></span></p></td>
<td><p><span data-ttu-id="b0abc-177">Disponível</span><span class="sxs-lookup"><span data-stu-id="b0abc-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

