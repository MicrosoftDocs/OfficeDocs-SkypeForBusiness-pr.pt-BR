---
title: Configurar um VTC para interoperação com Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: Configure os dispositivos VTC para trabalhar com Skype para Business Server.'
ms.openlocfilehash: 15998fd313faed03886cdc64e758e3436fa858c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894434"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="b7384-103">Configurar um VTC para interoperação com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b7384-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="b7384-104">**Resumo:** Configure os dispositivos VTC para trabalhar com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7384-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="b7384-105">Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectarão o Skype para servidor de negócios VIS por meio de um tronco SIP e Cisco Gerenciador de comunicações unificadas (CallManager ou CUCM) gateway de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7384-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="b7384-106">As configurações descritas aqui servem apenas como exemplos de como CUCM pode ser configurado para funcionar com um VIS.</span><span class="sxs-lookup"><span data-stu-id="b7384-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="b7384-107">Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="b7384-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="b7384-108">Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.</span><span class="sxs-lookup"><span data-stu-id="b7384-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="b7384-109">Configurar um VTC registrado no CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="b7384-110">Faça logon no dispositivo Cisco VTC e navegue até configuração -\>configuração do sistema -\>provisionamento.</span><span class="sxs-lookup"><span data-stu-id="b7384-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="b7384-111">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="b7384-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7384-112">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-112">**Parameter**</span></span>|<span data-ttu-id="b7384-113">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7384-114">Modo de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="b7384-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="b7384-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="b7384-116">Endereço ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b7384-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="b7384-117">FQDN do CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="b7384-118">Domínio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="b7384-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="b7384-119">Domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="b7384-120">Navegue até configuração -\>configuração do sistema -\>rede.</span><span class="sxs-lookup"><span data-stu-id="b7384-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="b7384-121">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="b7384-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7384-122">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-122">**Parameter**</span></span>|<span data-ttu-id="b7384-123">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7384-124">Nome do Domínio DNS</span><span class="sxs-lookup"><span data-stu-id="b7384-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="b7384-125">Nome do Domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="b7384-126">Endereço do Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="b7384-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="b7384-127">Endereço do servidor DNS desejado</span><span class="sxs-lookup"><span data-stu-id="b7384-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="b7384-128">Navegue até configuração -\>configuração do sistema -\>serviços de rede.</span><span class="sxs-lookup"><span data-stu-id="b7384-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="b7384-129">Verifique se o modo H.323 está desativado e se o modo SIP está ativado.</span><span class="sxs-lookup"><span data-stu-id="b7384-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="b7384-p103">Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM. Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="b7384-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7384-132">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-132">**Parameter**</span></span>|<span data-ttu-id="b7384-133">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7384-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="b7384-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="b7384-135">Desativado</span><span class="sxs-lookup"><span data-stu-id="b7384-135">Off</span></span> <br/> |
   |<span data-ttu-id="b7384-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="b7384-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="b7384-137">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-137">On</span></span> <br/> |
   | <span data-ttu-id="b7384-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="b7384-138">SIP Mode</span></span> <br/> | <span data-ttu-id="b7384-139">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-139">On</span></span> <br/> |
   |<span data-ttu-id="b7384-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="b7384-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="b7384-141">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-141">On</span></span> <br/> |
   |<span data-ttu-id="b7384-142">Texto de Boas-vindas</span><span class="sxs-lookup"><span data-stu-id="b7384-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="b7384-143">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-143">On</span></span> <br/> |
   |<span data-ttu-id="b7384-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="b7384-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="b7384-145">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-145">On</span></span> <br/> |
   
