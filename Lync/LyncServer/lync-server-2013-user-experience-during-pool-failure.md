---
title: Experiência do usuário do Lync Server 2013 durante falha de pool
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
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="315de-102">Experiência do usuário durante uma falha de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="315de-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="315de-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="315de-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="315de-104">Se um pool tiver failover, todos os usuários do pool afetado serão forçados a se desconectarem e entrarem no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="315de-105">Por um curto período os usuários que entram no pool de backup podem estar no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="315de-106">No modo de resiliência, os usuários não conseguem executar tarefas que poderiam causar uma alteração persistente no Lync Server, como adicionar um contato.</span><span class="sxs-lookup"><span data-stu-id="315de-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="315de-107">Após a conclusão do failover, todos os usuários podem obter todos os serviços do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="315de-108">Todas as sessões que um usuário tenha quando o pool falhar, e o usuário deve restabelecer essas sessões após o failover para continuar.</span><span class="sxs-lookup"><span data-stu-id="315de-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="315de-109">Os usuários não são hospedados novamente durante o failover ou o failback.</span><span class="sxs-lookup"><span data-stu-id="315de-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="315de-110">Os usuários que são hospedados em um pool que falha serão atendidos temporariamente pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="315de-111">Quando o pool inicial é restaurado, o administrador pode fazer failback para que esses usuários sejam atendidos pelo pool inicial original.</span><span class="sxs-lookup"><span data-stu-id="315de-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="315de-112">Observação no Lync 2013, o banco de dados do servidor de informações de localização não é replicado para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="315de-113">Como prática recomendada, o administrador deve efetuar regularmente o backup do banco de dados LIS e usar a cópia de backup mais recente para restaurar o banco de dados LIS no pool de backup depois do failover.</span><span class="sxs-lookup"><span data-stu-id="315de-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="315de-114">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="315de-114">User Experience During Failover</span></span>

<span data-ttu-id="315de-115">Quando um usuário está em um pool que falha, o usuário é desconectado. Qualquer sessão ponto a ponto na qual o usuário estava participando foi encerrada, assim como as conferências organizadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="315de-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="315de-116">o usuário não pode se conectar até o temporizador de resiliência do registrador expirar ou o administrador iniciar procedimentos de failover, o que ocorrer primeiro.</span><span class="sxs-lookup"><span data-stu-id="315de-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="315de-117">Quando o usuário entrar novamente, isso ocorrerá no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="315de-118">Se entrarem antes da conclusão do failover, estarão no modo Resiliência até a conclusão do failover.</span><span class="sxs-lookup"><span data-stu-id="315de-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="315de-119">Somente o usuário poderá estabelecer novas sessões ou restabelecer sessões anteriores.</span><span class="sxs-lookup"><span data-stu-id="315de-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="315de-120">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="315de-120">User Experience During Failback</span></span>

