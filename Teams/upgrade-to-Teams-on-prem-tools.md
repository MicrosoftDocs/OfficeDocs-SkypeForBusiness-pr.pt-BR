---
title: Ferramentas para atualizar para o Teams a partir de uma implantação local do Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Ferramentas para atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61dc34d56ebb10dc7319d855bbd0d98184f1e54a
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347842"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="5963f-103">Ferramentas para atualizar para o Teams &mdash; para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="5963f-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="5963f-104">Este artigo descreve ferramentas para atualizar para o Teams.</span><span class="sxs-lookup"><span data-stu-id="5963f-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="5963f-105">Este artigo é o terceiro de vários que descrevem conceitos de atualização e implementação para administradores de IT.</span><span class="sxs-lookup"><span data-stu-id="5963f-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="5963f-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="5963f-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="5963f-107">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="5963f-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="5963f-108">**Ferramentas para gerenciar sua atualização**   (Este artigo)</span><span class="sxs-lookup"><span data-stu-id="5963f-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="5963f-109">Considerações adicionais para organizações com o Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="5963f-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="5963f-110">Implementar sua atualização</span><span class="sxs-lookup"><span data-stu-id="5963f-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="5963f-111">Considerações sobre a PSTN (Rede Telefônica Pública Comucionária)</span><span class="sxs-lookup"><span data-stu-id="5963f-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="5963f-112">Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="5963f-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="5963f-113">Coexistência do Teams e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5963f-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="5963f-114">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="5963f-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="5963f-115">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="5963f-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="5963f-116">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="5963f-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="5963f-117">Qualquer método de atualização que você escolher, para usuários que já têm o Skype for Business Online, você gerencia a transição para o TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="5963f-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="5963f-118">Para usuários com uma conta local no Skype for Business Server, você também usa para `Move-CsUser` [movê-los para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="5963f-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="5963f-119">Para obter mais informações sobre cada um dos modos, consulte [Modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="5963f-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5963f-120">Se você estiver usando o Conector do Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo do PowerShell do Teams e atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5963f-120">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="5963f-121">Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="5963f-121">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="5963f-122">Se você executar uma transição de recursos selecionados usando os modos do Skype for Business ou simplesmente atualizar para o modo TeamsOnly da configuração padrão das Ilhas, o TeamsUpgradePolicy é a principal ferramenta para usuários que já têm o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="5963f-122">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="5963f-123">Como qualquer outra política no Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário.</span><span class="sxs-lookup"><span data-stu-id="5963f-123">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="5963f-124">Você também pode definir a política como o padrão de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="5963f-124">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="5963f-125">Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.</span><span class="sxs-lookup"><span data-stu-id="5963f-125">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="5963f-126">Você pode gerenciar a política no Console de Administração do Teams e no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5963f-126">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="5963f-127">Você também pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários que estão no Skype for Business no local.</span><span class="sxs-lookup"><span data-stu-id="5963f-127">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="5963f-128">**O modo TeamsOnly só** pode ser atribuído a um usuário que já está no Skype for Business Online .</span><span class="sxs-lookup"><span data-stu-id="5963f-128">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="5963f-129">Isso acontece porque a interopção com usuários e federação do Skype for Business, bem como a funcionalidade do Sistema de Telefonia do Microsoft 365 só é possível se o usuário estiver no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="5963f-129">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="5963f-130">Além disso, não será possível atribuir o modo **TeamsOnly** como o padrão de todo o locatário se você tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5963f-130">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="5963f-131">Os usuários com contas do Skype for Business no local devem ser movidos [online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business Online ou diretamente para o Teams) usando o Move-CsUser no toolset local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5963f-131">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="5963f-132">Esses usuários podem ser movidos para o TeamsOnly em 1 ou 2 etapas:</span><span class="sxs-lookup"><span data-stu-id="5963f-132">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="5963f-133">1 etapa: Especifique a opção -MoveToTeams em Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="5963f-133">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="5963f-134">Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com CU8 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="5963f-134">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="5963f-135">2 etapas: depois de executar Move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="5963f-135">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="5963f-136">Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy no Microsoft 365 ou No Office 365.</span><span class="sxs-lookup"><span data-stu-id="5963f-136">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5963f-137">Todas as instâncias existentes são criadas no serviço.</span><span class="sxs-lookup"><span data-stu-id="5963f-137">All the existing instances are built into the service.</span></span>  <span data-ttu-id="5963f-138">(Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos os casos, o nome da instância da política é o mesmo do modo.</span><span class="sxs-lookup"><span data-stu-id="5963f-138">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="5963f-139">Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="5963f-139">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="5963f-140">Para ver uma lista de todas as instâncias, você pode executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5963f-140">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="5963f-141">Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="5963f-141">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="5963f-142">Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use Move-CsUser no toolset local:</span><span class="sxs-lookup"><span data-stu-id="5963f-142">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="5963f-143">Para alterar o modo para todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5963f-143">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="5963f-144">Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="5963f-144">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="5963f-145">Você deve mover esses usuários individualmente para a nuvem usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="5963f-145">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="5963f-146">Usando notificações em clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5963f-146">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="5963f-147">Os administradores têm a opção de fornecer notificações de usuário final no cliente skype for Business para informar aos usuários que eles serão atualizados em breve para o Teams, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="5963f-147">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="5963f-148">Por exemplo, uma semana antes de o administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, talvez o administrador queira ativar essas notificações para esse grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="5963f-148">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="5963f-149">Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="5963f-149">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="5963f-150">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="5963f-150">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="5963f-151">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="5963f-151">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="5963f-153">Se seus usuários estão no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="5963f-153">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="5963f-154">Se seus usuários estão no Skype for Business Server local, você precisará usar o toolset local e precisará do Skype for Business Server 2019 ou cu8 para Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5963f-154">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="5963f-155">Para usuários instalados no Skype for Business Server no local, a propriedade mode da instância online do TeamsUpgradePolicy é agraciada, mas a propriedade NotifySfbUsers não é.</span><span class="sxs-lookup"><span data-stu-id="5963f-155">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="5963f-156">Se as notificações são desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="5963f-156">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="5963f-157">Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="5963f-157">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="5963f-158">Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:</span><span class="sxs-lookup"><span data-stu-id="5963f-158">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="5963f-159">Migração de reunião</span><span class="sxs-lookup"><span data-stu-id="5963f-159">Meeting migration</span></span>

<span data-ttu-id="5963f-160">Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões existentes do Skype for Business que organizaram serão convertidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="5963f-160">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="5963f-161">Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário.</span><span class="sxs-lookup"><span data-stu-id="5963f-161">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="5963f-162">Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de convertidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="5963f-162">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="5963f-163">Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="5963f-163">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="5963f-164">Se quiser atribuir o modo TeamsOnly ao nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer um loop por cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="5963f-164">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="5963f-165">Para obter detalhes, [consulte Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="5963f-165">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="5963f-166">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="5963f-166">Related links</span></span>

[<span data-ttu-id="5963f-167">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5963f-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="5963f-168">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="5963f-168">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="5963f-169">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="5963f-169">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="5963f-170">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="5963f-170">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="5963f-171">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="5963f-171">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="5963f-172">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="5963f-172">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

