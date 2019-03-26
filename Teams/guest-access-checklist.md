---
title: Lista de verificação de acesso de convidado Teams da Microsoft
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: 68beeba403f6a64e194594d5bd40b985c8051dc6
ms.sourcegitcommit: fba1151c968aa2c43d0c5b42b889b2cdd8dba3cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2019
ms.locfileid: "30795582"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="f6fc5-103">Lista de verificação de acesso de convidado equipes</span><span class="sxs-lookup"><span data-stu-id="f6fc5-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="f6fc5-104">Use esta lista de verificação para ajudá-lo a ativar e configurar o recurso de acesso de convidado no Microsoft Teams acordo com as preferências de sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="f6fc5-105">Compreender as limitações de convidados</span><span class="sxs-lookup"><span data-stu-id="f6fc5-105">Understand the limitations for guests</span></span>

<span data-ttu-id="f6fc5-106">A experiência de convidado tem limitações por design.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="f6fc5-107">Verifique se que você compreende a experiência de convidado, então você não tenta corrigir algo que não é um problema.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="f6fc5-108">Por exemplo, aqui está uma lista de alguns da funcionalidade que não está disponível para um convidado em Teams da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f6fc5-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="f6fc5-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f6fc5-109">OneDrive for Business</span></span>
- <span data-ttu-id="f6fc5-110">Pesquisa de pessoas fora de equipes</span><span class="sxs-lookup"><span data-stu-id="f6fc5-110">People search outside of Teams</span></span>
- <span data-ttu-id="f6fc5-111">Calendário, reuniões agendadas ou detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="f6fc5-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="f6fc5-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="f6fc5-112">PSTN</span></span>
- <span data-ttu-id="f6fc5-113">Organograma</span><span class="sxs-lookup"><span data-stu-id="f6fc5-113">Organization chart</span></span>
- <span data-ttu-id="f6fc5-114">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="f6fc5-114">Create or revise a team</span></span>
- <span data-ttu-id="f6fc5-115">Navegar para uma equipe</span><span class="sxs-lookup"><span data-stu-id="f6fc5-115">Browse for a team</span></span>
- <span data-ttu-id="f6fc5-116">Carregar arquivos para um bate-papo entre duas pessoas</span><span class="sxs-lookup"><span data-stu-id="f6fc5-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="f6fc5-117">Para obter mais detalhes, consulte [o que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="f6fc5-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="f6fc5-118">Acesso de convidado versus acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="f6fc5-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="f6fc5-119">Se seus convidados estão vendo erros de licença</span><span class="sxs-lookup"><span data-stu-id="f6fc5-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="f6fc5-120">Acesso de convidado no Microsoft Teams usa o Azure Active Directory corporativos para negócios (B2B) e seu modelo de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="f6fc5-121">Se você está vendo a erros de licenciamento, certifique-se ler as orientações de licenciamento B2B para entender os requisitos de licenciamento que sua organização tem para que os usuários sejam capazes de convidar as pessoas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="f6fc5-122">Algumas coisas lembrar:</span><span class="sxs-lookup"><span data-stu-id="f6fc5-122">A few things to remember:</span></span>

- <span data-ttu-id="f6fc5-123">Para cada paga licença do Azure AD que você pode atribuir a um usuário, os usuários podem convidar usuários de convidado até cinco sob a permissão de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="f6fc5-124">Convidados são usuários fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-124">Guests are users outside your organization.</span></span> <span data-ttu-id="f6fc5-125">Seus funcionários, prestadores de serviços no local, os operadores no local e assim por diante, não podem ser adicionados como convidados.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="f6fc5-126">O mesmo se aplica às suas afiliadas.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="f6fc5-127">As licenças de convidado são contadas contra a organização convidando.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="f6fc5-128">Considere isso ao calcular o número de licenças que necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="f6fc5-129">As licenças são contadas contra a sua organização se os convidados vêm de outro locatário do Office 365 ou estiver usando seus endereços de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="f6fc5-130">□ Etapa 1: definir as configurações no Azure AD business-to-business</span><span class="sxs-lookup"><span data-stu-id="f6fc5-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="f6fc5-131">Entrar no https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="f6fc5-132">No painel esquerdo, clique em **do Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="f6fc5-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="f6fc5-133">Em **Gerenciar**, clique em **configurações do usuário**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="f6fc5-134">Em **usuários externos**, clique em **configurações de gerenciar externo de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="f6fc5-135">Na página **configurações de colaboração externa** , certifique-se de **que membros podem convidar** estiver definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="f6fc5-136">Captura de tela mostra um exemplo de uma alternância de configurações AAD.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-136">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="f6fc5-137">Para suportar os convidados, **os membros podem convidar** deve ser definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="f6fc5-138">Se você define **membros podem convidar** como **não** e, em seguida, habilita o acesso de convidado no Office 365 grupos e Teams da Microsoft, os administradores podem controlar a convites de convidado para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="f6fc5-139">Depois que os convidados estão no diretório, podem ser adicionados às equipes pelos membros não seja o administrador que são proprietários de equipe.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="f6fc5-140">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f6fc5-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="f6fc5-141">□ Etapa 2: configurar grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="f6fc5-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="f6fc5-142">No Centro de administração do Microsoft 365, vá para **configurações** > **Serviços & suplementos** > **Grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="f6fc5-143">Certifique-se de **Permitir que os membros do grupo fora o conteúdo de grupo de acesso de organização** está definida como **On**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="f6fc5-144">Se essa configuração estiver desativada, os convidados não conseguirá acessar nenhum conteúdo de grupo.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="f6fc5-145">Certifique-se de **Permitir que os proprietários de grupo adicionar pessoas fora da organização para grupos** está definida como **On**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="f6fc5-146">Se essa configuração estiver desativada, os proprietários de equipe não conseguirá adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="f6fc5-147">No mínimo, essa configuração deve ser no suporte ao acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Captura de tela mostra as grupos comuta o Office 365](media/guest-access-checklist-office365.png)

