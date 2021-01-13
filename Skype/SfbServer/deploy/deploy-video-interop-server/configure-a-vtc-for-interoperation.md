---
title: Configurar um VTC para interoperação com o Skype for Business Server
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
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: configure os dispositivos VTC para trabalhar com o Skype for Business Server.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802071"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="d8439-103">Configurar um VTC para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8439-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="d8439-104">**Resumo:** Configure os dispositivos VTC para trabalhar com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8439-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="d8439-105">Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectará ao servidor VIS do Skype for Business por meio de um tronco SIP e gateway de vídeo cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="d8439-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="d8439-106">As configurações descritas aqui são apenas exemplos de como o CUCM pode ser configurado para funcionar com um VIS.</span><span class="sxs-lookup"><span data-stu-id="d8439-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="d8439-107">Outras configurações e/ou usos de funcionalidades alternativas do CUCM também podem ser usadas para obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="d8439-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="d8439-108">Nenhuma recomendação está implícita quanto à configuração ideal para um cenário específico.</span><span class="sxs-lookup"><span data-stu-id="d8439-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="d8439-109">Configurar um VTC registrado no CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="d8439-110">Faça logoff no dispositivo Cisco VTC e navegue até Configuração - \> Configuração do Sistema \> - Provisionamento.</span><span class="sxs-lookup"><span data-stu-id="d8439-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="d8439-111">Verifique as seguintes configurações, corrigindo conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="d8439-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="d8439-112">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-112">**Parameter**</span></span>|<span data-ttu-id="d8439-113">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d8439-114">Modo de provisionamento</span><span class="sxs-lookup"><span data-stu-id="d8439-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="d8439-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="d8439-116">Endereço ExternalManager</span><span class="sxs-lookup"><span data-stu-id="d8439-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="d8439-117">FQDN do CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="d8439-118">Domínio ExternalManager</span><span class="sxs-lookup"><span data-stu-id="d8439-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="d8439-119">Domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="d8439-120">Navegue até Configuração - \> Configuração do Sistema - \> Rede.</span><span class="sxs-lookup"><span data-stu-id="d8439-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="d8439-121">Verifique as seguintes configurações, corrigindo conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="d8439-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="d8439-122">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-122">**Parameter**</span></span>|<span data-ttu-id="d8439-123">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d8439-124">Nome de domínio DNS</span><span class="sxs-lookup"><span data-stu-id="d8439-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="d8439-125">Nome de domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="d8439-126">Endereço dns server 1</span><span class="sxs-lookup"><span data-stu-id="d8439-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="d8439-127">seu endereço de servidor DNS desejado</span><span class="sxs-lookup"><span data-stu-id="d8439-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="d8439-128">Navegue até Configuração - \> Configuração do Sistema - \> Serviços de Rede.</span><span class="sxs-lookup"><span data-stu-id="d8439-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="d8439-129">Verifique se o modo H.323 está desligado e o modo SIP está ligado.</span><span class="sxs-lookup"><span data-stu-id="d8439-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="d8439-130">Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM.</span><span class="sxs-lookup"><span data-stu-id="d8439-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="d8439-131">Verifique as seguintes configurações, corrigindo conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="d8439-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="d8439-132">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-132">**Parameter**</span></span>|<span data-ttu-id="d8439-133">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d8439-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="d8439-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="d8439-135">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-135">Off</span></span> <br/> |
   |<span data-ttu-id="d8439-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="d8439-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="d8439-137">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-137">On</span></span> <br/> |
   | <span data-ttu-id="d8439-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="d8439-138">SIP Mode</span></span> <br/> | <span data-ttu-id="d8439-139">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-139">On</span></span> <br/> |
   |<span data-ttu-id="d8439-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="d8439-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="d8439-141">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-141">On</span></span> <br/> |
   |<span data-ttu-id="d8439-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="d8439-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="d8439-143">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-143">On</span></span> <br/> |
   |<span data-ttu-id="d8439-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="d8439-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="d8439-145">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-145">On</span></span> <br/> |
   
