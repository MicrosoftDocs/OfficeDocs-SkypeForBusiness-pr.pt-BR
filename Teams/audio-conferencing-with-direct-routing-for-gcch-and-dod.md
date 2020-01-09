---
title: Conferência de áudio com roteamento direto para GCCH e DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Saiba como você pode usar a conferência de áudio com roteamento direto em ambientes GCCH e DoD.
ms.openlocfilehash: 6c1403fedbbb47231780916eb8c7acb8014539e9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992891"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bed82-103">Conferências de Áudio com Roteamento Direto para GCC Alto e DoD</span><span class="sxs-lookup"><span data-stu-id="bed82-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bed82-104">Conferência de áudio com roteamento direto para GCC elevado e DoD permite que os participantes ingressem em reuniões de equipe na sua organização GCC alta ou DoD usando um dispositivo de telefone.</span><span class="sxs-lookup"><span data-stu-id="bed82-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="bed82-105">Os participantes da reunião podem preferir usar um dispositivo de telefone para ingressar em reuniões de equipe em cenários, como quando a conectividade com a Internet é limitada ou quando os usuários estão em trânsito e não têm acesso ao Teams.</span><span class="sxs-lookup"><span data-stu-id="bed82-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don’t have access to Teams.</span></span> <span data-ttu-id="bed82-106">Os participantes podem optar por ingressar em reuniões discando para um número de telefone de discagem para a sua organização ou fazendo com que a reunião disque para o dispositivo telefônico.</span><span class="sxs-lookup"><span data-stu-id="bed82-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="bed82-107">Com o roteamento direto para GCC High e DoD, a sua organização usa seus próprios números como números de telefone de discagem e todas as chamadas discadas na reunião para dispositivos telefônicos são roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="bed82-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="bed82-108">Para habilitar o serviço, as organizações precisam configurar o roteamento direto e configurar os números de telefone que podem ser usados como números de telefone de discagem.</span><span class="sxs-lookup"><span data-stu-id="bed82-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="bed82-109">A necessidade de usar o roteamento direto é diferente do serviço de audioconferência, que é oferecido a organizações não-GCC altas e não-DoD nas quais os números de telefone de discagem são fornecidos pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bed82-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bed82-110">Implantar a videoconferência com roteamento direto para GCC elevado e DoD</span><span class="sxs-lookup"><span data-stu-id="bed82-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="bed82-111">Etapa 1: obter a conferência de áudio com roteamento direto para licenças GCC elevadas ou DoD</span><span class="sxs-lookup"><span data-stu-id="bed82-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="bed82-112">Para usar a conferência de áudio no GCC High ou DoD, sua organização e os usuários da sua organização precisam ter uma conferência de áudio com licença de roteamento direto atribuída.</span><span class="sxs-lookup"><span data-stu-id="bed82-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="bed82-113">Aqui estão as licenças de que você precisa para habilitar a audioconferência com roteamento direto para GCC High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="bed82-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="bed82-114">GCC alto: uma conferência de áudio-GCC alta licença de locatário para sua organização e conferência de áudio-GCC licenças elevadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="bed82-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="bed82-115">DoD: uma conferência de áudio-licença de locatário DoD para sua organização e conferência de áudio – licenças DoD para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="bed82-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="bed82-116">É preciso ter uma licença de locatário e pelo menos uma licença de usuário para habilitar o serviço.</span><span class="sxs-lookup"><span data-stu-id="bed82-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="bed82-117">Você não pode habilitar o serviço apenas com a licença de locatário ou com apenas licenças de usuário.</span><span class="sxs-lookup"><span data-stu-id="bed82-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="bed82-118">Para obter licenças de serviço para o seu locatário e os usuários da sua organização, entre em contato com a equipe da sua conta.</span><span class="sxs-lookup"><span data-stu-id="bed82-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bed82-119">Os usuários não podem ser habilitados para conferências de áudio com roteamento direto até que os números de telefone de discagem estejam configurados.</span><span class="sxs-lookup"><span data-stu-id="bed82-119">Users can’t be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="bed82-120">Recomendamos que você não atribua conferências de áudio com roteamento direto para licenças de GCC elevada ou DoD para os usuários até configurar números de telefone de discagem conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bed82-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="bed82-121">Etapa 2: configurar o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="bed82-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="bed82-122">Para configurar o roteamento direto, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="bed82-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="bed82-123">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="bed82-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="bed82-124">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="bed82-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="bed82-125">Ao configurar o roteamento direto, lembre-se de usar os FQDNs e as portas do GCC superiores ou DoD específicas descritos nestes dois artigos.</span><span class="sxs-lookup"><span data-stu-id="bed82-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="bed82-126">Etapa 3: configurar números de telefone de discagem</span><span class="sxs-lookup"><span data-stu-id="bed82-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="bed82-127">Os números de telefone de discagem são os números de telefone associados à sua ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="bed82-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="bed82-128">Esses números são usados pelos participantes para ingressar em reuniões agendadas pelos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bed82-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="bed82-129">Esses números também estão incluídos nos convites de reunião dos usuários que agendam reuniões em sua organização e na página "encontrar um número local".</span><span class="sxs-lookup"><span data-stu-id="bed82-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the “Find a local number” page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="bed82-130">Definir números de telefone de serviço em seu locatário</span><span class="sxs-lookup"><span data-stu-id="bed82-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="bed82-131">Você pode usar o cmdlet New-csHybridTelephoneNumber do PowerShell para definir números de telefone de serviço em seu locatário que podem ser usados para direcionar chamadas para o serviço de audioconferência via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="bed82-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="bed82-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bed82-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber “+14250000000”
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bed82-133">Atribuir os números de telefone do serviço à ponte de videoconferência da sua organização</span><span class="sxs-lookup"><span data-stu-id="bed82-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bed82-134">Você pode atribuir números de telefone de serviço à ponte de videoconferência da sua organização usando o cmdlet Register-Csonlinedialinconferencingservicenumberhttp do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bed82-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="bed82-135">Você pode ver a identificação da sua ponte de conferência de áudio usando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="bed82-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="bed82-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bed82-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="bed82-137">Etapa 4: atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para seus usuários</span><span class="sxs-lookup"><span data-stu-id="bed82-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="bed82-138">Para atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para o usuário, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="bed82-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="bed82-139">Etapa 5: (opcional) Veja uma lista de números de conferência de áudio no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bed82-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="bed82-140">Para ver a lista de números de conferência de áudio da sua organização, acesse [ver uma lista de números de conferência de áudio no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bed82-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="bed82-141">Etapa 6: (opcional) definir idiomas do atendedor automático para os números de discagem da conferência de áudio da sua organização</span><span class="sxs-lookup"><span data-stu-id="bed82-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="bed82-142">Para alterar os idiomas dos números de discagem da conferência de áudio da sua organização, consulte [definir idiomas do atendedor automático para videoconferências no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bed82-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="bed82-143">Etapa 7: (opcional) alterar as configurações da ponte de conferência de áudio da sua organização</span><span class="sxs-lookup"><span data-stu-id="bed82-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="bed82-144">Para alterar as configurações da ponte de conferência de áudio da sua organização, consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="bed82-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="bed82-145">Etapa 8: (opcional) definir os números de telefone incluídos nos convites para reunião dos usuários em sua organização</span><span class="sxs-lookup"><span data-stu-id="bed82-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="bed82-146">Para alterar o conjunto de números de telefone que estão incluídos nos convites de reunião dos usuários em sua organização, confira [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bed82-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="bed82-147">Os recursos de audioconferência não são compatíveis com a videoconferências com roteamento direto para GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="bed82-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="bed82-148">Veja a seguir os recursos de audioconferência que não têm suporte na videoconferência com roteamento direto para GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="bed82-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="bed82-149">Notificações de entrada e saída usando a gravação de nomes.</span><span class="sxs-lookup"><span data-stu-id="bed82-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="bed82-150">Para videoconferências com roteamento direto, as notificações de entrada e saída são reproduzidas na reunião como tons.</span><span class="sxs-lookup"><span data-stu-id="bed82-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="bed82-151">Políticas de restrição de chamadas de saída para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="bed82-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="bed82-152">Os controles em nível de usuário para restringir chamadas de saída não são aplicáveis a chamadas discadas de reunião roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="bed82-152">User-level controls to restrict outbound calls aren’t applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bed82-153">Desative o uso de números de chamada gratuita para o organizador de reuniões específico.</span><span class="sxs-lookup"><span data-stu-id="bed82-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="bed82-154">Os controles em nível de usuário para restringir o uso de números de chamada gratuita para ingressar nas reuniões de sua organização não são aplicáveis a chamadas roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="bed82-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren’t applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="bed82-155">Enviar emails de notificação para os usuários quando as configurações forem alteradas.</span><span class="sxs-lookup"><span data-stu-id="bed82-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="bed82-156">Os emails de notificação de audioconferência não têm suporte para videoconferências com roteamento direto para GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="bed82-156">Audio Conferencing notification emails aren’t supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