<span data-ttu-id="f6fc5-149">Para obter instruções detalhadas sobre como definir essas configurações, consulte a seção "Office 365 grupos" em [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md)e [Gerenciar o acesso de convidado em grupos do Office 365](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) .</span><span class="sxs-lookup"><span data-stu-id="f6fc5-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="f6fc5-150">□ Etapa 3: habilitar o acesso de convidado a nível de locatário</span><span class="sxs-lookup"><span data-stu-id="f6fc5-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="f6fc5-151">No mínimo, você deve ativar acesso como convidado for Microsoft Teams sob o **Centro de administração de equipes da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="f6fc5-152">No Centro de administração de equipes, selecione **configurações de toda a organização** > **acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="f6fc5-153">Defina a opção de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Captura de tela mostra um exemplo de uma alternância de configurações de equipes](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="f6fc5-155">Nesta página mesmo, configure qualquer outra configuração de convidado que você precisa.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="f6fc5-156">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-156">Click **Save**.</span></span>

<span data-ttu-id="f6fc5-157">Para obter instruções detalhadas, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="f6fc5-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="f6fc5-158">□ Etapa 4: configurar o compartilhamento no Office 365</span><span class="sxs-lookup"><span data-stu-id="f6fc5-158">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="f6fc5-159">Certifique-se de que os usuários podem adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-159">Make sure that users can add guests.</span></span> <span data-ttu-id="f6fc5-160">Veja como:</span><span class="sxs-lookup"><span data-stu-id="f6fc5-160">Here's how:</span></span>

1. <span data-ttu-id="f6fc5-161">No Centro de administração do Microsoft 365, vá para **configurações** > **segurança & privacidade**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Captura de tela mostra um exemplo de configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="f6fc5-163">Em **compartilhamento**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-163">In **Sharing**, select **Edit**.</span></span>

     ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="f6fc5-165">Definir **permitem aos usuários adicionar novos convidados para esta organização** para **ativado**e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="f6fc5-167">Essa configuração equivale à configuração de **membros podem convidar** em **configurações do usuário** > **usuários externos** no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="f6fc5-168">□ Etapa 5: verificar a configuração de compartilhamento no SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6fc5-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="f6fc5-169">Entre no Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="f6fc5-170">Clique em **Administração Central**e selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="f6fc5-171">No Centro de administração do SharePoint, selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="f6fc5-172">Verifique se a opção para **não permitir o compartilhamento fora da sua organização** *não* está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Captura de tela mostra um exemplo de uma alternância de configurações SparePoint Online.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="f6fc5-174">□ Etapa 6: Habilitar configurações específicas para canais</span><span class="sxs-lookup"><span data-stu-id="f6fc5-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="f6fc5-175">No aplicativo de equipes, no nível equipe individuais, configure permissões de convidado para que os convidados podem criar, atualizar e excluir canais.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="f6fc5-176">Além dos administradores, os proprietários de equipe podem configurar essa definição.</span><span class="sxs-lookup"><span data-stu-id="f6fc5-176">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de tela mostra um exemplo de uma alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="f6fc5-178">Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado em equipes da Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="f6fc5-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="f6fc5-179">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f6fc5-179">Troubleshooting</span></span>

<span data-ttu-id="f6fc5-180">Se você tiver problemas com a adição de convidados no Teams da Microsoft, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="f6fc5-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


