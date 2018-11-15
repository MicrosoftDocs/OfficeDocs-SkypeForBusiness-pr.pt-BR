---
title: Mover os usuários no local para equipes
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Resumo: Saiba como migrar configurações do usuário e movam usuários às equipes.'
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533138"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="02916-103">Mover os usuários no local para equipes</span><span class="sxs-lookup"><span data-stu-id="02916-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="02916-104">Com Skype para Business Server 2019, você pode migrar seus usuários no local para equipes, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="02916-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="02916-105">Lembre-se que depois de mover os usuários para equipes:</span><span class="sxs-lookup"><span data-stu-id="02916-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="02916-106">Suas reuniões são migrados para o Skype para Business Online e seus contatos são migrados para as equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="02916-107">Eles podem ingressar em reuniões do Skype por meio do Skype para Business rich client (os usuários não são solicitados para cada vez que entrar) ou o aplicativo de reuniões do Skype (requer um download único e entrar).</span><span class="sxs-lookup"><span data-stu-id="02916-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="02916-108">Quando um usuário clica em um Skype para o link da reunião de negócios dentro de equipes, a reunião será iniciado no aplicativo apropriado.</span><span class="sxs-lookup"><span data-stu-id="02916-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="02916-109">Em Mobile, os usuários poderão ingressar Skype existente para reuniões de negócios usando o app nativo somente.</span><span class="sxs-lookup"><span data-stu-id="02916-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="02916-110">Depois que um usuário é movido para o modo de TeamsOnly, o usuário está hospedado no Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="02916-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="02916-111">Pré-requisitos para mover usuários locais para equipes</span><span class="sxs-lookup"><span data-stu-id="02916-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="02916-112">Esta seção descreve os pré-requisitos para mover os usuários no local para equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="02916-113">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="02916-113">You must:</span></span>
- <span data-ttu-id="02916-114">[Configurar a conectividade híbrida](#set-up-hybrid-connectivity) (se você ainda não tiver feito isso)</span><span class="sxs-lookup"><span data-stu-id="02916-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="02916-115">[Notifique os usuários da mudança às equipes](#notify-your-users-of-the-move-to-teams) (opcional)</span><span class="sxs-lookup"><span data-stu-id="02916-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="02916-116">Certifique-se de que os usuários têm uma licença válida</span><span class="sxs-lookup"><span data-stu-id="02916-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="02916-117">Esteja ciente dos requisitos de configuração de voz</span><span class="sxs-lookup"><span data-stu-id="02916-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="02916-118">[Atribuir uma política de atualização de equipes](#assign-a-teams-upgrade-policy) (opcional)</span><span class="sxs-lookup"><span data-stu-id="02916-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="02916-119">Configurar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="02916-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="02916-120">Antes de migrar os usuários, se você ainda não tiver feito isso, você deve garantir que você tenha configurado a conectividade híbrida entre o Skype para o ambiente do Business Server local e Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="02916-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="02916-121">Conectividade híbrida exige a sincronização do Active Directory, configurando federação e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="02916-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="02916-122">Para obter mais informações, consulte [Planejar a conectividade híbrida](plan-hybrid-connectivity.md) e [conectividade de híbrida Configure](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="02916-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="02916-123">Notifique os usuários da mudança às equipes</span><span class="sxs-lookup"><span data-stu-id="02916-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="02916-124">Essa é uma etapa opcional, mas que você deve considerar.</span><span class="sxs-lookup"><span data-stu-id="02916-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="02916-125">Para notificar os usuários da atualização pendente equipes, você pode usar os cmdlets de TeamsUpgradePolicy e TeamsUpgradeConfiguration do local.</span><span class="sxs-lookup"><span data-stu-id="02916-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="02916-126">Você também pode configurar o download automático silencioso de equipes em segundo plano antes da atualização (somente clientes do Win32).</span><span class="sxs-lookup"><span data-stu-id="02916-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="02916-127">Por exemplo, para notificar os usuários que estão sendo atualizados para equipes, use o cmdlet de TeamsUpgradePolicy de local com o parâmetro - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="02916-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="02916-128">Você pode definir a diretiva no nível global, site, pool ou usuário.</span><span class="sxs-lookup"><span data-stu-id="02916-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="02916-129">O comando a seguir cria e concede uma política de nível de usuário:</span><span class="sxs-lookup"><span data-stu-id="02916-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="02916-130">Você pode verificar esta diretiva usando o cmdlet Get-csTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="02916-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="02916-131">Os usuários verão uma notificação da movimentação iminente às equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="02916-132">A notificação ocorre no Win32, Mac, móveis e clientes Web (com a versão correta).</span><span class="sxs-lookup"><span data-stu-id="02916-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="02916-133">Você pode especificar o download automático de equipes (para clientes do Win32) para usuários que estão sendo atualizados usando o cmdlet de TeamsUpgradeConfiguration local com o parâmetro DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="02916-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="02916-134">Defini-la no nível de locatário, e ele pode ser aplicada em um site global e nível de pool.</span><span class="sxs-lookup"><span data-stu-id="02916-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="02916-135">Por exemplo, o comando a seguir define a política no nível do site:</span><span class="sxs-lookup"><span data-stu-id="02916-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="02916-136">Por padrão, o valor de DownloadTeams é True, mas você também deve definir NotifySfbUser como True para permitir que equipes para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="02916-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="02916-137">Certificar-se de que os usuários têm uma licença válida</span><span class="sxs-lookup"><span data-stu-id="02916-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="02916-138">Antes da migração, o usuário local deve ser fornecido uma licença válida, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="02916-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="02916-139">Usuário deve ter uma licença de equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="02916-140">Se o usuário estiver configurado para usar o Enterprise Voice do local, eles devem ter uma licença de voz online durante a mudança.</span><span class="sxs-lookup"><span data-stu-id="02916-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="02916-141">Se o usuário estiver configurado para conferência discada do local, eles devem ter uma licença para o sistema telefônico (nuvem PBX).</span><span class="sxs-lookup"><span data-stu-id="02916-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="02916-142">Requisitos de configuração de voz</span><span class="sxs-lookup"><span data-stu-id="02916-142">Voice configuration requirements</span></span>

<span data-ttu-id="02916-143">Se os usuários no local tiverem voz no local, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="02916-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="02916-144">**Migre usuários com os recursos de telefonia.**</span><span class="sxs-lookup"><span data-stu-id="02916-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="02916-145">Os usuários podem fazer e receber chamadas usando o cliente de equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="02916-146">Você pode escolher entre Microsoft chamar planejar ou em roteamento direto para conectar os serviços de telefonia para equipes.</span><span class="sxs-lookup"><span data-stu-id="02916-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="02916-147">Chamar plano Microsoft fornece uma solução de voz all nuvem.</span><span class="sxs-lookup"><span data-stu-id="02916-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="02916-148">Para obter mais informações sobre como chamar plano Microsoft, consulte (link em breve).</span><span class="sxs-lookup"><span data-stu-id="02916-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="02916-149">Roteamento direto permite usar praticamente qualquer tronco PSTN, e você pode configurar a interoperabilidade entre o sistema de telefone da Microsoft e equipamentos de telefonia de propriedade do cliente.</span><span class="sxs-lookup"><span data-stu-id="02916-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="02916-150">Para obter mais informações, consulte [Planejar roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) e [Configurar o roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="02916-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="02916-151">**Migre usuários sem recursos de telefonia.**</span><span class="sxs-lookup"><span data-stu-id="02916-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="02916-152">Se você migrar usuários sem preservar os recursos de telefonia, certifique-se de usuários têm licenças apropriadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02916-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="02916-153">Atribuir uma política de atualização de equipes</span><span class="sxs-lookup"><span data-stu-id="02916-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="02916-154">Você pode usar as ferramentas on-line para gerenciar políticas de usuário, tais como controlar o roteamento de chamadas e mensagens de entrada.</span><span class="sxs-lookup"><span data-stu-id="02916-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="02916-155">Para obter mais informações, consulte (link em breve).</span><span class="sxs-lookup"><span data-stu-id="02916-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="02916-156">Mover usuários locais para equipes</span><span class="sxs-lookup"><span data-stu-id="02916-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="02916-157">Você pode mover os usuários no local para equipes usando cmdlets do PowerShell ou usando o Skype para painel de controle do Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="02916-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="02916-158">Mover usuários usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="02916-158">Move users by using PowerShell</span></span>
<span data-ttu-id="02916-159">Para mover os usuários para equipes usando o PowerShell, você vai usar o cmdlet Move-CsUser com o parâmetro moveToTeams da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="02916-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="02916-160">($cred = get-credenciais.</span><span class="sxs-lookup"><span data-stu-id="02916-160">($cred = get-Credentials.</span></span> <span data-ttu-id="02916-161">Você deve fornecer credenciais de administrador do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="02916-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="02916-162">Esse comando define o TeamsUpgradePolicy para o modo de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="02916-162">This command sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="02916-163">Após a mudança para equipes for bem-sucedida, Skype do usuário para o cliente de negócios exibirá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="02916-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Migração bem-sucedida a mensagem de equipes](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="02916-165">Observe que Skype para negócios não ficarão mais disponível para o usuário, exceto ao ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="02916-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="02916-166">Em casos raros, ao mover os usuários para equipes, você talvez queira substituir a conferência discada e funcionalidade de voz na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02916-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="02916-167">Você pode fazer isso usando os seguintes parâmetros com o comando Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="02916-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="02916-168">**BypassAudioConferencingCheck:** Se um usuário tiver discada habilitada para o local, o usuário também deve ter uma licença de AudioConf atribuída no Office 365 antes da migração.</span><span class="sxs-lookup"><span data-stu-id="02916-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="02916-169">Uma vez migrados para a nuvem, o usuário será provisionado para conferência de áudio na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02916-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="02916-170">Se, por algum motivo, que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de conferência de áudio, você pode substitui-la especificando-se esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="02916-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="02916-171">**ByPassEnterpriseVoice:** Se um usuário tiver o Enterprise Voice habilitado para o local, o usuário deve ter uma licença Enterprise Voice atribuída no Office 365 antes da migração.</span><span class="sxs-lookup"><span data-stu-id="02916-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="02916-172">Após a migração para a nuvem, o usuário será provisionado para voz na nuvem.</span><span class="sxs-lookup"><span data-stu-id="02916-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="02916-173">Se, por algum motivo, que você deseja mover um usuário na nuvem, mas não usar a funcionalidade de voz de nuvem, você pode substituir a nuvem voz especificando-se esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="02916-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="02916-174">Mover usuários usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="02916-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="02916-175">Para mover usuários para equipes usando o Skype para painel de controle de negócios:</span><span class="sxs-lookup"><span data-stu-id="02916-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="02916-176">Abra o Skype para painel de controle de negócios e entrar em sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="02916-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="02916-177">Selecione os **usuários** no painel de navegação esquerdo e selecione os usuários para migrar.</span><span class="sxs-lookup"><span data-stu-id="02916-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="02916-178">No menu **ação** , selecione **mover usuários selecionados para equipes**.</span><span class="sxs-lookup"><span data-stu-id="02916-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Clicar em Avançar para confirmar a migração](../media/migration-confirmation.png)
    
4. <span data-ttu-id="02916-180">Clique em **Avançar** para confirmar sua migração.</span><span class="sxs-lookup"><span data-stu-id="02916-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="02916-181">Depois que o usuário é movido para equipes, você verá as confirmações semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="02916-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="02916-182">![Mover a confirmação de usuários](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="02916-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="02916-183">![Se os usuários foram movidos de mensagem](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="02916-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="02916-184">Se a movimentação não tiver sido bem-sucedida, você verá uma mensagem semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="02916-184">If the move was not successful, you will see a message like the following:</span></span>

![Mensagem que não puderam ser movido usuário](../media/users-not-moved.png)
