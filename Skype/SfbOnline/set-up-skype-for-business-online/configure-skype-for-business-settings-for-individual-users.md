---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 8659434542696ccb37a0353cd491cc0d01f01e30
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="55c8f-103">Administradores: Definir as configurações do Skype for Business para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="55c8f-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="55c8f-104">Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="55c8f-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="55c8f-105">Para fazer estas etapas em massa, incluímos links para cmdlets do Windows PowerShell que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="55c8f-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="55c8f-106">Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:</span><span class="sxs-lookup"><span data-stu-id="55c8f-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="55c8f-107">[Permitir que os usuários entrar em contato com o Skype externo para usuários comerciais](allow-users-to-contact-external-skype-for-business-users.md): permitem que sua organização use avançadas Skype para recursos corporativos (compartilhamento de desktops, procure por quem está online, etc) para se comunicar com pessoas em uma determinada confiáveis corporativos (federados).</span><span class="sxs-lookup"><span data-stu-id="55c8f-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="55c8f-108">O artigo também explica como bloquear a comunicação com domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="55c8f-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="55c8f-109">[Permitir que o Skype para usuários comerciais adicionar contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="55c8f-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="55c8f-110">Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.</span><span class="sxs-lookup"><span data-stu-id="55c8f-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="55c8f-111">Definir configurações gerais para um usuário</span><span class="sxs-lookup"><span data-stu-id="55c8f-111">Configure general settings for one user</span></span>
<span data-ttu-id="55c8f-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="55c8f-112"></span></span>

<span data-ttu-id="55c8f-113">Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55c8f-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="55c8f-114">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="55c8f-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="55c8f-115">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="55c8f-116">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="55c8f-118">Selecione quais usuários você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="55c8f-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="55c8f-119">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="55c8f-121">Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="55c8f-122">**Opção**</span><span class="sxs-lookup"><span data-stu-id="55c8f-122">**Option**</span></span>|<span data-ttu-id="55c8f-123">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="55c8f-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55c8f-124">Áudio e vídeo em HD</span><span class="sxs-lookup"><span data-stu-id="55c8f-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="55c8f-125">Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo e áudio, ou não permita que agendem nenhuma reunião (nenhum).</span><span class="sxs-lookup"><span data-stu-id="55c8f-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="55c8f-126">Gravar conversas e reuniões</span><span class="sxs-lookup"><span data-stu-id="55c8f-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="55c8f-127">Escolha o que esta pessoa tem permissão para gravar.</span><span class="sxs-lookup"><span data-stu-id="55c8f-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="55c8f-128">Essa opção não está disponível com Skype para básica de negócios.</span><span class="sxs-lookup"><span data-stu-id="55c8f-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="55c8f-129">Para fins de conformidade, desligue os recursos não arquivados</span><span class="sxs-lookup"><span data-stu-id="55c8f-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="55c8f-130">Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="55c8f-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="55c8f-131">Esta opção desativa a recursos que não são capturados quando você tem um [Bloqueio In-loco](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="55c8f-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="55c8f-132">Ele desativa os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="55c8f-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="55c8f-133">Transferência de arquivos usando mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="55c8f-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="55c8f-134">Páginas do OneNote compartilhadas</span><span class="sxs-lookup"><span data-stu-id="55c8f-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="55c8f-135">Anotações do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="55c8f-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="55c8f-136">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c8f-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="55c8f-137">Consulte [Gerenciando diretivas no Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="55c8f-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="55c8f-138">Bloquear comunicações externas</span><span class="sxs-lookup"><span data-stu-id="55c8f-138">Block external communications</span></span>
<span data-ttu-id="55c8f-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="55c8f-139"></span></span>

<span data-ttu-id="55c8f-140">Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55c8f-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="55c8f-141">Escolher **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="55c8f-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="55c8f-142">Escolha **Comunicações externas** e desmarque as opções conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="55c8f-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="55c8f-143">**Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.</span><span class="sxs-lookup"><span data-stu-id="55c8f-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="55c8f-144">**Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.</span><span class="sxs-lookup"><span data-stu-id="55c8f-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="55c8f-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-145">Click **Save**.</span></span>
    
<span data-ttu-id="55c8f-146">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c8f-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="55c8f-147">Consulte [Gerenciando communications no Skype para negócios Online com externo usuários e organizações](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="55c8f-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="55c8f-148">Editar configurações de conferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="55c8f-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="55c8f-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="55c8f-149"></span></span>

1. <span data-ttu-id="55c8f-150">Escolher **usuários**, selecione o usuário cujas configurações de conferência de áudio que você quer editar, e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="55c8f-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="55c8f-151">Escolha a **conferência de áudio**, selecione seu provedor de serviços de audioconferência, digite ou alterar as informações solicitadas e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55c8f-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="55c8f-152">**Configuração da audioconferência**</span><span class="sxs-lookup"><span data-stu-id="55c8f-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="55c8f-153">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="55c8f-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="55c8f-154">**Nome do provedor**</span><span class="sxs-lookup"><span data-stu-id="55c8f-154">**Provider name**</span></span> <br/> |<span data-ttu-id="55c8f-155">Escolha seu provedor da lista.</span><span class="sxs-lookup"><span data-stu-id="55c8f-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="55c8f-156">**Número de chamada tarifada** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="55c8f-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="55c8f-157">Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="55c8f-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="55c8f-158">Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, estes serão os números que estão definidos a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="55c8f-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="55c8f-159">Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55c8f-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="55c8f-160">**Número de chamada gratuita**</span><span class="sxs-lookup"><span data-stu-id="55c8f-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="55c8f-161">Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="55c8f-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="55c8f-162">Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, estes serão os números que estão definidos a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="55c8f-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="55c8f-163">Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55c8f-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="55c8f-164">**PIN e ID de conferência** (necessário)</span><span class="sxs-lookup"><span data-stu-id="55c8f-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="55c8f-165">O código PIN do participante ou conferência, usado para ingressar em reuniões que são agendadas pelo usuário e são fornecidos a partir de um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="55c8f-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="55c8f-166">Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, isso não será necessário.</span><span class="sxs-lookup"><span data-stu-id="55c8f-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="55c8f-167">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c8f-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="55c8f-168">Consulte [Definir convidam números incluídos no telefone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="55c8f-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="55c8f-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="55c8f-169">Related topics</span></span> 

[<span data-ttu-id="55c8f-170">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="55c8f-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="55c8f-171">Licenciamento de complementos do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55c8f-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 