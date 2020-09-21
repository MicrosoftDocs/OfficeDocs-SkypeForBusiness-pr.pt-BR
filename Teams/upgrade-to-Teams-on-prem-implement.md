---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955898"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="e4482-103">Implementar a atualização do Skype for Business para o Teams &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="e4482-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="e4482-104">Este artigo descreve como implementar a atualização.</span><span class="sxs-lookup"><span data-stu-id="e4482-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="e4482-105">Este artigo é o quinto de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="e4482-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="e4482-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e4482-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="e4482-107">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="e4482-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="e4482-108">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="e4482-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="e4482-109">Considerações adicionais sobre organizações com o Skype for Business no local</span><span class="sxs-lookup"><span data-stu-id="e4482-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="e4482-110">**Implementar a atualização** (este artigo)</span><span class="sxs-lookup"><span data-stu-id="e4482-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="e4482-111">Considerações sobre PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="e4482-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="e4482-112">Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="e4482-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e4482-113">Coexistência de Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e4482-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="e4482-114">Modos de coexistência-referência</span><span class="sxs-lookup"><span data-stu-id="e4482-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e4482-115">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="e4482-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="e4482-116">Opções de atualização</span><span class="sxs-lookup"><span data-stu-id="e4482-116">Upgrade options</span></span>

<span data-ttu-id="e4482-117">Esta seção descreve como implementar a atualização usando uma das seguintes opções de atualização:</span><span class="sxs-lookup"><span data-stu-id="e4482-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="e4482-118">Atualização de recursos sobrepostos (usando o modo de ilhas)</span><span class="sxs-lookup"><span data-stu-id="e4482-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="e4482-119">Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams</span><span class="sxs-lookup"><span data-stu-id="e4482-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="e4482-120">Uma atualização de recursos de seleção para uma organização que já está usando equipes no modo de ilhas</span><span class="sxs-lookup"><span data-stu-id="e4482-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="e4482-121">Se precisar de mais informações sobre as opções, verifique se você já leu os [métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e4482-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="e4482-122">Atualização de recursos sobrepostos (usando o modo de ilhas)</span><span class="sxs-lookup"><span data-stu-id="e4482-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="e4482-123">Para a opção de atualização de recursos sobrepostos:</span><span class="sxs-lookup"><span data-stu-id="e4482-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="e4482-124">Considere esta opção se você pode fazer uma atualização rápida para a sua organização geral.</span><span class="sxs-lookup"><span data-stu-id="e4482-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="e4482-125">Como há potencial risco de confusão para os usuários finais executarem ambos os clientes, é melhor minimizar o período de tempo durante o qual os usuários devem executar ambos os clientes.</span><span class="sxs-lookup"><span data-stu-id="e4482-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="e4482-126">Você deve garantir que os usuários saibam que executar os dois clientes.</span><span class="sxs-lookup"><span data-stu-id="e4482-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="e4482-127">Essa opção é o modelo de caixa de saída e não exige ação do administrador para começar a usar o Microsoft Teams, exceto para atribuir a licença do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4482-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="e4482-128">Se seus usuários já têm o Skype for Business Online, você pode já estar nesse modelo.</span><span class="sxs-lookup"><span data-stu-id="e4482-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="e4482-129">Pode ser difícil sair do modo de recursos sobrepostos e mover para TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e4482-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="e4482-130">Como os usuários atualizados só se comunicam via Teams, qualquer outro usuário na organização que se comunique com esse usuário deve estar usando o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="e4482-131">Se você tiver usuários que não começaram a usar o Teams, eles serão expostos a mensagens ausentes.</span><span class="sxs-lookup"><span data-stu-id="e4482-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="e4482-132">Além disso, eles não verão os usuários do TeamsOnly online no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e4482-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="e4482-133">Algumas organizações optam por fazer uma atualização em todo o locatário usando a política global do locatário para evitar isso, no entanto, isso requer o planejamento antecipado, bem como aguardar até que todos os usuários estejam prontos para serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="e4482-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="e4482-134">Uma atualização de recursos selecionados para uma organização que ainda não começou a usar o Teams</span><span class="sxs-lookup"><span data-stu-id="e4482-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="e4482-135">Se a sua organização ainda não tem usuários ativos no Teams, a primeira etapa é definir a política padrão de todo o locatário do TeamsUpgradePolicy para um dos modos do Skype for Business, por exemplo, SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e4482-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="e4482-136">Os usuários que ainda não começaram a usar o Teams não notarão diferença no comportamento.</span><span class="sxs-lookup"><span data-stu-id="e4482-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="e4482-137">No entanto, definir essa política no nível do locatário torna possível iniciar a atualização dos usuários para o modo TeamsOnly e garante que os usuários atualizados ainda possam se comunicar com usuários não atualizados.</span><span class="sxs-lookup"><span data-stu-id="e4482-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="e4482-138">Depois de identificar os usuários piloto, você pode atualizá-los para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e4482-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="e4482-139">Se eles estiverem locais, use move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e4482-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="e4482-140">Se estiverem online, basta atribuí-los ao modo TeamsOnly usando Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e4482-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="e4482-141">Por padrão, todas as reuniões do Skype for Business agendadas por esses usuários serão migradas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="e4482-142">Veja a seguir os comandos principais:</span><span class="sxs-lookup"><span data-stu-id="e4482-142">Following are the key commands:</span></span>

1. <span data-ttu-id="e4482-143">Defina o padrão do locatário-Wide para mode SfbWithTeamsCollab da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e4482-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="e4482-144">Atualize os usuários piloto para o TeamsOnly da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e4482-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="e4482-145">Para um usuário que está online:</span><span class="sxs-lookup"><span data-stu-id="e4482-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="e4482-146">Para um usuário local:</span><span class="sxs-lookup"><span data-stu-id="e4482-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="e4482-147">Observações</span><span class="sxs-lookup"><span data-stu-id="e4482-147">Notes</span></span>
 
- <span data-ttu-id="e4482-148">Em vez de definir a política de todo o locatário como SfbWithTeamsCollab, você pode defini-la como SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="e4482-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="e4482-149">Isso faz com que todos os usuários agendem todas as novas reuniões no Teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="e4482-150">`Move-CsUser` é um cmdlet nas ferramentas locais.</span><span class="sxs-lookup"><span data-stu-id="e4482-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="e4482-151">O `MoveToTeams` switch requer o Skype for Business server 2019 ou o Skype for Business server 2015 com o CU8 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="e4482-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="e4482-152">Se estiver usando uma versão anterior, você pode primeiro mover o usuário para o Skype for Business Online e, em seguida, conceder o modo TeamsOnly a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="e4482-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="e4482-153">Por padrão, as reuniões do Skype for Business são migradas para o Microsoft Teams durante a atualização para o modo TeamsOnly ou ao atribuir o modo de SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="e4482-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="e4482-154">O diagrama a seguir mostra a atualização das fases conceituais de recursos selecionados para uma organização sem o uso anterior do teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="e4482-155">A altura das barras representa o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e4482-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="e4482-156">Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="e4482-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="e4482-157">Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e4482-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="e4482-158">Os usuários no modo de ilhas devem ter certeza de que devem executar os dois clientes.</span><span class="sxs-lookup"><span data-stu-id="e4482-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagrama mostrando a atualização de recursos de seleção sem uso anterior do teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="e4482-160">Uma atualização de recursos de seleção para uma organização que já está usando equipes no modo de ilhas</span><span class="sxs-lookup"><span data-stu-id="e4482-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="e4482-161">Se alguns usuários da sua organização estiverem usando ativamente o Microsoft Teams no modo de ilhas, provavelmente não deseja remover a funcionalidade de usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="e4482-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="e4482-162">Portanto, uma etapa adicional é necessária antes de alterar a política de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="e4482-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="e4482-163">A solução é "avô" esses usuários existentes do Microsoft Teams no modo de ilhas, antes de definir a política de todo o locatário como SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e4482-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="e4482-164">Depois de fazer isso, você poderá prosseguir com a implantação da maneira acima, no entanto, terá dois grupos de usuários que estão indo para o TeamsOnly: os usuários que estavam ativos no Teams estarão no modo de ilhas e os usuários restantes estarão no modo SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="e4482-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="e4482-165">Você pode mover progressivamente esses usuários para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e4482-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="e4482-166">Encontre os usuários ativos no Teams da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e4482-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="e4482-167">No centro de administração do Microsoft 365, na navegação à esquerda, vá para relatórios e use o uso.</span><span class="sxs-lookup"><span data-stu-id="e4482-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="e4482-168">Na lista suspensa "selecionar um relatório", escolha Microsoft Teams e, em seguida, atividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4482-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="e4482-169">Isso fornecerá uma tabela exportável de usuários que já estão ativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="e4482-170">Clique em exportar, abrir Excel e filtrar para mostrar somente os usuários que estão ativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="e4482-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="e4482-171">Para cada usuário do Active Teams encontrado na etapa 1, atribua o modo de ilhas no PowerShell no PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e4482-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="e4482-172">Isso permite que você vá para a próxima etapa e assegure-se de que não altere a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4482-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="e4482-173">Defina a política de todo o locatário como SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="e4482-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="e4482-174">Atualizar os usuários selecionados para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e4482-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="e4482-175">Você pode optar por atualizar os usuários no modo de ilhas ou no modo SfbWithTeamsCollab, embora você queira priorizar a atualização dos usuários no modo ilhas primeiro para minimizar o potencial de confusão que podem surgir quando os usuários estiverem no modo de ilhas.</span><span class="sxs-lookup"><span data-stu-id="e4482-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="e4482-176">Para usuários hospedados no Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="e4482-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="e4482-177">Para os usuários hospedados no Skype for Business Server no local:</span><span class="sxs-lookup"><span data-stu-id="e4482-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="e4482-178">O diagrama a seguir mostra as fases conceituais de uma transição de recursos selecionados em que há usuários de ilhas ativas no início.</span><span class="sxs-lookup"><span data-stu-id="e4482-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="e4482-179">A altura das barras representa o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="e4482-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="e4482-180">Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="e4482-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="e4482-181">Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e4482-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagrama mostrando a atualização de recursos de seleção com usuários ativos no modo de ilhas](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="e4482-183">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="e4482-183">Related links</span></span>

[<span data-ttu-id="e4482-184">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e4482-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e4482-185">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="e4482-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e4482-186">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="e4482-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e4482-187">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="e4482-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e4482-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e4482-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e4482-189">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="e4482-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

