---
title: Alterar os números de telefone de sua ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Quando você adquire licenças de serviços de audioconferência, a Microsoft está hospedando sua ponte de conferência de áudio para sua organização. A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone.
ms.openlocfilehash: 26a6e8dcb467ceea990b974d1687e0a5998eeb4b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372238"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="a3f1f-104">Alterar os números de telefone de sua ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="a3f1f-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="a3f1f-105">Quando você adquire licenças de **Serviços de audioconferência** , a Microsoft está hospedando sua *ponte de conferência de áudio* para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your *audio conferencing bridge*  for your organization.</span></span> <span data-ttu-id="a3f1f-106">A ponte de conferência de áudio oferece check-out de números de telefone de discagem de diferentes locais para que participantes e os organizadores da reunião podem usá-los para ingressar Skype para reuniões de negócios ou Microsoft Teams usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="a3f1f-107">Além dos números já atribuídos a sua ponte de conferência, você pode [obter os números de serviço adicionais](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (tarifas e números para ligações gratuitas usados para serviços de audioconferência) de outros locais e, em seguida, atribui-los para a conferência ponte para que você possa Expanda cobertura para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3f1f-108">Para poder atribuir/retirar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de '*service*'.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="a3f1f-109">Você pode ver o tipo de número é navegando até **voz** > **números de telefone** e procurando na coluna **Tipo de número** .</span><span class="sxs-lookup"><span data-stu-id="a3f1f-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column.</span></span> <span data-ttu-id="a3f1f-110">Créditos de comunicações do Office 365 deve ser configurados primeiro, em ordem, para que os usuários discam para a ponte de um número de telefone gratuito.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="a3f1f-111">Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="a3f1f-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="a3f1f-112">Etapa 1 - atribuir o novo número de telefone para sua ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="a3f1f-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="a3f1f-113">Entre no Office 365 com sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="a3f1f-114">Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **voz** > **números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-114">Go to the **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="a3f1f-115">Selecione o número de telefone da lista e, no painel de ações, clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="a3f1f-116">Na página **Atribuir**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="a3f1f-117">Apenas um número de Chamada Tarifada do serviço pode ser definido como o número padrão para sua ponte de conferência; **números para ligações gratuitas service não podem ser definidos como o número padrão de sua ponte de conferência**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-117">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="a3f1f-118">Se você estiver atribuindo um número de Chamada Tarifada do serviço e você gostaria de defini-la como o novo número padrão para sua ponte de conferência de áudio, selecione **usar este número como padrão**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-118">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, select **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3f1f-119">[!OBSERVAçãO] Após a atribuição do novo número de telefone, mesmo que ele se torne o novo número padrão, o número padrão dos usuários existentes não mudará.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="a3f1f-120">Para definir as tarifas padrão ou um número de chamada gratuito que é adicionado à convites de reunião do organizador, consulte as instruções para [As equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou as instruções para [Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see the instructions for [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or the instructions for [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span> 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="a3f1f-121">Etapa 2 - Alterar os números de telefone padrão que são incluídos nos convites de reunião de usuários (opcional)</span><span class="sxs-lookup"><span data-stu-id="a3f1f-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="a3f1f-122">Os números de telefone padrão para o usuário são aqueles incluídos em seus convites de reunião quando agendam uma reunião.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="a3f1f-123">Para obter mais informações, consulte [definir o telefone números incluídos no convidam em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir o telefone números incluídos no convidam no Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-123">For more information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="a3f1f-124">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a3f1f-125">Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **audioconferências** > **usuários** e selecione os usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-125">Go to the **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users** and select the users in the list.</span></span>

3. <span data-ttu-id="a3f1f-126">Clique em **Editar** no painel de ação.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="a3f1f-127">Em **número de Chamada Tarifada padrão** ou **número de chamada gratuito padrão**, selecione o número na lista e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-127">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="a3f1f-128">Depois que as alterações foram salvas, o novo telefone padrão números serão incluídos na reunião convida de organizadores na próxima vez em que eles agendarem uma nova reunião.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-128">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="a3f1f-129">Etapa 3 - Atualizar convites de reunião existentes de usuários do Meeting Migration Service (opcional)</span><span class="sxs-lookup"><span data-stu-id="a3f1f-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="a3f1f-130">As próximas duas etapas, você precisará para iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-130">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="a3f1f-131">Usando o serviço de migração de reunião, você poderá atualizar opcionalmente convites de reunião que já foram enviados aos usuários em sua organização antes de seus números de telefone padrão foram alterados.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-131">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed.</span></span> <span data-ttu-id="a3f1f-132">Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-132">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="a3f1f-133">Execute o serviço de migração de reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-133">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="a3f1f-134">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-134">To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="a3f1f-p109">Você também pode visualizar o status de migração da reunião. Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .</span><span class="sxs-lookup"><span data-stu-id="a3f1f-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="a3f1f-137">Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="a3f1f-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="a3f1f-138">Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-138">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="a3f1f-139">Como o número de telefone está mudando, é importante para atualizar todos os usuários que poderia ter um número de telefone como seu número padrão (se houver) e atualizar seus convites de reunião antes que o número de telefone não atribuído da ponte de conferência de áudio existentes.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-139">Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="a3f1f-140">Se o número de telefone for removido sem atualizar os usuários e suas reuniões, os convites de reunião existentes poderiam conter um número de telefone que não funcionará mais para ingressar nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="a3f1f-141">Para as primeiras três etapas, você deverá iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="a3f1f-142">Para ver como fazer isso, clique em [para saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="a3f1f-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="a3f1f-143">Etapa 1 - Atualizar usuários que terão a atribuição de um de seus números padrão cancelada</span><span class="sxs-lookup"><span data-stu-id="a3f1f-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="a3f1f-p112">Substituir o número de chamada tarifada ou gratuita para todos os usuários que têm o número que deixará de ser o número padrão e iniciar o processo de reagendamento das reuniões. Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="a3f1f-146">Você também pode alterar o tarifas padrão ou gratuito número de usuários no Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-146">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="a3f1f-147">No entanto, isso automaticamente não reagendar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-147">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="a3f1f-148">Para obter informações adicionais, consulte [definir o telefone números incluídos no convidam em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir o telefone números incluídos no convidam no Skype para negócios Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-148">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a3f1f-149">[!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="a3f1f-150">Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3f1f-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="a3f1f-151">Todas as reuniões serão ser reagendadas quando não há nenhuma operação no estado *pendente* ou *Em andamento* .</span><span class="sxs-lookup"><span data-stu-id="a3f1f-151">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="a3f1f-152">Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="a3f1f-153">Etapa 3 - retirar o antigo número de telefone de ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="a3f1f-153">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="a3f1f-154">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="a3f1f-155">Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes & Skype** > **portal herdada** > **voz** > **números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-155">Go to the **Office 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="a3f1f-156">Selecione o número de telefone da lista e, no painel de ações, clique em **não atribuído**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-156">Select the phone number from the list, and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="a3f1f-157">Na janela de confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-157">In the confirmation window, click **Yes**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a3f1f-158">Após um número de telefone não atribuído a partir de uma ponte de conferência de áudio, o número de telefone ficarão mais disponível para os usuários ingressem em reuniões de novos ou existentes.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-158">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a3f1f-159">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a3f1f-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="a3f1f-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="a3f1f-160"></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="a3f1f-161">Para verificar se o Windows PowerShell está pronto</span><span class="sxs-lookup"><span data-stu-id="a3f1f-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="a3f1f-162">Estas etapas Verifique que você está executando o Windows PowerShell versão 3.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-162">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="a3f1f-163">Digite o **Menu Iniciar** > **do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="a3f1f-164">Digite _Get-Host_ na janela do **Windows PowerShell** para verificar a versão.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="a3f1f-p114">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="a3f1f-168">Você também precisará instalar o módulo do Windows PowerShell para Skype para Business Online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-168">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="a3f1f-169">Este módulo só tem suporte em computadores de 64 bits e pode ser baixado do Microsoft Download Center em um [Módulo do Windows PowerShell para Skype para negócios Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-169">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="a3f1f-170">Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="a3f1f-171">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="a3f1f-172">Para iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3f1f-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="a3f1f-173">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a3f1f-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="a3f1f-174">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="a3f1f-175">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3f1f-176">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="a3f1f-177">Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a3f1f-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="a3f1f-178">Poupe tempo e automatizar</span><span class="sxs-lookup"><span data-stu-id="a3f1f-178">Save time and automate</span></span>

<span data-ttu-id="a3f1f-179">Para poupar tempo automatizando esse processo, você pode usar o [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou os cmdlets **Set-CsOnlineDialInConferencingUserDefaultNumber** .</span><span class="sxs-lookup"><span data-stu-id="a3f1f-179">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="a3f1f-180">Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="a3f1f-181">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="a3f1f-182">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a3f1f-183">Para localizar o BridgeID, use o **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-183">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="a3f1f-184">Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="a3f1f-185">Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="a3f1f-186">Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="a3f1f-187">[!OBSERVAçãO] O local usado acima deve corresponder às informações de contato dos usuários definidas no centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="a3f1f-188">Sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3f1f-188">About Windows PowerShell</span></span>

<span data-ttu-id="a3f1f-189">Com o Windows PowerShell, você pode gerenciar usuários e o que eles são ou não têm permissão para fazer.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="a3f1f-190">Windows PowerShell pode ajudá-lo a gerenciar o Office 365 e Skype para negócios Online usando um único ponto de administração que pode simplificar o seu trabalho diário, especialmente quando você acaba de criar várias tarefas fazer.</span><span class="sxs-lookup"><span data-stu-id="a3f1f-190">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="a3f1f-191">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="a3f1f-192">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a3f1f-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="a3f1f-193">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3f1f-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="a3f1f-p117">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a3f1f-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="a3f1f-196">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3f1f-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="a3f1f-197">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a3f1f-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="a3f1f-198">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a3f1f-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="a3f1f-199">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a3f1f-199">Related topics</span></span>
[<span data-ttu-id="a3f1f-200">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="a3f1f-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
