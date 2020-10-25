---
title: Administradores Definir as configurações do Skype for Business para usuários individuais
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: cf54637bda51a7994121035b3db1585213c56c00
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753416"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="73952-103">Administradores: Definir as configurações do Skype for Business para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="73952-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73952-104">O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado).</span><span class="sxs-lookup"><span data-stu-id="73952-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="73952-105">Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="73952-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="73952-106">Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="73952-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="73952-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="73952-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="73952-108">Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="73952-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="73952-109">Para executar essas etapas em massa, incluímos links para os cmdlets do Windows PowerShell que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="73952-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="73952-110">Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:</span><span class="sxs-lookup"><span data-stu-id="73952-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="73952-111">[Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md): você pode permitir que sua organização use recursos avançados do Skype for Business (Compartilhe áreas de trabalho, procure quem está online etc.) para se comunicar com as pessoas de uma empresa confiável (federada) específica.</span><span class="sxs-lookup"><span data-stu-id="73952-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="73952-112">O artigo também explica como bloquear a comunicação com domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="73952-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="73952-113">[Deixe que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="73952-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="73952-114">Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.</span><span class="sxs-lookup"><span data-stu-id="73952-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="73952-115">Definir configurações gerais para um usuário</span><span class="sxs-lookup"><span data-stu-id="73952-115">Configure general settings for one user</span></span>
<span data-ttu-id="73952-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="73952-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="73952-117">Você deve ter [permissões de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="73952-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="73952-118">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="73952-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="73952-119">Entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="73952-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="73952-120">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="73952-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="73952-121">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="73952-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="73952-123">Selecione quais usuários você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="73952-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="73952-124">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="73952-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="73952-126">Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73952-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="73952-127">**Opção**</span><span class="sxs-lookup"><span data-stu-id="73952-127">**Option**</span></span>|<span data-ttu-id="73952-128">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="73952-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73952-129">Áudio e vídeo em HD</span><span class="sxs-lookup"><span data-stu-id="73952-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="73952-130">Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo ou não permita que elas agendem reuniões (nenhuma).</span><span class="sxs-lookup"><span data-stu-id="73952-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="73952-131">Gravar conversas e reuniões</span><span class="sxs-lookup"><span data-stu-id="73952-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="73952-132">Escolha o que esta pessoa tem permissão para gravar.</span><span class="sxs-lookup"><span data-stu-id="73952-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="73952-133">Essa opção não está disponível com o Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="73952-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="73952-134">Para fins de conformidade, desligue os recursos não arquivados</span><span class="sxs-lookup"><span data-stu-id="73952-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="73952-135">Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="73952-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="73952-136">Selecionar essa opção desativa os recursos que não são capturados quando você tem um [bloqueio in-loco](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) configurado no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="73952-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="73952-137">Ele desativa os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="73952-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="73952-138">Transferência de arquivos usando mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="73952-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="73952-139">Páginas do OneNote compartilhadas</span><span class="sxs-lookup"><span data-stu-id="73952-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="73952-140">Anotações do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="73952-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="73952-141">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73952-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="73952-142">Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="73952-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="73952-143">Bloquear comunicações externas</span><span class="sxs-lookup"><span data-stu-id="73952-143">Block external communications</span></span>
<span data-ttu-id="73952-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="73952-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="73952-145">Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.</span><span class="sxs-lookup"><span data-stu-id="73952-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="73952-146">Escolha **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![ Editar ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="73952-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="73952-147">Escolha **Comunicações externas** e desmarque as opções conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="73952-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="73952-148">**Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.</span><span class="sxs-lookup"><span data-stu-id="73952-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="73952-149">**Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.</span><span class="sxs-lookup"><span data-stu-id="73952-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="73952-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73952-150">Click **Save**.</span></span>
    
<span data-ttu-id="73952-151">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73952-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="73952-152">Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="73952-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="73952-153">Editar as configurações de audioconferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="73952-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="73952-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="73952-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="73952-155">Escolha **usuários**, selecione o usuário cujas configurações de audioconferência você deseja editar e escolha **Editar** ![ Editar ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="73952-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="73952-156">Escolha **videoconferência**, selecione seu provedor de serviços de audioconferência, digite ou altere as informações solicitadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="73952-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="73952-157">**Configuração da audioconferência**</span><span class="sxs-lookup"><span data-stu-id="73952-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="73952-158">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73952-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73952-159">**Nome do provedor**</span><span class="sxs-lookup"><span data-stu-id="73952-159">**Provider name**</span></span> <br/> |<span data-ttu-id="73952-160">Escolha seu provedor na lista.</span><span class="sxs-lookup"><span data-stu-id="73952-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="73952-161">**Número de chamada tarifada** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="73952-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="73952-162">Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="73952-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="73952-163">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="73952-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="73952-164">Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73952-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="73952-165">**Número de chamada gratuita**</span><span class="sxs-lookup"><span data-stu-id="73952-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="73952-166">Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="73952-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="73952-167">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="73952-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="73952-168">Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73952-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="73952-169">**ID de conferência e PIN** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="73952-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="73952-170">O PIN do participante ou o código de conferência usado para ingressar em reuniões agendadas por esse usuário e são fornecidas por um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="73952-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="73952-171">Se o usuário estiver usando a Microsoft como provedor de serviços de audioconferência, isso não será necessário.</span><span class="sxs-lookup"><span data-stu-id="73952-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="73952-172">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73952-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="73952-173">Consulte [definir os números de telefone incluídos nos convites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="73952-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="73952-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="73952-174">Related topics</span></span> 

[<span data-ttu-id="73952-175">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="73952-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="73952-176">Licenciamento de complementos do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73952-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
