---
title: Configurar a conferência de áudio para Skype para negócios
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Aprenda a configurar dial-in ou conferência de áudio para as pessoas na sua empresa que precisam usar um telefone para ingressar em chamadas de conferência. '
ms.openlocfilehash: 64ebcb97157d94a5c25ddff38e8e1ca58d3975ec
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633294"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="204e7-103">Configurar a conferência de áudio para Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="204e7-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="204e7-104">Em alguns casos, as pessoas na sua organização precisará usar um telefone para efetuar uma chamada para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="204e7-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="204e7-105">Skype para negócios inclui o recurso de conferência de áudio para apenas essa situação!</span><span class="sxs-lookup"><span data-stu-id="204e7-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="204e7-106">As pessoas podem ligar para Skype para reuniões de negócios usando um telefone, em vez de usar o Skype para aplicativo de negócios em um PC ou dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="204e7-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="204e7-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="204e7-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="204e7-109">Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="204e7-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="204e7-110">Etapa 1: Descobrir se a audioconferência está disponível em seu país/região</span><span class="sxs-lookup"><span data-stu-id="204e7-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="204e7-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-111"><a name="__top"> </a></span></span>

<span data-ttu-id="204e7-112">Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação.</span><span class="sxs-lookup"><span data-stu-id="204e7-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="204e7-113">Etapa 2: Comprar e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="204e7-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="204e7-114">Para caudioonferências, você precisa de uma licença de cada usuário que irá configurar as reuniões discadas.</span><span class="sxs-lookup"><span data-stu-id="204e7-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="204e7-115">Para saber quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo, consulte [Skype para licenciamento de complemento de negócios](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="204e7-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="204e7-116">Serviços de audioconferência é incluído no Office 365 Enterprise E5 licenças e como um complemento.</span><span class="sxs-lookup"><span data-stu-id="204e7-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="204e7-117">Depois que você adquire as licenças de audioconferência, é preciso atribuí-las às pessoas em sua organização que irão agendar ou realizar as reuniões.</span><span class="sxs-lookup"><span data-stu-id="204e7-117">After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="204e7-118">Consulte [atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) você comprou às pessoas em sua organização que pretende agendar ou líder de reuniões.</span><span class="sxs-lookup"><span data-stu-id="204e7-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="204e7-119">Também é recomendável que você atribua licenças créditos de comunicação (são gratuitas) para as mesmas pessoas a quem você atribuiu as licenças na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="204e7-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="204e7-120">Para saber como configurar os créditos de comunicação, consulte [Configurar créditos de comunicação para sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="204e7-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="204e7-121">Você também pode configurar a [Conferência de áudio de pagamento por minuto](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="204e7-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="204e7-122">Etapa 3: Obtenha números de serviço para suas pontes de conferência</span><span class="sxs-lookup"><span data-stu-id="204e7-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="204e7-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-123"></span></span>

<span data-ttu-id="204e7-124">Para audioconferências, você não pode usar números de telefone para usuários; será preciso obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="204e7-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="204e7-125">Você pode obter números de serviço tarifado ou gratuito para suas pontes de conferência.</span><span class="sxs-lookup"><span data-stu-id="204e7-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="204e7-126">Há três maneiras de obter números de serviço tarifado ou gratuito:</span><span class="sxs-lookup"><span data-stu-id="204e7-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="204e7-127">**Use o Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="204e7-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="204e7-128">Para alguns países/regiões, você pode obter os números de serviço para seus pontes de conferência usando o Skype para o Centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="204e7-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="204e7-129">Consulte [Getting números de telefone de serviço](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="204e7-129">See [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span>
    
- <span data-ttu-id="204e7-130">**Porta seus números de serviço existente**.</span><span class="sxs-lookup"><span data-stu-id="204e7-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="204e7-131">Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="204e7-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="204e7-132">Consulte [Transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ou [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações sobre esse assunto.</span><span class="sxs-lookup"><span data-stu-id="204e7-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="204e7-133">**Usar um formulário de solicitação para novos números**.</span><span class="sxs-lookup"><span data-stu-id="204e7-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="204e7-134">Às vezes (dependendo do seu país/região) não será possível obter seus números de serviço nova usando o Skype para o Centro de administração de negócios ou, você precisará de números de telefone específico ou códigos de área.</span><span class="sxs-lookup"><span data-stu-id="204e7-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="204e7-135">Se for o caso, será necessário baixar um formulário e enviá-lo para nós.</span><span class="sxs-lookup"><span data-stu-id="204e7-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="204e7-136">Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="204e7-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="204e7-137">Etapa 4: Atribuir um número de serviço para a ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="204e7-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="204e7-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-138"></span></span>

<span data-ttu-id="204e7-139">Depois que você obtenha sua chamada Tarifada e/ou números de telefone gratuitos para sua ponte de conferência, você precisa atribuir números para que possam ser usadas em convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="204e7-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="204e7-140">Para atribuir um novo número de telefone para sua ponte de audioconferência:</span><span class="sxs-lookup"><span data-stu-id="204e7-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="204e7-141">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**</span><span class="sxs-lookup"><span data-stu-id="204e7-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="204e7-142">Vá para o **Centro de administração do Microsoft 365** > **Admin centrais** > **equipes** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="204e7-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="204e7-143">Selecione **voz** > **números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="204e7-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="204e7-144">Selecione o número de telefone e clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="204e7-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="204e7-145">Para obter mais detalhes, consulte [alterar os números de telefone na sua ponte de conferência de áudio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="204e7-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="204e7-146">Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="204e7-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="204e7-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-147"></span></span>

<span data-ttu-id="204e7-148">Em seguida, você deseja [definir os idiomas de atendedor automático de conferência de áudio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático de conferência usa para saudar chamadores quando eles discam para um número de telefone para audioconferências.</span><span class="sxs-lookup"><span data-stu-id="204e7-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="204e7-149">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:</span><span class="sxs-lookup"><span data-stu-id="204e7-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="204e7-150">No painel, vá para **reuniões** > **pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="204e7-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="204e7-151">Selecione o número de telefone de ponte de conferência, clique em **Editar**e escolha o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="204e7-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="204e7-152">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**:</span><span class="sxs-lookup"><span data-stu-id="204e7-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="204e7-153">Vá para o **Centro de administração do Office 365** > **Admin centrais** > **equipes** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="204e7-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="204e7-154">Selecione **audioconferências** > **ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="204e7-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="204e7-155">Selecione o número de telefone de ponte de conferência, selecione **o conjunto de idiomas**e escolha o idioma padrão.</span><span class="sxs-lookup"><span data-stu-id="204e7-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="204e7-156">Etapa 6: Definir suas configurações da ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="204e7-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="204e7-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-157"></span></span>
    
<span data-ttu-id="204e7-158">Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las.</span><span class="sxs-lookup"><span data-stu-id="204e7-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="204e7-159">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:</span><span class="sxs-lookup"><span data-stu-id="204e7-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="204e7-160">No painel, vá para **reuniões** > **pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="204e7-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="204e7-161">Selecione **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="204e7-161">Select **Bridge settings**.</span></span> <span data-ttu-id="204e7-162">Esse procedimento abrirá o painel **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="204e7-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="204e7-163">Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="204e7-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="204e7-164">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**</span><span class="sxs-lookup"><span data-stu-id="204e7-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="204e7-165">Vá para o **Centro de administração do Microsoft 365** > **Admin centrais** > **equipes** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="204e7-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="204e7-166">Selecione **audioconferências** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="204e7-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="204e7-167">Esse procedimento abrirá a página de **Configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="204e7-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="204e7-168">Para mais detalhes, consulte [Alterar as configurações de uma ponte de audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="204e7-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="204e7-169">Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões</span><span class="sxs-lookup"><span data-stu-id="204e7-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="204e7-170">Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="204e7-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="204e7-171">Você precisará fazer isso para todas as pessoas na sua organização que irão agendar ou realizar as reuniões.</span><span class="sxs-lookup"><span data-stu-id="204e7-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="204e7-172">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**:</span><span class="sxs-lookup"><span data-stu-id="204e7-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="204e7-173">No painel, clique em **usuários**, selecione o usuário na lista e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="204e7-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="204e7-174">Selecione **Editar** ao lado de **Conferência de áudio**e, em seguida, no painel de **Conferência de áudio** , escolha um número nas listas de número de **número de Chamada Tarifada** e de **chamada gratuita** .</span><span class="sxs-lookup"><span data-stu-id="204e7-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="204e7-175">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**</span><span class="sxs-lookup"><span data-stu-id="204e7-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="204e7-176">Vá para o **Centro de administração do Microsoft 365** > **equipes** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="204e7-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="204e7-177">Selecione **audioconferências** > **usuários**e, em seguida, selecione o usuário na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="204e7-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="204e7-178">Se você precisar de mais detalhes, consulte [Atribuir a Microsoft como o provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="204e7-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="204e7-179">Etapa 8: Configurar os convites para reuniões (opcional)</span><span class="sxs-lookup"><span data-stu-id="204e7-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="204e7-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="204e7-180"></span></span>
 
<span data-ttu-id="204e7-181">Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião que são enviados para os participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="204e7-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="204e7-182">No entanto, você pode adicionar seus próprios links jurídico, uma mensagem de texto e um pequeno gráfico da empresa.</span><span class="sxs-lookup"><span data-stu-id="204e7-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="204e7-183">Consulte [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="204e7-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="204e7-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="204e7-184">Related topics</span></span>

[<span data-ttu-id="204e7-185">Perguntas comuns sobre a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="204e7-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="204e7-186">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="204e7-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="204e7-187">Números de telefone para audioconferência</span><span class="sxs-lookup"><span data-stu-id="204e7-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="204e7-188">Definir opções para reuniões online e chamadas em conferência</span><span class="sxs-lookup"><span data-stu-id="204e7-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
