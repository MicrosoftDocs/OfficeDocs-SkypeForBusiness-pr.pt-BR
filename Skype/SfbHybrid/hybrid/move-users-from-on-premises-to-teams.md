---
title: Mover usuários do Skype for Business Server 2019 para o Teams
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
description: 'Resumo: saiba como migrar as configurações do usuário e mover os usuários para o Teams.'
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836978"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="ff6c3-103">Migrar usuários de um ambiente local para o Teams</span><span class="sxs-lookup"><span data-stu-id="ff6c3-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="ff6c3-104">Quando um usuário é movido do local apenas para o Teams, a casa do Skype for Business do usuário é movida do local para o online e o usuário recebe o TeamsUpgradePolicy com mode=TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="ff6c3-105">Depois que um usuário é movido do local para o modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="ff6c3-106">Todas as chamadas de entrada e chats de outros usuários (sejam enviadas do Skype for Business ou do Teams), serão recebidas no cliente do Teams do usuário.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="ff6c3-107">O usuário poderá interoperar com outros usuários que usam o Skype for Business (online ou local).</span><span class="sxs-lookup"><span data-stu-id="ff6c3-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="ff6c3-108">O usuário poderá se comunicar com usuários em organizações federadas.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="ff6c3-109">Novas reuniões agendadas por esse usuário são reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="ff6c3-110">O usuário ainda pode ingressar em qualquer reunião do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="ff6c3-111">As reuniões pré-existentes do usuário agendadas para o futuro serão migradas do local para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="ff6c3-112">Os contatos que existiam no local estão disponíveis no Teams logo após o usuário fazer logor pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="ff6c3-113">Os usuários não podem iniciar chamadas ou chats do Skype for Business, nem agendar novas reuniões no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="ff6c3-114">Se eles tentarem abrir o cliente skype for Business, eles serão redirecionados para usar o Teams, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="ff6c3-115">Se o cliente do Teams não estiver instalado, ele será direcionado para a versão da Web do Teams usando seu navegador.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="ff6c3-116">![Redirecionamento de mensagens de um usuário para o Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="ff6c3-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="ff6c3-117">Antes de mover qualquer usuário, revise os [pré-requisitos](move-users-between-on-premises-and-cloud.md#prerequisites) para mover os usuários para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="ff6c3-118">Também revise as diretrizes de migração e interoperabilidade para organizações [que usam o Teams juntamente com o Skype for Business.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="ff6c3-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="ff6c3-119">O Armazenamento de Contatos Unificados deve ser desabilitado na conta SfB no momento para que o contato seja movido para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="ff6c3-120">Há dois métodos para mover um usuário local para o Teams:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="ff6c3-121">Se você estiver usando uma versão anterior à CU8 do Skype for Business Server 2015, a movimentação exigirá duas etapas (que podem ser feitas em script como uma única etapa, se desejado):</span><span class="sxs-lookup"><span data-stu-id="ff6c3-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="ff6c3-122">[Mover o usuário do Skype for Business Server (local) para o Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="ff6c3-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="ff6c3-123">Depois que o usuário for instalado no Skype for Business Online, atribua o usuário TeamsUpgradePolicy com mode= TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="ff6c3-124">Para conceder o modo TeamsOnly, execute o seguinte cmdlet de uma janela do PowerShell do Skype for Business Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="ff6c3-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="ff6c3-125">Se você tiver ferramentas de administração do Skype for Business Server 2015 CU8 ou posterior, poderá usar o método acima ou pode fazer essa movimentação em uma etapa, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="ff6c3-126">Além disso, você pode, opcionalmente, fornecer uma notificação dentro do cliente skype for Business antes de mudo para o Teams Somente, bem como, opcionalmente, fazer com que o cliente do Teams seja baixado silenciosamente pelo cliente skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="ff6c3-127">Mover um usuário diretamente do Skype for Business local para o Teams Only</span><span class="sxs-lookup"><span data-stu-id="ff6c3-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="ff6c3-128">As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você mova os usuários do local para o modo Somente do Teams em uma única etapa usando o cmdlet Move-CsUser no PowerShell ou o Painel de Controle do Skype for Business Server, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="ff6c3-129">Mover para o Teams usando Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ff6c3-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="ff6c3-130">Move-CsUser está disponível em uma janela local do Shell de Gerenciamento do Skype for Business PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="ff6c3-131">As etapas abaixo e as permissões necessárias são as mesmas que mover um usuário para o Skype for Business Online, exceto que você também deve especificar a opção MoveToTeams e você deve garantir que o usuário também tenha sido concedido uma licença para o Teams (além do Skype for Business Online).</span><span class="sxs-lookup"><span data-stu-id="ff6c3-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="ff6c3-132">Você deve ter privilégios suficientes no ambiente local e no serviço de nuvem (Microsoft 365 ou Office 365), conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="ff6c3-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="ff6c3-133">Você pode usar uma única conta que tenha privilégios em ambos os ambientes ou pode iniciar uma janela do Shell de Gerenciamento do Skype for Business Server local com credenciais locais e usar o parâmetro para especificar credenciais para uma conta do `-Credential` Microsoft 365 ou office 365 com a função administrativa necessária.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="ff6c3-134">Para mover um usuário para o modo Somente do Teams usando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="ff6c3-135">Especifique o usuário para mover usando o `Identity` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="ff6c3-136">Especifique o parâmetro -Target com o valor "sipfed.online.lync. <span> com".</span><span class="sxs-lookup"><span data-stu-id="ff6c3-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="ff6c3-137">Especifique a `MoveToTeams` opção.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="ff6c3-138">Se você não tiver uma conta com permissões suficientes no local e no serviço de nuvem (Microsoft 365 ou Office 365), use o parâmetro para fornecer uma conta com permissões suficientes no `-credential` Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="ff6c3-139">Se a conta com permissões no Microsoft 365 ou Office 365 não terminar em "onmicrosoft. <span> com", você deve especificar o `-HostedMigrationOverrideUrl` parâmetro, com o valor correto conforme descrito em [Credenciais administrativas necessárias.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="ff6c3-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="ff6c3-140">A sequência de cmdlets a seguir pode ser usada para mover um usuário para o TeamsOnly e presume que a credencial do Microsoft 365 ou office 365 seja uma conta separada e fornecida como entrada para o prompt Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="ff6c3-141">Como há circunstâncias diferentes que exigem parâmetros diferentes, o comando padrão para a maioria dos casos é:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-141">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ff6c3-142">Mover para o Teams usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ff6c3-142">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ff6c3-143">Abra o aplicativo Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-143">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="ff6c3-144">Na navegação à esquerda, escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-144">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="ff6c3-145">Use **Localizar** para localizar os usuários que você gostaria de mover para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-145">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="ff6c3-146">Selecione os usuários e, em seguida, na lista suspenso **Ação** acima da lista, escolha **Mover usuários selecionados para o Teams**.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-146">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="ff6c3-147">No assistente, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-147">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="ff6c3-148">Se solicitado, entre no Microsoft 365 ou Office 365 com uma conta que termine em .onmicrosoft.com e tenha permissões suficientes.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-148">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="ff6c3-149">Clique **em** Avançar e **em Avançar mais** uma vez para mover o usuário.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-149">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="ff6c3-150">Observe que as mensagens de status relacionadas ao sucesso ou falha são fornecidas na parte superior do aplicativo painel de controle principal, não no assistente.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-150">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="ff6c3-151">Notificar os usuários locais do Skype for Business sobre a próxima movimentação para o Teams</span><span class="sxs-lookup"><span data-stu-id="ff6c3-151">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="ff6c3-152">As ferramentas de administração locais no Skype for Business Server 2015 com CU8, bem como no Skype for Business Server 2019, permitem que você notifique os usuários locais do Skype for Business sobre sua próxima mudança para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-152">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="ff6c3-153">Quando você habilita essas notificações, os usuários verão uma notificação em seu cliente do Skype for Business (Win32, Mac, Web e celular), conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-153">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="ff6c3-154">Se os usuários clicarem **no botão Experimentar,** o cliente do Teams será lançado se estiver instalado; caso contrário, os usuários serão navegados para a versão da Web do Teams em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-154">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="ff6c3-155">Por padrão, quando as notificações são habilitadas, os clientes do Skype for Business Win32 baixam silenciosamente o cliente do Teams para que o cliente rich está disponível antes de mover o usuário para o modo Somente equipes; no entanto, você também pode desabilitar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-155">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="ff6c3-156">As notificações são configuradas usando a versão local de , e o download silencioso para clientes Win32 é controlado por meio do `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet local.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-156">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="ff6c3-157">Alguns servidores podem precisar reiniciar para que isso funcione no Skype for Business 2015 com CU8.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-157">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![Notificação da próxima movimentação para o Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="ff6c3-159">Para notificar os usuários locais de que eles serão atualizados em breve para o Teams, crie uma nova instância do TeamsUpgradePolicy com NotifySfBUsers=true.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-159">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="ff6c3-160">Em seguida, atribua essa política aos usuários que você deseja notificar, atribuindo a política diretamente ao usuário ou definindo a política no site, pool ou nível global.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-160">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="ff6c3-161">Os cmdlets a seguir criam e concedem uma política no nível do usuário:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-161">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="ff6c3-162">O download automático do Teams por meio do cliente Do Skype for Business Win32 é controlado por meio do cmdlet TeamsUpgradeConfiguration local com o parâmetro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-162">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="ff6c3-163">Você cria essa configuração em um nível global, de site e de pool.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-163">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="ff6c3-164">Por exemplo, o comando a seguir cria a configuração do site Redmond1:</span><span class="sxs-lookup"><span data-stu-id="ff6c3-164">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="ff6c3-165">Por padrão, o valor de DownloadTeams é True; no entanto, ele só *será* honrado se NotifySfbUser = True para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="ff6c3-165">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff6c3-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="ff6c3-166">See also</span></span>

[<span data-ttu-id="ff6c3-167">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ff6c3-167">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="ff6c3-168">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ff6c3-168">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="ff6c3-169">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ff6c3-169">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="ff6c3-170">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ff6c3-170">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
