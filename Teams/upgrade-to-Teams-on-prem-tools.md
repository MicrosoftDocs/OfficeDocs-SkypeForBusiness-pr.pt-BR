---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualize o Skype for Business para o Teams – ferramentas para atualização
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533568"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="10a79-103">Ferramentas para a atualização do teams &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="10a79-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="10a79-104">Este artigo descreve as ferramentas para a atualização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10a79-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="10a79-105">Este artigo é o terceiro de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="10a79-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="10a79-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="10a79-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="10a79-107">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="10a79-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="10a79-108">**Ferramentas para gerenciar a atualização**   (este artigo)</span><span class="sxs-lookup"><span data-stu-id="10a79-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="10a79-109">Considerações adicionais sobre organizações com o Skype for Business no local</span><span class="sxs-lookup"><span data-stu-id="10a79-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="10a79-110">Implementar sua atualização</span><span class="sxs-lookup"><span data-stu-id="10a79-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="10a79-111">Considerações sobre PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="10a79-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="10a79-112">Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="10a79-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="10a79-113">Coexistência de Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="10a79-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="10a79-114">Modos de coexistência-referência</span><span class="sxs-lookup"><span data-stu-id="10a79-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="10a79-115">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="10a79-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="10a79-116">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="10a79-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="10a79-117">Seja qual for o método de atualização que você escolher, para os usuários que já têm o Skype for Business Online, você gerencia a transição para TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário.</span><span class="sxs-lookup"><span data-stu-id="10a79-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="10a79-118">Para usuários com uma conta local no Skype for Business Server, você também pode usar `Move-CsUser` para [movê-los para a nuvem](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span><span class="sxs-lookup"><span data-stu-id="10a79-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="10a79-119">Para obter mais informações sobre cada um dos modos, consulte [modos de coexistência](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="10a79-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="10a79-120">Não importa se você executa uma transição de recursos selecionados usando os modos Skype for Business ou simplesmente atualiza para o modo TeamsOnly da configuração de ilhas padrão, TeamsUpgradePolicy é a principal ferramenta para usuários que já têm o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="10a79-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="10a79-121">Como qualquer outra política do Teams, você pode atribuir TeamsUpgradePolicy diretamente a um usuário.</span><span class="sxs-lookup"><span data-stu-id="10a79-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="10a79-122">Você também pode definir a política como o padrão de todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="10a79-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="10a79-123">Qualquer atribuição para um usuário tem precedência sobre a configuração padrão do locatário.</span><span class="sxs-lookup"><span data-stu-id="10a79-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="10a79-124">Você pode gerenciar a política no console de administração do Teams e no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10a79-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="10a79-125">Você também pode atribuir qualquer modo de TeamsUpgradePolicy, exceto para o modo TeamsOnly, aos usuários hospedados no Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="10a79-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="10a79-126">**O modo TeamsOnly só pode ser atribuído a um usuário que já esteja hospedado no Skype for Business online**.</span><span class="sxs-lookup"><span data-stu-id="10a79-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="10a79-127">Isso ocorre porque a interoperabilidade com os usuários do Skype for Business e a Federação, bem como a funcionalidade do sistema telefônico do Microsoft 365 só é possível se o usuário estiver hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="10a79-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="10a79-128">Além disso, **você não pode atribuir o modo TeamsOnly como o padrão geral do locatário se tiver uma implantação do Skype for Business local** (que é detectada pela presença de um registro DNS lyncdiscover que aponta para o local diferente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="10a79-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="10a79-129">Os usuários com contas do Skype for Business hospedadas no local [devem ser movidos online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business online ou direto para o Microsoft Teams) usando Move-CsUser no conjunto de ferramentas local do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="10a79-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="10a79-130">Esses usuários podem ser movidos para o TeamsOnly nas etapas 1 ou 2:</span><span class="sxs-lookup"><span data-stu-id="10a79-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="10a79-131">1 etapa: Especifique a opção-MoveToTeams em move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="10a79-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="10a79-132">Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com o CU8 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="10a79-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="10a79-133">2 etapas: após executar move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="10a79-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="10a79-134">Ao contrário de outras políticas, não é possível criar novas instâncias de TeamsUpgradePolicy no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="10a79-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="10a79-135">Todas as instâncias existentes são incorporadas ao serviço.</span><span class="sxs-lookup"><span data-stu-id="10a79-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="10a79-136">(Observe que Mode é uma propriedade dentro de TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns--mas não em todos os casos, o nome da instância da política é o mesmo que o modo.</span><span class="sxs-lookup"><span data-stu-id="10a79-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="10a79-137">Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" de TeamsUpgradePolicy a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="10a79-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="10a79-138">Para ver uma lista de todos os casos, você pode executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10a79-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="10a79-139">Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="10a79-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="10a79-140">Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use Move-CsUser no conjunto de ferramentas local:</span><span class="sxs-lookup"><span data-stu-id="10a79-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="10a79-141">Para alterar o modo de todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="10a79-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="10a79-142">Se você tiver usuários com contas do Skype for Business locais, não será possível atribuir o modo TeamsOnly no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="10a79-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="10a79-143">Você deve mover esses usuários individualmente para a nuvem usando move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="10a79-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="10a79-144">Usar notificações nos clientes Skype for Business</span><span class="sxs-lookup"><span data-stu-id="10a79-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="10a79-145">Os administradores têm a opção de fornecer notificações de usuário final no cliente Skype for Business para informar aos usuários que eles logo serão atualizados para o Microsoft Teams, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="10a79-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="10a79-146">Por exemplo, uma semana antes de o administrador planejar a atualização de um grupo de usuários para o modo TeamsOnly, o administrador pode querer ativar essas notificações para esse grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="10a79-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="10a79-147">Essas notificações são habilitadas usando uma instância de TeamsUpgradePolicy com NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="10a79-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="10a79-148">Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="10a79-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="10a79-149">Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="10a79-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="10a79-151">Se seus usuários estiverem hospedados no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers = verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="10a79-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="10a79-152">Se seus usuários estiverem hospedados no Skype for Business Server no local, você precisará usar o conjunto de ferramentas local e será necessário o Skype for Business Server 2019 ou o CU8 para o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="10a79-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="10a79-153">Para os usuários hospedados no Skype for Business Server no local, a propriedade Mode da instância online do TeamsUpgradePolicy é respeitada, mas a propriedade NotifySfbUsers não é.</span><span class="sxs-lookup"><span data-stu-id="10a79-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="10a79-154">Se as notificações forem desejadas, você deve criar uma instância local do TeamsUpgradePolicy para controlar o comportamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="10a79-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="10a79-155">Na janela do PowerShell local, crie uma nova instância de TeamsUpgradePolicy com NotifySfbUsers = verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="10a79-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="10a79-156">Em seguida, usando a mesma janela do PowerShell local, atribua essa nova política aos usuários desejados:</span><span class="sxs-lookup"><span data-stu-id="10a79-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="10a79-157">Migração de reunião</span><span class="sxs-lookup"><span data-stu-id="10a79-157">Meeting migration</span></span>

<span data-ttu-id="10a79-158">Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões do Skype for Business existentes que eles organizadas serão convertidas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10a79-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="10a79-159">Opcionalmente, você pode desativar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário.</span><span class="sxs-lookup"><span data-stu-id="10a79-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="10a79-160">Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para que funcionem com a conta de usuário online, mas se você não especificar-MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de serem convertidas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10a79-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="10a79-161">Ao atribuir o modo TeamsOnly no nível do locatário, a migração da reunião não é disparada para nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="10a79-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="10a79-162">Se quiser atribuir o modo TeamsOnly no nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usando Get-CsOnlineUser com os filtros necessários) e executar um loop por cada um desses usuários para disparar a migração de reunião usando o Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="10a79-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="10a79-163">Para obter detalhes, consulte [usando o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="10a79-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="10a79-164">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="10a79-164">Related links</span></span>

[<span data-ttu-id="10a79-165">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="10a79-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="10a79-166">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="10a79-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="10a79-167">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="10a79-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="10a79-168">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="10a79-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="10a79-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="10a79-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="10a79-170">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="10a79-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

