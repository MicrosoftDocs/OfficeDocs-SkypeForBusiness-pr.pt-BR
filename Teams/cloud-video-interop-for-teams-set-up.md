---
title: Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: Este artigo explica como você pode planejar e configurar o Cloud Video Interop para usuários em sua organização.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582628"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="9689d-103">Configurar a interoperabilidade de vídeo na nuvem para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9689d-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="9689d-104">Depois de escolher [seu(s) parceiro(s) Cloud Video Interop(s),](cloud-video-interop.md)você precisará planejar sua implantação, configurar com detalhes de provisionamento e chave de locatário do parceiro e consentir com o aplicativo interop de vídeo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9689d-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="9689d-105">O diagrama a seguir descreve o processo.</span><span class="sxs-lookup"><span data-stu-id="9689d-105">The following diagram outlines the process.</span></span> 

![Implantando o CVI em sua organização](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="9689d-107">Plano</span><span class="sxs-lookup"><span data-stu-id="9689d-107">Plan</span></span>

<span data-ttu-id="9689d-108">Consulte [Cloud Video Interop para Microsoft Teams](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros a usar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9689d-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="9689d-109">Para planejar a habilitação de usuário baseado/simultâneo/em todo o site:</span><span class="sxs-lookup"><span data-stu-id="9689d-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="9689d-110">Escolha um modelo de implantação/modelo hospedado para seu uso</span><span class="sxs-lookup"><span data-stu-id="9689d-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="9689d-111">Selecione o plano de licença ideal para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9689d-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="9689d-112">O plano para a capacidade de VMs é que você está hospedando sua infraestrutura de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9689d-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="9689d-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="9689d-113">Configure</span></span> 

<span data-ttu-id="9689d-114">Para configurar o Cloud Video Interop, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9689d-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="9689d-115">Obtenha informações de configuração dos parceiros que você escolheu (chave do locatário, appIds...).</span><span class="sxs-lookup"><span data-stu-id="9689d-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="9689d-116">Você pode usar um ou mais parceiros de interop de vídeo em sua organização</span><span class="sxs-lookup"><span data-stu-id="9689d-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="9689d-117">Verifique se sua rede está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="9689d-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="9689d-118">Configure seu firewall de vídeo baseado em padrões para a transição de rede de perímetro para suporte.</span><span class="sxs-lookup"><span data-stu-id="9689d-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="9689d-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9689d-119">For example:</span></span> 
    - <span data-ttu-id="9689d-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="9689d-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="9689d-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="9689d-121">Polycom RPAD</span></span>

3. <span data-ttu-id="9689d-122">Configure salas integradas com o Exchange e o OTD.</span><span class="sxs-lookup"><span data-stu-id="9689d-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="9689d-123">Na maioria dos casos, a retransmissão adicional precisaria ser configurada e configurada em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="9689d-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="9689d-124">Disposição</span><span class="sxs-lookup"><span data-stu-id="9689d-124">Provision</span></span>
 
<span data-ttu-id="9689d-125">A chave do locatário será a discagem para o serviço de parceiro.</span><span class="sxs-lookup"><span data-stu-id="9689d-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="9689d-126">No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário.</span><span class="sxs-lookup"><span data-stu-id="9689d-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Exemplo de chave do locatário](media/tenant-key-example.png) 

<span data-ttu-id="9689d-128">Você precisará executar os cmdlets a seguir para provisionar a chave do locatário e também permitir que usuários selecionados ou toda a organização criem reuniões com coordenadas de interop de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9689d-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="9689d-129">**[Get-CsTeamsVideoInteropServicepolicy:](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)** A Microsoft fornece políticas pré-construídas para cada um dos nossos parceiros com suporte que permitem designar quais parceiros usar para interop de vídeo na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9689d-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="9689d-130">Esse cmdlet permite identificar as políticas pré-construídas que você pode usar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9689d-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="9689d-131">Você pode atribuir essa política a um ou mais usuários aproveitando o cmdlet Grant-CsTeamsVideoInteropServicePolicy usuário.</span><span class="sxs-lookup"><span data-stu-id="9689d-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="9689d-132">**[Grant-CsTeamsVideoInteropServicePolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** O Grant-CsTeamsVideoInteropServicePolicy cmdlet permite atribuir uma política pré-construída para uso em sua organização ou atribuir a política a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="9689d-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="9689d-133">**[New-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)** Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.</span><span class="sxs-lookup"><span data-stu-id="9689d-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="9689d-134">**[Set-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)** Use a Set-CsVideoInteropServiceProvider para atualizar informações sobre um parceiro CVI com suporte que sua organização usa.</span><span class="sxs-lookup"><span data-stu-id="9689d-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="9689d-135">**[Get-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)** Obter todos os provedores que foram configurados para uso dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="9689d-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="9689d-136">**[Remove-CsVideoInteropServiceProvider:](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)** Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor que sua organização não usa mais.</span><span class="sxs-lookup"><span data-stu-id="9689d-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="9689d-137">Consentimento</span><span class="sxs-lookup"><span data-stu-id="9689d-137">Consent</span></span>

<span data-ttu-id="9689d-138">Você precisará fornecer o consentimento de permissão para que os dispositivos de teleconferência de vídeo (VTCs) in join your organizations meetings via serviço de parceiro.</span><span class="sxs-lookup"><span data-stu-id="9689d-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="9689d-139">Este link de consentimento também será fornecido por seu parceiro.</span><span class="sxs-lookup"><span data-stu-id="9689d-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="9689d-140">Quando essas etapas são concluídas, os usuários habilitados individualmente por meio do cmdlet Grant acima ou todos os usuários da organização, se o locatário estiver habilitado, terão coordenadas VTC em todas as reuniões do Teams agendadas por eles.</span><span class="sxs-lookup"><span data-stu-id="9689d-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="9689d-141">Qualquer VTC pode ingressar nessas reuniões por meio dessas coordenadas.</span><span class="sxs-lookup"><span data-stu-id="9689d-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="9689d-142">Nome</span><span class="sxs-lookup"><span data-stu-id="9689d-142">Name</span></span>|<span data-ttu-id="9689d-143">Descrição resumida da permissão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9689d-143">Application Permission Short Description</span></span>| <span data-ttu-id="9689d-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="9689d-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="9689d-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="9689d-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="9689d-146">Ingressar em Chamadas e Reuniões em Grupo como um aplicativo (visualização)</span><span class="sxs-lookup"><span data-stu-id="9689d-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="9689d-147">Permite que o aplicativo in join group calls and scheduled meetings in your organization, without a signed-in user.</span><span class="sxs-lookup"><span data-stu-id="9689d-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="9689d-148">O aplicativo será ingressar com os privilégios de um usuário de diretório para reuniões em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9689d-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="9689d-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="9689d-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="9689d-150">Ingressar em Chamadas e Reuniões em Grupo como usuário convidado (visualização)</span><span class="sxs-lookup"><span data-stu-id="9689d-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="9689d-151">Permite que o aplicativo inscresse chamadas em grupo e reuniões agendadas anonimamente em sua organização, sem um usuário de acesso.</span><span class="sxs-lookup"><span data-stu-id="9689d-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="9689d-152">O aplicativo será ingressar como convidado para reuniões em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9689d-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="9689d-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="9689d-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="9689d-154">Acessar fluxos de mídia em uma chamada como um aplicativo (visualização)</span><span class="sxs-lookup"><span data-stu-id="9689d-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="9689d-155">Permite que o aplicativo tenha acesso direto a fluxos de mídia em uma chamada, sem um usuário de entrada.</span><span class="sxs-lookup"><span data-stu-id="9689d-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="9689d-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="9689d-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="9689d-157">Ler detalhes da Reunião Online (visualização)</span><span class="sxs-lookup"><span data-stu-id="9689d-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="9689d-158">Permite que o aplicativo leia os detalhes da Reunião Online em sua organização, sem um usuário de acesso.</span><span class="sxs-lookup"><span data-stu-id="9689d-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="9689d-159">Agenda</span><span class="sxs-lookup"><span data-stu-id="9689d-159">Schedule</span></span>

<span data-ttu-id="9689d-160">Em seguida, agende uma reunião do Teams com coordenadas de interop vídeo.</span><span class="sxs-lookup"><span data-stu-id="9689d-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="9689d-161">O usuário habilitado pode agendar reuniões de equipes por meio de:</span><span class="sxs-lookup"><span data-stu-id="9689d-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="9689d-162">Add-in de Reunião do Teams para Outlook</span><span class="sxs-lookup"><span data-stu-id="9689d-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="9689d-163">Área de trabalho e dispositivos móveis do cliente Teams</span><span class="sxs-lookup"><span data-stu-id="9689d-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="9689d-164">Ingressar</span><span class="sxs-lookup"><span data-stu-id="9689d-164">Join</span></span>

<span data-ttu-id="9689d-165">Você pode ingressar em reuniões do Teams com seus dispositivos VTC das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="9689d-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="9689d-166">IVR (Resposta interativa de voz)</span><span class="sxs-lookup"><span data-stu-id="9689d-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="9689d-167">Você pode discar para a IVR do parceiro usando o tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="9689d-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="9689d-168">Depois de entrar no IVR do parceiro, você será solicitado a inserir a ID da conferência VTC, que o conectará à reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="9689d-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="9689d-169">Discagem direta</span><span class="sxs-lookup"><span data-stu-id="9689d-169">Direct dial</span></span>
    - <span data-ttu-id="9689d-170">Você pode discar diretamente para a reunião do Teams sem interagir com o IVR do parceiro usando o recurso de discagem direta usando a cadeia completa de chaves de locatário. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="9689d-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="9689d-171">Discagem com um toque</span><span class="sxs-lookup"><span data-stu-id="9689d-171">One-touch dial</span></span>
    - <span data-ttu-id="9689d-172">Se você tiver uma sala integrada do Teams, poderá usar os recursos de discagem de um toque oferecidos por seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).</span><span class="sxs-lookup"><span data-stu-id="9689d-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="9689d-173">Por fim, interaja com os usuários do Teams em suas reuniões usando áudio, vídeo e compartilhamento de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9689d-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
