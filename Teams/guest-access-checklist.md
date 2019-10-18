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
ms.openlocfilehash: e7f019f2260b1e86b422f8b4238439fbd2f1607a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563487"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="fff06-103">Lista de verificação de acesso de convidados do teams</span><span class="sxs-lookup"><span data-stu-id="fff06-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="fff06-104">Use esta lista de verificação para ajudá-lo a habilitar e configurar o recurso de acesso de convidado no Microsoft Teams de acordo com as preferências da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fff06-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="fff06-105">Para as restrições de colaboração [, consulte Habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="fff06-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="fff06-106">Entender as limitações dos convidados</span><span class="sxs-lookup"><span data-stu-id="fff06-106">Understand the limitations for guests</span></span>

<span data-ttu-id="fff06-107">A experiência de convidado tem limitações por meio do design.</span><span class="sxs-lookup"><span data-stu-id="fff06-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="fff06-108">Certifique-se de entender a experiência de convidado para não tentar corrigir algo que não seja um problema.</span><span class="sxs-lookup"><span data-stu-id="fff06-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="fff06-109">Por exemplo, veja a seguir uma lista de alguns dos recursos que não estão disponíveis para um convidado no Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="fff06-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="fff06-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="fff06-110">OneDrive for Business</span></span>
- <span data-ttu-id="fff06-111">Pesquisa de pessoas fora do teams</span><span class="sxs-lookup"><span data-stu-id="fff06-111">People search outside of Teams</span></span>
- <span data-ttu-id="fff06-112">Calendário, reuniões agendadas ou detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="fff06-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="fff06-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="fff06-113">PSTN</span></span>
- <span data-ttu-id="fff06-114">Organograma</span><span class="sxs-lookup"><span data-stu-id="fff06-114">Organization chart</span></span>
- <span data-ttu-id="fff06-115">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="fff06-115">Create or revise a team</span></span>
- <span data-ttu-id="fff06-116">Procurar uma equipe</span><span class="sxs-lookup"><span data-stu-id="fff06-116">Browse for a team</span></span>
- <span data-ttu-id="fff06-117">Carregar arquivos para um chat de pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="fff06-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="fff06-118">Os convidados ainda podem pesquisar e localizar usuários (fora de sua equipe) se saberem a identificação de email completa do usuário.</span><span class="sxs-lookup"><span data-stu-id="fff06-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="fff06-119">Para evitar isso, os administradores de ti podem usar padrões como [pesquisa de diretório em escopo](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) que têm a capacidade de restringir convidados à sua GAL virtual.</span><span class="sxs-lookup"><span data-stu-id="fff06-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="fff06-120">Para obter mais detalhes, consulte o [que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="fff06-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="fff06-121">Acesso de convidado vs. acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="fff06-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="fff06-122">No momento, o Microsoft Teams não é compatível com a função de convidado de convidado.</span><span class="sxs-lookup"><span data-stu-id="fff06-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="fff06-123">Pelo menos a opção "os membros podem convidar" deve ser definida como "Sim" para que o acesso de convidado funcione no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fff06-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="fff06-124">Se você definir "os membros podem convidar" para "não" e habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="fff06-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="fff06-125">Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="fff06-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="fff06-126">Se seus convidados estiverem vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="fff06-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="fff06-127">O acesso de convidado no Microsoft Teams usa o Azure Active Directory (Azure AD) Business to Business (B2B) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="fff06-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="fff06-128">Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para entender os requisitos de licenciamento que a sua organização tem para que seus usuários possam convidar convidados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fff06-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="fff06-129">Lembre-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="fff06-129">A few things to remember:</span></span>

- <span data-ttu-id="fff06-130">Convidados são usuários de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fff06-130">Guests are users outside your organization.</span></span> <span data-ttu-id="fff06-131">Seus funcionários, prestadores de no local, agentes no local e assim por diante não podem ser adicionados como convidados.</span><span class="sxs-lookup"><span data-stu-id="fff06-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="fff06-132">O mesmo se aplica às suas afiliadas.</span><span class="sxs-lookup"><span data-stu-id="fff06-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="fff06-133">As licenças de convidado são contadas em relação à organização que convida.</span><span class="sxs-lookup"><span data-stu-id="fff06-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="fff06-134">Considere isso quando você calcular o número de licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="fff06-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="fff06-135">As licenças são contadas em relação à sua organização se os convidados convidados vierem de outro locatário do Office 365 ou estiverem usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="fff06-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="fff06-136">□ Etapa 1: definir as configurações do Azure AD para empresas</span><span class="sxs-lookup"><span data-stu-id="fff06-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="fff06-137">Entre no [portal do Azure](https://portal.azure.com) como um administrador de locatários.</span><span class="sxs-lookup"><span data-stu-id="fff06-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="fff06-138">Selecione**as configurações de usuário** **do Azure Active Directory** > **Users** > .</span><span class="sxs-lookup"><span data-stu-id="fff06-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="fff06-139">Em **usuários externos**, selecione **gerenciar configurações de colaboração externa**.</span><span class="sxs-lookup"><span data-stu-id="fff06-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="fff06-140">As **configurações de colaboração externa** também estão disponíveis na página **relações organizacionais** .</span><span class="sxs-lookup"><span data-stu-id="fff06-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="fff06-141">No Azure Active Directory, em **gerenciar**, acesse > **configurações**de **relações organizacionais**.</span><span class="sxs-lookup"><span data-stu-id="fff06-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="fff06-142">Na página **configurações de colaboração externas** , escolha as políticas que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="fff06-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="fff06-143">**As permissões de usuários convidados são limitadas**: esta política determina permissões para convidados em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="fff06-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="fff06-144">Selecione **Sim** para bloquear convidados de determinadas tarefas de diretório, como enumerar usuários, grupos ou outros recursos de diretório.</span><span class="sxs-lookup"><span data-stu-id="fff06-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="fff06-145">Selecione **não** para dar aos convidados o mesmo acesso aos dados do diretório como usuários regulares em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="fff06-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="fff06-146">**Administradores e usuários na função de convite de convidado podem convidar**: para permitir que administradores e usuários na função "convidador de convidado" possam convidar convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fff06-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="fff06-147">**Os membros podem convidar**: para permitir que membros que não sejam administradores do seu diretório convidem convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fff06-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="fff06-148">Se você definir que **os membros podem convidar** para **não** e, em seguida, habilitar o acesso de convidado nos grupos do Office 365 e no Microsoft Teams, os administradores poderão controlar os convites convidados para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="fff06-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="fff06-149">Depois que os convidados estiverem no diretório, eles poderão ser adicionados às equipes por membros não-administradores que sejam proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="fff06-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="fff06-150">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="fff06-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="fff06-151">**Convidados podem convidar**: para permitir que os convidados convidem outros convidados, defina essa política como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fff06-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="fff06-152">**Habilitar a senha de senha única para convidados (visualização)**: para obter mais informações sobre o recurso de senha de uso único, consulte [autenticação de senha única (visualização) de email](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="fff06-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>

   - <span data-ttu-id="fff06-153">**Restrições de colaboração**: para obter mais informações sobre como permitir ou bloquear convites para domínios específicos, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="fff06-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
    
## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="fff06-154">□ Etapa 2: configurar grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="fff06-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="fff06-155">No centro de administração do Microsoft 365, vá para **configurações** > de**Serviços & suplementos** > **do Office 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="fff06-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="fff06-156">Verifique se **deixar que os membros do grupo fora do conteúdo do grupo de acesso à organização** estejam definidos como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="fff06-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="fff06-157">Se essa configuração estiver desativada, os convidados não poderão acessar qualquer conteúdo do grupo.</span><span class="sxs-lookup"><span data-stu-id="fff06-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="fff06-158">Certifique-se de **que o recurso proprietários de grupos Adicione pessoas de fora da organização a grupos** esteja definido como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="fff06-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="fff06-159">Se essa configuração estiver desativada, os proprietários da equipe não poderão adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="fff06-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="fff06-160">No mínimo, essa configuração deve estar ativada para dar suporte ao acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="fff06-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![A captura de tela mostra as alternâncias dos grupos do Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="fff06-162">Para obter instruções detalhadas sobre como definir essas configurações, consulte [gerenciar o acesso de convidados nos grupos do Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) e [controlar o acesso de convidados a grupos do Office 365](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="fff06-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="fff06-163">□ Etapa 3: habilitar o acesso de convidado no nível do locatário</span><span class="sxs-lookup"><span data-stu-id="fff06-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="fff06-164">No mínimo, você deve ativar o acesso de convidado para o Microsoft Teams no **centro de administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="fff06-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="fff06-165">No centro de administração do Teams, selecione o > **acesso de convidados**às **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="fff06-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="fff06-166">Defina a opção **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="fff06-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![A captura de tela mostra um exemplo de alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="fff06-168">Na mesma página, configure qualquer outra configuração de convidado necessária.</span><span class="sxs-lookup"><span data-stu-id="fff06-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="fff06-169">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fff06-169">Click **Save**.</span></span>

<span data-ttu-id="fff06-170">Para obter instruções detalhadas, confira [Ativar ou desativar o acesso de convidado ao Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="fff06-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="fff06-171">□ Etapa 4: configurar o compartilhamento no Office 365</span><span class="sxs-lookup"><span data-stu-id="fff06-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="fff06-172">Certifique-se de que os usuários possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="fff06-172">Make sure that users can add guests.</span></span> <span data-ttu-id="fff06-173">Veja como:</span><span class="sxs-lookup"><span data-stu-id="fff06-173">Here's how:</span></span>

1. <span data-ttu-id="fff06-174">No centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.</span><span class="sxs-lookup"><span data-stu-id="fff06-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![A captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="fff06-176">Em **compartilhamento**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fff06-176">In **Sharing**, select **Edit**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="fff06-178">Defina **permitir que os usuários adicionem novos convidados a essa organização** para serem **ativados**e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="fff06-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![A captura de tela mostra um exemplo de alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="fff06-180">Essa configuração é equivalente à configuração os **Membros podem convidar** em **configurações** > do usuário**usuários externos** do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fff06-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="fff06-181">□ Etapa 5: verificar a configuração de compartilhamento no SharePoint</span><span class="sxs-lookup"><span data-stu-id="fff06-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="fff06-182">Entre no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fff06-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="fff06-183">Clique em **centro de administração**e selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="fff06-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="fff06-184">No centro de administração do SharePoint, selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="fff06-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="fff06-185">Certifique-se de que a opção **não permitir o compartilhamento fora da sua organização** *não* esteja selecionada.</span><span class="sxs-lookup"><span data-stu-id="fff06-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![A captura de tela mostra um exemplo de uma alternância de configurações online do SparePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="fff06-187">□ Etapa 6: Habilitar configurações específicas de canais</span><span class="sxs-lookup"><span data-stu-id="fff06-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="fff06-188">No aplicativo Teams, no nível individual da equipe, configure as permissões de convidado para que os convidados possam criar, atualizar e excluir canais.</span><span class="sxs-lookup"><span data-stu-id="fff06-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="fff06-189">Além dos administradores, os proprietários da equipe podem definir essa configuração.</span><span class="sxs-lookup"><span data-stu-id="fff06-189">In addition to admins,  team owners can configure this setting.</span></span>

![A captura de tela mostra um exemplo de alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="fff06-191">Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado no Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="fff06-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="fff06-192">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="fff06-192">Troubleshooting</span></span>

<span data-ttu-id="fff06-193">Se você tiver problemas para adicionar convidados no Microsoft Teams, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="fff06-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


