---
title: Alterar os números de telefone na ponte de audioconferência
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
description: Conheça as etapas necessárias para atribuir um novo número de telefone de serviço à sua ponte de conferência para expandir a cobertura para seus usuários.
ms.openlocfilehash: 233678bd953046eed5e6425e0b1a36c5a39b1061
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780350"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="f4915-103">Alterar os números de telefone em sua ponte de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="f4915-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="f4915-104">Quando você compra licenças de **audioconferência** , a Microsoft está hospedando sua ponte de conferência de áudio para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4915-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="f4915-105">A ponte de audioconferência fornece números de telefone de discagem de locais diferentes para que os organizadores da reunião e os participantes possam usá-los para ingressar em reuniões do Skype for Business ou do Microsoft Teams usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="f4915-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="f4915-106">Além dos números de telefone já atribuídos à sua ponte de conferência, você pode [obter números de serviço adicionais](/microsoftteams/getting-service-phone-numbers) (números de chamada tarifada e de chamada gratuita usados para videoconferências) de outros locais e atribuí-los à ponte de conferência para que você possa expandir a cobertura para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f4915-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4915-107">Para poder atribuir/cancelar a atribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um número de "*serviço*".</span><span class="sxs-lookup"><span data-stu-id="f4915-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="f4915-108">Você pode ver o tipo de número ao navegar para números de **Voice** > **telefone** de voz no portal herdado e procurar na coluna **tipo de número** .</span><span class="sxs-lookup"><span data-stu-id="f4915-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="f4915-109">Os créditos de comunicações do Office 365 devem ser configurados primeiro para que os usuários disquem para a ponte em um número de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="f4915-109">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="f4915-110">Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="f4915-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="f4915-111">Etapa 1-atribuir o novo número de telefone à sua ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="f4915-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="f4915-112">Entre no Office 365 com sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="f4915-112">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="f4915-113">Vá para **Centro** > de administração do Microsoft 365 Teams**centers** > Administration**Teams &** > **números de telefone**de**voz** > do**portal** > herdado do Skype</span><span class="sxs-lookup"><span data-stu-id="f4915-113">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="f4915-114">Selecione o número de telefone na lista e, no painel Ação, clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="f4915-114">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="f4915-115">Na página **Atribuir**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4915-115">On the **Assign** page, click **Save**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="f4915-116">Etapa 2-alterar o número de telefone padrão da sua ponte de conferência (opcional)</span><span class="sxs-lookup"><span data-stu-id="f4915-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="f4915-117">O número de telefone padrão da sua ponte de conferência define a identificação de chamadas que será usada quando uma chamada de saída for feita por um participante ou pelo organizador dentro de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="f4915-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="f4915-118">Somente um número de chamada de serviço pode ser definido como o número padrão para a sua ponte de conferência; **números de chamada gratuita do serviço não podem ser definidos como o número padrão de sua ponte de conferência**.</span><span class="sxs-lookup"><span data-stu-id="f4915-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="f4915-119">Se você estiver atribuindo um número de chamada de serviço e quiser defini-lo como o novo número padrão para a sua ponte de audioconferência, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f4915-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="f4915-120">Entre no Office 365 com sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="f4915-120">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="f4915-121">Vá para **Centro** > **Admin centers** > de administração do Microsoft 365 Team centers**Teams & reuniões do Skype** > **reuniões** > **conferência**.</span><span class="sxs-lookup"><span data-stu-id="f4915-121">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="f4915-122">Realce o número de chamada de serviço que você deseja configurar como padrão.</span><span class="sxs-lookup"><span data-stu-id="f4915-122">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="f4915-123">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="f4915-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="f4915-124">Etapa 3-alterar os números de telefone padrão que estão incluídos nos convites de reunião de usuários (opcional)</span><span class="sxs-lookup"><span data-stu-id="f4915-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="f4915-125">Os números de telefone padrão de um usuário são aqueles que estão incluídos nos convites de reunião quando eles agendam uma reunião.</span><span class="sxs-lookup"><span data-stu-id="f4915-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="f4915-126">Para obter mais informações, incluindo como os números de telefone do defaul são atribuídos para novos usuários, consulte [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir os números de telefone incluídos nos convites no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="f4915-126">For more information, including how the defaul phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="f4915-127">Entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f4915-127">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f4915-128">Vá para o & **centro de administração do 365** > **de administração** > do centro de administração do,**usuários**de**videoconferência** > **do** > **portal** > herdado do Skype e selecione os usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="f4915-128">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="f4915-129">Clique em **Editar** no painel de ação.</span><span class="sxs-lookup"><span data-stu-id="f4915-129">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="f4915-130">Em **número de chamada padrão** ou **número de chamada gratuita padrão**, selecione o número na lista e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4915-130">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="f4915-131">Depois que as alterações forem salvas, os novos números de telefone padrão serão incluídos nos convites de reunião dos organizadores na próxima vez que agendarem uma nova reunião.</span><span class="sxs-lookup"><span data-stu-id="f4915-131">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="f4915-132">Etapa 4-atualizar os convites de reunião existentes de usuários usando o serviço de migração de reunião (opcional)</span><span class="sxs-lookup"><span data-stu-id="f4915-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="f4915-133">Para as próximas duas etapas, será necessário iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4915-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="f4915-134">Se você atualizou os números de telefone padrão que estão inlcuded nos convites de reunião para alguns ou todos os seus usuários, você pode, opcionalmente, atualizar os convites de reunião que já foram enviados para os usuários de sua organização antes de seus números de telefone padrão terem sido alterados usando o serviço de migração de reunião.</span><span class="sxs-lookup"><span data-stu-id="f4915-134">If you updated the default phone numbers that are inlcuded in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="f4915-135">Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="f4915-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="f4915-136">Execute o serviço de migração de reunião (MMS) para os usuários que tiveram seus números de telefone padrão alterados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f4915-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="f4915-137">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4915-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="f4915-138">Você também pode visualizar o status de migração da reunião.</span><span class="sxs-lookup"><span data-stu-id="f4915-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="f4915-139">Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .</span><span class="sxs-lookup"><span data-stu-id="f4915-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="f4915-140">Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="f4915-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="f4915-141">Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone.</span><span class="sxs-lookup"><span data-stu-id="f4915-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="f4915-142">Como o número de telefone está mudando, é importante atualizar todos os usuários que podem ter um número de telefone como número padrão (se houver) e atualizar seus convites de reunião existentes antes que o número de telefone seja reatribuído da ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="f4915-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="f4915-143">Se o número de telefone for removido sem Atualizar os usuários e suas reuniões, os convites de reunião existentes poderão conter um número de telefone que não funcionará para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f4915-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="f4915-144">Para as primeiras três etapas, você deverá iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4915-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="f4915-145">Para ver como fazer isso, clique em [deseja saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="f4915-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="f4915-146">Etapa 1: atualizar os usuários que têm o número de telefone para serem reatribuídos como um dos números padrão</span><span class="sxs-lookup"><span data-stu-id="f4915-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="f4915-147">Substitua o número de chamada tarifada ou gratuita padrão de todos os usuários que tenham o número a ser atribuído como um número padrão e inicie o processo de reagendar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f4915-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="f4915-148">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4915-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="f4915-149">Você também pode alterar o número de chamada tarifada ou gratuita padrão de usuários no centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f4915-149">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="f4915-150">No entanto, isso não reagendará automaticamente suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="f4915-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="f4915-151">Para obter mais informações, consulte [definir os números de telefone incluídos nos convites do Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [definir os números de telefone incluídos nos convites no Skype for Business online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span><span class="sxs-lookup"><span data-stu-id="f4915-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f4915-152">[!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.</span><span class="sxs-lookup"><span data-stu-id="f4915-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="f4915-153">Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4915-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="f4915-154">Todas as reuniões serão reagendadas quando não houver operações no estado *pendente* ou *em andamento* .</span><span class="sxs-lookup"><span data-stu-id="f4915-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="f4915-155">Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="f4915-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="f4915-156">Etapa 3-cancelar a atribuição do número de telefone antigo da ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="f4915-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="f4915-157">Entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="f4915-157">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="f4915-158">Vá para o **centro de administração do 365 do centro** > **Admin centers** > de administração do Microsoft &**números de telefone**de**voz** > do**portal** > herdado**do Skype** > .</span><span class="sxs-lookup"><span data-stu-id="f4915-158">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="f4915-159">Se o número de telefone for um número de chamada gratuita, selecione o número de telefone na lista e, no painel Ação, clique em **Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="f4915-159">If the phone number is a toll-free number, select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> <span data-ttu-id="f4915-160">Se o número de telefone for um número de chamada tarifada, entre em contato com o [suporte da Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que o número de telefone não seja atribuído.</span><span class="sxs-lookup"><span data-stu-id="f4915-160">If the phone number is a toll-number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

