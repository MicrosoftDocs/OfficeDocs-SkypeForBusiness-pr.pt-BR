---
title: Configurar a interoperabilidade de vídeo de nuvem for Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Este artigo explica como planejar e configurar o interoperabilidade de vídeo de nuvem para usuários em sua organização.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2090036aa5e1a05e46581d365d9b6b4aeb94b32
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294132"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="c1b81-103">Configurar a interoperabilidade de vídeo de nuvem for Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1b81-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="c1b81-104">Depois que você tiver [escolhido em seus parceiros de interoperabilidade de vídeo de nuvem](cloud-video-interop.md), você precisará planejar sua implantação, get configurar com detalhes de provisionamento e chave do locatário de parceiro e consentimento para o aplicativo de interoperabilidade de vídeo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1b81-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="c1b81-105">O diagrama a seguir destaca o processo.</span><span class="sxs-lookup"><span data-stu-id="c1b81-105">The following diagram outlines the process.</span></span> 

![Implantando CVI na sua organização](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="c1b81-107">Planejamento</span><span class="sxs-lookup"><span data-stu-id="c1b81-107">Plan</span></span>

<span data-ttu-id="c1b81-108">Consulte a [Interoperabilidade de vídeo de nuvem para equipes da Microsoft](cloud-video-interop.md) para obter informações sobre como identificar um parceiro ou parceiros para uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1b81-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="c1b81-109">Planejar a habilitação de ampla de site com base no/simultâneos/usuário:</span><span class="sxs-lookup"><span data-stu-id="c1b81-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="c1b81-110">Selecionar um modelo de modelo/hospedados de implantação para uso</span><span class="sxs-lookup"><span data-stu-id="c1b81-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="c1b81-111">Selecione o plano de licença ideal para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1b81-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="c1b81-112">Planejamento de capacidade de VMs é que você está hospedando sua infra-estrutura de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1b81-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="c1b81-113">Configurar</span><span class="sxs-lookup"><span data-stu-id="c1b81-113">Configure</span></span> 

<span data-ttu-id="c1b81-114">Para configurar a interoperabilidade de vídeo de nuvem, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c1b81-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="c1b81-115">Obter informações de configuração dos parceiro/parceiros que você tiver escolhido (chave de locatário, appIds …).</span><span class="sxs-lookup"><span data-stu-id="c1b81-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="c1b81-116">Você pode usar um ou mais parceiros interoperabilidade vídeos em sua organização</span><span class="sxs-lookup"><span data-stu-id="c1b81-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="c1b81-117">Certifique-se de que sua rede está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c1b81-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="c1b81-118">Configure o firewall de vídeo baseada em padrões para passagem da rede de perímetro dar suporte.</span><span class="sxs-lookup"><span data-stu-id="c1b81-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="c1b81-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c1b81-119">For example:</span></span> 
    - <span data-ttu-id="c1b81-120">Cisco VCS-f</span><span class="sxs-lookup"><span data-stu-id="c1b81-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="c1b81-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="c1b81-121">Polycom RPAD</span></span>

3. <span data-ttu-id="c1b81-122">Configure salas integradas com o exchange e OTD.</span><span class="sxs-lookup"><span data-stu-id="c1b81-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="c1b81-123">Na maioria dos casos, retransmissão adicional precisa ser instalado e configurado em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1b81-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="c1b81-124">Provisão</span><span class="sxs-lookup"><span data-stu-id="c1b81-124">Provision</span></span>
 
<span data-ttu-id="c1b81-125">A chave do locatário será a discagem externa para o serviço de parceiro.</span><span class="sxs-lookup"><span data-stu-id="c1b81-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="c1b81-126">No exemplo a seguir, 813878896@t.plcm.vc é a chave do locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b81-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Exemplo de chave do locatário](media/tenant-key-example.png) 

<span data-ttu-id="c1b81-128">Você precisará executar os cmdlets a seguir para provisionar a chave do locatário e também permitem selecionar usuários ou em toda sua organização criar reuniões com coordenadas de interoperabilidade de vídeos.</span><span class="sxs-lookup"><span data-stu-id="c1b81-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="c1b81-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* A Microsoft fornece diretivas previamente construídas para cada um de nossos parceiros com suporte que permitem que você determine qual parceiros a ser usado para a interoperabilidade de vídeo de nuvem.</span><span class="sxs-lookup"><span data-stu-id="c1b81-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="c1b81-130">Este cmdlet permite que você identifique as políticas de pré-construídas que você pode usar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1b81-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="c1b81-131">Você pode atribuir essa política a um ou mais dos seus usuários utilizando o cmdlet Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="c1b81-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="c1b81-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* O cmdlet Grant-CsTeamsVideoInteropServicePolicy permite atribuir uma política previamente construída para uso em sua organização ou atribuir a política a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="c1b81-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="c1b81-133">\*\* [Novo-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Use o New-CsVideoInteropServiceProvider para especificar informações sobre um parceiro CVI com suporte que sua organização gostaria de usar.</span><span class="sxs-lookup"><span data-stu-id="c1b81-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="c1b81-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Use o Set-CsVideoInteropServiceProvider para atualizar as informações sobre um parceiro CVI com suporte, que sua organização usa.</span><span class="sxs-lookup"><span data-stu-id="c1b81-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="c1b81-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Obtenha todos os provedores que tiverem sido configurados para uso dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="c1b81-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="c1b81-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Use Remove-CsVideoInteropServiceProvider para remover todas as informações do provedor sobre um provedor de sua organização não os utiliza mais.</span><span class="sxs-lookup"><span data-stu-id="c1b81-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="c1b81-137">Consentimento</span><span class="sxs-lookup"><span data-stu-id="c1b81-137">Consent</span></span>

<span data-ttu-id="c1b81-138">Você precisará fornecer o consentimento de permissão para os dispositivos de videoconferência (VTCs) para participar de reuniões suas organizações por meio do serviço de parceiro.</span><span class="sxs-lookup"><span data-stu-id="c1b81-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="c1b81-139">Este link consentimento também será fornecido pelo seu parceiro.</span><span class="sxs-lookup"><span data-stu-id="c1b81-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="c1b81-140">Quando essas etapas forem concluídas, os usuários que são habilitados individualmente por meio do cmdlet Grant acima, ou todos os usuários na organização, se o inquilino estiver habilitado, terá VTC coordenadas em todas as reuniões de equipes que eles agendarem.</span><span class="sxs-lookup"><span data-stu-id="c1b81-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="c1b81-141">Qualquer VTC pode ingressar nessas reuniões via naquelas coordenadas.</span><span class="sxs-lookup"><span data-stu-id="c1b81-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="c1b81-142">Nome</span><span class="sxs-lookup"><span data-stu-id="c1b81-142">Name</span></span>|<span data-ttu-id="c1b81-143">Descrição curta de permissão de aplicativo</span><span class="sxs-lookup"><span data-stu-id="c1b81-143">Application Permission Short Description</span></span>| <span data-ttu-id="c1b81-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="c1b81-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="c1b81-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="c1b81-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="c1b81-146">Ingressar em reuniões e chamadas de grupo como um aplicativo (preview)</span><span class="sxs-lookup"><span data-stu-id="c1b81-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="c1b81-147">Permite que o aplicativo ingressar em chamadas de grupo e reuniões agendadas em sua organização, sem que um usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="c1b81-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="c1b81-148">O aplicativo ingressarão com os privilégios de um usuário do diretório em reuniões no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b81-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="c1b81-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="c1b81-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="c1b81-150">Ingressar em reuniões e chamadas de grupo como um usuário convidado (preview)</span><span class="sxs-lookup"><span data-stu-id="c1b81-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="c1b81-151">Permite que o aplicativo ingressar em chamadas de grupo e reuniões agendadas anonimamente em sua organização, sem que um usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="c1b81-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="c1b81-152">O aplicativo ingressarão como convidado em reuniões no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b81-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="c1b81-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="c1b81-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="c1b81-154">Fluxos de mídia de acesso em uma chamada como um aplicativo (preview)</span><span class="sxs-lookup"><span data-stu-id="c1b81-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="c1b81-155">Permite que o aplicativo obter acesso direto aos fluxos de mídia em uma chamada, sem que um usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="c1b81-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="c1b81-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="c1b81-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="c1b81-157">Detalhes da Reunião Online de leitura (preview)</span><span class="sxs-lookup"><span data-stu-id="c1b81-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="c1b81-158">Permite que o aplicativo ler os detalhes da Reunião Online em sua organização, sem que um usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="c1b81-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="c1b81-159">Agenda</span><span class="sxs-lookup"><span data-stu-id="c1b81-159">Schedule</span></span>

<span data-ttu-id="c1b81-160">Em seguida, agende reunião de equipes com coordenadas de interoperabilidade de vídeos.</span><span class="sxs-lookup"><span data-stu-id="c1b81-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="c1b81-161">O usuário habilitado pode agendar reuniões de equipes via:</span><span class="sxs-lookup"><span data-stu-id="c1b81-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="c1b81-162">Suplemento para Outlook reunião de equipes</span><span class="sxs-lookup"><span data-stu-id="c1b81-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="c1b81-163">Cliente de equipes desktop e portáteis</span><span class="sxs-lookup"><span data-stu-id="c1b81-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="c1b81-164">Ingressar</span><span class="sxs-lookup"><span data-stu-id="c1b81-164">Join</span></span>

<span data-ttu-id="c1b81-165">Você pode ingressar em reuniões de equipes com seus dispositivos VTC das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="c1b81-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="c1b81-166">IVR (resposta de voz interativa)</span><span class="sxs-lookup"><span data-stu-id="c1b81-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="c1b81-167">Você pode discar para IVR do parceiro usando o tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="c1b81-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="c1b81-168">Quando você estiver no parceiro de IVR, você será solicitado para inserir o conferenceId VTC, que, em seguida, o conectará à reunião equipes.</span><span class="sxs-lookup"><span data-stu-id="c1b81-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="c1b81-169">Discagem direta</span><span class="sxs-lookup"><span data-stu-id="c1b81-169">Direct dial</span></span>
    - <span data-ttu-id="c1b81-170">Diretamente, você poderá discar para a reunião de equipes sem interação com IVR do parceiro usando o recurso de discagem direta interna usando a cadeia completa de tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="c1b81-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="c1b81-171">Discagem de um toque</span><span class="sxs-lookup"><span data-stu-id="c1b81-171">One-touch dial</span></span>
    - <span data-ttu-id="c1b81-172">Se você tiver uma sala de equipes integrada, você pode usar os recursos de discagem de um toque oferecidos pelo seu parceiro (sem precisar digitar qualquer cadeia de caracteres de discagem).</span><span class="sxs-lookup"><span data-stu-id="c1b81-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="c1b81-173">Finalmente, se comprometer com usuários de equipes em suas reuniões usando o compartilhamento de áudio, vídeo e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c1b81-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 