---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
ms.openlocfilehash: f99c99fc291a2df71a3e47448e3cc8fcf01e371f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295139"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="2671b-103">Administradores: Definir as configurações do Skype for Business para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="2671b-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="2671b-104">Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="2671b-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="2671b-105">Para fazer estas etapas em massa, incluímos links para cmdlets do Windows PowerShell que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="2671b-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="2671b-106">Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:</span><span class="sxs-lookup"><span data-stu-id="2671b-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="2671b-107">[Permitir que os usuários entrar em contato com o Skype externo para usuários comerciais](allow-users-to-contact-external-skype-for-business-users.md): permitem que sua organização use avançadas Skype para recursos corporativos (compartilhamento de desktops, procure por quem está online, etc) para se comunicar com pessoas em uma determinada confiáveis corporativos (federados).</span><span class="sxs-lookup"><span data-stu-id="2671b-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="2671b-108">O artigo também explica como bloquear a comunicação com domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="2671b-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="2671b-109">[Permitir que o Skype para usuários comerciais adicionar contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="2671b-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="2671b-110">Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.</span><span class="sxs-lookup"><span data-stu-id="2671b-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="2671b-111">Definir configurações gerais para um usuário</span><span class="sxs-lookup"><span data-stu-id="2671b-111">Configure general settings for one user</span></span>
<span data-ttu-id="2671b-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="2671b-112"></span></span>

<span data-ttu-id="2671b-113">Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2671b-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="2671b-114">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="2671b-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="2671b-115">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="2671b-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="2671b-116">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2671b-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="2671b-117">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="2671b-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="2671b-119">Selecione quais usuários você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="2671b-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="2671b-120">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2671b-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="2671b-122">Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2671b-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="2671b-123">**Opção**</span><span class="sxs-lookup"><span data-stu-id="2671b-123">**Option**</span></span>|<span data-ttu-id="2671b-124">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2671b-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2671b-125">Áudio e vídeo em HD</span><span class="sxs-lookup"><span data-stu-id="2671b-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="2671b-126">Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo e áudio, ou não permita que agendem nenhuma reunião (nenhum).</span><span class="sxs-lookup"><span data-stu-id="2671b-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="2671b-127">Gravar conversas e reuniões</span><span class="sxs-lookup"><span data-stu-id="2671b-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="2671b-128">Escolha o que esta pessoa tem permissão para gravar.</span><span class="sxs-lookup"><span data-stu-id="2671b-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="2671b-129">Essa opção não está disponível com Skype para básica de negócios.</span><span class="sxs-lookup"><span data-stu-id="2671b-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="2671b-130">Para fins de conformidade, desligue os recursos não arquivados</span><span class="sxs-lookup"><span data-stu-id="2671b-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="2671b-131">Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="2671b-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="2671b-132">Esta opção desativa a recursos que não são capturados quando você tem um [Bloqueio In-loco](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2671b-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="2671b-133">Ele desativa os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="2671b-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="2671b-134">Transferência de arquivos usando mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="2671b-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="2671b-135">Páginas do OneNote compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2671b-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="2671b-136">Anotações do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2671b-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="2671b-137">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2671b-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="2671b-138">Consulte [Gerenciando diretivas no Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2671b-138">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="2671b-139">Bloquear comunicações externas</span><span class="sxs-lookup"><span data-stu-id="2671b-139">Block external communications</span></span>
<span data-ttu-id="2671b-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="2671b-140"></span></span>

<span data-ttu-id="2671b-141">Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2671b-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="2671b-142">Escolher **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="2671b-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="2671b-143">Escolha **Comunicações externas** e desmarque as opções conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="2671b-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="2671b-144">**Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.</span><span class="sxs-lookup"><span data-stu-id="2671b-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="2671b-145">**Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.</span><span class="sxs-lookup"><span data-stu-id="2671b-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="2671b-146">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2671b-146">Click **Save**.</span></span>
    
<span data-ttu-id="2671b-147">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2671b-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="2671b-148">Consulte [Gerenciando communications no Skype para negócios Online com externo usuários e organizações](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2671b-148">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="2671b-149">Editar configurações de conferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="2671b-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="2671b-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="2671b-150"></span></span>

1. <span data-ttu-id="2671b-151">Escolher **usuários**, selecione o usuário cujas configurações de conferência de áudio que você quer editar, e escolha **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="2671b-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="2671b-152">Escolha a **conferência de áudio**, selecione seu provedor de serviços de audioconferência, digite ou alterar as informações solicitadas e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2671b-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="2671b-153">**Configuração da audioconferência**</span><span class="sxs-lookup"><span data-stu-id="2671b-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="2671b-154">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2671b-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2671b-155">**Nome do provedor**</span><span class="sxs-lookup"><span data-stu-id="2671b-155">**Provider name**</span></span> <br/> |<span data-ttu-id="2671b-156">Escolha seu provedor da lista.</span><span class="sxs-lookup"><span data-stu-id="2671b-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="2671b-157">**Número de chamada tarifada** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="2671b-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="2671b-158">Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2671b-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="2671b-159">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2671b-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="2671b-160">Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2671b-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="2671b-161">**Número de chamada gratuita**</span><span class="sxs-lookup"><span data-stu-id="2671b-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="2671b-162">Para um ACP de terceiros, esses números de telefone são os que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2671b-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="2671b-163">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="2671b-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="2671b-164">Formate os números de como você deseja que apareçam na Skype para solicitações de reunião de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2671b-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="2671b-165">**PIN e ID de conferência** (necessário)</span><span class="sxs-lookup"><span data-stu-id="2671b-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="2671b-166">O código PIN do participante ou conferência, usado para ingressar em reuniões que são agendadas pelo usuário e são fornecidos a partir de um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2671b-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="2671b-167">Se o usuário está usando o Microsoft como um provedor de serviços de audioconferência, isso não será necessário.</span><span class="sxs-lookup"><span data-stu-id="2671b-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="2671b-168">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2671b-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="2671b-169">Consulte [Definir convidam números incluídos no telefone](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="2671b-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="2671b-170">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2671b-170">Related topics</span></span> 

[<span data-ttu-id="2671b-171">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2671b-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="2671b-172">Licenciamento de complementos do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2671b-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 