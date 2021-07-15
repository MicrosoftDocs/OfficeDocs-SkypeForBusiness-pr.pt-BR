---
title: Ferramentas para atualizar para Teams de uma implantação Skype for Business local
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Ferramentas para atualização de Skype for Business para Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437628"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="6c707-103">Ferramentas para atualizar para Teams &mdash; para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="6c707-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="6c707-104">Este artigo descreve ferramentas para atualizar para Teams de Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6c707-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="6c707-105">Antes de iniciar a atualização, a Microsoft recomenda os seguintes artigos que descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="6c707-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="6c707-106">Coexistência de Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6c707-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="6c707-107">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="6c707-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="6c707-108">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="6c707-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="6c707-109">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="6c707-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="6c707-110">Qualquer método de atualização que você escolher, para usuários que já Skype for Business Online, você gerencia a transição para o TeamsOnly usando [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="6c707-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="6c707-111">Para usuários com uma conta local no Skype for Business Server, você também usa `Move-CsUser` para movê-los [para a nuvem](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span><span class="sxs-lookup"><span data-stu-id="6c707-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="6c707-112">Para obter mais informações sobre cada um dos modos, consulte [Modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="6c707-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6c707-113">Se você estiver usando o Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo Teams PowerShell e atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c707-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="6c707-114">Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module for](teams-powershell-move-from-sfbo.md) more information.</span><span class="sxs-lookup"><span data-stu-id="6c707-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="6c707-115">Se você executar uma transição de recursos selecionados usando Skype for Business modos ou simplesmente atualizar para o modo TeamsOnly a partir da configuração padrão das Ilhas, TeamsUpgradePolicy é a ferramenta principal. Como qualquer outra política Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário.</span><span class="sxs-lookup"><span data-stu-id="6c707-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="6c707-116">Você também pode definir a política como o padrão de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="6c707-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="6c707-117">Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.</span><span class="sxs-lookup"><span data-stu-id="6c707-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="6c707-118">Você pode gerenciar a política no console Teams Admin e no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c707-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="6c707-119">Você pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários que estão Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="6c707-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="6c707-120">Por outro lado, os usuários que estão na nuvem só podem ser atribuídos ao modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="6c707-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="6c707-121">O modo **TeamsOnly** só pode ser atribuído a um usuário que já está na nuvem porque a interop e a federação com usuários do Skype for Business, bem como a funcionalidade Microsoft 365 Sistema de Telefonia, só serão possíveis se o usuário estiver em casa no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="6c707-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="6c707-122">Além disso, não será possível atribuir o modo **TeamsOnly** como o padrão de todo o locatário se você tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c707-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="6c707-123">Para obter detalhes, [consulte Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="6c707-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="6c707-124">Os usuários com Skype for Business contas no local devem ser [movidos](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) online para o modo Somente Teams usando Move-CsUser no Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="6c707-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="6c707-125">Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy em Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="6c707-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6c707-126">Todas as instâncias existentes são criadas no serviço.</span><span class="sxs-lookup"><span data-stu-id="6c707-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="6c707-127">(Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos os casos, o nome da instância da política é o mesmo que o modo.</span><span class="sxs-lookup"><span data-stu-id="6c707-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="6c707-128">Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="6c707-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="6c707-129">Para ver uma lista de todas as instâncias, você pode executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6c707-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="6c707-130">Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="6c707-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="6c707-131">Para atualizar um usuário local Skype for Business para o modo TeamsOnly, use Move-CsUser no toolset local:</span><span class="sxs-lookup"><span data-stu-id="6c707-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="6c707-132">Para alterar o modo para todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6c707-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="6c707-133">Se você tiver usuários com Skype for Business contas locais, não poderá atribuir o modo TeamsOnly no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="6c707-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="6c707-134">Você deve mover esses usuários individualmente para Teams modo Somente usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="6c707-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="6c707-135">Usando notificações em Skype for Business clientes</span><span class="sxs-lookup"><span data-stu-id="6c707-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="6c707-136">Os administradores têm a opção de fornecer notificações de usuário final no cliente Skype for Business para informar aos usuários que eles serão atualizados em breve para Teams, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c707-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="6c707-137">Por exemplo, uma semana antes de o administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, talvez o administrador queira ativar essas notificações para esse grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="6c707-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="6c707-138">Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="6c707-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="6c707-139">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="6c707-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="6c707-140">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="6c707-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="6c707-142">Se os usuários estão em casa no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="6c707-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="6c707-143">Se os usuários estão Skype for Business Server no local, você precisará usar o toolset local e você precisará do Skype for Business Server 2019 ou cu8 para Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6c707-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="6c707-144">Para usuários que estão Skype for Business Server local, a propriedade mode da instância online do TeamsUpgradePolicy é agraciada, mas a propriedade NotifySfbUsers não é.</span><span class="sxs-lookup"><span data-stu-id="6c707-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="6c707-145">Se as notificações são desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="6c707-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="6c707-146">Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="6c707-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="6c707-147">Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:</span><span class="sxs-lookup"><span data-stu-id="6c707-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="6c707-148">Migração de reunião</span><span class="sxs-lookup"><span data-stu-id="6c707-148">Meeting migration</span></span>

<span data-ttu-id="6c707-149">Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões Skype for Business existentes que organizaram serão convertidas em Teams.</span><span class="sxs-lookup"><span data-stu-id="6c707-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="6c707-150">Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário.</span><span class="sxs-lookup"><span data-stu-id="6c707-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="6c707-151">Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões Skype for Business, em vez de convertidas em Teams.</span><span class="sxs-lookup"><span data-stu-id="6c707-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="6c707-152">Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="6c707-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="6c707-153">Se você deseja atribuir o modo TeamsOnly ao nível do locatário e migrar reuniões, poderá usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer um loop por cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="6c707-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="6c707-154">Para obter detalhes, [consulte Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="6c707-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="6c707-155">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="6c707-155">Related links</span></span>

[<span data-ttu-id="6c707-156">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="6c707-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="6c707-157">Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="6c707-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="6c707-158">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="6c707-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="6c707-159">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="6c707-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="6c707-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="6c707-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="6c707-161">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="6c707-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
