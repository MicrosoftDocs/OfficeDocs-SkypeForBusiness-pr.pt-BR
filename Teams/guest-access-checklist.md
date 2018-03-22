---
title: Lista de verificação de acesso de convidado de equipes do Microsoft
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Use esta lista de verificação para ajudar a configurar o acesso de convidado no Microsoft Access de convidado equipes.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="11da4-103">Lista de verificação de acesso de convidado de equipes</span><span class="sxs-lookup"><span data-stu-id="11da4-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="11da4-104">Use esta lista de verificação para ajudá-lo a ativar e configurar o recurso de acesso de convidado no Microsoft Teams acordo com as preferências de sua organização.</span><span class="sxs-lookup"><span data-stu-id="11da4-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="11da4-105">Acesso de convidado Enable □ no nível de locatário</span><span class="sxs-lookup"><span data-stu-id="11da4-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="11da4-106">No mínimo, você deve ativar Teams da Microsoft para todos os usuários do tipo de licença **Convidado**.</span><span class="sxs-lookup"><span data-stu-id="11da4-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="11da4-107">Para obter instruções detalhadas, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="11da4-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Captura de tela mostra um exemplo de uma alternância de configurações de equipes](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="11da4-109">□ Habilitar configurações específicas para canais</span><span class="sxs-lookup"><span data-stu-id="11da4-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="11da4-110">No aplicativo de equipes, no nível equipe individuais, configure permissões de convidado para que os convidados podem criar, atualizar e excluir canais.</span><span class="sxs-lookup"><span data-stu-id="11da4-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="11da4-111">Além dos administradores, os proprietários de equipe podem configurar essa definição.</span><span class="sxs-lookup"><span data-stu-id="11da4-111">In addition to admins,  team owners can configure this setting.</span></span>

