---
title: Configurando o Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários. MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.
ms.openlocfilehash: 8da3aaabdd772c5de8f110996585f1386f9eeb05
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="f7d6d-104">Configurando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="f7d6d-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="f7d6d-105">Serviço de migração (MMS) de reunião é um Skype para serviço de negócios que é executado em segundo plano e atualiza automaticamente o Skype para reuniões de negócios e Teams da Microsoft para usuários.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="f7d6d-106">MMS foi projetado para eliminar a necessidade de usuários executar a ferramenta de migração de reunião para atualizar seu Skype para reuniões de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>  <span data-ttu-id="f7d6d-107">Essa ferramenta não transfere Skype para reuniões de negócios em reuniões de Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="f7d6d-108">**Requisitos**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-108">**Requirements**</span></span>
  
<span data-ttu-id="f7d6d-109">O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="f7d6d-110">**Cenários principais**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="f7d6d-111">O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="f7d6d-112">Quando o usuário é migrado do Skype local para o servidor de negócios para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="f7d6d-113">Quando um administrador faz uma alteração para configurações de serviços de audioconferência do usuário que exigiriam a atualizar as informações de conferência de áudio em reuniões desse usuário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-113">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="f7d6d-114">**Cenários comuns em que o MMS não pode ser usado**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="f7d6d-p103">Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="f7d6d-118">As caixas de correio do usuário estão no Exchange Server local</span><span class="sxs-lookup"><span data-stu-id="f7d6d-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="f7d6d-119">Usando um provedor de serviços de audioconferência de terceiros</span><span class="sxs-lookup"><span data-stu-id="f7d6d-119">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="f7d6d-120">Migrar usuários do Skype para Business Online para o servidor local Skype</span><span class="sxs-lookup"><span data-stu-id="f7d6d-120">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="f7d6d-121">Atualizando reuniões quando um usuário local migra para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f7d6d-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="f7d6d-122">Este é o cenário mais comum em que o MMS pode ajudar a proporcionar uma transição mais fluida para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="f7d6d-123">Quando um usuário é migrado do Skype local para o servidor de negócios para Skype para Business Online, MMS detectará o novo usuário e examinará calendário desse usuário para Skype para reuniões de negócios e Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="f7d6d-124">Qualquer futuras reuniões serão atualizadas com as novas informações para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-124">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="f7d6d-125">Se você estiver no momento usando Skype Server 2015 para serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="f7d6d-125">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="f7d6d-126">Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="f7d6d-127">Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="f7d6d-128">Atribuir a licença de **Conferência de áudio** ao usuário antes de executar o `Move-CSUser` cmdlet para migrar o usuário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-128">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="f7d6d-129">Isso acontece porque MMS também atualiza reuniões quando as configurações de serviços de audioconferência são alteradas para um usuário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-129">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="f7d6d-130">Se você não atribuir a licença primeiro, o MMS atualizará todas as reuniões novamente no momento da atribuição da licença.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="f7d6d-131">Se estiver usando um provedor de serviços de audioconferência (ACP, Audio Conferencing Provider) de terceiros</span><span class="sxs-lookup"><span data-stu-id="f7d6d-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="f7d6d-132">Com um ACP de terceiros, ou não executa o MMS depende das configurações de conferência de áudio da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-132">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="f7d6d-133">Você pode optar por substituir automaticamente os números de discagem do seu ACP ao atribuir um usuário uma licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="f7d6d-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="f7d6d-134">Por outro lado, talvez seja necessário impedir que isso aconteça e manter os números de discagem do seu ACP.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="f7d6d-135">Para ver a definição da sua organização, execute o seguinte comando do Windows PowerShell e verifique o valor do parâmetro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="f7d6d-136">Se precisar de ajuda com o PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="f7d6d-137">Se o valor desse parâmetro for $true, MMS será executado quando um usuário é atribuído com uma licença de **Conferência de áudio** e atualizar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-137">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="f7d6d-138">Os números de discagem do seu ACP são mantidos até que a **Conferência de áudio** de licença foi distribuída.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-138">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="f7d6d-139">Se o valor desse parâmetro for $false, MMS não atualize as reuniões, mesmo se um usuário é atribuído com uma licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="f7d6d-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="f7d6d-140">Os números de discagem do seu ACP são mantidos até que o usuário é provisionado manualmente para conferência de áudio no Skype para o Centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="f7d6d-141">Atualizando reuniões quando alteram as configurações de serviços de audioconferência do usuário</span><span class="sxs-lookup"><span data-stu-id="f7d6d-141">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="f7d6d-142">MMS atualizará um Skype existente para reuniões de negócios e Teams Microsoft nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-142">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="f7d6d-143">Quando você atribuir ou remove a licença de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="f7d6d-143">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="f7d6d-144">Quando você habilitar ou desabilitar os serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-144">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="f7d6d-145">Quando você alterar ou reiniciar o ID de conferência para um usuário configurado para usar as reuniões públicas.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-145">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="f7d6d-146">Quando você move o usuário para uma nova ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-146">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="f7d6d-147">Quando um número de telefone é não atribuído a partir de uma ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-147">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="f7d6d-148">Esse é um cenário complexo que requer etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="f7d6d-149">Para obter mais informações, consulte [alterar as tarifas ou números de Chamada Tarifada livres na sua ponte de conferência de áudio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-149">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="f7d6d-150">[!IMPORTANTE] O MMS atualiza as reuniões somente quando você usa a ponte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="f7d6d-151">Se você estiver usando um provedor de serviços de audioconferência de terceiros, os usuários serão necessário atualizar suas reuniões manualmente.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-151">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="f7d6d-152">Nesse caso, você pode usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="f7d6d-153">Nem todas as alterações nas configurações de conferência de áudio de um usuário disparam MMS.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-153">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="f7d6d-154">Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="f7d6d-155">Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="f7d6d-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="f7d6d-156">Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="f7d6d-157">O que acontece quando o MMS atualiza as reuniões?</span><span class="sxs-lookup"><span data-stu-id="f7d6d-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="f7d6d-158">Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="f7d6d-159">Identificar todos os Skype para reuniões Teams da Microsoft e de negócios, o usuário tiver programado no futuro</span><span class="sxs-lookup"><span data-stu-id="f7d6d-159">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="f7d6d-160">Qualquer Skype para reuniões de negócios ou Microsoft Teams que ocorreram antes de quando MMS é executado são ignorados</span><span class="sxs-lookup"><span data-stu-id="f7d6d-160">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="f7d6d-161">Somente as reuniões organizadas pelo usuário são atualizadas</span><span class="sxs-lookup"><span data-stu-id="f7d6d-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="f7d6d-162">Substitua o bloco de informações da reunião online nos detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="f7d6d-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="f7d6d-163">Envie atualizações para todos os destinatários da reunião em nome do organizador</span><span class="sxs-lookup"><span data-stu-id="f7d6d-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="f7d6d-164">**Quanto tempo levará para o MMS ser executado?**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="f7d6d-165">A quantidade de tempo que leva para MMS migrar reuniões varia dependendo de quantos usuários são impactados e o número total de Skype para reuniões de negócios ou Microsoft Teams que cada usuário tem no seu calendário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="f7d6d-166">A execução levará pelo menos dez minutos.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="f7d6d-167">Embora algumas migrações maiores possam levar até 12 horas, a maioria delas deve ser concluída em uma hora.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="f7d6d-168">**Limitações e possíveis problemas**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="f7d6d-169">Somente o Skype para reuniões de negócios ou Teams da Microsoft que foram agendadas clicando no botão **Adicionar Skype reunião** no Outlook na Web, ou usando o suplemento de reunião Skype para Outlook são migradas.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-169">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="f7d6d-170">Em outras palavras, se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova, essa nova reunião não será atualizada.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="f7d6d-p114">O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="f7d6d-p115">O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="f7d6d-p116">O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="f7d6d-179">Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="f7d6d-180">Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="f7d6d-181">O que os usuários verão quando o MMS atualizar suas reuniões?</span><span class="sxs-lookup"><span data-stu-id="f7d6d-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="f7d6d-182">Assim como a ferramenta de migração de reunião, MMS envia atualizações de reunião em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="f7d6d-183">Portanto, a única coisa que os usuários verão é outra round de reunião notificações de aceitação para suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="f7d6d-184">Isso pode ser confuso para os usuários, portanto, recomendamos que você notifique os usuários com antecedência não somente quando você migrá-los no local para Skype para Business Online, mas também quando você faz alterações de conferência de áudio que irá disparar MMS.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="f7d6d-185">Gerenciando o MMS</span><span class="sxs-lookup"><span data-stu-id="f7d6d-185">Managing MMS</span></span>

<span data-ttu-id="f7d6d-p118">Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento. As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar sua organização do Skype for Business. Se você é iniciante no PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="f7d6d-189">Como faço para conferir o status das migrações de reuniões?</span><span class="sxs-lookup"><span data-stu-id="f7d6d-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="f7d6d-p119">Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="f7d6d-192">Para ver um status resumido de todas as migrações do MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="f7d6d-193">Ele fornecerá todos os estados de migração em uma exibição tabular, assim:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="f7d6d-194">Estado UserCount--</span><span class="sxs-lookup"><span data-stu-id="f7d6d-194">State UserCount---------------</span></span><br/> <span data-ttu-id="f7d6d-195">21 pendente</span><span class="sxs-lookup"><span data-stu-id="f7d6d-195">Pending 21</span></span><br/><span data-ttu-id="f7d6d-196">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="f7d6d-196">InProgress 6</span></span><br/> <span data-ttu-id="f7d6d-197">2 com falha</span><span class="sxs-lookup"><span data-stu-id="f7d6d-197">Failed 2</span></span> <br/> <span data-ttu-id="f7d6d-198">131 sucedidas</span><span class="sxs-lookup"><span data-stu-id="f7d6d-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="f7d6d-p120">[!IMPORTANTE] Se houver migrações com falha, tome as medidas necessárias para resolver os problemas assim que possível. As pessoas não conseguirão discar para as reuniões organizadas por esses usuários até que você os resolva. Veja a seção [O que devo fazer se ocorrer um erro?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="f7d6d-p121">Para ver detalhes completos de todas as migrações de um período específico, você pode usar os parâmetros  `StartTime` e `EndTime`. Por exemplo, o comando a seguir retornará detalhes completos de todas as migrações ocorridas de 1º a 8 de outubro de 2016.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="f7d6d-p122">Talvez você também queira conferir o status da migração de um usuário específico. Para isso, use o parâmetro  `UserId`. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="f7d6d-206">O que devo fazer se ocorrer um erro?</span><span class="sxs-lookup"><span data-stu-id="f7d6d-206">What do I do if there is an error?</span></span>
<span data-ttu-id="f7d6d-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d6d-207"></span></span>

<span data-ttu-id="f7d6d-208">Quando você executa o cmdlet  `Get-CsMeetingMigrationStatus` para ver um resumo e o estado Com falhaé observado, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="f7d6d-p123">Determine quais usuários são afetados. Execute o comando a seguir para obter a lista de usuários afetados e o erro específico que foi informado:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="f7d6d-211">Para cada um desses usuários, execute a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) para fazer a migração manual de suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="f7d6d-212">Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="f7d6d-213">Fazer os usuários criarem novas reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="f7d6d-214">[Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="f7d6d-215">Habilitando e desabilitando o MMS</span><span class="sxs-lookup"><span data-stu-id="f7d6d-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="f7d6d-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d6d-216"></span></span>

<span data-ttu-id="f7d6d-217">O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="f7d6d-218">Por exemplo, se você quiser migrar manualmente todas as reuniões ou se você usar um provedor de serviços de audioconferência de terceiros, talvez não seja necessário MMS executando.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-218">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="f7d6d-219">Você também pode optar por desabilitar o MMS temporariamente.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="f7d6d-220">Por exemplo, você talvez esteja fazendo alterações substanciais às definições de serviços de audioconferência para sua organização e você não quer MMS execução autorizada até que todas as alterações são concluídas.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-220">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="f7d6d-p125">Para ver se o MMS está habilitado em sua organização, execute o comando a seguir e confira o valor do parâmetro  `MeetingMigrationEnabled`. Se esse parâmetro está definido como $true, o MMS está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="f7d6d-223">Para desabilitar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="f7d6d-224">Para habilitar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="f7d6d-225">Habilitando e desabilitando MMS somente para alterações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="f7d6d-225">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="f7d6d-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d6d-226"></span></span>

<span data-ttu-id="f7d6d-227">Você também pode desativar MMS somente para alterações de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-227">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="f7d6d-228">Ele ainda será executado quando um usuário é migrado do Skype para negócios local para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-228">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="f7d6d-229">Para verificar o status atual do MMS para atualizações de conferência de áudio, execute o seguinte comando e verifique o valor para o `AutomaticallyMigrateUserMeetings` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-229">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="f7d6d-230">Se esse parâmetro for definido como true$, MMS é definido para atualizar as reuniões do usuário quando as configurações de serviços de audioconferência são alteradas.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-230">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="f7d6d-231">Para desativar MMS para conferência de áudio, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-231">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="f7d6d-232">Para habilitar MMS para conferência de áudio, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-232">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="f7d6d-233">Como executo a Migração de Reunião manualmente para um usuário?</span><span class="sxs-lookup"><span data-stu-id="f7d6d-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="f7d6d-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d6d-234"></span></span>

<span data-ttu-id="f7d6d-235">Além das migrações automáticas de reunião, você também pode executar a migração de reunião manualmente para um usuário executando o cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="f7d6d-236">Este cmdlet adiciona o usuário na fila de migração de reunião.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-236">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="f7d6d-237">O Meeting Migration Service lerá a solicitação do usuário e migrará sua reunião.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="f7d6d-238">Você pode verificar o status da migração da reunião com o cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="f7d6d-239">Este é um exemplo que inicia a migração da reunião para o usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="f7d6d-240">Usando o PowerShell para gerenciar a organização do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f7d6d-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="f7d6d-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="f7d6d-241"></span></span>

 <span data-ttu-id="f7d6d-242">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="f7d6d-243">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f7d6d-244">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="f7d6d-p128">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="f7d6d-p129">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="f7d6d-251">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="f7d6d-252">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f7d6d-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="f7d6d-253">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="f7d6d-254">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f7d6d-255">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f7d6d-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="f7d6d-256">Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f7d6d-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="f7d6d-p130">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f7d6d-260">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f7d6d-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f7d6d-261">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f7d6d-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="f7d6d-p131">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f7d6d-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f7d6d-264">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7d6d-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="f7d6d-265">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f7d6d-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f7d6d-266">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f7d6d-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="f7d6d-267">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f7d6d-267">Related topics</span></span>

[<span data-ttu-id="f7d6d-268">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="f7d6d-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
