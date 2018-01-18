---
title: Configurando o Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários. MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft."
ms.openlocfilehash: 66cfd8ef0c11aa481e095b406f0dd1264b611b61
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="0aba5-104">Configurando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="0aba5-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="0aba5-105">Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários.</span><span class="sxs-lookup"><span data-stu-id="0aba5-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="0aba5-106">MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0aba5-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="0aba5-107">**Requisitos**</span><span class="sxs-lookup"><span data-stu-id="0aba5-107">**Requirements**</span></span>
  
<span data-ttu-id="0aba5-108">O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0aba5-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="0aba5-109">**Cenários principais**</span><span class="sxs-lookup"><span data-stu-id="0aba5-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="0aba5-110">O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:</span><span class="sxs-lookup"><span data-stu-id="0aba5-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="0aba5-111">Quando o usuário é migrado do Skype local para o servidor de negócios para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="0aba5-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="0aba5-112">Quando um administrador faz uma alteração para configurações de serviços de audioconferência do usuário que exigiriam a atualizar as informações de conferência de áudio em reuniões desse usuário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="0aba5-113">**Cenários comuns em que o MMS não pode ser usado**</span><span class="sxs-lookup"><span data-stu-id="0aba5-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="0aba5-p103">Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="0aba5-117">As caixas de correio do usuário estão no Exchange Server local</span><span class="sxs-lookup"><span data-stu-id="0aba5-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="0aba5-118">Usando um provedor de serviços de audioconferência de terceiros</span><span class="sxs-lookup"><span data-stu-id="0aba5-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="0aba5-119">Migrar usuários do Skype para Business Online para o servidor local Skype</span><span class="sxs-lookup"><span data-stu-id="0aba5-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="0aba5-120">Atualizando reuniões quando um usuário local migra para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0aba5-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="0aba5-121">Esse é o cenário mais comum onde MMS pode ajudar a criar uma transição mais suave para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="0aba5-121">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="0aba5-122">Quando um usuário é migrado do Skype local para o servidor de negócios para Skype para Business Online, MMS detectará o novo usuário e examinará calendário desse usuário para Skype para reuniões de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0aba5-122">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="0aba5-123">Qualquer futuras reuniões serão atualizadas com as novas informações para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-123">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="0aba5-124">Se você estiver no momento usando Skype Server 2015 para serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="0aba5-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="0aba5-125">Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:</span><span class="sxs-lookup"><span data-stu-id="0aba5-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="0aba5-126">Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0aba5-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="0aba5-127">Atribuir a licença de **Conferência de áudio** ao usuário antes de executar o `Move-CSUser` cmdlet para migrar o usuário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-127">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="0aba5-128">Isso acontece porque MMS também atualiza reuniões quando as configurações de serviços de audioconferência são alteradas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-128">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="0aba5-129">Se você não atribuir a licença pela primeira vez, MMS atualizará todas as reuniões novamente ao atribuir a licença.</span><span class="sxs-lookup"><span data-stu-id="0aba5-129">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="0aba5-130">Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros</span><span class="sxs-lookup"><span data-stu-id="0aba5-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="0aba5-131">Com um ACP de terceiros, ou não executa o MMS depende das configurações de conferência de áudio da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0aba5-131">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="0aba5-132">Você pode optar por substituir automaticamente os números de discagem do seu ACP ao atribuir um usuário uma licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="0aba5-132">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="0aba5-133">Por outro lado, você pode precisar evitar que isso aconteça e reter os números de discagem do seu ACP.</span><span class="sxs-lookup"><span data-stu-id="0aba5-133">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="0aba5-134">Para ver a definição da sua organização, execute o seguinte comando do Windows PowerShell e verifique o valor do parâmetro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="0aba5-134">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="0aba5-135">Se você precisa de ajuda com o PowerShell, consulte a seção [Usando o PowerShell para gerenciar sua Skype para organização de negócios](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="0aba5-135">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="0aba5-136">Se o valor desse parâmetro for $true, MMS será executado quando um usuário é atribuído com uma licença de **Conferência de áudio** e atualizar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="0aba5-136">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="0aba5-137">Os números de discagem do seu ACP são mantidos até que a **Conferência de áudio** de licença foi distribuída.</span><span class="sxs-lookup"><span data-stu-id="0aba5-137">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="0aba5-138">Se o valor desse parâmetro for $false, MMS não atualize as reuniões, mesmo se um usuário é atribuído com uma licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="0aba5-138">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="0aba5-139">Os números de discagem do seu ACP são mantidos até que o usuário é provisionado manualmente para conferência de áudio no Skype para o Centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0aba5-139">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="0aba5-140">Atualizando reuniões quando alteram as configurações de serviços de audioconferência do usuário</span><span class="sxs-lookup"><span data-stu-id="0aba5-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="0aba5-141">MMS atualizará um Skype existente para reuniões de negócios e Teams Microsoft nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="0aba5-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="0aba5-142">Quando você atribuir ou remove a licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="0aba5-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="0aba5-143">Quando você habilitar ou desabilitar os serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="0aba5-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="0aba5-144">Quando você alterar ou reiniciar o ID de conferência para um usuário configurado para usar as reuniões públicas.</span><span class="sxs-lookup"><span data-stu-id="0aba5-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="0aba5-145">Quando você move o usuário para uma nova ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="0aba5-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="0aba5-146">Quando um número de telefone é não atribuído a partir de uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="0aba5-146">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="0aba5-147">Esse é um cenário complexo que requer etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="0aba5-147">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="0aba5-148">Para obter mais informações, consulte [alterar as tarifas ou números de Chamada Tarifada livres na sua ponte de conferência de áudio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="0aba5-148">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0aba5-149">MMS somente atualiza reuniões quando você estiver usando a ponte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0aba5-149">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="0aba5-150">Se você estiver usando um provedor de serviços de audioconferência de terceiros, os usuários serão necessário atualizar suas reuniões manualmente.</span><span class="sxs-lookup"><span data-stu-id="0aba5-150">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="0aba5-151">Nesse caso, você pode usar a [Ferramenta de migração de reunião](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="0aba5-151">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="0aba5-152">Nem todas as alterações nas configurações de conferência de áudio de um usuário disparam MMS.</span><span class="sxs-lookup"><span data-stu-id="0aba5-152">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="0aba5-153">Especificamente, as alterações a seguir não resultará em MMS atualizando reuniões:</span><span class="sxs-lookup"><span data-stu-id="0aba5-153">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="0aba5-154">Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="0aba5-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="0aba5-155">Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="0aba5-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="0aba5-156">O que acontece quando o MMS atualiza as reuniões?</span><span class="sxs-lookup"><span data-stu-id="0aba5-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="0aba5-157">Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0aba5-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="0aba5-158">Identificar todos os Skype para reuniões Teams da Microsoft e de negócios, o usuário tiver programado no futuro</span><span class="sxs-lookup"><span data-stu-id="0aba5-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="0aba5-159">Qualquer Skype para reuniões de negócios ou Microsoft Teams que ocorreram antes de quando MMS é executado são ignorados</span><span class="sxs-lookup"><span data-stu-id="0aba5-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="0aba5-160">Somente as reuniões organizadas pelo usuário são atualizadas</span><span class="sxs-lookup"><span data-stu-id="0aba5-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="0aba5-161">Substitua o bloco de informações da reunião online nos detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="0aba5-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="0aba5-162">Envie atualizações para todos os destinatários da reunião em nome do organizador</span><span class="sxs-lookup"><span data-stu-id="0aba5-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="0aba5-163">**Quanto tempo levará para o MMS ser executado?**</span><span class="sxs-lookup"><span data-stu-id="0aba5-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="0aba5-164">A quantidade de tempo que leva para MMS migrar reuniões varia dependendo de quantos usuários são impactados e o número total de Skype para reuniões de negócios ou Microsoft Teams que cada usuário tem no seu calendário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-164">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="0aba5-165">No mínimo, levará 10 minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="0aba5-165">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="0aba5-166">Enquanto alguns grandes migrações podem levar até 12 horas, a maioria das migrações deverá ser concluída dentro de 1 hora.</span><span class="sxs-lookup"><span data-stu-id="0aba5-166">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="0aba5-167">**Limitações e possíveis problemas**</span><span class="sxs-lookup"><span data-stu-id="0aba5-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="0aba5-168">Somente o Skype para reuniões de negócios ou Teams da Microsoft que foram agendadas clicando no botão **Adicionar Skype reunião** no Outlook na Web, ou usando o suplemento de reunião Skype para Outlook são migradas.</span><span class="sxs-lookup"><span data-stu-id="0aba5-168">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="0aba5-169">Em outras palavras, se um usuário copia e cola as informações de reunião online do Skype de uma reunião para uma nova reunião, essa nova reunião não será atualizado.</span><span class="sxs-lookup"><span data-stu-id="0aba5-169">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="0aba5-p114">O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="0aba5-p115">O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="0aba5-p116">O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="0aba5-178">Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.</span><span class="sxs-lookup"><span data-stu-id="0aba5-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="0aba5-179">Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="0aba5-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="0aba5-180">O que os usuários verão quando o MMS atualizar suas reuniões?</span><span class="sxs-lookup"><span data-stu-id="0aba5-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="0aba5-181">Assim como a ferramenta de migração de reunião, MMS envia atualizações de reunião em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="0aba5-181">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="0aba5-182">Portanto, a única coisa que os usuários verão é outra round de reunião notificações de aceitação para suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="0aba5-182">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="0aba5-183">Isso pode ser confuso para os usuários, portanto, recomendamos que você notifique os usuários com antecedência não somente quando você migrá-los no local para Skype para Business Online, mas também quando você faz alterações de conferência de áudio que irá disparar MMS.</span><span class="sxs-lookup"><span data-stu-id="0aba5-183">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="0aba5-184">Gerenciando o MMS</span><span class="sxs-lookup"><span data-stu-id="0aba5-184">Managing MMS</span></span>

<span data-ttu-id="0aba5-p118">Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar sua organização do Skype for Business. Se você é iniciante no PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="0aba5-188">Como faço para conferir o status das migrações de reuniões?</span><span class="sxs-lookup"><span data-stu-id="0aba5-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="0aba5-p119">Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="0aba5-191">Para ver um status resumido de todas as migrações do MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="0aba5-192">Ele fornecerá todos os estados de migração em uma exibição tabular, assim:</span><span class="sxs-lookup"><span data-stu-id="0aba5-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="0aba5-193">Estado UserCount--</span><span class="sxs-lookup"><span data-stu-id="0aba5-193">State UserCount---------------</span></span><br/> <span data-ttu-id="0aba5-194">21 pendente</span><span class="sxs-lookup"><span data-stu-id="0aba5-194">Pending 21</span></span><br/><span data-ttu-id="0aba5-195">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="0aba5-195">InProgress 6</span></span><br/> <span data-ttu-id="0aba5-196">2 com falha</span><span class="sxs-lookup"><span data-stu-id="0aba5-196">Failed 2</span></span> <br/> <span data-ttu-id="0aba5-197">131 sucedidas</span><span class="sxs-lookup"><span data-stu-id="0aba5-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="0aba5-p120">[!IMPORTANTE] Se houver migrações com falha, tome as medidas necessárias para resolver os problemas assim que possível. As pessoas não conseguirão discar para as reuniões organizadas por esses usuários até que você os resolva. Veja a seção [O que devo fazer se ocorrer um erro?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="0aba5-p121">Para ver detalhes completos de todas as migrações de um período específico, você pode usar os parâmetros  `StartTime` e `EndTime`. Por exemplo, o comando a seguir retornará detalhes completos de todas as migrações ocorridas de 1º a 8 de outubro de 2016.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="0aba5-p122">Talvez você também queira conferir o status da migração de um usuário específico. Para isso, use o parâmetro  `UserId`. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0aba5-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="0aba5-205">O que devo fazer se ocorrer um erro?</span><span class="sxs-lookup"><span data-stu-id="0aba5-205">What do I do if there is an error?</span></span>
<span data-ttu-id="0aba5-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="0aba5-206"></span></span>

<span data-ttu-id="0aba5-207">Quando você executa o cmdlet  `Get-CsMeetingMigrationStatus` para ver um resumo e o estado Com falhaé observado, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0aba5-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="0aba5-p123">Determine quais usuários são afetados. Execute o comando a seguir para obter a lista de usuários afetados e o erro específico que foi informado:</span><span class="sxs-lookup"><span data-stu-id="0aba5-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="0aba5-210">Para cada um desses usuários, execute a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) para fazer a migração manual de suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="0aba5-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="0aba5-211">Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="0aba5-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="0aba5-212">Fazer os usuários criarem novas reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="0aba5-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="0aba5-213">[Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="0aba5-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="0aba5-214">Habilitando e desabilitando o MMS</span><span class="sxs-lookup"><span data-stu-id="0aba5-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="0aba5-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="0aba5-215"></span></span>

<span data-ttu-id="0aba5-216">MMS é habilitado por padrão para todas as organizações, mas ele pode ser desabilitado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0aba5-216">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="0aba5-217">Por exemplo, se você quiser migrar manualmente todas as reuniões ou se você usar um provedor de serviços de audioconferência de terceiros, talvez não seja necessário MMS executando.</span><span class="sxs-lookup"><span data-stu-id="0aba5-217">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="0aba5-218">Você também pode optar por desabilitar temporariamente MMS.</span><span class="sxs-lookup"><span data-stu-id="0aba5-218">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="0aba5-219">Por exemplo, você talvez esteja fazendo alterações substanciais às definições de serviços de audioconferência para sua organização e você não quer MMS execução autorizada até que todas as alterações são concluídas.</span><span class="sxs-lookup"><span data-stu-id="0aba5-219">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="0aba5-p125">Para ver se o MMS está habilitado em sua organização, execute o comando a seguir e confira o valor do parâmetro  `MeetingMigrationEnabled`. Se esse parâmetro está definido como $true, o MMS está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="0aba5-222">Para desabilitar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="0aba5-223">Para habilitar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="0aba5-224">Habilitando e desabilitando MMS somente para alterações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="0aba5-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="0aba5-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="0aba5-225"></span></span>

<span data-ttu-id="0aba5-226">Você também pode desativar MMS somente para alterações de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="0aba5-226">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="0aba5-227">Ele ainda será executado quando um usuário é migrado do Skype para negócios local para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="0aba5-227">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="0aba5-228">Para verificar o status atual do MMS para atualizações de conferência de áudio, execute o seguinte comando e verifique o valor para o `AutomaticallyMigrateUserMeetings` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0aba5-228">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="0aba5-229">Se esse parâmetro for definido como true$, MMS é definido para atualizar as reuniões do usuário quando as configurações de serviços de audioconferência são alteradas.</span><span class="sxs-lookup"><span data-stu-id="0aba5-229">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="0aba5-230">Para desativar MMS para conferência de áudio, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="0aba5-231">Para habilitar MMS para conferência de áudio, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="0aba5-232">Como executo a Migração de Reunião manualmente para um usuário?</span><span class="sxs-lookup"><span data-stu-id="0aba5-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="0aba5-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="0aba5-233"></span></span>

<span data-ttu-id="0aba5-234">Além de migrações de reunião automáticos, também é possível executar a migração de reunião manualmente para um usuário executando o cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="0aba5-234">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="0aba5-235">Este cmdlet adiciona o usuário na fila de migração de reunião.</span><span class="sxs-lookup"><span data-stu-id="0aba5-235">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="0aba5-236">Serviço de migração de reunião, leia a solicitação do usuário e migrar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="0aba5-236">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="0aba5-237">Você pode verificar o status da migração de reunião pelo cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="0aba5-237">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="0aba5-238">Este é um exemplo que inicia a migração da reunião para o usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0aba5-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="0aba5-239">Usando o PowerShell para gerenciar a organização do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0aba5-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="0aba5-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="0aba5-240"></span></span>

 <span data-ttu-id="0aba5-241">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="0aba5-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="0aba5-242">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0aba5-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0aba5-243">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0aba5-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0aba5-p128">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="0aba5-p129">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="0aba5-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="0aba5-250">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="0aba5-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="0aba5-251">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0aba5-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="0aba5-252">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0aba5-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0aba5-253">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="0aba5-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0aba5-254">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="0aba5-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="0aba5-255">Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0aba5-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="0aba5-p130">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="0aba5-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0aba5-259">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0aba5-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0aba5-260">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="0aba5-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0aba5-p131">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="0aba5-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0aba5-263">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0aba5-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0aba5-264">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0aba5-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0aba5-265">Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0aba5-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0aba5-266">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0aba5-266">Related topics</span></span>

[<span data-ttu-id="0aba5-267">Configurar a Audioconferência para o Skype for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0aba5-267">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
