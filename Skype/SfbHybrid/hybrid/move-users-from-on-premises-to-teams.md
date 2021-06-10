---
title: Mover usuários do Skype for Business Server 2019 para Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como migrar as configurações do usuário e mover os usuários para Teams.'
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856300"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="7f5d3-103">Migrar usuários de um ambiente local para o Teams</span><span class="sxs-lookup"><span data-stu-id="7f5d3-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="7f5d3-104">Quando um usuário é movido do local para o Teams Somente, a Skype for Business do usuário é movida do local para o online e o usuário recebe o TeamsUpgradePolicy com mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="7f5d3-105">Depois que um usuário é movido do local para o modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="7f5d3-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="7f5d3-106">Todas as chamadas de entrada e chats de outros usuários (sejam enviadas de Skype for Business ou Teams), serão enviadas no cliente de Teams do usuário.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="7f5d3-107">O usuário poderá interoperar com outros usuários que usam Skype for Business (online ou local).</span><span class="sxs-lookup"><span data-stu-id="7f5d3-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="7f5d3-108">O usuário poderá se comunicar com usuários em organizações federadas.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="7f5d3-109">Novas reuniões agendadas por esse usuário são Teams reuniões.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="7f5d3-110">O usuário ainda pode ingressar em qualquer Skype for Business reuniões.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="7f5d3-111">As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="7f5d3-112">Os contatos que existiam no local estão disponíveis Teams logo após o usuário fazer logor pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="7f5d3-113">Os usuários não podem iniciar chamadas ou chats Skype for Business, nem podem agendar novas reuniões no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="7f5d3-114">Se eles tentarem abrir o Skype for Business cliente, eles serão redirecionados para usar Teams como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="7f5d3-115">Se o Teams cliente não estiver instalado, eles serão direcionados para a versão web do Teams usando seu navegador.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="7f5d3-116">![Redirecionamento de mensagens de um usuário para Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="7f5d3-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="7f5d3-117">Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="7f5d3-118">Além disso, revise as diretrizes [de migração](/microsoftteams/migration-interop-guidance-for-teams-with-skype)e interoperabilidade para organizações que Teams em conjunto com Skype for Business .</span><span class="sxs-lookup"><span data-stu-id="7f5d3-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="7f5d3-119">O Armazenamento de Contatos Unificados deve ser desabilitado na conta SfB no momento para que o contato seja movido para Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>

> [!IMPORTANT]
><span data-ttu-id="7f5d3-120">Ao mover um usuário do local para a nuvem com o Move-CsUser, os usuários agora são atribuídos automaticamente ao modo TeamsOnly e suas reuniões no local são automaticamente convertidas em reuniões Teams, independentemente de a opção ser `-MoveToTeams` realmente especificada.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-120">When moving a user from on-premises to the cloud with Move-CsUser, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automatically converted to Teams meetings, regardless of whether the `-MoveToTeams` switch is actually specified.</span></span> <span data-ttu-id="7f5d3-121">(Isso inclui migrações do Lync Server 2013, que nunca tiveram a `-MoveToTeams` opção.)  Anteriormente, se essa opção não foi especificada, os usuários mudaram de Skype for Business Server local para o Skype for Business Online, e seu modo permaneceu inalterado.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-121">(This includes migrations from Lync Server 2013, which never had the `-MoveToTeams` switch.)  Previously if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="7f5d3-122">Isso foi alterado recentemente na preparação para a aposentadoria do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-122">This has recently been changed in preparation for retirement of Skype for Business Online.</span></span>


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="7f5d3-123">Mover um usuário diretamente do Skype for Business local para o Teams Only</span><span class="sxs-lookup"><span data-stu-id="7f5d3-123">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="7f5d3-124">As ferramentas de administração locais no Skype for Business Server e no Lync Server 2013 permitem que você mova os usuários do local para o modo TeamsOnly em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o Painel de Controle Skype for Business Server, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-124">The on-premises admin tools in Skype for Business Server and Lync Server 2013 enable you to move users from on premises to TeamsOnly mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span> <span data-ttu-id="7f5d3-125">Não é mais necessário especificar a opção e o comportamento para mover diretamente do local para o Teams Somente agora é automático, independentemente de qual versão do Skype for Business Server ou `-MoveToTeams` do Lync Server é usada.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-125">It is no longer required to specify the `-MoveToTeams` switch and the behavior to move directly from on premises to Teams Only is now automatic, regardless of which version of Skype for Business Server or Lync Server is used.</span></span> 

<span data-ttu-id="7f5d3-126">Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="7f5d3-126">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="7f5d3-127">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela local do Shell de Gerenciamento do Skype for Business Server com credenciais locais e usar o parâmetro para especificar credenciais para um Microsoft 365 com a função administrativa `-Credential` necessária.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 with the necessary administrative role.</span></span>

<span data-ttu-id="7f5d3-128">Além disso, você deve garantir que o usuário tenha sido concedido uma licença para Teams (além de Skype for Business Online).</span><span class="sxs-lookup"><span data-stu-id="7f5d3-128">In addition, you must ensure the user has been granted a license for Teams (in addition to Skype for Business Online).</span></span> <span data-ttu-id="7f5d3-129">Não desabilite a licença Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-129">Do not disable the Skype for Business Online license.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="7f5d3-130">Mover para Teams usando Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="7f5d3-130">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="7f5d3-131">Move-CsUser está disponível em uma janela local do Shell de Gerenciamento Skype for Business Server PowerShell ou em uma janela do Shell de Gerenciamento do Lync Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-131">Move-CsUser is available from an on-premises Skype for Business Server Management Shell PowerShell window or from a Lync Server Management Shell PowerShell window.</span></span> <span data-ttu-id="7f5d3-132">Para mover um usuário para o modo TeamsOnly usando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="7f5d3-132">To move a user to TeamsOnly mode using Move-CsUser:</span></span>
- <span data-ttu-id="7f5d3-133">Especifique o usuário para mover usando o `Identity` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-133">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="7f5d3-134">`-Target`Especifique o parâmetro com o valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="7f5d3-134">Specify the `-Target` parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="7f5d3-135">Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365), use o parâmetro para fornecer uma conta com permissões suficientes `-credential` Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-135">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365), use the `-credential` parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="7f5d3-136">Se a conta com permissões em Microsoft 365 não terminar em "onmicrosoft. <span> com", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="7f5d3-136">If the account with permissions in Microsoft 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="7f5d3-137">A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e supõe que a credencial Microsoft 365 é uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-137">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span> <span data-ttu-id="7f5d3-138">O comportamento é o mesmo se `-MoveToTeams` a opção é especificada ou não.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-138">The behavior is the same whether `-MoveToTeams` switch is specified or not.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="7f5d3-139">Como há circunstâncias diferentes que exigem parâmetros diferentes, o comando padrão para a maioria dos casos é:</span><span class="sxs-lookup"><span data-stu-id="7f5d3-139">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7f5d3-140">Mover para o Teams usando Skype for Business Server Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="7f5d3-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7f5d3-141">Abra o aplicativo Skype for Business Server Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="7f5d3-142">Na navegação à esquerda, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="7f5d3-143">Use **Localizar** para localizar os usuários que você gostaria de mover para Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="7f5d3-144">Selecione o(s) usuário(s)  e, em seguida, na lista suspenso Ação acima da lista, escolha **Mover** usuários selecionados para Teams ou Mover usuários selecionados para Skype for Business **Online**.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams** or **Move selected users to Skype for Business Online**.</span></span>   <span data-ttu-id="7f5d3-145">Uma das opções agora move os usuários diretamente para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-145">Either option now moves users directly to TeamsOnly.</span></span>
5. <span data-ttu-id="7f5d3-146">No assistente, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="7f5d3-147">Se solicitado, entre no Microsoft 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-147">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="7f5d3-148">Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="7f5d3-149">Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="7f5d3-150">Notifique Skype for Business usuários locais sobre a próxima movimentação para Teams</span><span class="sxs-lookup"><span data-stu-id="7f5d3-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="7f5d3-151">As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você notifique os usuários locais Skype for Business sobre sua próxima movimentação para Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="7f5d3-152">Quando você habilita essas notificações, os usuários verão uma notificação em seu cliente Skype for Business (Win32, Mac, Web e mobile), conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="7f5d3-153">Se os usuários clicarem no **botão Experimentar,** o Teams cliente será lançado se estiver instalado; caso contrário, os usuários serão navegados para a versão web do Teams em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="7f5d3-154">Por padrão, quando as notificações são habilitadas, os clientes do Win32 Skype for Business baixam silenciosamente o cliente Teams para que o cliente rico está disponível antes de mover o usuário para o modo TeamsOnly; no entanto, você também pode desabilitar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to TeamsOnly mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="7f5d3-155">As notificações são configuradas usando a versão local de , e o download silencioso para clientes Win32 é controlado por meio do `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="7f5d3-156">Alguns servidores podem precisar reiniciar para que isso funcione Skype for Business 2015 com CU8.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Notificação da próxima movimentação para Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="7f5d3-158">Para notificar os usuários locais de que eles serão atualizados em breve para Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="7f5d3-159">Em seguida, atribua essa política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou definindo a política no site, pool ou nível global.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="7f5d3-160">Os cmdlets a seguir criam e concedem uma política no nível do usuário:</span><span class="sxs-lookup"><span data-stu-id="7f5d3-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="7f5d3-161">O download automático do Teams por meio do cliente Skype for Business Win32 é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="7f5d3-162">Você cria essa configuração em um nível global, de site e de pool.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="7f5d3-163">Por exemplo, o comando a seguir cria a configuração do site Redmond1:</span><span class="sxs-lookup"><span data-stu-id="7f5d3-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="7f5d3-164">Por padrão, o valor de DownloadTeams é True; no entanto, ele só *será* honrado se NotifySfbUser = True para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="7f5d3-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f5d3-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="7f5d3-165">See also</span></span>

[<span data-ttu-id="7f5d3-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="7f5d3-166">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="7f5d3-167">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="7f5d3-167">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="7f5d3-168">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7f5d3-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="7f5d3-169">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7f5d3-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
