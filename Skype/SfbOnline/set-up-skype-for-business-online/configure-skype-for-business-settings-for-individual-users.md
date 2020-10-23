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
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739169"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="68e7c-103">Administradores: Definir as configurações do Skype for Business para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="68e7c-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68e7c-104">O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado).</span><span class="sxs-lookup"><span data-stu-id="68e7c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="68e7c-105">Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="68e7c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="68e7c-106">Para saber mais, confira [gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="68e7c-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="68e7c-107">Este artigo explica como os administradores configuram o Skype for Business para um pequeno número de usuários.</span><span class="sxs-lookup"><span data-stu-id="68e7c-107">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="68e7c-108">Para executar essas etapas em massa, incluímos links para os cmdlets do Windows PowerShell que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="68e7c-108">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="68e7c-109">Para permitir (ou impedir) que todos na empresa se comuniquem com pessoas externas, veja:</span><span class="sxs-lookup"><span data-stu-id="68e7c-109">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="68e7c-110">[Permitir que os usuários entrem em contato com usuários externos do Skype for Business](allow-users-to-contact-external-skype-for-business-users.md): você pode permitir que sua organização use recursos avançados do Skype for Business (Compartilhe áreas de trabalho, procure quem está online etc.) para se comunicar com as pessoas de uma empresa confiável (federada) específica.</span><span class="sxs-lookup"><span data-stu-id="68e7c-110">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="68e7c-111">O artigo também explica como bloquear a comunicação com domínios específicos.</span><span class="sxs-lookup"><span data-stu-id="68e7c-111">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="68e7c-112">[Deixe que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="68e7c-112">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="68e7c-113">Você pode permitir que sua organização use o Skype for Business para procurar usuários do aplicativo gratuito Skype e enviar mensagens instantâneas para eles.</span><span class="sxs-lookup"><span data-stu-id="68e7c-113">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="68e7c-114">Definir configurações gerais para um usuário</span><span class="sxs-lookup"><span data-stu-id="68e7c-114">Configure general settings for one user</span></span>
<span data-ttu-id="68e7c-115"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="68e7c-115"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="68e7c-116">Você deve ter [permissões de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="68e7c-116">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="68e7c-117">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="68e7c-117">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="68e7c-118">Entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="68e7c-118">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="68e7c-119">Escolha **Centros de administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-119">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="68e7c-120">Escolha **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-120">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="68e7c-122">Selecione quais usuários você deseja editar:</span><span class="sxs-lookup"><span data-stu-id="68e7c-122">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="68e7c-123">No painel direito, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-123">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="68e7c-125">Na página de opções **Geral**, marque ou desmarque a caixa de seleção ao lado dos recursos que você quer alterar e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-125">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="68e7c-126">**Opção**</span><span class="sxs-lookup"><span data-stu-id="68e7c-126">**Option**</span></span>|<span data-ttu-id="68e7c-127">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="68e7c-127">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68e7c-128">Áudio e vídeo em HD</span><span class="sxs-lookup"><span data-stu-id="68e7c-128">Audio and HD video</span></span>  <br/> |<span data-ttu-id="68e7c-129">Permita que esta pessoa grave reuniões de áudio, reuniões de áudio e vídeo ou não permita que elas agendem reuniões (nenhuma).</span><span class="sxs-lookup"><span data-stu-id="68e7c-129">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="68e7c-130">Gravar conversas e reuniões</span><span class="sxs-lookup"><span data-stu-id="68e7c-130">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="68e7c-131">Escolha o que esta pessoa tem permissão para gravar.</span><span class="sxs-lookup"><span data-stu-id="68e7c-131">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="68e7c-132">Essa opção não está disponível com o Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="68e7c-132">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="68e7c-133">Para fins de conformidade, desligue os recursos não arquivados</span><span class="sxs-lookup"><span data-stu-id="68e7c-133">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="68e7c-134">Selecione esta opção se você for obrigado legalmente a preservar informações armazenadas eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="68e7c-134">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="68e7c-135">Selecionar essa opção desativa os recursos que não são capturados quando você tem um [bloqueio in-loco](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) configurado no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="68e7c-135">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="68e7c-136">Ele desativa os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="68e7c-136">It turns off the following features:</span></span> <br/>  <span data-ttu-id="68e7c-137">Transferência de arquivos usando mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="68e7c-137">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="68e7c-138">Páginas do OneNote compartilhadas</span><span class="sxs-lookup"><span data-stu-id="68e7c-138">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="68e7c-139">Anotações do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="68e7c-139">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="68e7c-140">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68e7c-140">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="68e7c-141">Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68e7c-141">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="68e7c-142">Bloquear comunicações externas</span><span class="sxs-lookup"><span data-stu-id="68e7c-142">Block external communications</span></span>
<span data-ttu-id="68e7c-143"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="68e7c-143"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="68e7c-144">Depois de [Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md) para todos na sua empresa, você pode bloquear seletivamente as comunicações externas de indivíduos específicos usando estas etapas.</span><span class="sxs-lookup"><span data-stu-id="68e7c-144">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="68e7c-145">Escolha **usuários**, selecione os usuários cujas configurações você deseja desabilitar e escolha **Editar** ![ Editar ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="68e7c-145">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="68e7c-146">Escolha **Comunicações externas** e desmarque as opções conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="68e7c-146">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="68e7c-147">**Usuários externos do Skype for Business**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do Skype for Business em domínios federados.</span><span class="sxs-lookup"><span data-stu-id="68e7c-147">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="68e7c-148">**Usuários externos do Skype**: desmarque esta caixa se não quiser que o usuário seja capaz de se comunicar com usuários do aplicativo Skype gratuito.</span><span class="sxs-lookup"><span data-stu-id="68e7c-148">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="68e7c-149">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-149">Click **Save**.</span></span>
    
<span data-ttu-id="68e7c-150">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68e7c-150">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="68e7c-151">Consulte [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68e7c-151">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="68e7c-152">Editar as configurações de audioconferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="68e7c-152">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="68e7c-153"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="68e7c-153"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="68e7c-154">Escolha **usuários**, selecione o usuário cujas configurações de audioconferência você deseja editar e escolha **Editar** ![ Editar ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="68e7c-154">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="68e7c-155">Escolha **videoconferência**, selecione seu provedor de serviços de audioconferência, digite ou altere as informações solicitadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="68e7c-155">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="68e7c-156">**Configuração da audioconferência**</span><span class="sxs-lookup"><span data-stu-id="68e7c-156">**Audio conferencing setting**</span></span>|<span data-ttu-id="68e7c-157">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="68e7c-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68e7c-158">**Nome do provedor**</span><span class="sxs-lookup"><span data-stu-id="68e7c-158">**Provider name**</span></span> <br/> |<span data-ttu-id="68e7c-159">Escolha seu provedor na lista.</span><span class="sxs-lookup"><span data-stu-id="68e7c-159">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="68e7c-160">**Número de chamada tarifada** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="68e7c-160">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="68e7c-161">Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="68e7c-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="68e7c-162">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="68e7c-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="68e7c-163">Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="68e7c-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="68e7c-164">**Número de chamada gratuita**</span><span class="sxs-lookup"><span data-stu-id="68e7c-164">**Toll-free number**</span></span> <br/> |<span data-ttu-id="68e7c-165">Para um ACP terceirizado, esses números de telefone são aqueles que você recebeu do provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="68e7c-165">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="68e7c-166">Se o usuário estiver usando o Microsoft como um provedor de audioconferência, estes serão os números definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="68e7c-166">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="68e7c-167">Formate os números como deseja que eles apareçam nas solicitações de reunião do Skype for Business e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="68e7c-167">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="68e7c-168">**ID de conferência e PIN** (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="68e7c-168">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="68e7c-169">O PIN do participante ou o código de conferência usado para ingressar em reuniões agendadas por esse usuário e são fornecidas por um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="68e7c-169">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="68e7c-170">Se o usuário estiver usando a Microsoft como provedor de serviços de audioconferência, isso não será necessário.</span><span class="sxs-lookup"><span data-stu-id="68e7c-170">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="68e7c-171">Para definir essas configurações em massa, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68e7c-171">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="68e7c-172">Consulte [definir os números de telefone incluídos nos convites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="68e7c-172">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="68e7c-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="68e7c-173">Related topics</span></span> 

[<span data-ttu-id="68e7c-174">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="68e7c-174">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="68e7c-175">Licenciamento de complementos do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68e7c-175">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
