---
title: Conferência de áudio com roteamento direto, GCCH e DoD
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: O administrador pode saber mais sobre como usar a conferência de áudio com roteamento direto em ambientes GCCH e DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262488"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="63899-103">Conferências de Áudio com Roteamento Direto para GCC Alto e DoD</span><span class="sxs-lookup"><span data-stu-id="63899-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="63899-104">Conferência de áudio com roteamento direto para GCC elevado e DoD permite que os participantes ingressem em reuniões de equipe na sua organização GCC alta ou DoD usando um dispositivo de telefone.</span><span class="sxs-lookup"><span data-stu-id="63899-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="63899-105">Os participantes da reunião podem preferir usar um dispositivo de telefone para ingressar em reuniões de equipe em cenários, como quando a conectividade com a Internet é limitada ou quando os usuários estão em trânsito e não têm acesso ao Teams.</span><span class="sxs-lookup"><span data-stu-id="63899-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="63899-106">Os participantes podem optar por ingressar em reuniões discando para um número de telefone de discagem para a sua organização ou fazendo com que a reunião disque para o dispositivo telefônico.</span><span class="sxs-lookup"><span data-stu-id="63899-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="63899-107">Com o roteamento direto para GCC High e DoD, a sua organização usa seus próprios números como números de telefone de discagem e todas as chamadas discadas na reunião para dispositivos telefônicos são roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="63899-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="63899-108">Para habilitar o serviço, as organizações precisam configurar o roteamento direto e configurar os números de telefone que podem ser usados como números de telefone de discagem.</span><span class="sxs-lookup"><span data-stu-id="63899-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="63899-109">A necessidade de usar o roteamento direto é diferente do serviço de audioconferência, que é oferecido a organizações não-GCC altas e não-DoD nas quais os números de telefone de discagem são fornecidos pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63899-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="63899-110">Implantar a videoconferência com roteamento direto para GCC elevado e DoD</span><span class="sxs-lookup"><span data-stu-id="63899-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="63899-111">Etapa 1: obter a conferência de áudio com roteamento direto para licenças GCC elevadas ou DoD</span><span class="sxs-lookup"><span data-stu-id="63899-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="63899-112">Para usar a conferência de áudio no GCC High ou DoD, sua organização e os usuários da sua organização precisam ter uma conferência de áudio com licença de roteamento direto atribuída.</span><span class="sxs-lookup"><span data-stu-id="63899-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="63899-113">Aqui estão as licenças de que você precisa para habilitar a audioconferência com roteamento direto para GCC High ou DoD.</span><span class="sxs-lookup"><span data-stu-id="63899-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="63899-114">GCC alto: uma conferência de áudio-GCC alta licença de locatário para sua organização e conferência de áudio-GCC licenças elevadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="63899-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="63899-115">DoD: uma conferência de áudio-licença de locatário DoD para sua organização e conferência de áudio – licenças DoD para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="63899-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="63899-116">É preciso ter uma licença de locatário e pelo menos uma licença de usuário para habilitar o serviço.</span><span class="sxs-lookup"><span data-stu-id="63899-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="63899-117">Você não pode habilitar o serviço apenas com a licença de locatário ou com apenas licenças de usuário.</span><span class="sxs-lookup"><span data-stu-id="63899-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="63899-118">Para obter licenças de serviço para o seu locatário e os usuários da sua organização, entre em contato com a equipe da sua conta.</span><span class="sxs-lookup"><span data-stu-id="63899-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63899-119">Os usuários não podem ser habilitados para conferências de áudio com roteamento direto até que os números de telefone de discagem estejam configurados.</span><span class="sxs-lookup"><span data-stu-id="63899-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="63899-120">Recomendamos que você não atribua conferências de áudio com roteamento direto para licenças de GCC elevada ou DoD para os usuários até configurar números de telefone de discagem conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="63899-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="63899-121">Etapa 2: configurar o roteamento direto</span><span class="sxs-lookup"><span data-stu-id="63899-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="63899-122">Para configurar o roteamento direto, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="63899-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="63899-123">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="63899-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="63899-124">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="63899-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="63899-125">Ao configurar o roteamento direto, lembre-se de usar os FQDNs e as portas do GCC superiores ou DoD específicas descritos nestes dois artigos.</span><span class="sxs-lookup"><span data-stu-id="63899-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="63899-126">Etapa 3: configurar números de telefone de discagem</span><span class="sxs-lookup"><span data-stu-id="63899-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="63899-127">Os números de telefone de discagem são os números de telefone associados à sua ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="63899-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="63899-128">Esses números são usados pelos participantes para ingressar em reuniões agendadas pelos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="63899-129">Esses números também estão incluídos nos convites de reunião dos usuários que agendam reuniões em sua organização e na página "encontrar um número local".</span><span class="sxs-lookup"><span data-stu-id="63899-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="63899-130">Definir números de telefone de serviço em seu locatário</span><span class="sxs-lookup"><span data-stu-id="63899-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="63899-131">Você pode usar o cmdlet New-csHybridTelephoneNumber do PowerShell para definir números de telefone de serviço em seu locatário que podem ser usados para direcionar chamadas para o serviço de audioconferência via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="63899-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="63899-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="63899-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="63899-133">Atribuir os números de telefone do serviço à ponte de videoconferência da sua organização</span><span class="sxs-lookup"><span data-stu-id="63899-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="63899-134">Você pode atribuir números de telefone de serviço à ponte de videoconferência da sua organização usando o cmdlet Register-Csonlinedialinconferencingservicenumberhttp do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63899-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="63899-135">Você pode ver a identificação da sua ponte de conferência de áudio usando Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="63899-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="63899-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="63899-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="63899-137">Etapa 4: definir uma política de roteamento de voz global para habilitar o roteamento de chamadas de saída de reuniões</span><span class="sxs-lookup"><span data-stu-id="63899-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="63899-138">O roteamento de chamadas de saída feitas à PSTN de reuniões organizadas por usuários em sua organização é definido pela política de roteamento de voz global da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="63899-139">Se a sua organização tiver uma política global de roteamento de voz definida, verifique se a política de roteamento de voz global permite as chamadas de saída para a PSTN que devem ser iniciadas a partir de reuniões organizadas por usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="63899-140">Se a sua organização não tiver uma política global de roteamento de voz definida, você precisará definir uma para habilitar o roteamento de chamadas de saída para a PSTN de reuniões organizadas por usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="63899-141">Observe que a política de roteamento de voz global da sua organização também se aplica a chamadas individuais feitas à PSTN pelos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="63899-142">Se as chamadas individuais para a PSTN estiverem habilitadas para os usuários de sua organização, certifique-se de que a política de roteamento de voz global atenda às necessidades da sua organização para ambos os tipos de chamadas.</span><span class="sxs-lookup"><span data-stu-id="63899-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="63899-143">O roteamento baseado em local não está disponível nas implantações do Microsoft 365 governo Community Cloud (GCC) de alta ou DoD.</span><span class="sxs-lookup"><span data-stu-id="63899-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="63899-144">Ao habilitar a conferência de áudio, verifique se nenhum usuário de videoconferência nos ambientes GCC High ou DoD está habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="63899-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="63899-145">Definindo uma política de roteamento de voz global</span><span class="sxs-lookup"><span data-stu-id="63899-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="63899-146">Uma política de roteamento de voz global pode ser definida definindo um uso de PSTN, uma rota de voz, uma política de roteamento de voz e atribuindo a nova política de roteamento de voz como a política de roteamento de voz global da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="63899-147">As etapas a seguir descrevem como definir uma nova política de roteamento de voz global para uma organização sem uma.</span><span class="sxs-lookup"><span data-stu-id="63899-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="63899-148">Se a sua organização já tiver políticas de roteamento de voz definidas, verifique se a seguinte configuração não está em conflito com as políticas de roteamento de voz existentes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="63899-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="63899-149">Para criar um novo uso de PSTN em uma sessão remota do PowerShell no Skype for Business Online, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="63899-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="63899-150">Para obter informações adicionais, consulte [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span><span class="sxs-lookup"><span data-stu-id="63899-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="63899-151">Para criar uma nova rota de voz, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="63899-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="63899-152">Ao definir uma nova rota de voz para sua organização, especifique um ou vários dos gateways PSTN online PSTN que foram definidos para a sua organização durante a configuração de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="63899-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="63899-153">O padrão de número especifica quais chamadas serão roteadas na lista especificada de gateways com base no número de telefone de destino da chamada.</span><span class="sxs-lookup"><span data-stu-id="63899-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="63899-154">No exemplo acima, as chamadas para todos os destinos do mundo corresponderão à rota de voz.</span><span class="sxs-lookup"><span data-stu-id="63899-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="63899-155">Se quiser restringir os números de telefone que podem ser discados das reuniões de usuários em sua organização, você pode alterar o padrão de número para que a rota de voz corresponda apenas os padrões de número dos destinos permitidos.</span><span class="sxs-lookup"><span data-stu-id="63899-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="63899-156">Observe que, se não houver rotas de voz que correspondam ao padrão de número do número de telefone de destino de uma determinada chamada, a chamada não será roteada.</span><span class="sxs-lookup"><span data-stu-id="63899-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="63899-157">Para obter informações adicionais, consulte [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span><span class="sxs-lookup"><span data-stu-id="63899-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="63899-158">Para criar uma nova política de roteamento de voz, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="63899-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="63899-159">Se vários usos de PSTN estiverem sendo definidos na política de roteamento de voz, eles serão avaliados na ordem em que estão definidos.</span><span class="sxs-lookup"><span data-stu-id="63899-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="63899-160">É recomendável que os usos de PSTN sejam definidos na ordem do mais específico para o mais genérico em termos dos padrões de número das rotas de voz associadas aos usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="63899-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="63899-161">Por exemplo, se um uso de PSTN foi definido para direcionar chamadas para os Estados Unidos, e outro uso de PSTN foi definido para direcionar chamadas para qualquer outro local do mundo, o uso de PSTN para chamadas para os Estados Unidos deve estar listado na política de roteamento de voz à frente do uso de PSTN para direcionar chamadas para qualquer outro local do mundo.</span><span class="sxs-lookup"><span data-stu-id="63899-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="63899-162">Para obter informações adicionais, consulte [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="63899-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="63899-163">Para atribuir a nova rota de voz à política de roteamento de voz global da sua organização, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="63899-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="63899-164">Para obter informações adicionais, consulte [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="63899-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="63899-165">Após a definição da política de roteamento de voz global, todas as chamadas feitas a partir de reuniões organizadas por usuários em sua organização serão avaliadas em relação às rotas de voz associadas aos usos de PSTN da política de roteamento de voz global.</span><span class="sxs-lookup"><span data-stu-id="63899-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="63899-166">As chamadas de saída serão roteadas de acordo com a primeira rota de voz que corresponde ao padrão de número do número de telefone discado.</span><span class="sxs-lookup"><span data-stu-id="63899-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="63899-167">Etapa 5: atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para seus usuários</span><span class="sxs-lookup"><span data-stu-id="63899-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="63899-168">Para atribuir uma conferência de áudio com roteamento direto para licenças de GCC elevada ou DoD para o usuário, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="63899-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="63899-169">Etapa 6: (opcional) Veja uma lista de números de conferência de áudio no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63899-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="63899-170">Para ver a lista de números de conferência de áudio da sua organização, vá para [ver uma lista de números de conferência de áudio no Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="63899-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="63899-171">Etapa 7: (opcional) definir idiomas do atendedor automático para os números de discagem da conferência de áudio da sua organização</span><span class="sxs-lookup"><span data-stu-id="63899-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="63899-172">Para alterar os idiomas dos números de discagem da conferência de áudio da sua organização, consulte [definir idiomas do atendedor automático para videoconferências no Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="63899-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="63899-173">Etapa 8: (opcional) alterar as configurações da ponte de conferência de áudio da sua organização</span><span class="sxs-lookup"><span data-stu-id="63899-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="63899-174">Para alterar as configurações da ponte de conferência de áudio da sua organização, consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="63899-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="63899-175">Etapa 9: (opcional) definir os números de telefone incluídos nos convites para reunião dos usuários em sua organização</span><span class="sxs-lookup"><span data-stu-id="63899-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="63899-176">Para alterar o conjunto de números de telefone que estão incluídos nos convites de reunião dos usuários em sua organização, confira [definir os números de telefone incluídos nos convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="63899-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="63899-177">Os recursos de audioconferência não são compatíveis com a videoconferências com roteamento direto para GCC High e DoD</span><span class="sxs-lookup"><span data-stu-id="63899-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="63899-178">Veja a seguir os recursos de audioconferência que não têm suporte na videoconferência com roteamento direto para GCC High e DoD:</span><span class="sxs-lookup"><span data-stu-id="63899-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="63899-179">Notificações de entrada e saída usando a gravação de nomes.</span><span class="sxs-lookup"><span data-stu-id="63899-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="63899-180">Para videoconferências com roteamento direto, as notificações de entrada e saída são reproduzidas na reunião como tons.</span><span class="sxs-lookup"><span data-stu-id="63899-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="63899-181">Políticas de restrição de chamadas de saída para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="63899-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="63899-182">Os controles em nível de usuário para restringir chamadas de saída não são aplicáveis a chamadas discadas de reunião roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="63899-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="63899-183">Desative o uso de números de chamada gratuita para o organizador de reuniões específico.</span><span class="sxs-lookup"><span data-stu-id="63899-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="63899-184">Os controles em nível de usuário para restringir o uso de números de chamada gratuita para ingressar nas reuniões de sua organização não são aplicáveis a chamadas roteadas via roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="63899-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="63899-185">Enviar emails de notificação para os usuários quando as configurações forem alteradas.</span><span class="sxs-lookup"><span data-stu-id="63899-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="63899-186">Os emails de notificação de audioconferência não têm suporte para videoconferências com roteamento direto para GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="63899-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
