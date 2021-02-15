---
title: Alterar números de telefone na ponte de Audioconferência
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
description: Conheça as etapas necessárias para atribuir um novo número de telefone de serviço à ponte de conferência para expandir a cobertura para os usuários.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918747"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="95179-103">Alterar os números de telefone em sua ponte de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="95179-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="95179-104">Quando você compra **licenças de Audioconferência,** a Microsoft hospeda sua ponte de audioconferência para sua organização.</span><span class="sxs-lookup"><span data-stu-id="95179-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="95179-105">A ponte de audioconferência fornece números de telefone de discagem de locais diferentes para que os organizadores e participantes da reunião possam usá-los para ingressar em reuniões do Skype for Business ou do Microsoft Teams usando um telefone.</span><span class="sxs-lookup"><span data-stu-id="95179-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="95179-106">Além dos números de telefone já atribuídos à ponte de conferência, você pode obter números de serviço adicionais [(números](/microsoftteams/getting-service-phone-numbers) de chamada tarifada e gratuita usados para audioconferência) de outros locais e atribuí-los à ponte de conferência para que você possa expandir a cobertura para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="95179-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="95179-107">Para poder atribuir/desatribuição de um número de telefone para uma ponte de conferência, o número de telefone deve ser um "*número* de serviço ".</span><span class="sxs-lookup"><span data-stu-id="95179-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="95179-108">Para ver o tipo de número, navege até números de Telefone De Voz no Centro de administração do Microsoft Teams e veja a coluna Tipo   >   **de** Número.</span><span class="sxs-lookup"><span data-stu-id="95179-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="95179-109">Os Créditos de Comunicação do Microsoft 365 ou office 365 devem ser definidos primeiro para que os usuários disquem para a ponte por meio de um número de ligação gratuita.</span><span class="sxs-lookup"><span data-stu-id="95179-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="95179-110">Etapas durante a atribuição de um novo número de telefone de serviço a sua ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="95179-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="95179-111">Etapa 1 - Atribuir o novo número de telefone à ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="95179-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="95179-112">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="95179-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="95179-113">No painel de navegação esquerdo, vá para **números de Telefone** De  >  **Voz.**</span><span class="sxs-lookup"><span data-stu-id="95179-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="95179-114">Selecione o número de telefone na lista e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="95179-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="95179-115">Na página **Editar,** em **Atribuído a,** expanda a lista suspensa e selecione Aplicar **ponte de conferência.**  >  </span><span class="sxs-lookup"><span data-stu-id="95179-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="95179-116">Etapa 2 - Alterar o número de telefone padrão da ponte de conferência (opcional)</span><span class="sxs-lookup"><span data-stu-id="95179-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="95179-117">O número de telefone padrão da ponte de conferência define a ID de chamadas que será usada quando uma chamada de saída for feita por um participante ou pelo organizador de dentro de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="95179-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="95179-118">Somente um número de serviço de tarifa tarifada pode ser definido como o número padrão para sua ponte de conferência; **números de serviço de tarifa gratuita não podem ser definidos como o número padrão da ponte de conferência.**</span><span class="sxs-lookup"><span data-stu-id="95179-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="95179-119">Se você estiver atribuindo um número de serviço de tarifa tarifada e quiser defini-lo como o novo número padrão para a ponte de audioconferência, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="95179-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="95179-120">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="95179-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="95179-121">No painel de navegação esquerdo, vá para   >  **pontes de Conferência de Reuniões.**</span><span class="sxs-lookup"><span data-stu-id="95179-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="95179-122">Realça o número de serviço de tarifa tarifada que você deseja configurar como padrão.</span><span class="sxs-lookup"><span data-stu-id="95179-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="95179-123">Selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="95179-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="95179-124">Etapa 3 - Alterar os números de telefone padrão incluídos nos convites de reunião de usuários (opcional)</span><span class="sxs-lookup"><span data-stu-id="95179-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="95179-125">Os números de telefone padrão de um usuário são aqueles incluídos em seus convites de reunião quando agendam uma reunião.</span><span class="sxs-lookup"><span data-stu-id="95179-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="95179-126">Para obter mais informações, incluindo como os números de telefone padrão são [atribuídos](set-the-phone-numbers-included-on-invites-in-teams.md) para novos usuários, consulte Definir os números de telefone incluídos nos convites no Microsoft Teams ou Definir os números de telefone incluídos nos convites no [Skype for Business Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="95179-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="95179-127">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="95179-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="95179-128">No painel de navegação esquerdo, vá para **Usuários** e clique no nome de exibição do usuário desejado na lista.</span><span class="sxs-lookup"><span data-stu-id="95179-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="95179-129">Ao lado **de Audioconferência,** clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="95179-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="95179-130">Em **Número de tarifa** ou número de **tarifa** gratuita, selecione o número na lista suspenso e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="95179-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="95179-131">Depois que as alterações foram aplicadas, os novos números de telefone padrão serão incluídos nos convites de reunião dos organizadores na próxima vez que agendarem uma nova reunião.</span><span class="sxs-lookup"><span data-stu-id="95179-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="95179-132">Etapa 4 - Atualizar convites de reunião existentes de usuários usando o Serviço de Migração de Reunião (opcional)</span><span class="sxs-lookup"><span data-stu-id="95179-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="95179-133">Para as próximas duas etapas, você precisará iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95179-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="95179-134">Se você atualizou os números de telefone padrão incluídos nos convites de reunião para alguns ou todos os seus usuários, opcionalmente, você pode atualizar convites de reunião que já foram enviados para os usuários em sua organização antes que seus números de telefone padrão fossem alterados usando o Serviço de Migração de Reunião.</span><span class="sxs-lookup"><span data-stu-id="95179-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="95179-135">Para obter informações adicionais, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="95179-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="95179-136">Execute o MMS (Meeting Migration Service) para os usuários que tiveram seus números de telefone padrão alterados na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="95179-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="95179-137">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="95179-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="95179-138">Você também pode visualizar o status de migração da reunião.</span><span class="sxs-lookup"><span data-stu-id="95179-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="95179-139">Todas as reuniões seriam reagendadas, visto que não há operações no estado  *Pendente*  ou *Em Progresso*  .</span><span class="sxs-lookup"><span data-stu-id="95179-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="95179-140">Etapas durante o cancelamento de atribuição de um novo número de telefone de serviço para uma ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="95179-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="95179-141">Quando você cancelar a atribuição de um número de telefone de uma ponte de conferência, os usuários não poderão mais ingressar nas reuniões usando aquele número de telefone.</span><span class="sxs-lookup"><span data-stu-id="95179-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="95179-142">Como o número de telefone está mudando, é importante atualizar todos os usuários que poderiam ter um número de telefone como número padrão (se for o caso) e atualizar seus convites de reunião existentes antes que o número de telefone seja desaferido na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="95179-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="95179-143">Se o número de telefone for removido sem atualizar os usuários e suas reuniões, seus convites de reunião existentes poderão conter um número de telefone que não funcionará para ingressar em suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="95179-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="95179-144">Para as primeiras três etapas, você deverá iniciar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95179-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="95179-145">Para ver como fazer isso, clique [em Quer saber como gerenciar com o Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="95179-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="95179-146">Etapa 1 - Atualizar os usuários que têm o número de telefone a ser desacumprido como um dos números padrão</span><span class="sxs-lookup"><span data-stu-id="95179-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="95179-147">Substitua o número de tarifa tarifada ou gratuita padrão para todos os usuários que têm o número a ser não atribuído como número padrão e inicie o processo de reagendar suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="95179-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="95179-148">Para isso, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="95179-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="95179-149">Você também pode alterar o número de usuários padrão de tarifas tarifadas ou gratuitas no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95179-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="95179-150">No entanto, isso não reagendará automaticamente suas reuniões.</span><span class="sxs-lookup"><span data-stu-id="95179-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="95179-151">Para obter informações adicionais, consulte Definir os números de telefone [incluídos](set-the-phone-numbers-included-on-invites-in-teams.md) nos convites no Microsoft Teams ou Definir os números de telefone incluídos nos convites no [Skype for Business Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="95179-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="95179-152">[!OBSERVAçãO] Dependendo do tamanho de sua organização, isso poderia demorar para concluir.</span><span class="sxs-lookup"><span data-stu-id="95179-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="95179-153">Etapa 2 - Visualizar o status de migração da reunião usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95179-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="95179-154">Todas as reuniões serão reagenddas quando não houver operações no estado *Pendente* *ou Em Andamento.*</span><span class="sxs-lookup"><span data-stu-id="95179-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="95179-155">Para obter mais informações sobre o Meeting Migration Service, veja [Configurando o Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="95179-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="95179-156">Etapa 3 - Desa tempos sem a aferição do número de telefone antigo da ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="95179-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="95179-157">![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="95179-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="95179-158">No painel de navegação esquerdo, vá para **números de Telefone** De  >  **Voz.**</span><span class="sxs-lookup"><span data-stu-id="95179-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="95179-159">Se o número de telefone for um número de chamada gratuita, selecione o número de telefone na lista e clique em **Liberar.**</span><span class="sxs-lookup"><span data-stu-id="95179-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="95179-160">Se o número de telefone for um número de chamada tarifada, entre em contato com o suporte [da Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) para que o número de telefone não seja atribuído.</span><span class="sxs-lookup"><span data-stu-id="95179-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="95179-161">Se o número de telefone for um número de chamada gratuita, clique em **Sim** na janela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="95179-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="95179-162">Depois que um número de telefone não for atribuído a partir de uma ponte de audioconferência, o número de telefone não estará mais disponível para os usuários ingressarem em reuniões novas ou existentes.</span><span class="sxs-lookup"><span data-stu-id="95179-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="95179-163">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="95179-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="95179-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="95179-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="95179-165">Para verificar se o Windows PowerShell está pronto</span><span class="sxs-lookup"><span data-stu-id="95179-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="95179-166">Estas etapas verificam se você está executando o Windows PowerShell versão 3.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="95179-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="95179-167">Digite **Menu Iniciar** do Windows  >  **PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="95179-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="95179-168">Digite _Get-Host_ na janela **do Windows PowerShell** para verificar a versão.</span><span class="sxs-lookup"><span data-stu-id="95179-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="95179-169">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95179-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="95179-170">Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0.</span><span class="sxs-lookup"><span data-stu-id="95179-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="95179-171">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="95179-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="95179-172">Você também precisa instalar o módulo do Windows PowerShell para Skype for Business Online que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="95179-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="95179-173">Este módulo tem suporte apenas em computadores de 64 bits e pode ser baixado do Centro de Download da Microsoft no Módulo Windows PowerShell para [Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="95179-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="95179-174">Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="95179-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="95179-175">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95179-175">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="95179-176">Para iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95179-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="95179-177">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="95179-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="95179-178">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="95179-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="95179-179">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="95179-179">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>

> [!NOTE]
> <span data-ttu-id="95179-180">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="95179-180">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="95179-181">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="95179-181">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="95179-182">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="95179-182">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="95179-183">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou conectar-se ao Skype for Business Online usando [o Windows PowerShell.](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="95179-183">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="95179-184">Economizar tempo e automatizar</span><span class="sxs-lookup"><span data-stu-id="95179-184">Save time and automate</span></span>

<span data-ttu-id="95179-185">Para economizar tempo automatizando esse processo, você pode usar os cmdlets [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **Set-CsOnlineDialInConferencingUserDefaultNumber.**</span><span class="sxs-lookup"><span data-stu-id="95179-185">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="95179-186">Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="95179-186">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="95179-187">Para mudar o número de chamada gratuita padrão de um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="95179-187">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="95179-188">Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.</span><span class="sxs-lookup"><span data-stu-id="95179-188">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95179-189">Para encontrar o BridgeID, use **o Get-CsOnlineDialInConferencingBridge.**</span><span class="sxs-lookup"><span data-stu-id="95179-189">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="95179-190">Para definir 8005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:</span><span class="sxs-lookup"><span data-stu-id="95179-190">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="95179-191">Para mudar o número de chamada gratuita padrão de todos os usuários que têm 8005551234 como seu número de chamada gratuita padrão para 8005551239 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="95179-191">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="95179-192">Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA como 8005551234 e reagendar automaticamente suas reuniões, execute:</span><span class="sxs-lookup"><span data-stu-id="95179-192">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="95179-193">O local usado acima precisa corresponder às informações de contato dos usuários definidas no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95179-193">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="95179-194">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="95179-194">Troubleshooting</span></span>

<span data-ttu-id="95179-195">**O botão Desasinalhar não está disponível**</span><span class="sxs-lookup"><span data-stu-id="95179-195">**Unassign button isn't available**</span></span>

<span data-ttu-id="95179-196">Você deseja desapagar um número, mas o botão não está disponível e, ao passar o mouse sobre ele, você será redirecionado para contatar o Suporte com a seguinte mensagem "Números padrão ou compartilhados não podem ser atribuídos a partir da _ponte. Para desa designar números de tarifa dedicados, entre em contato com o suporte._".</span><span class="sxs-lookup"><span data-stu-id="95179-196">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="95179-197">Para obter mais informações sobre as pontes, execute o seguinte Powershell:</span><span class="sxs-lookup"><span data-stu-id="95179-197">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="95179-198">O resultado, além de outras informações, como Identidade, Nome e Região, também deve conter o DefaultServiceNumber.</span><span class="sxs-lookup"><span data-stu-id="95179-198">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="95179-199">**Exemplo,** para desaprotecar, o DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="95179-199">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="95179-200">Sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95179-200">About Windows PowerShell</span></span>

<span data-ttu-id="95179-201">Com o Windows PowerShell, você pode gerenciar usuários e o que eles estão ou não autorizados a fazer.</span><span class="sxs-lookup"><span data-stu-id="95179-201">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="95179-202">O Windows PowerShell pode ajudá-lo a gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário, especialmente quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="95179-202">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="95179-203">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="95179-203">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="95179-204">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95179-204">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="95179-205">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="95179-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="95179-206">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="95179-206">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="95179-207">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="95179-207">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="95179-208">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95179-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="95179-209">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95179-209">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="95179-210">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="95179-210">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="95179-211">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="95179-211">Related topics</span></span>
[<span data-ttu-id="95179-212">Alterar as configurações de uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="95179-212">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