7. <span data-ttu-id="d8439-146">Navegue até Configuração - \> Configuração do Sistema - \> SIP.</span><span class="sxs-lookup"><span data-stu-id="d8439-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="d8439-147">Verifique as seguintes configurações, corrigindo conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="d8439-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="d8439-148">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-148">**Parameter**</span></span>|<span data-ttu-id="d8439-149">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d8439-150">Perfil 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="d8439-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="d8439-151">TCP</span><span class="sxs-lookup"><span data-stu-id="d8439-151">TCP</span></span> <br/> |
   |<span data-ttu-id="d8439-152">Perfil 1 - Saída</span><span class="sxs-lookup"><span data-stu-id="d8439-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="d8439-153">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-153">Off</span></span> <br/> |
   |<span data-ttu-id="d8439-154">Perfil 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="d8439-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="d8439-155">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d8439-155">On</span></span> <br/> |
   |<span data-ttu-id="d8439-156">Perfil 1 - Tipo</span><span class="sxs-lookup"><span data-stu-id="d8439-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="d8439-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="d8439-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="d8439-158">Perfil 1 - URI</span><span class="sxs-lookup"><span data-stu-id="d8439-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="d8439-159">Atribuído automaticamente no registro CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="d8439-160">Proxy 1 - Endereço</span><span class="sxs-lookup"><span data-stu-id="d8439-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="d8439-161">O nome de host do CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="d8439-162">O VTC agora está configurado para interoperação.</span><span class="sxs-lookup"><span data-stu-id="d8439-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="d8439-163">Antes que o serviço possa começar, há etapas finais para executar no lado do CUCM.</span><span class="sxs-lookup"><span data-stu-id="d8439-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="d8439-164">Configurar dispositivos VTC no CUCM</span><span class="sxs-lookup"><span data-stu-id="d8439-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="d8439-165">Faça logon no CUCM e navegue até Administração do Cisco Unified CM - \> Dispositivo- \> Telefone- \> Encontrar.</span><span class="sxs-lookup"><span data-stu-id="d8439-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="d8439-166">Selecione o dispositivo VTC a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="d8439-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="d8439-167">Verifique as seguintes configurações na tela Configuração do Telefone, corrigindo conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="d8439-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="d8439-168">Depois que essas configurações foram alteradas ou verificadas, clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="d8439-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="d8439-169">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-169">**Parameter**</span></span>|<span data-ttu-id="d8439-170">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="d8439-171">Informações do Dispositivo - Modelo de Botão de Telefone</span><span class="sxs-lookup"><span data-stu-id="d8439-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="d8439-172">Codec de Telepresência da Cisco C40 padrão</span><span class="sxs-lookup"><span data-stu-id="d8439-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="d8439-173">Informações do Dispositivo - Perfil de Telefone Comum</span><span class="sxs-lookup"><span data-stu-id="d8439-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="d8439-174">Perfil de Telefone Comum Padrão</span><span class="sxs-lookup"><span data-stu-id="d8439-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="d8439-175">Informações do Dispositivo - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="d8439-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-177">Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR</span><span class="sxs-lookup"><span data-stu-id="d8439-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-179">Informações do Dispositivo - Lista de Grupos de Recursos de Mídia</span><span class="sxs-lookup"><span data-stu-id="d8439-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="d8439-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-181">Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="d8439-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="d8439-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="d8439-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="d8439-183">Informações Específicas do Protocolo - Redirecionando o Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="d8439-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-185">Informações Específicas do Protocolo - Espaço de Pesquisa de Chamada SUBSCRIBE</span><span class="sxs-lookup"><span data-stu-id="d8439-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-187">Informações Específicas do Protocolo - Perfil SIP</span><span class="sxs-lookup"><span data-stu-id="d8439-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="d8439-188">Perfil SIP padrão para o ponto de extremidade de telepresência</span><span class="sxs-lookup"><span data-stu-id="d8439-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="d8439-189">Depois que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d8439-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="d8439-190">Na parte superior da tela do grupo Associação, clique na associação para a Interop de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="d8439-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="d8439-191">Isso exibe a tela Configuração do Número de Diretório.</span><span class="sxs-lookup"><span data-stu-id="d8439-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="d8439-192">Verifique as seguintes configurações, corrigindo conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="d8439-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="d8439-193">Faça as alterações apropriadas, conforme mostrado nas Informações do Número de Diretório e nas Configurações do Número de Diretório.</span><span class="sxs-lookup"><span data-stu-id="d8439-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="d8439-194">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d8439-194">**Parameter**</span></span>|<span data-ttu-id="d8439-195">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="d8439-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="d8439-196">Informações de Número de Diretório - Partição de Rota</span><span class="sxs-lookup"><span data-stu-id="d8439-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="d8439-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="d8439-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="d8439-198">Configurações de Número de Diretório - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="d8439-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-200">Configurações de Nível de Acesso Confidencial e de Terceiros Alternativos MLPP - Espaço de Pesquisa de Chamada MLPP</span><span class="sxs-lookup"><span data-stu-id="d8439-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="d8439-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="d8439-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="d8439-202">Linha 1 no dispositivo - Exibição (ID do chamador)</span><span class="sxs-lookup"><span data-stu-id="d8439-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="d8439-203">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="d8439-203">As desired</span></span> <br/> |
   |<span data-ttu-id="d8439-204">Linha 1 no dispositivo - Exibição ASCII (ID do chamador)</span><span class="sxs-lookup"><span data-stu-id="d8439-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="d8439-205">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="d8439-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="d8439-206">Quando terminar, role até a parte superior da tela e pressione **Save**.</span><span class="sxs-lookup"><span data-stu-id="d8439-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="d8439-207">A configuração agora está concluída para este dispositivo VTC.</span><span class="sxs-lookup"><span data-stu-id="d8439-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="d8439-208">Você precisará repetir esse processo para outros dispositivos VTC em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d8439-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