4. <span data-ttu-id="f4915-161">Se o número de telefone for um número de chamada de fre, clique em **Sim** na janela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="f4915-161">If the phone number is a toll-fre number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f4915-162">Após a atribuição de um número de telefone de uma ponte de audioconferência, o número de telefone não estará mais disponível para que os usuários ingressem em reuniões novas ou existentes.</span><span class="sxs-lookup"><span data-stu-id="f4915-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f4915-163">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f4915-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="f4915-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="f4915-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="f4915-165">Para verificar se o Windows PowerShell está pronto</span><span class="sxs-lookup"><span data-stu-id="f4915-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="f4915-166">Estas etapas verificam se você está executando o Windows PowerShell versão 3,0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f4915-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="f4915-167">Digite **menu** > iniciar**Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f4915-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="f4915-168">Digite _Get-Host_ na janela do **Windows PowerShell** para verificar a versão.</span><span class="sxs-lookup"><span data-stu-id="f4915-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="f4915-169">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4915-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="f4915-170">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="f4915-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="f4915-171">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="f4915-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="f4915-172">Você também precisa instalar o módulo do Windows PowerShell para o Skype for Business online que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f4915-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="f4915-173">Este módulo tem suporte apenas em computadores de 64 bits e pode ser baixado do centro de download da Microsoft no [módulo do Windows PowerShell para Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="f4915-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="f4915-174">Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="f4915-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="f4915-175">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="f4915-175">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="f4915-176">Para iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4915-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="f4915-177">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f4915-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="f4915-178">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="f4915-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="f4915-179">Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="f4915-179">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="f4915-180">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f4915-180">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="f4915-181">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou conectar-se [ao Skype for Business online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f4915-181">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="f4915-182">Economize tempo e automatize</span><span class="sxs-lookup"><span data-stu-id="f4915-182">Save time and automate</span></span>

