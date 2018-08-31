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
description: O Meeting Migration Service (MMS) é um serviço do Skype for Business executado em segundo plano que atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para os usuários. O MMS foi projetado para que os usuários não precisem executar a ferramenta de migração de reunião para atualizar as reuniões do Skype for Business e do Microsoft Teams.
ms.openlocfilehash: 013e68ada16f15b3a410823680ec062b9fb7fa3a
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780497"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="7a079-104">Configurando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="7a079-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="7a079-105">O Meeting Migration Service (MMS) é um serviço do Skype for Business executado em segundo plano que atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7a079-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype meetings for users.</span></span> <span data-ttu-id="7a079-106">O MMS foi projetado para que os usuários não precisem executar a ferramenta de migração de reunião para atualizar as reuniões do Skype for Business e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a079-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype meetings.</span></span>  <span data-ttu-id="7a079-107">Essa ferramenta não migra as reuniões do Skype for Business para as reuniões do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7a079-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="7a079-108">**Requisitos**</span><span class="sxs-lookup"><span data-stu-id="7a079-108">**Requirements**</span></span>
  
<span data-ttu-id="7a079-109">O MMS exige que as caixas de correio dos organizadores da reunião estejam no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a079-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="7a079-110">**Cenários principais**</span><span class="sxs-lookup"><span data-stu-id="7a079-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="7a079-111">O MMS atualiza as reuniões do Skype para os usuários nestes dois cenários principais:</span><span class="sxs-lookup"><span data-stu-id="7a079-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="7a079-112">Quando o usuário migra do Skype for Business Server local para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7a079-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online</span></span>
    
- <span data-ttu-id="7a079-113">Quando um administrador faz uma alteração para configurações de audioconferência do usuário que exigiriam a atualização das informações de audioconferência em reuniões desse usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-113">When an admin makes a change to the user's dial-in conferencing settings that would require updating the dial-in conferencing information in that user's meetings</span></span>
    
 <span data-ttu-id="7a079-114">**Cenários comuns em que o MMS não pode ser usado**</span><span class="sxs-lookup"><span data-stu-id="7a079-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="7a079-p103">Veja alguns cenários comuns que podem se aplicar a você. Todos eles dão suporte à migração. Porém, o MMS não será executado nesses cenários e você deverá usar a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="7a079-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="7a079-118">As caixas de correio do usuário estão no Exchange Server local</span><span class="sxs-lookup"><span data-stu-id="7a079-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="7a079-119">Usar um provedor de serviços de audioconferência de terceiros</span><span class="sxs-lookup"><span data-stu-id="7a079-119">Using a third-party dial-in conferencing provider</span></span>
    
- <span data-ttu-id="7a079-120">Migrar usuários do Skype for Business Online para o Skype Server local</span><span class="sxs-lookup"><span data-stu-id="7a079-120">Migrating users from Skype for Business online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="7a079-121">Atualizar reuniões quando um usuário local migra para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a079-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="7a079-122">Este é o cenário mais comum em que o MMS pode ajudar a proporcionar uma transição mais fluida para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7a079-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="7a079-123">Quando o usuário migra do Skype for Business Server local para o Skype for Business Online, o MMS detecta o novo usuário e verifica as reuniões do Skype for Business e do Microsoft Teams no calendário desse usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype meetings.</span></span> <span data-ttu-id="7a079-124">Todas as reuniões futuras serão atualizadas com as novas informações do usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-124">Any future Skype meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="7a079-125">Se você usa o Skype Server 2015 para audioconferência</span><span class="sxs-lookup"><span data-stu-id="7a079-125">If you're currently using Skype Server 2015 for dial-in conferencing</span></span>

