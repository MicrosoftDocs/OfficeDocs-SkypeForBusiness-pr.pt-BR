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
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097497"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="61645-103">Ferramentas para atualizar para o Teams &mdash; para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="61645-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="61645-104">Este artigo descreve ferramentas para atualizar para o Teams do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="61645-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="61645-105">Antes de iniciar a atualização, a Microsoft recomenda os seguintes artigos que descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="61645-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="61645-106">Coexistência do Teams e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="61645-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="61645-107">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="61645-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="61645-108">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="61645-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="61645-109">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="61645-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="61645-110">Qualquer método de atualização que você escolher, para usuários que já têm o Skype for Business Online, você gerencia a transição para o TeamsOnly usando [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="61645-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="61645-111">Para usuários com uma conta local no Skype for Business Server, você também usa para `Move-CsUser` [movê-los para a nuvem.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="61645-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="61645-112">Para obter mais informações sobre cada um dos modos, consulte [Modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="61645-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61645-113">Se você estiver usando o Conector do Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo do PowerShell do Teams e atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61645-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="61645-114">Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="61645-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="61645-115">Se você executar uma transição de recursos selecionados usando os modos skype for Business ou simplesmente atualizar para o modo TeamsOnly a partir da configuração padrão das Ilhas, TeamsUpgradePolicy é a principal ferramenta para usuários que já têm o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="61645-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="61645-116">Como qualquer outra política no Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário.</span><span class="sxs-lookup"><span data-stu-id="61645-116">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="61645-117">Você também pode definir a política como o padrão de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="61645-117">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="61645-118">Qualquer atribuição a um usuário tem precedência sobre a configuração padrão do locatário.</span><span class="sxs-lookup"><span data-stu-id="61645-118">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="61645-119">Você pode gerenciar a política no Console de Administração do Teams e no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61645-119">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="61645-120">Você também pode atribuir qualquer modo do TeamsUpgradePolicy, exceto o modo TeamsOnly, aos usuários que estão no Skype for Business no local.</span><span class="sxs-lookup"><span data-stu-id="61645-120">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="61645-121">**O modo TeamsOnly só** pode ser atribuído a um usuário que já está no Skype for Business Online .</span><span class="sxs-lookup"><span data-stu-id="61645-121">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="61645-122">Isso acontece porque a interopção com usuários do Skype for Business e federação e a funcionalidade do Sistema de Telefonia do Microsoft 365 só são possíveis se o usuário estiver no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="61645-122">This is because interop with Skype for Business users and federation and Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="61645-123">Além disso, não será possível atribuir o modo **TeamsOnly** como o padrão de todo o locatário se você tiver uma implantação local do Skype for Business (que é detectada pela presença de um registro DNS de descoberta lyncdiscover que aponta para um local diferente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="61645-123">In addition, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="61645-124">Os usuários com contas do Skype for Business no local devem ser movidos [online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business Online ou diretamente para o Teams) usando o Move-CsUser no toolset local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="61645-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="61645-125">Esses usuários podem ser movidos para o TeamsOnly em 1 ou 2 etapas:</span><span class="sxs-lookup"><span data-stu-id="61645-125">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="61645-126">1 etapa: Especifique a opção -MoveToTeams em Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="61645-126">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="61645-127">Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com CU8 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="61645-127">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="61645-128">2 etapas: depois de executar Move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="61645-128">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="61645-129">Ao contrário de outras políticas, não é possível criar novas instâncias do TeamsUpgradePolicy no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="61645-129">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="61645-130">Todas as instâncias existentes são criadas no serviço.</span><span class="sxs-lookup"><span data-stu-id="61645-130">All the existing instances are built into the service.</span></span>  <span data-ttu-id="61645-131">(Observe que o modo é uma propriedade dentro do TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns casos, mas não em todos os casos, o nome da instância da política é o mesmo que o modo.</span><span class="sxs-lookup"><span data-stu-id="61645-131">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="61645-132">Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" do TeamsUpgradePolicy a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="61645-132">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="61645-133">Para ver uma lista de todas as instâncias, você pode executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="61645-133">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="61645-134">Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="61645-134">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="61645-135">Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use Move-CsUser no toolset local:</span><span class="sxs-lookup"><span data-stu-id="61645-135">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="61645-136">Para alterar o modo para todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="61645-136">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="61645-137">Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="61645-137">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="61645-138">Você deve mover esses usuários individualmente para a nuvem usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="61645-138">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="61645-139">Usando notificações em clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="61645-139">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="61645-140">Os administradores têm a opção de fornecer notificações de usuário final no cliente skype for Business para informar aos usuários que eles serão atualizados em breve para o Teams, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="61645-140">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="61645-141">Por exemplo, uma semana antes de o administrador planeja atualizar um grupo de usuários para o modo TeamsOnly, talvez o administrador queira ativar essas notificações para esse grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="61645-141">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="61645-142">Essas notificações são habilitadas usando uma instância do TeamsUpgradePolicy com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="61645-142">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="61645-143">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="61645-143">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="61645-144">Para todos os modos diferentes do TeamsOnly, na verdade, há duas instâncias por modo, correspondendo aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="61645-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="61645-146">Se seus usuários estão no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="61645-146">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="61645-147">Se seus usuários estão no Skype for Business Server local, você precisará usar o toolset local e precisará do Skype for Business Server 2019 ou cu8 para Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="61645-147">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="61645-148">Para usuários que estão no Skype for Business Server no local, a propriedade mode da instância online do TeamsUpgradePolicy é agraciada, mas a propriedade NotifySfbUsers não é.</span><span class="sxs-lookup"><span data-stu-id="61645-148">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="61645-149">Se as notificações são desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="61645-149">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="61645-150">Na janela local do PowerShell, crie uma nova instância do TeamsUpgradePolicy com NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="61645-150">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="61645-151">Em seguida, usando a mesma janela local do PowerShell, atribua essa nova política aos usuários desejados:</span><span class="sxs-lookup"><span data-stu-id="61645-151">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="61645-152">Migração de reunião</span><span class="sxs-lookup"><span data-stu-id="61645-152">Meeting migration</span></span>

<span data-ttu-id="61645-153">Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões existentes do Skype for Business que organizaram serão convertidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="61645-153">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="61645-154">Opcionalmente, você pode desabilitar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário.</span><span class="sxs-lookup"><span data-stu-id="61645-154">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="61645-155">Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para funcionar com a conta de usuário online, mas se você não especificar -MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de convertidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="61645-155">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="61645-156">Ao atribuir o modo TeamsOnly no nível do locatário, a migração de reunião não é disparada para nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="61645-156">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="61645-157">Se você deseja atribuir o modo TeamsOnly ao nível do locatário e migrar reuniões, poderá usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando o Get-CsOnlineUser com quaisquer filtros necessários) e, em seguida, fazer um loop por cada um desses usuários para disparar a migração de reunião usando Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="61645-157">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="61645-158">Para obter detalhes, [consulte Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="61645-158">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="61645-159">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="61645-159">Related links</span></span>

[<span data-ttu-id="61645-160">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="61645-160">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="61645-161">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="61645-161">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="61645-162">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="61645-162">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="61645-163">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="61645-163">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="61645-164">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="61645-164">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="61645-165">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="61645-165">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)