7. <span data-ttu-id="b7384-146">Navegue até configuração -\>configuração do sistema -\>SIP.</span><span class="sxs-lookup"><span data-stu-id="b7384-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="b7384-147">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="b7384-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="b7384-148">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-148">**Parameter**</span></span>|<span data-ttu-id="b7384-149">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7384-150">Perfil 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="b7384-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="b7384-151">TCP</span><span class="sxs-lookup"><span data-stu-id="b7384-151">TCP</span></span> <br/> |
   |<span data-ttu-id="b7384-152">Perfil 1 - Saída</span><span class="sxs-lookup"><span data-stu-id="b7384-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="b7384-153">Desativado</span><span class="sxs-lookup"><span data-stu-id="b7384-153">Off</span></span> <br/> |
   |<span data-ttu-id="b7384-154">Perfil 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="b7384-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="b7384-155">Ativado</span><span class="sxs-lookup"><span data-stu-id="b7384-155">On</span></span> <br/> |
   |<span data-ttu-id="b7384-156">Perfil 1 - Tipo</span><span class="sxs-lookup"><span data-stu-id="b7384-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="b7384-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="b7384-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="b7384-158">Perfil 1 - URI</span><span class="sxs-lookup"><span data-stu-id="b7384-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="b7384-159">Atribuído automaticamente durante o registro no CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="b7384-160">Proxy 1 - Endereço</span><span class="sxs-lookup"><span data-stu-id="b7384-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="b7384-161">O nome de host do CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="b7384-p104">Agora o VTC está configurado para interoperação. Antes de o serviço iniciar, é necessário executar algumas etapas finais no CUCM.</span><span class="sxs-lookup"><span data-stu-id="b7384-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="b7384-164">Configurar os dispositivos VTC no CUCM</span><span class="sxs-lookup"><span data-stu-id="b7384-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="b7384-165">Faça logon em CUCM e navegue até Cisco Unified CM administração -\>dispositivo -\>telefone -\>localizar.</span><span class="sxs-lookup"><span data-stu-id="b7384-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="b7384-p105">Selecione o dispositivo VTC a ser configurado. Verifique as seguintes configurações na tela Configuração do Telefone, fazendo as correções necessárias. Depois que essas configurações forem alteradas ou configuradas, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b7384-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="b7384-169">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-169">**Parameter**</span></span>|<span data-ttu-id="b7384-170">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b7384-171">Informações do Dispositivo - Modelo de Botão de Telefone</span><span class="sxs-lookup"><span data-stu-id="b7384-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="b7384-172">Cisco Standard Codec de telepresença C40</span><span class="sxs-lookup"><span data-stu-id="b7384-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b7384-173">Informações do Dispositivo - Perfil de Telefone Comum</span><span class="sxs-lookup"><span data-stu-id="b7384-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="b7384-174">Perfil de Telefone Comum Padrão</span><span class="sxs-lookup"><span data-stu-id="b7384-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="b7384-175">Informações do Dispositivo - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="b7384-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-177">Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR</span><span class="sxs-lookup"><span data-stu-id="b7384-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-179">Informações do Dispositivo - Lista de Grupos de Recursos de Mídia</span><span class="sxs-lookup"><span data-stu-id="b7384-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="b7384-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-181">Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7384-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="b7384-182">Cisco telepresença Codec C40</span><span class="sxs-lookup"><span data-stu-id="b7384-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="b7384-183">Informações Específicas do Protocolo - Reencaminhamento do Espaço de Pesquisa de de Chamada</span><span class="sxs-lookup"><span data-stu-id="b7384-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-185">Informações específicas de protocolo - inscrever-se chamar o espaço de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b7384-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-187">Informações Específicas do Protocolo - Perfil SIP</span><span class="sxs-lookup"><span data-stu-id="b7384-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="b7384-188">Perfil SIP Padrão para o Ponto de Extremidade de Telepresença</span><span class="sxs-lookup"><span data-stu-id="b7384-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="b7384-189">Assim que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7384-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="b7384-190">Na parte superior da tela, no grupo Associação, clique na associação correspondente à Interoperabilidade de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7384-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="b7384-191">Como resultado, a tela Configuração do Número de Diretório será exibida.</span><span class="sxs-lookup"><span data-stu-id="b7384-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="b7384-192">Verifique as seguintes configurações e faça as correções necessárias:</span><span class="sxs-lookup"><span data-stu-id="b7384-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="b7384-193">Faça as alterações adequadas nas Informações do Número de Diretório e nas Configurações do Número de Diretório, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="b7384-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="b7384-194">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7384-194">**Parameter**</span></span>|<span data-ttu-id="b7384-195">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="b7384-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="b7384-196">Informações do Número de Diretório - Partição de Rota</span><span class="sxs-lookup"><span data-stu-id="b7384-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="b7384-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="b7384-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="b7384-198">Configurações do Número de Diretório - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="b7384-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-200">Configurações de Nível de Acesso Confidencial e Parte Alternativa MLPP - Espaço de Pesquisa de Chamada MLPP</span><span class="sxs-lookup"><span data-stu-id="b7384-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="b7384-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="b7384-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="b7384-202">Linha 1 no dispositivo - exibição (ID de chamador)</span><span class="sxs-lookup"><span data-stu-id="b7384-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b7384-203">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="b7384-203">As desired</span></span> <br/> |
   |<span data-ttu-id="b7384-204">Linha 1 no dispositivo - exibição ASCII (ID de chamador)</span><span class="sxs-lookup"><span data-stu-id="b7384-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="b7384-205">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="b7384-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="b7384-206">Quando terminar, role até a parte superior da tela e pressione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b7384-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="b7384-p107">Agora a configuração do dispositivo VTC foi concluída. Você precisará repetir esse processo para outros dispositivos VTC de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="b7384-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

