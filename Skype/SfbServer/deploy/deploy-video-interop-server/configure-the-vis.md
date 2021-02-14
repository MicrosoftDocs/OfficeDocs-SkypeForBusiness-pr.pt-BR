---
title: Configurar o Servidor de Interop de Vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumo: Configure a função de Servidor de Interop de Vídeo (VIS) no Skype for Business Server.'
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820691"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="c1eb7-103">Configurar o Servidor de Interop de Vídeo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1eb7-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c1eb7-104">**Resumo:** Configure a função de Servidor de Interop de Vídeo (VIS) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="c1eb7-105">Definir as configurações que o VIS associará aos troncos de vídeo usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="c1eb7-106">Uma configuração de tronco de vídeo com escopo global é criada depois que o serviço VIS é instalado.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="c1eb7-107">Essa configuração de tronco de vídeo é aplicada pelo VIS a todos os troncos que não têm configuração de tronco de vídeo com um escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="c1eb7-108">Observe que a configuração do tronco de vídeo é uma coleção de configurações aplicáveis a troncos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="c1eb7-109">Configurar tronco de vídeo e plano de discagem</span><span class="sxs-lookup"><span data-stu-id="c1eb7-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="c1eb7-110">Use os seguintes comandos do Windows PowerShell para especificar a configuração do tronco de vídeo e o plano de discagem a serem associados aos troncos recentemente definidos no Documento de Topologia entre o VIS e todos os Gateways de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="c1eb7-111">Todas essas configurações podem ser definidas nos níveis global, de site ou de serviço (Gateway de Vídeo).</span><span class="sxs-lookup"><span data-stu-id="c1eb7-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="c1eb7-112">Um plano de discagem com escopo global é criado por implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="c1eb7-113">Esse plano de discagem é aplicado pelo VIS a todos os troncos que não têm nenhum plano de discagem com escopo mais específico.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="c1eb7-114">Configurar o VIS usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1eb7-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="c1eb7-115">Crie uma nova configuração de tronco de vídeo (uma coleção de configurações) a ser usada no tronco entre o VIS e o Cisco Unified Communications Manager (CallManager ou CUCM), usando o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1eb7-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="c1eb7-116">Se houver um tronco de vídeo existente que precise ser modificado, use o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1eb7-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="c1eb7-117">Para exibir as configurações associadas a uma determinada configuração de tronco de vídeo, use o seguinte cmdlet do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1eb7-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="c1eb7-118">Para remover uma determinada configuração de tronco de vídeo, use o seguinte cmdlet do Windows PowerShell (observe que a configuração de tronco de vídeo com escopo global será aplicada se não houver uma configuração de tronco de vídeo com escopo mais especificamente para um tronco específico):</span><span class="sxs-lookup"><span data-stu-id="c1eb7-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="c1eb7-119">Estabeleça um plano de discagem para associar ao tronco, usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1eb7-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="c1eb7-120">O **comando Remove-CsVoiceNormalizationRule** é necessário para substituir uma regra padrão que interferirá na interação esperada do VIS e do CUCM.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="c1eb7-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) pode ser usado para remover um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="c1eb7-122">Para uma chamada de Tronco SIP de vídeo de um Gateway de Vídeo cujo URI de Solicitação contém um número não E.164, o VIS lerá o nome do plano de discagem associado ao tronco associado e incluirá o nome do plano de discagem na parte de contexto de telefone do URI da Solicitação no Convite que o VIS envia para o Front-End.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="c1eb7-123">O Aplicativo de Tradução no Front End, em seguida, extrai e aplica as regras de normalização associadas ao plano de discagem para o URI de Solicitação.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="c1eb7-124">Opções de configuração de tronco</span><span class="sxs-lookup"><span data-stu-id="c1eb7-124">Trunk configuration options</span></span>

<span data-ttu-id="c1eb7-125">Os cmdlets do Windows PowerShell para configuração de tronco de vídeo mencionados anteriormente eram novos no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="c1eb7-126">As configurações associadas à configuração do tronco de vídeo exigem uma breve explicação.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="c1eb7-127">**GatewaySendsRtcpForActiveCalls** Este parâmetro determina se os pacotes RTCP são enviados do VTC para o VIS para chamadas ativas.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="c1eb7-128">Nesse contexto, uma chamada ativa é uma chamada na qual a mídia pode partir em pelo menos uma direção.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="c1eb7-129">Se GatewaySendsRtcpForActiveCalls for definido como True, o VIS poderá encerrar uma chamada se não receber pacotes RTCP por um período superior a 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="c1eb7-130">O padrão é **True**.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-130">The default is **True**.</span></span>
  
 <span data-ttu-id="c1eb7-131">**GatewaySendsRtcpForCallsOnHold** Este parâmetro determina se os pacotes RTCP continuarão a ser enviados através do tronco para chamadas que foram colocadas em espera e nenhum pacote de mídia deverá fluir em qualquer direção.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="c1eb7-132">O VIS pode encerrar a chamada se não houver nenhum pacote RTCP fluindo do VTC para o VIS enquanto a chamada está em espera.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="c1eb7-133">O padrão é **True**.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-133">The default is **True**.</span></span> <span data-ttu-id="c1eb7-134">Quando o protocolo SIPTransport é definido como TCP, essa configuração é ignorada.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="c1eb7-135">**EnableMediaEncryptionForSipOverTls** Esse parâmetro habilita ou desabilita o SRTP para mídia quando o protocolo SIPTransport é definido como TLS.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="c1eb7-136">O padrão é **True**.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-136">The default is **True**.</span></span> <span data-ttu-id="c1eb7-137">Quando o protocolo SIPTransport é definido como TCP, essa configuração é ignorada.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="c1eb7-138">**EnableSessionTimer** Esse parâmetro habilita ou desabilita temporizadores de sessão no lado do VIS para cada caixa de diálogo SIP associada ao tronco SIP de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="c1eb7-139">O padrão é **False**.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-139">The default is **False**.</span></span>
  
 <span data-ttu-id="c1eb7-140">**ForwardErrorCorrectionType** Esse parâmetro é usado para determinar se a Correção de Erro de Encaminhamento (FEC) para fluxos de vídeo deve ser aplicada no trecho entre o Servidor de Interop de Vídeo e um Gateway de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="c1eb7-141">A definição de ForwardErrorCorrectionType como "None" desliga o FEC entre o VIS e o Gateway de Vídeo/VTC.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="c1eb7-142">A definição de ForwardErrorCorrectionType como "Cisco" habilita o FEC compatível com gateways de vídeo pela Cisco, como o Cisco Unified Communications Manager (CUCM).</span><span class="sxs-lookup"><span data-stu-id="c1eb7-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="c1eb7-143">O padrão é **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c1eb7-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c1eb7-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1eb7-144">See also</span></span>

[<span data-ttu-id="c1eb7-145">Configurar o CUCM para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1eb7-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
