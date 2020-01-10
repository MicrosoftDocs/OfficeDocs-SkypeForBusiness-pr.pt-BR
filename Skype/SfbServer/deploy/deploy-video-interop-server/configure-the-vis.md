---
title: Configurar o servidor de interoperabilidade de vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumo: Configure a função do servidor de interoperabilidade de vídeo (VIS) no Skype for Business Server.'
ms.openlocfilehash: fb9dc36bcf2f1a6f1346705f74dd3cf2844a973c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003051"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="563ae-103">Configurar o servidor de interoperabilidade de vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="563ae-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="563ae-104">**Resumo:** Configurar a função servidor de interoperabilidade de vídeo (VIS) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="563ae-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="563ae-105">Defina as configurações que o VIS associará aos troncos de vídeo usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="563ae-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="563ae-106">Uma configuração de tronco de vídeo com escopo global é criada assim que o serviço VIS é instalado.</span><span class="sxs-lookup"><span data-stu-id="563ae-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="563ae-107">Esta configuração de vídeo é aplicada pelo VIS a todos os troncos que não têm uma configuração de tronco com um escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="563ae-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="563ae-108">Observe que a configuração do tronco de vídeo é uma coleção de configurações que pode ser aplicada a troncos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="563ae-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="563ae-109">Configurar tronco de vídeo e plano de discagem</span><span class="sxs-lookup"><span data-stu-id="563ae-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="563ae-110">Use os seguintes comandos do Windows PowerShell para especificar a configuração de tronco de vídeo e o plano de discagem a serem associados ao (s) tronco (s) recém-definido (s) definidos no documento de topologia entre o VIS e todos os gateways de vídeo.</span><span class="sxs-lookup"><span data-stu-id="563ae-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="563ae-111">Todas essas configurações podem ser definidas nos níveis de serviço (Gateway de Vídeo), de site ou global.</span><span class="sxs-lookup"><span data-stu-id="563ae-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="563ae-112">Um plano de discagem com escopo global é criado pela implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="563ae-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="563ae-113">Esse plano de discagem é aplicado pelo VIS a todos os troncos que não têm nenhum plano de discagem com escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="563ae-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="563ae-114">Configurar o VIS usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="563ae-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="563ae-115">Crie uma nova configuração de tronco de vídeo (um conjunto de configurações) para usar no tronco entre o VIS e o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM), usando o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="563ae-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="563ae-116">Se houver um tronco de vídeo existente que precisa ser modificado, use o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="563ae-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="563ae-117">Para exibir as configurações associadas a uma configuração de tronco de vídeo específica, use o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="563ae-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="563ae-118">Para remover uma configuração de tronco de vídeo específica, use o seguinte cmdlet do Windows PowerShell (Observe que a configuração de troncos de vídeo globalmente em escopo será aplicada se não houver uma configuração de tronco de vídeo com o escopo mais especificamente para um tronco específico):</span><span class="sxs-lookup"><span data-stu-id="563ae-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="563ae-119">Estabeleça um plano de discagem para associar ao tronco usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="563ae-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="563ae-120">O comando **Remove-CsVoiceNormalizationRule** é necessário para substituir uma regra padrão que interfira com a interação esperada entre VIS e CUCM.</span><span class="sxs-lookup"><span data-stu-id="563ae-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="563ae-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) pode ser usado para remover um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="563ae-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="563ae-122">Para uma chamada de tronco SIP de vídeo de um gateway de vídeo cujo URI de solicitação contém um número que não seja E. 164, VIS lerá o nome do plano de discagem associado ao tronco associado e incluirá o nome do plano de discagem na parte de contexto do telefone do URI de solicitação no convite que o VI S envia para o front-end.</span><span class="sxs-lookup"><span data-stu-id="563ae-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="563ae-123">O Aplicativo de Conversão no Front-End extrai e aplica as regras de normalização associadas ao plano plano de discagem ao URI de Solicitação.</span><span class="sxs-lookup"><span data-stu-id="563ae-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="563ae-124">Opções de configuração de tronco</span><span class="sxs-lookup"><span data-stu-id="563ae-124">Trunk configuration options</span></span>

