---
title: Lista de verificação de acesso de convidados do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ec3fb391feefae9daa5ffaa8c7b5955b6552f93
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221656"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="419cf-103">Lista de verificação de acesso de convidados do teams</span><span class="sxs-lookup"><span data-stu-id="419cf-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="419cf-104">Use esta lista de verificação para ajudá-lo a habilitar e configurar o recurso de acesso de convidado no Microsoft Teams de acordo com as preferências da sua organização.</span><span class="sxs-lookup"><span data-stu-id="419cf-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="419cf-105">Entender as limitações dos convidados</span><span class="sxs-lookup"><span data-stu-id="419cf-105">Understand the limitations for guests</span></span>

<span data-ttu-id="419cf-106">A experiência de convidado tem limitações por meio do design.</span><span class="sxs-lookup"><span data-stu-id="419cf-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="419cf-107">Certifique-se de entender a experiência de convidado para não tentar corrigir algo que não seja um problema.</span><span class="sxs-lookup"><span data-stu-id="419cf-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="419cf-108">Por exemplo, veja a seguir uma lista de alguns dos recursos que não estão disponíveis para um convidado no Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="419cf-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="419cf-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="419cf-109">OneDrive for Business</span></span>
- <span data-ttu-id="419cf-110">Pesquisa de pessoas fora do teams</span><span class="sxs-lookup"><span data-stu-id="419cf-110">People search outside of Teams</span></span>
- <span data-ttu-id="419cf-111">Calendário, reuniões agendadas ou detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="419cf-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="419cf-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="419cf-112">PSTN</span></span>
- <span data-ttu-id="419cf-113">Organograma</span><span class="sxs-lookup"><span data-stu-id="419cf-113">Organization chart</span></span>
- <span data-ttu-id="419cf-114">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="419cf-114">Create or revise a team</span></span>
- <span data-ttu-id="419cf-115">Procurar uma equipe</span><span class="sxs-lookup"><span data-stu-id="419cf-115">Browse for a team</span></span>
- <span data-ttu-id="419cf-116">Carregar arquivos para um chat de pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="419cf-116">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="419cf-117">Os convidados ainda podem pesquisar e localizar usuários (fora de sua equipe) se saberem a identificação de email completa do usuário.</span><span class="sxs-lookup"><span data-stu-id="419cf-117">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="419cf-118">Para evitar isso, os administradores de ti podem usar padrões como [pesquisa de diretório em escopo](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) que têm a capacidade de restringir convidados à sua GAL virtual.</span><span class="sxs-lookup"><span data-stu-id="419cf-118">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="419cf-119">Para obter mais detalhes, consulte o [que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="419cf-119">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="419cf-120">Acesso de convidado vs. acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="419cf-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="419cf-121">Se seus convidados estiverem vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="419cf-121">If your guests are seeing license errors</span></span>

<span data-ttu-id="419cf-122">O acesso de convidado no Microsoft Teams usa o Azure Active Directory (Azure AD) Business to Business (B2B) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="419cf-122">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="419cf-123">Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para entender os requisitos de licenciamento que a sua organização tem para que seus usuários possam convidar convidados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="419cf-123">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="419cf-124">Lembre-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="419cf-124">A few things to remember:</span></span>

- <span data-ttu-id="419cf-125">Para cada licença paga do Azure AD atribuída a um usuário, os usuários podem convidar até cinco usuários convidados sob a bonificação de usuário externa.</span><span class="sxs-lookup"><span data-stu-id="419cf-125">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="419cf-126">Convidados são usuários de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="419cf-126">Guests are users outside your organization.</span></span> <span data-ttu-id="419cf-127">Seus funcionários, prestadores de no local, agentes no local e assim por diante não podem ser adicionados como convidados.</span><span class="sxs-lookup"><span data-stu-id="419cf-127">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="419cf-128">O mesmo se aplica às suas afiliadas.</span><span class="sxs-lookup"><span data-stu-id="419cf-128">The same applies to your affiliates.</span></span>
- <span data-ttu-id="419cf-129">As licenças de convidado são contadas em relação à organização que convida.</span><span class="sxs-lookup"><span data-stu-id="419cf-129">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="419cf-130">Considere isso quando você calcular o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="419cf-130">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="419cf-131">As licenças são contadas em relação à sua organização se os convidados convidados vierem de outro locatário do Office 365 ou estiverem usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="419cf-131">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="419cf-132">□ Etapa 1: definir as configurações do Azure AD para empresas</span><span class="sxs-lookup"><span data-stu-id="419cf-132">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="419cf-133">Conectar-se https://portal.azure.comao.</span><span class="sxs-lookup"><span data-stu-id="419cf-133">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="419cf-134">Clique em **Azure Active Directory** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="419cf-134">Click **Azure Active Directory** in the left pane.</span></span>
3. <span data-ttu-id="419cf-135">Em **gerenciar**, clique em **configurações do usuário**.</span><span class="sxs-lookup"><span data-stu-id="419cf-135">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="419cf-136">Em **usuários externos**, clique em **gerenciar configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="419cf-136">Under **External users**, click **Manage external collaboration settings**.</span></span>
5. <span data-ttu-id="419cf-137">Na página **configurações de colaboração externas** , certifique-se de que **os membros podem convidar** esteja definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="419cf-137">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="419cf-138">A captura de tela mostra um exemplo de uma alternância de configurações do AAD.</span><span class="sxs-lookup"><span data-stu-id="419cf-138">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="419cf-139">Para dar suporte a convidados, **os membros podem convidar** devem ser definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="419cf-139">To support guests, **Members can invite** must be set to **Yes**.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="419cf-140">Se você definir que **os membros podem convidar** para **não** e, em seguida, habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="419cf-140">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="419cf-141">Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="419cf-141">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="419cf-142">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="419cf-142">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="419cf-143">□ Etapa 2: configurar grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="419cf-143">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="419cf-144">No centro de administração do Microsoft 365, vá para **configurações** > de**Serviços & suplementos** > **do Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="419cf-144">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="419cf-145">Verifique se **deixar que os membros do grupo fora do conteúdo do grupo de acesso à organização** estejam definidos como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="419cf-145">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="419cf-146">Se essa configuração estiver desativada, os convidados não poderão acessar qualquer conteúdo do grupo.</span><span class="sxs-lookup"><span data-stu-id="419cf-146">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="419cf-147">Certifique-se de **que o recurso proprietários de grupos Adicione pessoas de fora da organização a grupos** esteja definido como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="419cf-147">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="419cf-148">Se essa configuração estiver desativada, os proprietários da equipe não poderão adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="419cf-148">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="419cf-149">No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="419cf-149">At a minimum, this setting must be On to support guest access.</span></span>

     ![A captura de tela mostra as alternâncias dos grupos do Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="419cf-151">Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="419cf-151">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="419cf-152">□ Etapa 3: habilitar o acesso de convidado no nível do locatário</span><span class="sxs-lookup"><span data-stu-id="419cf-152">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="419cf-153">No mínimo, você deve ativar o acesso de convidado para o Microsoft Teams no **centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="419cf-153">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="419cf-154">No centro de administração do Teams, selecione o > **acesso de convidados**às **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="419cf-154">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="419cf-155">Defina a opção **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="419cf-155">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![A captura de tela mostra um exemplo de alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="419cf-157">Na mesma página, configure qualquer outra configuração de convidado necessária.</span><span class="sxs-lookup"><span data-stu-id="419cf-157">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="419cf-158">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="419cf-158">Click **Save**.</span></span>

<span data-ttu-id="419cf-159">Para obter instruções detalhadas, confira [Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="419cf-159">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="419cf-160">□ Etapa 4: configurar o compartilhamento no Office 365</span><span class="sxs-lookup"><span data-stu-id="419cf-160">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="419cf-161">Certifique-se de que os usuários possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="419cf-161">Make sure that users can add guests.</span></span> <span data-ttu-id="419cf-162">Veja como:</span><span class="sxs-lookup"><span data-stu-id="419cf-162">Here's how:</span></span>

1. <span data-ttu-id="419cf-163">No centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.</span><span class="sxs-lookup"><span data-stu-id="419cf-163">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="419cf-165">Em **compartilhamento**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="419cf-165">In **Sharing**, select **Edit**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="419cf-167">Defina **permitir que os usuários adicionem novos convidados a essa organização** para serem **ativados**e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="419cf-167">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="419cf-169">Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="419cf-169">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="419cf-170">□ Etapa 5: verificar a configuração de compartilhamento no SharePoint</span><span class="sxs-lookup"><span data-stu-id="419cf-170">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="419cf-171">Entre no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="419cf-171">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="419cf-172">Clique em **centro de administração**e selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="419cf-172">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="419cf-173">No centro de administração do SharePoint, selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="419cf-173">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="419cf-174">Certifique-se de que a opção **não permitir o compartilhamento fora da sua organização** *não* esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="419cf-174">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![A captura de tela mostra um exemplo de uma alternância de configurações online do SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="419cf-176">□ Etapa 6: Habilitar configurações específicas de canais</span><span class="sxs-lookup"><span data-stu-id="419cf-176">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="419cf-177">No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado para que os convidados possam criar, atualizar e excluir canais.</span><span class="sxs-lookup"><span data-stu-id="419cf-177">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="419cf-178">Além dos administradores, os proprietários da equipe podem definir essa configuração.</span><span class="sxs-lookup"><span data-stu-id="419cf-178">In addition to admins,  team owners can configure this setting.</span></span>

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="419cf-180">Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado no Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="419cf-180">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="419cf-181">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="419cf-181">Troubleshooting</span></span>

<span data-ttu-id="419cf-182">Se você tiver problemas para adicionar convidados no Microsoft Teams, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="419cf-182">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


