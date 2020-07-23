---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Saiba mais sobre como ativar e configurar o acesso de convidado no Microsoft Teams como um administrador global ou de equipes.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d38b0adf1a342c4398d2779e2f0b5ec3aa310144
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372000"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="bcdba-103">Lista de verificação de acesso de convidados do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcdba-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="bcdba-104">Use esta lista de verificação para ajudá-lo a habilitar e configurar o acesso de convidados no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bcdba-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="bcdba-105">Você precisa ser um administrador global ou administrador do Teams para corrigir essas alterações.</span><span class="sxs-lookup"><span data-stu-id="bcdba-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcdba-106">Talvez seja necessário esperar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="bcdba-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="bcdba-107">Assista a este vídeo curto (5:31 minutos) para saber como habilitar o acesso de convidados no Microsoft 365, incluindo o Teams.</span><span class="sxs-lookup"><span data-stu-id="bcdba-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="bcdba-108">Etapa 1: habilitar o acesso de convidados no nível de toda a organização do Teams</span><span class="sxs-lookup"><span data-stu-id="bcdba-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="bcdba-109">Você deve ser um administrador de serviços do teams para fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="bcdba-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="bcdba-110">Consulte [usar funções de administrador do teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.</span><span class="sxs-lookup"><span data-stu-id="bcdba-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="bcdba-111">No Centro de administração do Teams, selecione **Configurações em toda a organização** > **Acesso de convidados**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="bcdba-112">Defina o botão **Permitir acesso de convidados no Microsoft Teams** para **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![A tela de captura mostra um exemplo de alternância de configurações do Teams](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="bcdba-114">Na mesma página, habilite ou desabilite as configurações de **Chamada**, **Reunião** e **Mensagens** para os convidados.</span><span class="sxs-lookup"><span data-stu-id="bcdba-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="bcdba-115">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="bcdba-116">Se você estiver usando as configurações padrão nos grupos do Azure Active Directory, do SharePoint Online e do Microsoft 365, pode ser que você tenha concluído a configuração do acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="bcdba-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="bcdba-117">Nesse caso, você pode ignorar o restante das etapas.</span><span class="sxs-lookup"><span data-stu-id="bcdba-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="bcdba-118">Se você não tiver certeza ou se estiver usando configurações personalizadas para grupos do AAD, SharePoint Online ou Microsoft 365, continue com o restante das etapas desta lista de verificação.</span><span class="sxs-lookup"><span data-stu-id="bcdba-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="bcdba-119">Etapa 2: definir as configurações do Azure Active Directory entre empresas</span><span class="sxs-lookup"><span data-stu-id="bcdba-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="bcdba-120">Estas são as configurações do Azure AD que oferecem suporte ao acesso de convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="bcdba-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="bcdba-121">Depois de definir essas configurações, você poderá [Adicionar](add-guests.md) e [Gerenciar convidados](manage-guests.md) no Teams.</span><span class="sxs-lookup"><span data-stu-id="bcdba-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="bcdba-122">Acesse o [Portal do Azure](https://portal.azure.com) como administrador de locatários.</span><span class="sxs-lookup"><span data-stu-id="bcdba-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="bcdba-123">Selecione **Azure Active Directory** > **Usuários** > **Configurações do usuário**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="bcdba-124">Em **Usuários externos**, selecione **Gerenciar as configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bcdba-125">As **Configurações de colaboração externas** também estão disponíveis na página **Relações organizacionais**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="bcdba-126">No Azure Active Directory, em **Gerenciar**, acesse **Relações organizacionais** > **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="bcdba-127">Na página **Configurações de colaboração externas**, escolha as políticas que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="bcdba-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="bcdba-128">**As permissões de usuários convidados são limitadas**: essa política determina permissões para convidados em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="bcdba-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="bcdba-129">Selecione **Sim** para bloquear os convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório.</span><span class="sxs-lookup"><span data-stu-id="bcdba-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="bcdba-130">Selecione **Não** para conceder aos convidados o mesmo acesso aos dados de diretório que os usuários comuns têm em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="bcdba-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="bcdba-131">**Administradores e usuários na função de emissor do convite podem convidar**: defina esta política como **Sim** para permitir que os administradores e usuários na função de "Emissor de Convite" possam convidar pessoas.</span><span class="sxs-lookup"><span data-stu-id="bcdba-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="bcdba-132">**Os membros podem convidar**: para permitir que os membros não administradores do seu diretório convidem pessoas, defina essa política como **Sim** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="bcdba-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="bcdba-133">Se preferir que somente os administradores sejam capazes de adicionar convidados, você pode definir essa política como **Não**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="bcdba-134">Lembre-se de que definir **Não** limitará a experiência de convidado para proprietários de equipes não administrativos; eles só poderão adicionar convidados ao Teams que já foram adicionados ao AAD pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="bcdba-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="bcdba-135">**Os convidados podem convidar**: defina essa política como **Sim** para permitir que os convidados convidem outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="bcdba-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="bcdba-136">Atualmente, o Teams não oferece suporte à função de emissor de convites, portanto, mesmo se você definir **Convidados possam convidar** para **Sim**, os convidados não conseguirão convidar outros convidados no Teams.</span><span class="sxs-lookup"><span data-stu-id="bcdba-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="bcdba-137">**Habilitar senha de uso único por email para convidados (versão prévia)**: para obter mais informações sobre o recurso de senha de uso único, confira [Autenticação de senha de uso de único por email (versão prévia)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="bcdba-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="bcdba-138">**Restrições de colaboração**: para saber mais sobre como permitir ou bloquear convites para domínios específicos, confira [Permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="bcdba-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="bcdba-139">Para obter restrições de colaboração, confira [Habilitar colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="bcdba-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="bcdba-140">Para obter mais informações sobre como controlar quem pode convidar pessoas, confira [Delegar convites para colaboração B2B do Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="bcdba-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="bcdba-141">Etapa 3: configurar os grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bcdba-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="bcdba-142">No centro de administração do Microsoft 365, vá para **configurações**da  >  **organização**configurações, clique em **Serviços**e, em seguida, selecione **grupos do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![A captura de tela mostra as configurações de grupos do Microsoft 365](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="bcdba-144">Verifique se a caixa de seleção **Permitir que os membros do grupo fora da organização acessem o conteúdo do grupo** foi selecionada.</span><span class="sxs-lookup"><span data-stu-id="bcdba-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="bcdba-145">Se essa configuração não for selecionada, os convidados não poderão acessar nenhum conteúdo do grupo.</span><span class="sxs-lookup"><span data-stu-id="bcdba-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![A captura de tela mostra as configurações de grupos do Microsoft 365](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="bcdba-147">Verifique se a caixa de seleção **Permitir que os proprietários do grupo adicionem pessoas de fora da organização aos grupos** foi selecionada.</span><span class="sxs-lookup"><span data-stu-id="bcdba-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="bcdba-148">Se essa configuração não for selecionada, os proprietários de grupos não poderão adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="bcdba-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="bcdba-149">No mínimo, essa configuração deve estar ativada para oferecer suporte ao acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="bcdba-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="bcdba-150">Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Microsoft 365](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidado em grupos do Microsoft 365](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="bcdba-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="bcdba-151">Etapa 4: configurar o compartilhamento no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bcdba-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="bcdba-152">Certifique-se de que os usuários possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="bcdba-152">Make sure that users can add guests.</span></span> <span data-ttu-id="bcdba-153">Veja como:</span><span class="sxs-lookup"><span data-stu-id="bcdba-153">Here's how:</span></span>

1. <span data-ttu-id="bcdba-154">No centro de administração do Microsoft 365, vá **Settings**para configurações da  >  **organização**configurações, clique em **segurança & privacidade**e selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![A tela de captura mostra um exemplo de configurações de serviços](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="bcdba-156">Marque a caixa de seleção **Permitir que os usuários adicionem novos convidados a esta organização** e, em seguida, clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![A tela de captura mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="bcdba-158">Essa configuração é equivalente à configuração **Membros podem convidar** em **Configurações do usuário** > **Usuários externos** no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bcdba-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="bcdba-159">Etapa 5: verificar a configuração de compartilhamento do SharePoint</span><span class="sxs-lookup"><span data-stu-id="bcdba-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="bcdba-160">Acesse o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcdba-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="bcdba-161">Em **Centros de Administração**, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="bcdba-162">No novo Centro de administração do SharePoint, em **Sites**, selecione **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Sites ativos no Centro de administração do SharePoint](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="bcdba-164">Selecione o site e clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="bcdba-165">Verifique se a opção está definida como **Qualquer pessoa** ou **Convidados novos e existentes**.</span><span class="sxs-lookup"><span data-stu-id="bcdba-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![A tela de captura mostra um exemplo de alternância de configurações do SharePoint Online](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="bcdba-167">Etapa 6: configurar permissões de usuário convidado</span><span class="sxs-lookup"><span data-stu-id="bcdba-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="bcdba-168">No aplicativo Teams, no nível da equipe individual, configure as permissões de convidado que controlam se os convidados podem criar, atualizar ou excluir canais.</span><span class="sxs-lookup"><span data-stu-id="bcdba-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="bcdba-169">Os administradores do Teams, bem como os proprietários da equipe, podem definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="bcdba-169">Teams admins as well as team owners can configure these settings.</span></span>

![A tela de captura mostra um exemplo de alternância de configurações da equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="bcdba-171">Para saber mais sobre o acesso de convidados, confira o [Acesso de convidados no Teams](guest-access.md) e [Ativar ou desativar o acesso de convidados no Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="bcdba-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bcdba-172">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bcdba-172">Troubleshooting</span></span>

<span data-ttu-id="bcdba-173">Se você tiver problemas para configurar o acesso de convidados ou ao adicionar convidados no Temas, use estes recursos para ajudá-lo:</span><span class="sxs-lookup"><span data-stu-id="bcdba-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="bcdba-174">Solucionar problemas com o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bcdba-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="bcdba-175">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="bcdba-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