<span data-ttu-id="563ae-125">Os cmdlets do Windows PowerShell para configuração de troncos de vídeo mencionados anteriormente eram novos no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="563ae-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="563ae-126">As configurações associadas ao tronco de vídeo demandam uma breve explicação.</span><span class="sxs-lookup"><span data-stu-id="563ae-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="563ae-127">**GatewaySendsRtcpForActiveCalls** Esse parâmetro determina se os pacotes RTCP são enviados do VTC para o VIS para chamadas ativas.</span><span class="sxs-lookup"><span data-stu-id="563ae-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="563ae-128">Nesse contexto, uma chamada ativa é aquela na qual a mídia tem permissão para fluir em pelo menos uma direção.</span><span class="sxs-lookup"><span data-stu-id="563ae-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="563ae-129">Se GatewaySendsRtcpForActiveCalls estiver configurado como Verdadeiro, o VIS poderá encerrar uma chamada se não receber pacotes RTCP dento de um intervalo acima de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="563ae-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="563ae-130">O padrão é **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="563ae-130">The default is **True**.</span></span>
  
 <span data-ttu-id="563ae-131">**GatewaySendsRtcpForCallsOnHold** Esse parâmetro determina se os pacotes RTCP continuam a ser enviados pelo tronco para chamadas que foram colocadas em espera, e que nenhum pacote de mídia deve fluir em qualquer direção.</span><span class="sxs-lookup"><span data-stu-id="563ae-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="563ae-132">O VIS poderá encerrar a chamada se não houver nenhum pacote RTCP fluindo do VTC para o VIS enquanto a chamada está em espera.</span><span class="sxs-lookup"><span data-stu-id="563ae-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="563ae-133">O padrão é **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="563ae-133">The default is **True**.</span></span> <span data-ttu-id="563ae-134">Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.</span><span class="sxs-lookup"><span data-stu-id="563ae-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="563ae-135">**EnableMediaEncryptionForSipOverTls** Esse parâmetro habilita ou desabilita o SRTP para mídia quando o protocolo SIPTransport é definido como TLS.</span><span class="sxs-lookup"><span data-stu-id="563ae-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="563ae-136">O padrão é **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="563ae-136">The default is **True**.</span></span> <span data-ttu-id="563ae-137">Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.</span><span class="sxs-lookup"><span data-stu-id="563ae-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="563ae-138">**EnableSessionTimer** Esse parâmetro habilita ou desabilita os temporizadores de sessão no lado VIS para cada caixa de diálogo SIP associada ao tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="563ae-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="563ae-139">A padrão é **Falso**.</span><span class="sxs-lookup"><span data-stu-id="563ae-139">The default is **False**.</span></span>
  
 <span data-ttu-id="563ae-140">**ForwardErrorCorrectionType** Esse parâmetro é usado para determinar se a aplicação de correção de erros de encaminhamento (FEC) para fluxos de vídeo deve ser aplicada no trecho entre o servidor de interoperabilidade de vídeo e um gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="563ae-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="563ae-141">A configuração de ForwardErrorCorrectionType como "nenhum" desativa o FEC entre VIS e o gateway de vídeo/VTC.</span><span class="sxs-lookup"><span data-stu-id="563ae-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="563ae-142">A configuração de ForwardErrorCorrectionType para "Cisco" habilita a FEC compatível com gateways de vídeo pela Cisco, como o Gerenciador de comunicações unificadas da Cisco (CUCM).</span><span class="sxs-lookup"><span data-stu-id="563ae-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="563ae-143">O padrão é **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="563ae-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="563ae-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="563ae-144">See also</span></span>

[<span data-ttu-id="563ae-145">Configurar o CUCM para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="563ae-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