<span data-ttu-id="7a079-126">Recomendamos que você siga estas práticas recomendadas para ter a melhor experiência com o MMS neste cenário:</span><span class="sxs-lookup"><span data-stu-id="7a079-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="7a079-127">Como o MMS exige que a caixa de correio do usuário esteja no Exchange Online, se você também está migrando do Exchange Server local, primeiro mova a caixa de correio do usuário para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a079-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="7a079-128">Atribua a licença de **Audioconferência** ao usuário antes de executar o cmdlet `Move-CSUser` para fazer a migração do usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-128">Assign the PSTN Conferencing license to the user before you run the   cmdlet to migrate the user.</span></span> <span data-ttu-id="7a079-129">Assim, o MMS também atualizará as reuniões quando as configurações de audioconferência do usuário forem alteradas.</span><span class="sxs-lookup"><span data-stu-id="7a079-129">This is because MMS also updates meetings when dial-in conferencing settings are changed for a user.</span></span> <span data-ttu-id="7a079-130">Se você não atribuir a licença primeiro, o MMS atualizará todas as reuniões novamente no momento da atribuição da licença.</span><span class="sxs-lookup"><span data-stu-id="7a079-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="7a079-131">Se estiver usando um provedor de serviços de audioconferência (ACP) de terceiros</span><span class="sxs-lookup"><span data-stu-id="7a079-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="7a079-132">Com um ACP de terceiros, a execução do MMS depende das configurações de audioconferência da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7a079-132">With a third-party ACP, whether or not MMS runs depends on your organization's dial-in conferencing settings.</span></span> <span data-ttu-id="7a079-133">Você pode optar por substituir os números de discagem do ACP automaticamente quando atribuir a licença de **Audioconferência** ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a PSTN Conferencing license.</span></span> <span data-ttu-id="7a079-134">Por outro lado, talvez seja necessário impedir que isso aconteça e manter os números de discagem do seu ACP.</span><span class="sxs-lookup"><span data-stu-id="7a079-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="7a079-135">Para ver as configurações da sua organização, execute o comando do Windows PowerShell a seguir e confira o valor do parâmetro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="7a079-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter  `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="7a079-136">Se precisar de ajuda com o PowerShell, veja a seção [Usando o PowerShell para gerenciar a organização do Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7a079-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="7a079-137">Se o valor desse parâmetro for $true, o MMS será executado quando for atribuída uma licença de **Audioconferência** ao usuário, atualizando suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="7a079-137">If the value of this parameter is $true, then MMS will run when a user is assigned a PSTN Conferencing license and update their meetings.</span></span> <span data-ttu-id="7a079-138">Os números de discagem de seu ACP são mantidos até que seja atribuída a licença de **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="7a079-138">The dial-in numbers from your ACP are retained until the PSTN Conferencing license is assigned.</span></span>
    
- <span data-ttu-id="7a079-139">Se o valor deste parâmetro for $false, o MMS não atualizará as reuniões, mesmo que seja atribuída uma licença de **Audioconferência** ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7a079-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a PSTN Conferencing licence.</span></span> <span data-ttu-id="7a079-140">Os números de discagem de seu ACP são mantidos até que a audioconferência seja provisionada manualmente para o usuário no centro de administração do Skype for Business ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a079-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for dial-in conferencing in Skype admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="7a079-141">Atualizar reuniões quando as configurações de audioconferência do usuário são alteradas</span><span class="sxs-lookup"><span data-stu-id="7a079-141">Updating meetings when a user's dial-in conferencing settings change</span></span>

<span data-ttu-id="7a079-142">O MMS atualizará asa reuniões existentes do Skype for Business e do Microsoft Teams nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="7a079-142">MMS will update an existing Skype for Business online user's meetings in the following cases:</span></span>
  
- <span data-ttu-id="7a079-143">Quando você atribuir ou remover a licença de **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="7a079-143">When you assign or remove PSTN Conferencing license</span></span>
    
- <span data-ttu-id="7a079-144">Quando você ativar ou desativar os serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7a079-144">When you enable or disable dial-in conferencing</span></span>
    
- <span data-ttu-id="7a079-145">Quando você alterar ou redefinir a ID de Conferência de um usuário configurado para usar reuniões públicas.</span><span class="sxs-lookup"><span data-stu-id="7a079-145">When you change or reset the Conference ID for a user configured to use public meetings</span></span>
    
- <span data-ttu-id="7a079-146">Quando você mover o usuário para uma nova ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7a079-146">When you move the user to a new dial-in conferencing bridge</span></span>
    