<span data-ttu-id="315de-121">O failback de pool pode ocorrer enquanto um usuário afetado é conectado ao pool de backup e o usuário permanece conectado e trabalhando durante o failback.</span><span class="sxs-lookup"><span data-stu-id="315de-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="315de-122">Observe que o processo de failback demora vários minutos para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="315de-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="315de-123">Para referência, a expectativa é de até 60 minutos para um pool de 20.000 usuários.</span><span class="sxs-lookup"><span data-stu-id="315de-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="315de-124">As tabelas a seguir mostram mais detalhes sobre como um usuário com um cliente do Lync 2013 ou um cliente do Microsoft Lync 2010 é afetado durante e após o failback, e também como os usuários em outros pools vêem e interagem com um usuário em um pool com falha de volta.</span><span class="sxs-lookup"><span data-stu-id="315de-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="315de-125">Os usuários com os clientes do Microsoft Office Communicator 2007 R2 não podem entrar até que o pool de front-end tenha falhado completamente novamente.)</span><span class="sxs-lookup"><span data-stu-id="315de-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="315de-126">O termo *usuários afetado* se refere a qualquer usuário que sofreu failover no pool de hospedagem e está sendo atendido pelo pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="315de-127">Por definição, qualquer usuário originalmente hospedado no pool de backup não é um usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="315de-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="315de-128">Experiência do usuário para um usuário afetado em um pool em failback</span><span class="sxs-lookup"><span data-stu-id="315de-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="315de-129">Estado do usuário ou tarefa</span><span class="sxs-lookup"><span data-stu-id="315de-129">User state or task</span></span></th>
<th><span data-ttu-id="315de-130">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="315de-130">During failback</span></span></th>
<th><span data-ttu-id="315de-131">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="315de-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="315de-132">Estado do usuário do usuário já conectado</span><span class="sxs-lookup"><span data-stu-id="315de-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="315de-133">O usuário permanece conectado e conectado ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="315de-133">User stays signed in and connected to backup pool.</span></span> <span data-ttu-id="315de-134">Em algum usuário, o usuário será desconectado e se conectará novamente ao pool inicial original, no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-134">At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-135">O usuário permanece conectado e entra no modo normal.</span><span class="sxs-lookup"><span data-stu-id="315de-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-136">Novo logon de usuário</span><span class="sxs-lookup"><span data-stu-id="315de-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="315de-137">O usuário pode entrar no pool de Home no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-138">O usuário pode entrar no pool inicial original em modo normal.</span><span class="sxs-lookup"><span data-stu-id="315de-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315de-139">Conferências em andamento organizadas por um usuário afetado</span><span class="sxs-lookup"><span data-stu-id="315de-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="315de-140">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="315de-140">All modalities of conference are terminated.</span></span> <span data-ttu-id="315de-141">Botão reingressar aparecerá, mas nenhum usuário poderá se reconectar enquanto o usuário afetado estiver no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-141">Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-142">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="315de-142">All modalities now work.</span></span> <span data-ttu-id="315de-143">Todos os participantes devem clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="315de-143">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-144">Conferências em andamento organizadas por um usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="315de-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="315de-145">A conferência continua e o usuário afetado pode permanecer na conferência.</span><span class="sxs-lookup"><span data-stu-id="315de-145">Conference continues and affected user can stay in the conference.</span></span> <span data-ttu-id="315de-146">O usuário afetado está restrito ao que ele/ela pode fazer no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-146">Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-147">A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam após o usuário sair do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315de-148">Agendando ou modificando reuniões agendadas, criando conferências ad hoc</span><span class="sxs-lookup"><span data-stu-id="315de-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="315de-149">Não é possível enquanto o usuário está no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-150">Disponível para todas as modalidades.</span><span class="sxs-lookup"><span data-stu-id="315de-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-151">Presença como vista por outros usuários no mesmo pool</span><span class="sxs-lookup"><span data-stu-id="315de-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="315de-152">Presença desconhecida enquanto o usuário está conectado ao pool de backup durante o modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="315de-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="315de-153">Mostra o último estado de presença definido pelo usuário e as alterações de presença agora serão refletidas.</span><span class="sxs-lookup"><span data-stu-id="315de-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315de-154">Lista de contatos e disponibilidade do serviço de catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="315de-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="315de-155">Não disponível</span><span class="sxs-lookup"><span data-stu-id="315de-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="315de-156">Disponível</span><span class="sxs-lookup"><span data-stu-id="315de-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-157">Todas as sessões ponto a ponto e modalidades</span><span class="sxs-lookup"><span data-stu-id="315de-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="315de-158">Disponível</span><span class="sxs-lookup"><span data-stu-id="315de-158">Available</span></span></p></td>
<td><p><span data-ttu-id="315de-159">Disponível</span><span class="sxs-lookup"><span data-stu-id="315de-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="315de-160">Experiência do usuário para um usuário hospedado em um pool não afetado durante o failback de outro pool</span><span class="sxs-lookup"><span data-stu-id="315de-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="315de-161">Tarefa do usuário</span><span class="sxs-lookup"><span data-stu-id="315de-161">User task</span></span></th>
<th><span data-ttu-id="315de-162">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="315de-162">During failback</span></span></th>
<th><span data-ttu-id="315de-163">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="315de-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="315de-164">Visualizando a presença de um usuário afetado</span><span class="sxs-lookup"><span data-stu-id="315de-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="315de-165">Mostra o último estado de presença definido pelo usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="315de-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="315de-166">Trabalhando.</span><span class="sxs-lookup"><span data-stu-id="315de-166">Working.</span></span> <span data-ttu-id="315de-167">Usuários não afetados Veja as atualizações feitas por usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="315de-167">Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-168">Conferências em andamento organizadas por um usuário afetado</span><span class="sxs-lookup"><span data-stu-id="315de-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="315de-169">Todas as modalidades de conferência são encerradas.</span><span class="sxs-lookup"><span data-stu-id="315de-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="315de-170">Todas as modalidades agora funcionam.</span><span class="sxs-lookup"><span data-stu-id="315de-170">All modalities now work.</span></span> <span data-ttu-id="315de-171">Todos os participantes devem clicar para reingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="315de-171">Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="315de-172">Conferências em andamento organizadas por um usuário não afetado</span><span class="sxs-lookup"><span data-stu-id="315de-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="315de-173">A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="315de-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="315de-174">A conferência continua, e o usuário afetado pode permanecer na conferência e todas as modalidades funcionam.</span><span class="sxs-lookup"><span data-stu-id="315de-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="315de-175">Todas as sessões ponto a ponto e modalidades</span><span class="sxs-lookup"><span data-stu-id="315de-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="315de-176">Disponível</span><span class="sxs-lookup"><span data-stu-id="315de-176">Available</span></span></p></td>
<td><p><span data-ttu-id="315de-177">Disponível</span><span class="sxs-lookup"><span data-stu-id="315de-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