![Captura de tela mostra um exemplo de uma alternância de configurações de equipe/canal](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="11da4-113">Para obter mais informações, incluindo vídeos de instruções, consulte [acesso de convidado em equipes da Microsoft](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="11da4-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="11da4-114">□ Configurar o compartilhamento no Office 365</span><span class="sxs-lookup"><span data-stu-id="11da4-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="11da4-115">□ Certifique-se de que os usuários podem adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="11da4-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="11da4-116">Veja como:</span><span class="sxs-lookup"><span data-stu-id="11da4-116">Here's how:</span></span>

1. <span data-ttu-id="11da4-117">No Centro de administração do Office 365, vá para **configurações** > **de segurança e privacidade**.</span><span class="sxs-lookup"><span data-stu-id="11da4-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="11da4-118">![Captura de tela mostra um exemplo de um configurações de serviços](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="11da4-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="11da4-119">Em **compartilhamento**, selecione **Editar**. ![Captura de tela mostra um exemplo de um botão de editar configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="11da4-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="11da4-120">Definir **permitem aos usuários adicionar novos convidados para esta organização** para **ativado**e clique em **Salvar**. ![Captura de tela mostra um exemplo de uma alternância de configurações de compartilhamento](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="11da4-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="11da4-121">Essa configuração equivale à configuração de **membros podem convidar** em configurações do usuário > usuários externos em Azure AD.</span><span class="sxs-lookup"><span data-stu-id="11da4-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="11da4-122">□ Configurar grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="11da4-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="11da4-123">No Centro de administração do Office 365, vá para **configurações** > **Serviços & suplementos** > **Grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="11da4-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="11da4-124">Certifique-se de **Permitir que os membros do grupo fora o conteúdo de grupo de acesso de organização** está definida como **On**.</span><span class="sxs-lookup"><span data-stu-id="11da4-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="11da4-125">Se essa configuração estiver desativada, os convidados não conseguirá acessar nenhum conteúdo de grupo.</span><span class="sxs-lookup"><span data-stu-id="11da4-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="11da4-126">Certifique-se de **Permitir que os proprietários de grupo adicionar pessoas fora da organização para grupos** está definida como **On**.</span><span class="sxs-lookup"><span data-stu-id="11da4-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="11da4-127">Se essa configuração estiver desativada, os proprietários de equipe não conseguirá adicionar novos convidados.</span><span class="sxs-lookup"><span data-stu-id="11da4-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="11da4-128">(No entanto, se um administrador tivesse adicionado a um usuário convidado para o Windows Azure AD, em seguida, o proprietário de equipe seria capaz de adicionar o usuário para a equipe.) No mínimo, essa configuração deve ser "ligado" suportar o acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="11da4-128">(However, if an admin had added a guest user to Azure AD, then the Team owner would be able to add that user to the Team.) At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="11da4-129">Para obter instruções detalhadas sobre como definir essas configurações, consulte a seção "Grupos de 365 Office" em [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md) e [permitir/bloquear o acesso de convidado a grupos do Office 365](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="11da4-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="11da4-130">Configurar definições do □ no Azure AD para empresas (B2B)</span><span class="sxs-lookup"><span data-stu-id="11da4-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="11da4-131">Entrar no https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="11da4-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="11da4-132">No painel esquerdo, clique em **do Azure Active directory** .</span><span class="sxs-lookup"><span data-stu-id="11da4-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="11da4-133">Em **Gerenciar**, clique em **configurações do usuário**.</span><span class="sxs-lookup"><span data-stu-id="11da4-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="11da4-134">Em **usuários externos**, certifique-se de **que membros podem convidar** estiver definida como **Sim**. ![Captura de tela mostra um exemplo de uma alternância de configurações de AAD.</span><span class="sxs-lookup"><span data-stu-id="11da4-134">In **External users**, make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="11da4-135">**Os membros podem convidar** ► no mínimo para dar suporte a convidados, deve ser definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="11da4-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="11da4-136">Se você define **membros podem convidar** como **não** e habilita o acesso de convidado no Office 365 grupos e Teams da Microsoft, os administradores podem controlar a convites de convidado para seu diretório.</span><span class="sxs-lookup"><span data-stu-id="11da4-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="11da4-137">Depois que os convidados estão no diretório, podem ser adicionados às equipes pelos membros não seja o administrador (proprietários da equipe).</span><span class="sxs-lookup"><span data-stu-id="11da4-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="11da4-138">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="11da4-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="11da4-139">Configuração de compartilhamento □ Verify no SharePoint</span><span class="sxs-lookup"><span data-stu-id="11da4-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="11da4-140">Entre no Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="11da4-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="11da4-141">Clique em **Administração Central**e selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="11da4-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="11da4-142">No Centro de administração do SharePoint, selecione **compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="11da4-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="11da4-143">Verifique se a opção para **não permitir o compartilhamento fora da sua organização** *não* está selecionado. ![Captura de tela mostra um exemplo de uma alternância de configurações de Sparepoint Online.</span><span class="sxs-lookup"><span data-stu-id="11da4-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="11da4-144">Tipos e licenças de conta Verify □</span><span class="sxs-lookup"><span data-stu-id="11da4-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="11da4-145">**Conta licenciada para equipes**: para uma conta de "Convidado" como raiz com uma conta de usuário real em alguns outro locatário do Office 365, essa conta de usuário real deve ser licenciada para equipes para "Convidado".</span><span class="sxs-lookup"><span data-stu-id="11da4-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="11da4-146">**Conta deve ser escola do Office 365 ou trabalhar conta, ou conta MSA**: atualmente, os usuários que têm um endereço de email correspondente a um Windows Azure Active Directory, trabalho do Office 365 ou conta escola ou uma conta da Microsoft (MSA) podem ser adicionados como um usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="11da4-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="11da4-147">Ambiente de Configure □</span><span class="sxs-lookup"><span data-stu-id="11da4-147">□ Configure environment</span></span>


<span data-ttu-id="11da4-148">Convidados que são necessárias para usar a autenticação multifator (MFA), se for necessário para o inquilino de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="11da4-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="11da4-149">Para obter mais detalhes, consulte [modelos de identidade e autenticação no equipes da Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="11da4-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="11da4-150">Limitações de Noções básicas sobre □ para convidados</span><span class="sxs-lookup"><span data-stu-id="11da4-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="11da4-151">A experiência de convidado tem limitações por design.</span><span class="sxs-lookup"><span data-stu-id="11da4-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="11da4-152">Verifique se que você compreende a experiência de convidado, então você não tenta corrigir algo que não é um problema.</span><span class="sxs-lookup"><span data-stu-id="11da4-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="11da4-153">Por exemplo, aqui está uma lista de alguns da funcionalidade que não está disponível para um convidado em Teams da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="11da4-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="11da4-154">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="11da4-154">OneDrive for Business</span></span>
- <span data-ttu-id="11da4-155">Pesquisa de pessoas fora de equipes</span><span class="sxs-lookup"><span data-stu-id="11da4-155">People search outside of Teams</span></span>
- <span data-ttu-id="11da4-156">Calendário, reuniões agendadas ou detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="11da4-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="11da4-157">PSTN</span><span class="sxs-lookup"><span data-stu-id="11da4-157">PSTN</span></span>
- <span data-ttu-id="11da4-158">Organograma</span><span class="sxs-lookup"><span data-stu-id="11da4-158">Organization chart</span></span>
- <span data-ttu-id="11da4-159">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="11da4-159">Create or revise a team</span></span>
- <span data-ttu-id="11da4-160">Navegar para uma equipe</span><span class="sxs-lookup"><span data-stu-id="11da4-160">Browse for a team</span></span>
- <span data-ttu-id="11da4-161">Carregar arquivos para um bate-papo entre duas pessoas</span><span class="sxs-lookup"><span data-stu-id="11da4-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="11da4-162">Para obter mais detalhes, consulte [o que a experiência de convidado é como](guest-experience.md) e [acesso de convidado em grupos do Office 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="11da4-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="11da4-163">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="11da4-163">Troubleshooting</span></span>

<span data-ttu-id="11da4-164">Se você tiver problemas com a adição de convidados no Teams da Microsoft, consulte o [Guia de solução de problemas de acesso de convidado](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="11da4-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


