---
title: Configurar um VTC para interoperação com o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 'Resumo: configurar os dispositivos VTC para que funcionem com o Skype for Business Server.'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302786"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="e5ac9-103">Configurar um VTC para interoperação com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e5ac9-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="e5ac9-104">**Resumo:** Configure os dispositivos VTC para que funcionem com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="e5ac9-105">Você precisará executar os seguintes procedimentos de personalização de configuração para cada VTC que se conectarão ao servidor do Skype for Business VIS por meio de um tronco SIP e do gateway de vídeo do Cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="e5ac9-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="e5ac9-106">As configurações descritas aqui servem apenas como exemplos de como o CUCM pode ser configurado para trabalhar com um VIS.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="e5ac9-107">Outras configurações e/ou aplicações da funcionalidade alternativa do CUCM também poderiam ser usadas para alcançar o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="e5ac9-108">Não há qualquer recomendação implícita quanto à configuração ideal para determinado cenário.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="e5ac9-109">Configurar um VTC registrado no CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="e5ac9-110">Conecte-se ao dispositivo Cisco VTC e navegue até configuração-\>configuração do sistema\>-provisionamento.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="e5ac9-111">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="e5ac9-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e5ac9-112">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-112">**Parameter**</span></span>|<span data-ttu-id="e5ac9-113">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5ac9-114">Modo de Provisionamento</span><span class="sxs-lookup"><span data-stu-id="e5ac9-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="e5ac9-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="e5ac9-116">Endereço ExternalManager</span><span class="sxs-lookup"><span data-stu-id="e5ac9-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="e5ac9-117">FQDN do CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="e5ac9-118">Domínio externalmanager</span><span class="sxs-lookup"><span data-stu-id="e5ac9-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="e5ac9-119">Domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="e5ac9-120">Navegue até configuração-\>sistema-configuração\>do sistema-rede.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="e5ac9-121">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="e5ac9-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e5ac9-122">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-122">**Parameter**</span></span>|<span data-ttu-id="e5ac9-123">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5ac9-124">Nome do Domínio DNS</span><span class="sxs-lookup"><span data-stu-id="e5ac9-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="e5ac9-125">Nome do Domínio do CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="e5ac9-126">Endereço do Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="e5ac9-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="e5ac9-127">Endereço do servidor DNS desejado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="e5ac9-128">Navegue até configuração-\>sistema-configuração\>do sistema-serviços de rede.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="e5ac9-129">Verifique se o modo H.323 está desativado e se o modo SIP está ativado.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="e5ac9-p103">Essas opções são definidas automaticamente quando o ponto de extremidade é registrado no CUCM. Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="e5ac9-p103">These options are set automatically when the endpoint is registered with CUCM. Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e5ac9-132">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-132">**Parameter**</span></span>|<span data-ttu-id="e5ac9-133">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5ac9-134">Modo H.323</span><span class="sxs-lookup"><span data-stu-id="e5ac9-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="e5ac9-135">Desativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-135">Off</span></span> <br/> |
   |<span data-ttu-id="e5ac9-136">Modo HTTP</span><span class="sxs-lookup"><span data-stu-id="e5ac9-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="e5ac9-137">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-137">On</span></span> <br/> |
   | <span data-ttu-id="e5ac9-138">Modo SIP</span><span class="sxs-lookup"><span data-stu-id="e5ac9-138">SIP Mode</span></span> <br/> | <span data-ttu-id="e5ac9-139">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-139">On</span></span> <br/> |
   |<span data-ttu-id="e5ac9-140">Modo Telnet</span><span class="sxs-lookup"><span data-stu-id="e5ac9-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="e5ac9-141">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-141">On</span></span> <br/> |
   |<span data-ttu-id="e5ac9-142">Texto de Boas-vindas</span><span class="sxs-lookup"><span data-stu-id="e5ac9-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="e5ac9-143">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-143">On</span></span> <br/> |
   |<span data-ttu-id="e5ac9-144">Modo XMLAPI</span><span class="sxs-lookup"><span data-stu-id="e5ac9-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="e5ac9-145">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-145">On</span></span> <br/> |
   
