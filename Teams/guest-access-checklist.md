---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcba883166e01bd8a18d6d76b4622df0740500c8
ms.sourcegitcommit: 000fdb3bc1a0d4dda63fb00bab6a9a9ab0c85ab0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39813771"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="892e9-103">Lista de verificação de acesso de convidados do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="892e9-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="892e9-104">Use esta lista de verificação para ajudar você a ativar e configurar o acesso de convidados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="892e9-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="892e9-105">Você precisa ser um administrador global ou administrador do teams para fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="892e9-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="892e9-106">Talvez seja necessário aguardar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="892e9-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="892e9-107">Assista a este vídeo curto (5:31 minutos) para ver como ativar o acesso de convidados durante o Microsoft 365, incluindo o Teams.</span><span class="sxs-lookup"><span data-stu-id="892e9-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="892e9-108">Etapa 1: ativar o acesso de convidado no nível Teams de toda a organização</span><span class="sxs-lookup"><span data-stu-id="892e9-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="892e9-109">Para ativar o acesso de convidado, vá para o **centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="892e9-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="892e9-110">No centro de administração do Teams, selecione o > **acesso de convidados**às **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="892e9-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="892e9-111">Defina a opção **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="892e9-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![A captura de tela mostra um exemplo de alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="892e9-113">Na mesma página, ative ou desative as configurações de **chamada**, **reunião**e **mensagens** para convidados.</span><span class="sxs-lookup"><span data-stu-id="892e9-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="892e9-114">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="892e9-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="892e9-115">Se você estiver usando as configurações padrão nos grupos do Azure Active Directory, do SharePoint Online e do Office 365, pode ser que você tenha concluído a configuração do acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="892e9-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="892e9-116">Nesse caso, você pode ignorar o restante das etapas.</span><span class="sxs-lookup"><span data-stu-id="892e9-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="892e9-117">Se você não tiver certeza ou se estiver usando configurações personalizadas para grupos do AAD, SharePoint Online ou Office 365, continue com o restante das etapas desta lista de verificação.</span><span class="sxs-lookup"><span data-stu-id="892e9-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="892e9-118">Etapa 2: configurar as configurações do Azure AD Business para empresas</span><span class="sxs-lookup"><span data-stu-id="892e9-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="892e9-119">Entre no [portal do Azure](https://portal.azure.com) como um administrador de locatários.</span><span class="sxs-lookup"><span data-stu-id="892e9-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="892e9-120">Selecione**as configurações de usuário** **do Azure Active Directory** > **Users** > .</span><span class="sxs-lookup"><span data-stu-id="892e9-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="892e9-121">Em **usuários externos**, selecione **gerenciar configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="892e9-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="892e9-122">As **configurações de colaboração externa** também estão disponíveis na página **relações organizacionais** .</span><span class="sxs-lookup"><span data-stu-id="892e9-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="892e9-123">No Azure Active Directory, em **gerenciar**, acesse > **configurações**de **relações organizacionais**.</span><span class="sxs-lookup"><span data-stu-id="892e9-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="892e9-124">Na página **configurações de colaboração externas** , escolha as políticas que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="892e9-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="892e9-125">**As permissões de usuários convidados são limitadas**: esta política determina permissões para convidados em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="892e9-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="892e9-126">Selecione **Sim** para bloquear convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório.</span><span class="sxs-lookup"><span data-stu-id="892e9-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="892e9-127">Selecione **não** para dar aos convidados o mesmo acesso aos dados do diretório como usuários regulares em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="892e9-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="892e9-128">**Administradores e usuários na função de convite de convidado podem convidar**: para permitir que administradores e usuários na função "convidador de convidado" possam convidar convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="892e9-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="892e9-129">**Os membros podem convidar**: para permitir que membros que não sejam administradores do seu diretório convidem convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="892e9-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="892e9-130">Se você definir que **os membros podem convidar** para **não** e, em seguida, habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="892e9-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="892e9-131">Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="892e9-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="892e9-132">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="892e9-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="892e9-133">Para que o acesso de convidados funcione completamente no Teams, você deve definir o recurso**Membros podem convidar** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="892e9-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="892e9-134">**Convidados podem convidar**: para permitir que os convidados convidem outros convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="892e9-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="892e9-135">Atualmente, o Teams não oferece suporte à função de emissor de convites, portanto, mesmo se você definir **Convidados possam convidar** para **Sim**, os convidados não conseguirão convidar outros convidados no Teams.</span><span class="sxs-lookup"><span data-stu-id="892e9-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="892e9-136">**Habilitar a senha de senha única para convidados (visualização)**: para obter mais informações sobre o recurso de senha de uso único, consulte [autenticação de senha única (visualização) de email](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="892e9-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="892e9-137">**Restrições de colaboração**: para obter mais informações sobre como permitir ou bloquear convites para domínios específicos, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="892e9-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="892e9-138">Para obter restrições de colaboração, consulte [habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="892e9-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="892e9-139">Para obter mais informações sobre como controlar quem pode convidar pessoas, consulte [Delegar convites para colaboração B2B do Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="892e9-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="892e9-140">Etapa 3: configurar grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="892e9-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="892e9-141">No centro de administração do Microsoft 365, vá para **configurações** > de**Serviços & suplementos** > **do Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="892e9-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="892e9-142">Verifique se **deixar que os membros do grupo fora do conteúdo do grupo de acesso à organização** estejam definidos como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="892e9-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="892e9-143">Se essa configuração estiver desativada, os convidados não poderão acessar qualquer conteúdo do grupo.</span><span class="sxs-lookup"><span data-stu-id="892e9-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="892e9-144">Certifique-se de **que o recurso proprietários de grupos Adicione pessoas de fora da organização a grupos** esteja definido como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="892e9-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="892e9-145">Se essa configuração estiver desativada, os proprietários da equipe não poderão adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="892e9-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="892e9-146">No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="892e9-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![A captura de tela mostra as alternâncias dos grupos do Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="892e9-148">Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="892e9-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="892e9-149">Etapa 4: configurar o compartilhamento no Office 365</span><span class="sxs-lookup"><span data-stu-id="892e9-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="892e9-150">Certifique-se de que os usuários possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="892e9-150">Make sure that users can add guests.</span></span> <span data-ttu-id="892e9-151">Veja como:</span><span class="sxs-lookup"><span data-stu-id="892e9-151">Here's how:</span></span>

1. <span data-ttu-id="892e9-152">No centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.</span><span class="sxs-lookup"><span data-stu-id="892e9-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="892e9-154">Em **compartilhamento**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="892e9-154">In **Sharing**, select **Edit**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="892e9-156">Defina **permitir que os usuários adicionem novos convidados a essa organização** para serem **ativados**e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="892e9-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="892e9-158">Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="892e9-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="892e9-159">Etapa 5: verificar a configuração de compartilhamento no SharePoint</span><span class="sxs-lookup"><span data-stu-id="892e9-159">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="892e9-160">Isso é um pouco de uma outra.</span><span class="sxs-lookup"><span data-stu-id="892e9-160">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="892e9-161">O acesso de convidado no Microsoft Teams não funciona se a configuração **não permitir o compartilhamento fora da organização** estiver selecionada no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="892e9-161">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="892e9-162">Entre no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="892e9-162">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="892e9-163">Clique em **centro de administração**e selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="892e9-163">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="892e9-164">No centro de administração do SharePoint, selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="892e9-164">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="892e9-165">Certifique-se de que a opção **não permitir o compartilhamento fora da sua organização** *não* esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="892e9-165">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![A captura de tela mostra um exemplo de uma alternância de configurações online do SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="892e9-167">Etapa 6: configurar permissões de usuário convidado</span><span class="sxs-lookup"><span data-stu-id="892e9-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="892e9-168">No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado que controlam se os convidados podem criar, atualizar ou excluir canais.</span><span class="sxs-lookup"><span data-stu-id="892e9-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="892e9-169">Os administradores do Team e os proprietários da equipe podem definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="892e9-169">Teams admins as well as team owners can configure these settings.</span></span>

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="892e9-171">Para saber mais sobre o acesso de convidado, consulte [acesso de convidado em equipes](guest-access.md) e [ative ou desative o acesso de convidado ao Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="892e9-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="892e9-172">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="892e9-172">Troubleshooting</span></span>

<span data-ttu-id="892e9-173">Se você tiver problemas para configurar o acesso de convidado ou adicionar convidados ao Microsoft Teams, use estes recursos para ajudá-lo:</span><span class="sxs-lookup"><span data-stu-id="892e9-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="892e9-174">Solucionar problemas de acesso de convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="892e9-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="892e9-175">Solução de problemas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="892e9-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



