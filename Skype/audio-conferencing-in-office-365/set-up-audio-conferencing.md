---
title: "Configurar conferência de áudio para o Skype for Business e Teams da Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Saiba como configurar a conferência discada ou áudio para as pessoas em sua empresa que precisam para ingressar em chamadas de conferência usando um telefone. "
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="58554-103">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="58554-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="58554-104">Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião.</span><span class="sxs-lookup"><span data-stu-id="58554-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="58554-105">Skype para Teams da Microsoft e de negócios incluir o recurso de conferência de áudio para apenas essa situação!</span><span class="sxs-lookup"><span data-stu-id="58554-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="58554-106">As pessoas podem ligar para Skype para reuniões de negócios ou Microsoft Teams usando um telefone, em vez de usar o Skype para negócios ou Teams Microsoft app em um PC ou dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="58554-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="58554-107">Você precisa configurar a conferência de áudio para as pessoas que pretende agendar ou liderança de reuniões.</span><span class="sxs-lookup"><span data-stu-id="58554-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="58554-108">Os participantes da reunião que discam não precisam quaisquer licenças atribuídas a eles ou outro programa de instalação.</span><span class="sxs-lookup"><span data-stu-id="58554-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="58554-109">Para as perguntas frequentes sobre a conferência de áudio, consulte [perguntas comuns de conferência de áudio](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="58554-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="58554-110">Etapa 1: comprar e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="58554-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="58554-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="58554-111"></span></span>

<span data-ttu-id="58554-112">Você deve ser um [funções de administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="58554-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="58554-113">Descubra se a conferência de áudio no Office 365 está disponível em seu país/região.</span><span class="sxs-lookup"><span data-stu-id="58554-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="58554-114">[Disponibilidade de país e região para conferência de áudio e planos de chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="58554-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="58554-115">Saiba quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo.</span><span class="sxs-lookup"><span data-stu-id="58554-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="58554-116">Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e adquirir as licenças.</span><span class="sxs-lookup"><span data-stu-id="58554-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="58554-117">[Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que você comprou às pessoas na organização que vão agendar ou realizar reuniões.</span><span class="sxs-lookup"><span data-stu-id="58554-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="58554-118">Se adquiriu licenças de complemento de **Conferência de áudio** e licenças créditos de comunicações, atribua muito.</span><span class="sxs-lookup"><span data-stu-id="58554-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="58554-119">Para obter instruções, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="58554-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="58554-120">Etapa 2: Decidir qual seu provedor de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="58554-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="58554-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="58554-121"></span></span>

<span data-ttu-id="58554-122">Um provedor de serviços de audioconferência fornece uma *ponte de conferência de áudio*.</span><span class="sxs-lookup"><span data-stu-id="58554-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="58554-123">A ponte de conferência define seus números de telefone de discagem, PINs e IDs de conferência para reuniões.</span><span class="sxs-lookup"><span data-stu-id="58554-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="58554-124">Decida quanto ao uso da Microsoft ou um provedor de serviços de audioconferência de terceiros:</span><span class="sxs-lookup"><span data-stu-id="58554-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="58554-125">Usuários do Microsoft Teams não não um provedor de serviços de audioconferência de terceiros do usuário.</span><span class="sxs-lookup"><span data-stu-id="58554-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="58554-126">**Microsoft como seu provedor de serviços de audioconferência**: se você desejar a solução mais simples para conferência de áudio, escolha Microsoft como seu provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="58554-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="58554-127">**Terceiros como o seu provedor de serviços de audioconferência**: se você estiver em um país onde os serviços de audioconferência no Office 365 não está disponível, a qualidade de serviço não é ótima devido a seu local ou você tiver um contrato existente, escolha um áudio de terceiros provedor de conferência.</span><span class="sxs-lookup"><span data-stu-id="58554-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="58554-128">Para localizar um provedor, vá para a [Microsoft identifique](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="58554-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="58554-129">Em sua organização, você pode ter algumas pessoas que usam o Microsoft como seu provedor de serviços de audioconferência e outras pessoas que usam um provedor de terceiros.</span><span class="sxs-lookup"><span data-stu-id="58554-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="58554-130">Mas isso será mais complicado para configurar e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="58554-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="58554-131">Para obter uma comparação detalhada entre Microsoft como seu provedor de áudio e um provedor de terceiros, consulte [comparar os provedores de serviços de audioconferência](compare-audio-conferencing-providers.md).</span><span class="sxs-lookup"><span data-stu-id="58554-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="58554-132">Etapa 3: Atribuir o provedor de serviços de audioconferência para as pessoas de avanço ou agendem reuniões</span><span class="sxs-lookup"><span data-stu-id="58554-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="58554-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="58554-133"></span></span>

<span data-ttu-id="58554-134">Agora que você tiver decidido em seu provedor de serviços de audioconferência, você precisa atribuir o provedor para as pessoas na sua organização de avanço ou agendar reuniões.</span><span class="sxs-lookup"><span data-stu-id="58554-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="58554-135">Use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="58554-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="58554-136">[Atribuir a Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="58554-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="58554-137">[Atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="58554-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="58554-138">Etapa 4: Configurar os convites para reunião</span><span class="sxs-lookup"><span data-stu-id="58554-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="58554-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="58554-139"></span></span>

<span data-ttu-id="58554-140">As etapas a seguir são **opcionais**, mas muita admins like para executá-las:</span><span class="sxs-lookup"><span data-stu-id="58554-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="58554-141">[Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="58554-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="58554-142">Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes.</span><span class="sxs-lookup"><span data-stu-id="58554-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="58554-143">No entanto, você pode adicionar sua própria Ajuda e links legal, uma mensagem de texto e gráfico de pequena empresa.</span><span class="sxs-lookup"><span data-stu-id="58554-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="58554-144">[Conjunto de números de telefone de conferência de áudio para organizadores que estão incluídos nos convites de reunião](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="58554-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="58554-145">Esse é o número de telefone que serão exibidas na reunião programada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="58554-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="58554-146">[Definir os idiomas de atendedor automático de conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático de conferência de áudio usa para saudar um chamador quando eles discam para um número de telefone de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="58554-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="58554-147">Esta etapa só se aplica se você estiver usando o Microsoft como seu provedor de áudio.</span><span class="sxs-lookup"><span data-stu-id="58554-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="58554-148">[Definir o tamanho do PIN para reuniões de conferência de áudio](set-the-pin-length-for-audio-conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="58554-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="58554-149">Esse recurso ainda não disponível para clientes usando o Office 365 operado pela 21Vianet na China.</span><span class="sxs-lookup"><span data-stu-id="58554-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="58554-150">Para saber mais, consulte [Saiba mais sobre o Office 365 operado pela 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span><span class="sxs-lookup"><span data-stu-id="58554-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="58554-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="58554-151">Related topics</span></span>

[<span data-ttu-id="58554-152">Perguntas comuns sobre a audioconferência</span><span class="sxs-lookup"><span data-stu-id="58554-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="58554-153">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="58554-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="58554-154">Números de telefone para audioconferência</span><span class="sxs-lookup"><span data-stu-id="58554-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="58554-155">Definir opções para reuniões online e chamadas em conferência</span><span class="sxs-lookup"><span data-stu-id="58554-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