7. <span data-ttu-id="e5ac9-146">Navegue até configuração-\>sistema-configuração\>do sistema-SIP.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="e5ac9-147">Verifique as seguintes configurações e faça as correções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="e5ac9-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e5ac9-148">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-148">**Parameter**</span></span>|<span data-ttu-id="e5ac9-149">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5ac9-150">Perfil 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="e5ac9-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="e5ac9-151">TCP</span><span class="sxs-lookup"><span data-stu-id="e5ac9-151">TCP</span></span> <br/> |
   |<span data-ttu-id="e5ac9-152">Perfil 1 - Saída</span><span class="sxs-lookup"><span data-stu-id="e5ac9-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="e5ac9-153">Desativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-153">Off</span></span> <br/> |
   |<span data-ttu-id="e5ac9-154">Perfil 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="e5ac9-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="e5ac9-155">Ativado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-155">On</span></span> <br/> |
   |<span data-ttu-id="e5ac9-156">Perfil 1 - Tipo</span><span class="sxs-lookup"><span data-stu-id="e5ac9-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="e5ac9-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="e5ac9-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="e5ac9-158">Perfil 1 - URI</span><span class="sxs-lookup"><span data-stu-id="e5ac9-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="e5ac9-159">Atribuído automaticamente durante o registro no CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="e5ac9-160">Proxy 1 - Endereço</span><span class="sxs-lookup"><span data-stu-id="e5ac9-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="e5ac9-161">O nome de host do CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="e5ac9-p104">Agora o VTC está configurado para interoperação. Antes de o serviço iniciar, é necessário executar algumas etapas finais no CUCM.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-p104">The VTC is now configured for interoperation. Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="e5ac9-164">Configurar os dispositivos VTC no CUCM</span><span class="sxs-lookup"><span data-stu-id="e5ac9-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="e5ac9-165">Conecte-se ao CUCM e navegue até a administração do Gerenciador\>de telefonia\>unificado da Cisco-Device-Phone-\>Find.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="e5ac9-p105">Selecione o dispositivo VTC a ser configurado. Verifique as seguintes configurações na tela Configuração do Telefone, fazendo as correções necessárias. Depois que essas configurações forem alteradas ou configuradas, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-p105">Select the VTC device to be configured. Verify the following settings on the Phone Configuration screen, correcting as needed. Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="e5ac9-169">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-169">**Parameter**</span></span>|<span data-ttu-id="e5ac9-170">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e5ac9-171">Informações do Dispositivo - Modelo de Botão de Telefone</span><span class="sxs-lookup"><span data-stu-id="e5ac9-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="e5ac9-172">Codec padrão de telepresença Cisco C40</span><span class="sxs-lookup"><span data-stu-id="e5ac9-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e5ac9-173">Informações do Dispositivo - Perfil de Telefone Comum</span><span class="sxs-lookup"><span data-stu-id="e5ac9-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="e5ac9-174">Perfil de Telefone Comum Padrão</span><span class="sxs-lookup"><span data-stu-id="e5ac9-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="e5ac9-175">Informações do Dispositivo - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="e5ac9-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-177">Informações do Dispositivo - Espaço de Pesquisa de Chamada AAR</span><span class="sxs-lookup"><span data-stu-id="e5ac9-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-179">Informações do Dispositivo - Lista de Grupos de Recursos de Mídia</span><span class="sxs-lookup"><span data-stu-id="e5ac9-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="e5ac9-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-181">Informações Específicas do Protocolo - Perfil de Segurança do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="e5ac9-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="e5ac9-182">Codec de telepresença Cisco C40</span><span class="sxs-lookup"><span data-stu-id="e5ac9-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e5ac9-183">Informações Específicas do Protocolo - Reencaminhamento do Espaço de Pesquisa de de Chamada</span><span class="sxs-lookup"><span data-stu-id="e5ac9-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-185">Informações específicas do protocolo-assinar o espaço de pesquisa de chamadas</span><span class="sxs-lookup"><span data-stu-id="e5ac9-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-187">Informações Específicas do Protocolo - Perfil SIP</span><span class="sxs-lookup"><span data-stu-id="e5ac9-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="e5ac9-188">Perfil SIP Padrão para o Ponto de Extremidade de Telepresença</span><span class="sxs-lookup"><span data-stu-id="e5ac9-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="e5ac9-189">Assim que a configuração VTC for salva, navegue novamente até a tela Configuração do Telefone do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="e5ac9-190">Na parte superior da tela, no grupo Associação, clique na associação correspondente à Interoperabilidade de Vídeo.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="e5ac9-191">Como resultado, a tela Configuração do Número de Diretório será exibida.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="e5ac9-192">Verifique as seguintes configurações e faça as correções necessárias:</span><span class="sxs-lookup"><span data-stu-id="e5ac9-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="e5ac9-193">Faça as alterações adequadas nas Informações do Número de Diretório e nas Configurações do Número de Diretório, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="e5ac9-194">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-194">**Parameter**</span></span>|<span data-ttu-id="e5ac9-195">**Configuração recomendada**</span><span class="sxs-lookup"><span data-stu-id="e5ac9-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="e5ac9-196">Informações do Número de Diretório - Partição de Rota</span><span class="sxs-lookup"><span data-stu-id="e5ac9-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="e5ac9-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="e5ac9-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="e5ac9-198">Configurações do Número de Diretório - Espaço de Pesquisa de Chamada</span><span class="sxs-lookup"><span data-stu-id="e5ac9-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-200">Configurações de Nível de Acesso Confidencial e Parte Alternativa MLPP - Espaço de Pesquisa de Chamada MLPP</span><span class="sxs-lookup"><span data-stu-id="e5ac9-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="e5ac9-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e5ac9-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e5ac9-202">Linha 1 em Device-display (identificação de chamadas)</span><span class="sxs-lookup"><span data-stu-id="e5ac9-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e5ac9-203">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-203">As desired</span></span> <br/> |
   |<span data-ttu-id="e5ac9-204">Linha 1 na exibição dispositivo-ASCII (identificação de chamadas)</span><span class="sxs-lookup"><span data-stu-id="e5ac9-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e5ac9-205">Conforme desejado</span><span class="sxs-lookup"><span data-stu-id="e5ac9-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="e5ac9-206">Quando terminar, role até a parte superior da tela e pressione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="e5ac9-p107">Agora a configuração do dispositivo VTC foi concluída. Você precisará repetir esse processo para outros dispositivos VTC de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="e5ac9-p107">Configuration is now complete for this VTC device. You will need to repeat this process for other VTC devices in your enterprise.</span></span>

