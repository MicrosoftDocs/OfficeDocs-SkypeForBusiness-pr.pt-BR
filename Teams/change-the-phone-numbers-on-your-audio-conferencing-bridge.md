---
title: Alterar números de telefone na ponte audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba as etapas necessárias para atribuir um novo número de telefone de serviço à ponte de conferência para expandir a cobertura para seus usuários.
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102653"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="35144-103">Alterar os números de telefone em sua ponte de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="35144-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="35144-104">Quando você compra **licenças de Audioconferência,** a Microsoft está hospedando sua ponte de audioconferência para sua organização.</span><span class="sxs-lookup"><span data-stu-id="35144-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="35144-105">A ponte de audioconferência fornece números de telefone discados de locais diferentes para que os organizadores e participantes da reunião possam usá-los para ingressar em reuniões do Skype for Business ou do Microsoft Teams usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="35144-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="35144-106">Além dos números de telefone já atribuídos à ponte de conferência, você pode obter números de serviço adicionais [(números](./getting-service-phone-numbers.md) de chamada gratuita e de chamada gratuita usados para audioconferência) de outros locais e atribuí-los à ponte de conferência para que você possa expandir a cobertura para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="35144-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35144-107">Para poder atribuir/desatribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de '*serviço*'.</span><span class="sxs-lookup"><span data-stu-id="35144-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="35144-108">Você pode ver o tipo de número que é navegando até números de Telefone de Voz no centro de administração do Microsoft Teams e olhando na  >   coluna **Tipo de** Número.</span><span class="sxs-lookup"><span data-stu-id="35144-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="35144-109">Os Créditos de Comunicações do Microsoft 365 ou Office 365 devem ser definidos primeiro para que os usuários discem para a ponte em um número gratuito.</span><span class="sxs-lookup"><span data-stu-id="35144-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="35144-110">Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="35144-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="35144-111">Etapa 1 - Atribuir o novo número de telefone à ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="35144-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="35144-112">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="35144-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="35144-113">No painel de navegação esquerdo, vá para **Números de Telefone** de  >  **Voz**.</span><span class="sxs-lookup"><span data-stu-id="35144-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="35144-114">Selecione o número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="35144-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="35144-115">Na página **Editar,** em **Atribuído a**, expanda a lista suspensa e selecione **Ponte de Conferência**  >  **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="35144-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="35144-116">Etapa 2 - Alterar o número de telefone padrão da ponte de conferência (opcional)</span><span class="sxs-lookup"><span data-stu-id="35144-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="35144-117">O número de telefone padrão da ponte de conferência define a ID do chamador que será usada quando uma chamada de saída é feita por um participante ou pelo organizador de dentro de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="35144-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="35144-118">Somente um número de tarifa de serviço pode ser definido como o número padrão da ponte de conferência; **os números de serviço gratuito não podem ser definidos como o número padrão da ponte de conferência.**</span><span class="sxs-lookup"><span data-stu-id="35144-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="35144-119">Se você estiver atribuindo um número de tarifa de serviço e quiser defini-lo como o novo número padrão da ponte de audioconferência, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="35144-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="35144-120">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="35144-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="35144-121">No painel de navegação esquerdo, vá para Pontes **de**  >  **Conferência de Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="35144-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="35144-122">Realça o número de tarifa de serviço que você deseja configurar como padrão.</span><span class="sxs-lookup"><span data-stu-id="35144-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="35144-123">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="35144-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="35144-124">Etapa 3 - Alterar os números de telefone padrão incluídos nos convites de reunião dos usuários (opcional)</span><span class="sxs-lookup"><span data-stu-id="35144-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="35144-125">Os números de telefone padrão de um usuário são os que estão incluídos em seus convites de reunião ao agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="35144-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="35144-126">Para obter mais informações, incluindo como os números de telefone padrão são atribuídos para novos usuários, consulte Definir os números de telefone incluídos em [convites](set-the-phone-numbers-included-on-invites-in-teams.md) no Microsoft Teams ou Definir os números de telefone incluídos em [convites](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)no Skype for Business Online .</span><span class="sxs-lookup"><span data-stu-id="35144-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="35144-127">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="35144-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="35144-128">No painel de navegação esquerdo, vá para **Usuários** e clique no nome de exibição do usuário desejado na lista.</span><span class="sxs-lookup"><span data-stu-id="35144-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="35144-129">Ao lado **de Audioconferência,** clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="35144-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="35144-130">Em **Número de Telefone** ou Número de Tarifa **gratuita,** selecione o número na lista de menus suspenso e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="35144-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="35144-131">Depois que as alterações foram aplicadas, os novos números de telefone padrão serão incluídos nos convites de reunião dos organizadores na próxima vez que agendar uma nova reunião.</span><span class="sxs-lookup"><span data-stu-id="35144-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="35144-132">Etapa 4 - Atualizar convites de reunião existentes de usuários usando o Serviço de Migração de Reunião (opcional)</span><span class="sxs-lookup"><span data-stu-id="35144-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="35144-133">Para as próximas duas etapas, você precisará começar a Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35144-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="35144-134">Se você atualizou os números de telefone padrão incluídos nos convites da reunião para alguns ou todos os usuários, você pode, opcionalmente, atualizar convites de reunião que já foram enviados aos usuários em sua organização antes que seus números de telefone padrão fossem alterados usando o Serviço de Migração de Reunião.</span><span class="sxs-lookup"><span data-stu-id="35144-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="35144-135">Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="35144-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="35144-136">Execute o Serviço de Migração de Reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="35144-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="35144-137">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="35144-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="35144-138">Você também pode visualizar o status de migração da reunião.</span><span class="sxs-lookup"><span data-stu-id="35144-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="35144-139">Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .</span><span class="sxs-lookup"><span data-stu-id="35144-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="35144-140">Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="35144-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="35144-141">Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone.</span><span class="sxs-lookup"><span data-stu-id="35144-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="35144-142">Como o número de telefone está mudando, é importante atualizar todos os usuários que poderiam ter um número de telefone como número padrão (se algum) e atualizar seus convites de reunião existentes antes que o número de telefone seja não atribuído da ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="35144-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="35144-143">Se o número de telefone for removido sem atualizar os usuários e suas reuniões, os convites de reunião existentes poderão conter um número de telefone que não funcionará para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="35144-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="35144-144">Para as primeiras três etapas, você deverá iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35144-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="35144-145">Para ver como fazer isso, clique em [Deseja saber como gerenciar com Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="35144-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="35144-146">Etapa 1 - Atualizar usuários que têm o número de telefone a ser não atribuído como um de seus números padrão</span><span class="sxs-lookup"><span data-stu-id="35144-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="35144-147">Substitua o número padrão de tarifa ou gratuita para todos os usuários que têm o número a ser não atribuído como um número padrão e inicie o processo de remarcar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="35144-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="35144-148">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="35144-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="35144-149">Você também pode alterar o número de usuários de tarifação padrão ou gratuita no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="35144-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="35144-150">No entanto, isso não reagendará automaticamente suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="35144-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="35144-151">Para obter informações adicionais, consulte [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or Set the phone numbers included on [invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="35144-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="35144-152">[!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.</span><span class="sxs-lookup"><span data-stu-id="35144-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="35144-153">Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35144-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="35144-154">Todas as reuniões serão reagendadas depois que não houver operações no estado *Pendente* ou *Em Andamento.*</span><span class="sxs-lookup"><span data-stu-id="35144-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="35144-155">Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="35144-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="35144-156">Etapa 3 - Desaignar o número de telefone antigo da ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="35144-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="35144-157">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="35144-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="35144-158">Na navegação à esquerda, vá para **Números de Telefone** de  >  **Voz**.</span><span class="sxs-lookup"><span data-stu-id="35144-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="35144-159">Se o número de telefone for um número de chamada gratuita, selecione o número de telefone da lista e clique em **Liberar**.</span><span class="sxs-lookup"><span data-stu-id="35144-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="35144-160">Se o número de telefone for um número de chamada, entre em contato com o suporte [da Microsoft](/microsoft-365/admin/contact-support-for-business-products) para que o número de telefone não seja atribuído.</span><span class="sxs-lookup"><span data-stu-id="35144-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="35144-161">Se o número de telefone for um número de chamada gratuita, clique **em Sim** na janela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="35144-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="35144-162">Depois que um número de telefone não for atribuído a partir de uma ponte de audioconferência, o número de telefone não estará mais disponível para os usuários ingressarem em reuniões novas ou existentes.</span><span class="sxs-lookup"><span data-stu-id="35144-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="35144-163">Economizar tempo e automatizar</span><span class="sxs-lookup"><span data-stu-id="35144-163">Save time and automate</span></span>

<span data-ttu-id="35144-164">Para economizar tempo automatizando esse processo, você pode usar os cmdlets [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) ou **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="35144-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="35144-165">Use o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="35144-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="35144-166">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="35144-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="35144-167">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="35144-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35144-168">Para encontrar o BridgeID, use **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="35144-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="35144-169">Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:</span><span class="sxs-lookup"><span data-stu-id="35144-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="35144-170">Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="35144-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="35144-171">Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="35144-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="35144-172">O local usado acima precisa corresponder às informações de contato dos usuários definidas no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35144-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="35144-173">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="35144-173">Troubleshooting</span></span>

<span data-ttu-id="35144-174">**O botão Desinfere não está disponível**</span><span class="sxs-lookup"><span data-stu-id="35144-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="35144-175">Você deseja desaignar um número, mas o botão não está disponível e, se passar o mouse sobre ele, você será redirecionado para contatar o Suporte com a seguinte mensagem "Números padrão ou compartilhados não podem ser atribuídos da _ponte. Para desaignar números de telefone dedicados, entre em contato com o suporte._".</span><span class="sxs-lookup"><span data-stu-id="35144-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="35144-176">Para obter mais informações sobre a(s) ponte(s), execute o seguinte Powershell :</span><span class="sxs-lookup"><span data-stu-id="35144-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="35144-177">O resultado, além de outras informações como Identidade, Nome e Região, também deve conter DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="35144-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="35144-178">**Exemplo**, para desaproteção, o DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="35144-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="35144-179">Sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35144-179">About Windows PowerShell</span></span>

<span data-ttu-id="35144-180">Com Windows PowerShell você pode gerenciar usuários e o que eles são ou não têm permissão para fazer.</span><span class="sxs-lookup"><span data-stu-id="35144-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="35144-181">Windows PowerShell pode ajudá-lo a gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, especialmente quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="35144-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="35144-182">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="35144-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="35144-183">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35144-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="35144-184">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="35144-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="35144-185">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="35144-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="35144-186">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="35144-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="35144-187">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="35144-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="35144-188">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35144-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="35144-189">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35144-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="35144-190">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="35144-190">Related topics</span></span>
[<span data-ttu-id="35144-191">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="35144-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)