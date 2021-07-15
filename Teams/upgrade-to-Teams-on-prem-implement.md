---
title: Estratégias de atualização para administradores de IT
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: O artigo é para administradores de IT e descreve estratégias para implementar sua atualização de Skype for Business para Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f11d14bc7bf302a864afe3062ef8f2bb8eccd7da
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437638"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="e02f4-103">Estratégias de atualização para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="e02f4-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="e02f4-104">![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="e02f4-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e02f4-105">Este artigo é para administradores de IT que querem implementar sua atualização para Teams de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e02f4-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="e02f4-106">Antes de implementar sua atualização, recomendamos os seguintes artigos que descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="e02f4-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e02f4-107">Compreender Microsoft Teams e Skype for Business coexistência e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="e02f4-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="e02f4-108">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="e02f4-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e02f4-109">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="e02f4-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="e02f4-110">Opções de atualização</span><span class="sxs-lookup"><span data-stu-id="e02f4-110">Upgrade options</span></span>

<span data-ttu-id="e02f4-111">Esta seção descreve como implementar sua atualização usando uma das seguintes opções de atualização:</span><span class="sxs-lookup"><span data-stu-id="e02f4-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="e02f4-112">Atualização de recursos sobrepostos (usando o modo Ilhas)</span><span class="sxs-lookup"><span data-stu-id="e02f4-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="e02f4-113">Uma atualização de recursos selecionados para uma organização que ainda não começou a usar Teams</span><span class="sxs-lookup"><span data-stu-id="e02f4-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="e02f4-114">Uma atualização de recursos selecionados para uma organização que já está usando Teams no modo Ilhas</span><span class="sxs-lookup"><span data-stu-id="e02f4-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="e02f4-115">Se você precisar de mais informações sobre as opções, certifique-se de já ter lido Escolher sua jornada de atualização de Skype for Business [para Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e02f4-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="e02f4-116">Atualização de recursos sobrepostos (usando o modo Ilhas)</span><span class="sxs-lookup"><span data-stu-id="e02f4-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="e02f4-117">Para a opção de atualização de recursos sobrepostos:</span><span class="sxs-lookup"><span data-stu-id="e02f4-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="e02f4-118">Considere essa opção se você puder fazer uma atualização rápida para sua organização geral.</span><span class="sxs-lookup"><span data-stu-id="e02f4-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="e02f4-119">Como há um risco potencial de confusão para os usuários finais com a execução de ambos os clientes, é melhor minimizar o período durante o qual os usuários devem executar ambos os clientes.</span><span class="sxs-lookup"><span data-stu-id="e02f4-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="e02f4-120">Você deve garantir que seus usuários saibam executar ambos os clientes.</span><span class="sxs-lookup"><span data-stu-id="e02f4-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="e02f4-121">Essa opção é o modelo fora da caixa e não exige que a ação do administrador seja iniciada com Teams exceto para atribuir a licença Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e02f4-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="e02f4-122">Se os usuários já Skype for Business online, você já pode estar nesse modelo.</span><span class="sxs-lookup"><span data-stu-id="e02f4-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="e02f4-123">Pode ser um desafio sair do modo de recursos sobrepostos e mudar para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e02f4-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="e02f4-124">Como os usuários atualizados só se comunicam Teams, qualquer outro usuário na organização que se comunica com esse usuário deve estar usando Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="e02f4-125">Se você tiver usuários que não começaram a usar Teams, eles serão expostos a mensagens ausentes.</span><span class="sxs-lookup"><span data-stu-id="e02f4-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="e02f4-126">Além disso, eles não verão os usuários do TeamsOnly online no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e02f4-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="e02f4-127">Algumas organizações optam por fazer uma atualização em todo o locatário usando a política global tenant para evitar isso, no entanto, isso requer planejamento antecipado, bem como aguardar até que todos os usuários estão prontos para serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="e02f4-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="e02f4-128">Uma atualização de recursos selecionados para uma organização que ainda não começou a usar Teams</span><span class="sxs-lookup"><span data-stu-id="e02f4-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="e02f4-129">Se a sua organização ainda não tiver usuários ativos no Teams, a primeira etapa é definir a política de locatário padrão para TeamsUpgradePolicy como um dos modos Skype for Business, por exemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e02f4-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="e02f4-130">Os usuários que ainda não começaram a usar Teams não notam nenhuma diferença no comportamento.</span><span class="sxs-lookup"><span data-stu-id="e02f4-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="e02f4-131">No entanto, a configuração dessa política no nível do locatário possibilita iniciar a atualização de usuários para o modo TeamsOnly e garante que os usuários atualizados ainda possam se comunicar com usuários não atualizados.</span><span class="sxs-lookup"><span data-stu-id="e02f4-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="e02f4-132">Depois de identificar seus usuários piloto, você pode atualiza-los para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e02f4-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="e02f4-133">Se eles estão no local, use Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e02f4-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="e02f4-134">Se eles estão online, basta atribuir o modo TeamsOnly usando Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e02f4-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="e02f4-135">Por padrão, todas as Skype for Business agendadas por esses usuários serão migradas para Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="e02f4-136">A seguir estão os comandos principais:</span><span class="sxs-lookup"><span data-stu-id="e02f4-136">Following are the key commands:</span></span>

1. <span data-ttu-id="e02f4-137">De definir o padrão de todo o locatário para o modo SfbWithTeamsCollab da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e02f4-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="e02f4-138">Atualize os usuários piloto para o TeamsOnly da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e02f4-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="e02f4-139">Para um usuário que está online:</span><span class="sxs-lookup"><span data-stu-id="e02f4-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="e02f4-140">Para um usuário que está no local:</span><span class="sxs-lookup"><span data-stu-id="e02f4-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="e02f4-141">Observações</span><span class="sxs-lookup"><span data-stu-id="e02f4-141">Notes</span></span>
 
- <span data-ttu-id="e02f4-142">Em vez de definir a política de todo o locatário como SfbWithTeamsCollab, você pode defini-la como SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="e02f4-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="e02f4-143">Isso faz com que todos os usuários agendem todas as novas reuniões Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="e02f4-144">Por padrão, Skype for Business reuniões são migradas para Teams ao atualizar para o modo TeamsOnly ou ao atribuir o modo SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="e02f4-144">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="e02f4-145">Em preparação para a próxima reforma do Skype for Business Online, a Microsoft simplificou a forma como as organizações se movem para Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-145">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="e02f4-146">Não é mais necessário especificar a opção para mover os usuários diretamente do local diretamente `-MoveToTeams` `Move-CsUser` para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e02f4-146">It is no longer required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises directly to TeamsOnly.</span></span> <span data-ttu-id="e02f4-147">Anteriormente, se essa opção não fosse especificada, os usuários tinham feito a transição da sua residência no Skype for Business Server local para o Skype for Business Online, e o modo permaneceu inalterado.</span><span class="sxs-lookup"><span data-stu-id="e02f4-147">Previously, if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="e02f4-148">Agora, ao mover um usuário do local para a nuvem com , os usuários são atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local são automaticamente convertidas em reuniões Teams, como se o , independentemente de a opção ser `Move-CsUser` `-MoveToTeams switch had been specified` realmente especificada.</span><span class="sxs-lookup"><span data-stu-id="e02f4-148">Now when moving a user from on-premises to the cloud with `Move-CsUser`, users are automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="e02f4-149">Esse comportamento está disponível em todas as versões do Skype For Business Server e do Lync Server 2013 (que nunca tiveram suporte para `-MoveToTeams` ).</span><span class="sxs-lookup"><span data-stu-id="e02f4-149">This behavior is available on all versions of Skype For Business Server and Lync Server 2013 (which never had support for `-MoveToTeams`).</span></span>

<span data-ttu-id="e02f4-150">O diagrama a seguir mostra as fases conceituais da atualização de recursos selecionados para uma organização sem uso anterior de Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-150">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="e02f4-151">A altura das barras representa o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e02f4-151">The height of the bars represents number of users.</span></span> <span data-ttu-id="e02f4-152">Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="e02f4-152">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="e02f4-153">Skype for Business se comunicam com usuários do TeamsOnly usando o Interop e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e02f4-153">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="e02f4-154">Os usuários no modo Ilhas devem ter certeza de executar ambos os clientes.</span><span class="sxs-lookup"><span data-stu-id="e02f4-154">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama mostrando a atualização de recursos selecionados sem uso prévio de Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="e02f4-156">Uma atualização de recursos selecionados para uma organização que já está usando Teams no modo Ilhas</span><span class="sxs-lookup"><span data-stu-id="e02f4-156">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="e02f4-157">Se alguns usuários em sua organização estão usando ativamente Teams no modo Ilhas, você provavelmente não deseja remover a funcionalidade dos usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="e02f4-157">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="e02f4-158">Portanto, uma etapa extra é necessária antes de alterar a política de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="e02f4-158">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="e02f4-159">A solução é "avô" desses usuários Teams existentes no modo Ilhas, antes de definir a política de todo o locatário como SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e02f4-159">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="e02f4-160">Depois de fazer isso, você pode prosseguir com a implantação como acima, no entanto, você terá dois grupos de usuários que estão mudando para o TeamsOnly: os usuários que estavam ativos no Teams estarão no modo Ilhas e os usuários restantes estarão no modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e02f4-160">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="e02f4-161">Você pode mover progressivamente esses usuários para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e02f4-161">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="e02f4-162">Encontre usuários que estão ativos Teams a seguir:</span><span class="sxs-lookup"><span data-stu-id="e02f4-162">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="e02f4-163">No Centro de administração do Microsoft 365, na navegação à esquerda, vá para Relatórios e, em seguida, Uso.</span><span class="sxs-lookup"><span data-stu-id="e02f4-163">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="e02f4-164">No menu suspenso "Selecionar um relatório", escolha Microsoft Teams e, em seguida, Atividade do Usuário.</span><span class="sxs-lookup"><span data-stu-id="e02f4-164">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="e02f4-165">Isso fornecerá uma tabela exportável de usuários que tenham sido ativos Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-165">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="e02f4-166">Clique em Exportar, abra Excel e filtre para mostrar somente os usuários que estão ativos Teams.</span><span class="sxs-lookup"><span data-stu-id="e02f4-166">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="e02f4-167">Para cada usuário Teams ativo encontrado na etapa 1, atribua-lhes o modo Ilhas no PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e02f4-167">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="e02f4-168">Isso permite que você vá para a próxima etapa e garante que você não altere a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="e02f4-168">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="e02f4-169">De definir a política de todo o locatário como SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="e02f4-169">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="e02f4-170">Atualize os usuários selecionados para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e02f4-170">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="e02f4-171">Você pode optar por atualizar usuários no modo Ilhas ou no modo SfbWithTeamsCollab, embora você queira priorizar a atualização dos usuários no modo Ilhas primeiro para minimizar o potencial de confusão que pode surgir quando os usuários estão no modo Ilhas.</span><span class="sxs-lookup"><span data-stu-id="e02f4-171">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="e02f4-172">Para usuários que estão no Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="e02f4-172">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="e02f4-173">Para usuários que estão Skype for Business Server local:</span><span class="sxs-lookup"><span data-stu-id="e02f4-173">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="e02f4-174">O diagrama a seguir mostra as fases conceituais de uma transição de recursos selecionados na qual há usuários ativos das Ilhas no início.</span><span class="sxs-lookup"><span data-stu-id="e02f4-174">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="e02f4-175">A altura das barras representa o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e02f4-175">The height of the bars represents the number of users.</span></span> <span data-ttu-id="e02f4-176">Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="e02f4-176">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="e02f4-177">Skype for Business os usuários se comunicam com usuários do TeamsOnly usando a interop e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e02f4-177">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama mostrando a atualização de recursos selecionados com usuários ativos no modo Ilhas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="e02f4-179">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="e02f4-179">Related links</span></span>

[<span data-ttu-id="e02f4-180">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e02f4-180">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e02f4-181">Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="e02f4-181">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e02f4-182">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="e02f4-182">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e02f4-183">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="e02f4-183">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e02f4-184">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e02f4-184">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e02f4-185">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="e02f4-185">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