<span data-ttu-id="f4915-183">Para poupar tempo automatizando esse processo, você pode usar os cmdlets [set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **set-CsOnlineDialInConferencingUserDefaultNumber** .</span><span class="sxs-lookup"><span data-stu-id="f4915-183">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="f4915-184">Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="f4915-184">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="f4915-185">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="f4915-185">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="f4915-186">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="f4915-186">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4915-187">Para localizar o Bridgeid, use **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="f4915-187">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="f4915-188">Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:</span><span class="sxs-lookup"><span data-stu-id="f4915-188">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="f4915-189">Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="f4915-189">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="f4915-190">Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="f4915-190">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="f4915-191">O local usado acima precisa corresponder às informações de contato do (s) usuário (s) definido (s) no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4915-191">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f4915-192">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f4915-192">Troubleshooting</span></span>

<span data-ttu-id="f4915-193">**O botão Cancelar atribuição está acinzentado**</span><span class="sxs-lookup"><span data-stu-id="f4915-193">**Unassign button is greyed-out**</span></span>

<span data-ttu-id="f4915-194">Você deseja cancelar a atribuição de um número, mas o botão está esmaecido e, se enquanto hoovering sobre ele, você será redirecionado para contatar o suporte com a seguinte mensagem _"os números padrão ou compartilhados podem possível ser cancelados da ponte. Para cancelar a atribuição de números de chamada dedicada, entre em contato com o suporte._".</span><span class="sxs-lookup"><span data-stu-id="f4915-194">You want to Unassign a number but the button is greyed-out and if while hoovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="f4915-195">Para obter mais informações sobre a (s) ponte (s), execute o seguinte PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f4915-195">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="f4915-196">O resultado, além de outras informações, como identidade, nome e região, também devem conter o DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="f4915-196">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="f4915-197">**Exemplo**, para cancelar a atribuição, o DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="f4915-197">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="f4915-198">Sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4915-198">About Windows PowerShell</span></span>

<span data-ttu-id="f4915-199">Com o Windows PowerShell você pode gerenciar usuários e o que eles estão ou não podem fazer.</span><span class="sxs-lookup"><span data-stu-id="f4915-199">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="f4915-200">O Windows PowerShell pode ajudá-lo a gerenciar o Office 365 e o Skype for Business online usando um único ponto de administração que pode simplificar seu trabalho diário, especialmente quando você tem várias tarefas para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="f4915-200">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="f4915-201">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f4915-201">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="f4915-202">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4915-202">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="f4915-203">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="f4915-203">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="f4915-204">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="f4915-204">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f4915-205">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f4915-205">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="f4915-206">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4915-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="f4915-207">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4915-207">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="f4915-208">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f4915-208">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="f4915-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f4915-209">Related topics</span></span>
[<span data-ttu-id="f4915-210">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="f4915-210">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