- <span data-ttu-id="7a079-147">Quando for cancelada a atribuição de um número de telefone de uma ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7a079-147">When a phone number is unassigned from a dial-in conferencing bridge.</span></span> <span data-ttu-id="7a079-148">Esse é um cenário complexo que requer etapas adicionais.</span><span class="sxs-lookup"><span data-stu-id="7a079-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="7a079-149">Para obter mais informações, consulte [Mudar números de chamada tarifada ou de chamada gratuita para sua ponte de audioconferência](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="7a079-149">For more information, see [Change the toll or toll-free numbers on your dial-in conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="7a079-150">O MMS atualiza as reuniões somente quando você usa a ponte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a079-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="7a079-151">Se estiver usando um provedor de serviços de audioconferência de terceiros, os usuários deverão atualizar as reuniões manualmente.</span><span class="sxs-lookup"><span data-stu-id="7a079-151">If you are using a third-party dial-in conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="7a079-152">Nesse caso, você pode usar a [ferramenta de migração de reunião](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="7a079-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="7a079-153">Nem todas as alterações das configurações de audioconferência do usuário acionam o MMS.</span><span class="sxs-lookup"><span data-stu-id="7a079-153">Not all changes to a user's dial-in conferencing settings trigger MMS.</span></span> <span data-ttu-id="7a079-154">Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:</span><span class="sxs-lookup"><span data-stu-id="7a079-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="7a079-155">Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)</span><span class="sxs-lookup"><span data-stu-id="7a079-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="7a079-156">Quando você altera a URL da reunião da organização usando o comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="7a079-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="7a079-157">O que acontece quando o MMS atualiza as reuniões?</span><span class="sxs-lookup"><span data-stu-id="7a079-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="7a079-158">Quando o MMS detecta que as reuniões de um usuário precisam ser atualizadas, ele faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7a079-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="7a079-159">Identifica todas as reuniões do Skype for Business e do Microsoft Teams que o usuário tiver programado no futuro</span><span class="sxs-lookup"><span data-stu-id="7a079-159">Identify all Skype meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="7a079-160">Qualquer reunião do Skype for Business e do Microsoft Teams que ocorreu antes da execução do MMS é ignorada</span><span class="sxs-lookup"><span data-stu-id="7a079-160">Any Skype meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="7a079-161">Somente as reuniões organizadas pelo usuário são atualizadas</span><span class="sxs-lookup"><span data-stu-id="7a079-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="7a079-162">Substitua o bloco de informações da reunião online nos detalhes da reunião</span><span class="sxs-lookup"><span data-stu-id="7a079-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="7a079-163">Envie atualizações para todos os destinatários da reunião em nome do organizador</span><span class="sxs-lookup"><span data-stu-id="7a079-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="7a079-164">**Quanto tempo levará para o MMS ser executado?**</span><span class="sxs-lookup"><span data-stu-id="7a079-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="7a079-165">O tempo necessário para o MMS migrar as reuniões varia de acordo com o número de usuários afetados e o número total de reuniões do Skype for Business ou do Microsoft Teams que cada usuário tem no calendário.</span><span class="sxs-lookup"><span data-stu-id="7a079-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype meetings each user has on their calendar.</span></span> <span data-ttu-id="7a079-166">A execução levará pelo menos dez minutos.</span><span class="sxs-lookup"><span data-stu-id="7a079-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="7a079-167">Embora algumas migrações maiores possam levar até 12 horas, a maioria delas deve ser concluída em uma hora.</span><span class="sxs-lookup"><span data-stu-id="7a079-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="7a079-168">**Limitações e possíveis problemas**</span><span class="sxs-lookup"><span data-stu-id="7a079-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="7a079-169">Somente as reuniões do Skype for Business ou do Microsoft Teams que foram agendadas clicando no botão **Adicionar reunião do Skype** no Outlook na Web ou usando o suplemento Reunião do Skype para Outlook são migradas.</span><span class="sxs-lookup"><span data-stu-id="7a079-169">Only the Skype meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="7a079-170">Em outras palavras, se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova, essa nova reunião não será atualizada.</span><span class="sxs-lookup"><span data-stu-id="7a079-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="7a079-p114">O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.</span><span class="sxs-lookup"><span data-stu-id="7a079-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="7a079-p115">O conteúdo que foi criado ou anexado à reunião (quadros de comunicações, votações e outros) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.</span><span class="sxs-lookup"><span data-stu-id="7a079-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="7a079-p116">O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas reais da reunião armazenadas no OneNote continuarão lá, apenas o link para as notas compartilhadas será sobrescrito.</span><span class="sxs-lookup"><span data-stu-id="7a079-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="7a079-179">Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.</span><span class="sxs-lookup"><span data-stu-id="7a079-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="7a079-180">Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="7a079-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="7a079-181">O que os usuários verão quando o MMS atualizar suas reuniões?</span><span class="sxs-lookup"><span data-stu-id="7a079-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="7a079-182">Assim como a ferramenta de migração de reunião, o MMS envia atualizações de reunião em nome de usuários.</span><span class="sxs-lookup"><span data-stu-id="7a079-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="7a079-183">Portanto, a única coisa que os usuários verão é outra rodada de notificações de aceitação para suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="7a079-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="7a079-184">Isso pode ser confuso para os usuários, portanto, recomendamos que os notifique com antecedência, não somente quando você migrá-los do local para o Skype for Business Online, mas também quando você fizer alterações de audioconferência que irão acionar o MMS.</span><span class="sxs-lookup"><span data-stu-id="7a079-184">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make dial-in conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="7a079-185">Gerenciando o MMS</span><span class="sxs-lookup"><span data-stu-id="7a079-185">Managing MMS</span></span>

<span data-ttu-id="7a079-186">Você precisa usar o Windows PowerShell para gerenciar o MMS e verificar o status das migrações em andamento.</span><span class="sxs-lookup"><span data-stu-id="7a079-186">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations.</span></span> <span data-ttu-id="7a079-187">As informações contidas nesta seção pressupõem que você saiba como usar o PowerShell para gerenciar Skype for Business de sua organização.</span><span class="sxs-lookup"><span data-stu-id="7a079-187">The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization.</span></span> <span data-ttu-id="7a079-188">Se você é iniciante no PowerShell, consulte a seção [Usando o PowerShell para gerenciar o Skype for Business se dua organização](setting-up-the-meeting-migration-service-mms.md#WPSInfo) no final deste artigo.</span><span class="sxs-lookup"><span data-stu-id="7a079-188">If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="7a079-189">Como faço para conferir o status das migrações de reuniões?</span><span class="sxs-lookup"><span data-stu-id="7a079-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="7a079-p119">Você pode usar o cmdlet  `Get-CsMeetingMigrationStatus` para verificar o status das migrações de reuniões. Veja alguns exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="7a079-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="7a079-192">Para ver um status resumido de todas as migrações do MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="7a079-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="7a079-193">Ele fornecerá um modo de exibição tabular de todos os estados de migração desse modo:</span><span class="sxs-lookup"><span data-stu-id="7a079-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="7a079-194">Estado UserCount---------------</span><span class="sxs-lookup"><span data-stu-id="7a079-194">State UserCount---------------</span></span><br/> <span data-ttu-id="7a079-195">Pending 21</span><span class="sxs-lookup"><span data-stu-id="7a079-195">Pending 21</span></span><br/><span data-ttu-id="7a079-196">InProgress 6</span><span class="sxs-lookup"><span data-stu-id="7a079-196">InProgress 6</span></span><br/> <span data-ttu-id="7a079-197">Failed 2</span><span class="sxs-lookup"><span data-stu-id="7a079-197">Failed 2</span></span> <br/> <span data-ttu-id="7a079-198">Succeeded 131</span><span class="sxs-lookup"><span data-stu-id="7a079-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="7a079-p120">[!IMPORTANTE] Se houver migrações com falha, tome as medidas necessárias para resolver os problemas assim que possível. As pessoas não conseguirão discar para as reuniões organizadas por esses usuários até que você os resolva. Veja a seção [O que devo fazer se ocorrer um erro?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7a079-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="7a079-p121">Para ver detalhes completos de todas as migrações de um período específico, você pode usar os parâmetros  `StartTime` e `EndTime`. Por exemplo, o comando a seguir retornará detalhes completos de todas as migrações ocorridas de 1º a 8 de outubro de 2016.</span><span class="sxs-lookup"><span data-stu-id="7a079-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="7a079-p122">Talvez você também queira conferir o status da migração de um usuário específico. Para isso, use o parâmetro  `UserId`. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="7a079-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="7a079-206">O que devo fazer se ocorrer um erro?</span><span class="sxs-lookup"><span data-stu-id="7a079-206">What do I do if there is an error?</span></span>
<span data-ttu-id="7a079-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="7a079-207"></span></span>

<span data-ttu-id="7a079-208">Quando você executa o cmdlet  `Get-CsMeetingMigrationStatus` para ver um resumo e o estado Com falhaé observado, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7a079-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="7a079-p123">Determine quais usuários são afetados. Execute o comando a seguir para obter a lista de usuários afetados e o erro específico que foi informado:</span><span class="sxs-lookup"><span data-stu-id="7a079-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="7a079-211">Para cada um desses usuários, execute a [ferramenta de migração de reuniões](https://go.microsoft.com/fwlink/p/?linkid=626047) para fazer a migração manual de suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="7a079-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="7a079-212">Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:</span><span class="sxs-lookup"><span data-stu-id="7a079-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="7a079-213">Fazer os usuários criarem novas reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="7a079-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="7a079-214">[Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="7a079-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="7a079-215">Habilitando e desabilitando o MMS</span><span class="sxs-lookup"><span data-stu-id="7a079-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="7a079-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="7a079-216"></span></span>

<span data-ttu-id="7a079-217">O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7a079-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="7a079-218">Por exemplo, se quiser migrar todas as reuniões manualmente ou se usar um provedor de serviços de audioconferência de terceiros, talvez você não precise executar o MMS.</span><span class="sxs-lookup"><span data-stu-id="7a079-218">For example, if you want to manually migrate all meetings or if you use a third-party dial-in conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="7a079-219">Você também pode optar por desativar o MMS temporariamente.</span><span class="sxs-lookup"><span data-stu-id="7a079-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="7a079-220">Por exemplo, se estiver alterando substancialmente as configurações de audioconferência da organização e não quiser que o MMS seja executado até que todas as alterações sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="7a079-220">For example, you may be doing substantial changes to the dial-in conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="7a079-p125">Para ver se o MMS está habilitado em sua organização, execute o comando a seguir e confira o valor do parâmetro  `MeetingMigrationEnabled`. Se esse parâmetro está definido como $true, o MMS está habilitado.</span><span class="sxs-lookup"><span data-stu-id="7a079-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="7a079-223">Para desabilitar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="7a079-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="7a079-224">Para ativar o MMS, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="7a079-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="7a079-225">Ativar e desativar o MMS somente para alterações de audioconferência</span><span class="sxs-lookup"><span data-stu-id="7a079-225">Enabling and disabling MMS only for dial-in conferencing changes</span></span>
<span data-ttu-id="7a079-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="7a079-226"></span></span>

<span data-ttu-id="7a079-227">Você também pode desativar o MMS somente para alterações de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7a079-227">You can also disable MMS only for dial-in conferencing changes.</span></span> <span data-ttu-id="7a079-228">Ele continuará sendo executado quando um usuário migrar do Skype for Business local para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="7a079-228">It will still run when a user is migrated from Skype on-premises to Skype for Business Online.</span></span> <span data-ttu-id="7a079-229">Para verificar o status atual do MMS para atualizações de audioconferência, execute o comando a seguir e confira o valor do parâmetro  `AutomaticallyMigrateUserMeetings`.</span><span class="sxs-lookup"><span data-stu-id="7a079-229">To check the current MMS status for dial-in conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="7a079-230">Se esse parâmetro está definido como $true, o MMS está definido para atualizar as reuniões do usuário quando as configurações de audioconferência forem alteradas.</span><span class="sxs-lookup"><span data-stu-id="7a079-230">If this parameter is set to$true, MMS is set to update user meetings when dial-in conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="7a079-231">Para desativar o MMS para audioconferência, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a079-231">To disable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="7a079-232">Para ativar o MMS para audioconferência, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a079-232">To enable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="7a079-233">Como executo a Migração de Reunião manualmente para um usuário?</span><span class="sxs-lookup"><span data-stu-id="7a079-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="7a079-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="7a079-234"></span></span>

<span data-ttu-id="7a079-235">Além das migrações automáticas de reunião, você também pode executar a migração de reunião manualmente para um usuário executando o cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="7a079-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="7a079-236">Este cmdlet adiciona o usuário na fila de migração de reunião.</span><span class="sxs-lookup"><span data-stu-id="7a079-236">This cmdlet addsthe user in meeting migration queue.</span></span> <span data-ttu-id="7a079-237">O Meeting Migration Service lerá a solicitação do usuário e migrará sua reunião.</span><span class="sxs-lookup"><span data-stu-id="7a079-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="7a079-238">Você pode verificar o status da migração da reunião com o cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="7a079-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="7a079-239">Este é um exemplo que inicia a migração da reunião para o usuário ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="7a079-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="7a079-240">Usando o PowerShell para gerenciar a organização do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7a079-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="7a079-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="7a079-241"></span></span>

 <span data-ttu-id="7a079-242">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="7a079-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="7a079-243">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a079-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7a079-244">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a079-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="7a079-p128">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="7a079-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="7a079-p129">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="7a079-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="7a079-251">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a079-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="7a079-252">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7a079-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="7a079-253">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a079-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7a079-254">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="7a079-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a079-255">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7a079-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="7a079-256">Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a079-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="7a079-p130">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7a079-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7a079-260">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a079-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7a079-261">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="7a079-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7a079-p131">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7a079-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7a079-264">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a079-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7a079-265">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a079-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7a079-266">Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a079-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7a079-267">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7a079-267">Related topics</span></span>

[<span data-ttu-id="7a079-268">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="7a079-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
