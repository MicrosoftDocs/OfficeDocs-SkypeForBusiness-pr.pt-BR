---
title: Planejamento para IPv6 no Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/21/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Resumo: Implemente IPv6 antes de instalar Skype para Business Server 2015.'
ms.openlocfilehash: 40c5209a582aeb55657e8e1f0b8971f2c8ed79d0
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="56799-103">Planejamento para IPv6 no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="56799-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="56799-104">**Resumo:** Implemente o IPv6 antes de instalar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="56799-104">**Summary:** Implement IPv6 before you install Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="56799-105">Skype para Business Server inclui o suporte para IP versão 6 (IPv6) endereços, juntamente com o suporte contínuo de IP versão 4 (IPv4) endereços.</span><span class="sxs-lookup"><span data-stu-id="56799-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="56799-106">Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet.</span><span class="sxs-lookup"><span data-stu-id="56799-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="56799-107">Devido ao número crescente de dispositivos em todo o mundo, os endereços IPv4 disponíveis executaram check-out. Dessa forma, muitos novos dispositivos estejam mudando para usar endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="56799-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="56799-108">Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32 bits, os endereços IPv6 usam 128 bits.</span><span class="sxs-lookup"><span data-stu-id="56799-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="56799-109">Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.</span><span class="sxs-lookup"><span data-stu-id="56799-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="56799-110">Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="56799-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="56799-111">A alteração na formatação e funcionalidade para dispositivos que usam os endereços IPv6 requer várias considerações de implantação e configuração no seu Skype para instalação do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="56799-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="56799-112">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="56799-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="56799-113">Overview of IP address types</span><span class="sxs-lookup"><span data-stu-id="56799-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="56799-114">Technical requirements for IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="56799-115">Migration and coexistence considerations for IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="56799-116">Se você determinar que você usará endereços IPv6, consulte o artigo de [tipos de endereço de IP configurar no Skype para negócios](ip-address-types.md) .</span><span class="sxs-lookup"><span data-stu-id="56799-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="56799-117">Visão geral dos tipos de endereço IP</span><span class="sxs-lookup"><span data-stu-id="56799-117">Overview of IP address types</span></span>
<span data-ttu-id="56799-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-118"></span></span>

<span data-ttu-id="56799-119">Você tem três opções ao configurar endereços IP no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="56799-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="56799-120">Você pode configurar Skype para Business Server com suporte para IP versão 4 (IPv4), somente IP versão 6 (IPv6), ou uma combinação de ambos (conhecida como uma pilha dupla).</span><span class="sxs-lookup"><span data-stu-id="56799-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="56799-121">Vários problemas devem ser considerados para cada tipo de configuração:</span><span class="sxs-lookup"><span data-stu-id="56799-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="56799-122">**Apenas IPv4** IPv6 foi criado porque o mundo está ficando sem endereços IPv4.</span><span class="sxs-lookup"><span data-stu-id="56799-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="56799-123">No fim das contas, o IPv6 será completamente suportado em todo o mundo, mas no momento, várias empresas e dispositivos aos quais sua empresa pode precisar se comunicar ainda não oferecem suporte ao IPv6, e poderão não oferecer por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="56799-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="56799-124">Uma configuração apenas IPv4 ajudará a garantir que sua Skype para implementação da Business Server pode se comunicar com a maioria dos dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="56799-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="56799-125">**Somente IPv6** Por outro lado, uma implementação completamente IPv6 excluirá a comunicação com vários dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="56799-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="56799-126">**Pilha dupla** Pilha dupla é uma rede onde os endereços IPv4 e IPv6 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="56799-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="56799-127">Essa configuração é suportada no Skype para Business Server porque na maioria dos casos, a transição de IPv4 completo para full-IPv6 levará alguns anos.</span><span class="sxs-lookup"><span data-stu-id="56799-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="56799-128">As seções a seguir destacam a compatibilidade entre essas três configurações Skype vários recursos do Business Server.</span><span class="sxs-lookup"><span data-stu-id="56799-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56799-p106">Configuração de cliente ou servidor com somente IPv6 é suportada apenas para fins de validação ou utilização em laboratório. A configuração somente IPv6 não é suportada na implantação de produção.</span><span class="sxs-lookup"><span data-stu-id="56799-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="56799-131">Registro de cliente</span><span class="sxs-lookup"><span data-stu-id="56799-131">Client Registration</span></span>
<span data-ttu-id="56799-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-132"></span></span>

|<span data-ttu-id="56799-133">**Rede de ponto de extremidade do cliente**</span><span class="sxs-lookup"><span data-stu-id="56799-133">**Client endpoint network**</span></span>|<span data-ttu-id="56799-134">**Rede de servidor**</span><span class="sxs-lookup"><span data-stu-id="56799-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56799-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-135">IPv4</span></span>  <br/> |<span data-ttu-id="56799-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-137">IPv4</span></span>  <br/> |<span data-ttu-id="56799-138">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-139">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-139">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-141">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-141">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-142">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-143">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-143">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="56799-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-145">IPv6</span></span>  <br/> |<span data-ttu-id="56799-146">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-147">IPv6</span></span>  <br/> |<span data-ttu-id="56799-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="56799-149">Cliente ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="56799-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="56799-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-150"></span></span>

<span data-ttu-id="56799-p107">As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após o registro bem sucedido de ambos os clientes, as combinações a seguir são suportadas.</span><span class="sxs-lookup"><span data-stu-id="56799-p107">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="56799-153">**Ponto de extremidade do cliente 1**</span><span class="sxs-lookup"><span data-stu-id="56799-153">**Client endpoint 1**</span></span>|<span data-ttu-id="56799-154">**Ponto de extremidade do cliente 2**</span><span class="sxs-lookup"><span data-stu-id="56799-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56799-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-155">IPv4</span></span>  <br/> |<span data-ttu-id="56799-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-157">IPv4</span></span>  <br/> |<span data-ttu-id="56799-158">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-159">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-159">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-160">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-161">IPv6</span></span>  <br/> |<span data-ttu-id="56799-162">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-163">IPv6</span></span>  <br/> |<span data-ttu-id="56799-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="56799-165">Conferência</span><span class="sxs-lookup"><span data-stu-id="56799-165">Conferencing</span></span>
<span data-ttu-id="56799-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-166"></span></span>

<span data-ttu-id="56799-167">As conferências incluem áudio/vídeo, compartilhamento de aplicativos e colaboração de dados, como uso de quadro de comunicações e compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="56799-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="56799-168">**Rede de ponto de extremidade do cliente**</span><span class="sxs-lookup"><span data-stu-id="56799-168">**Client endpoint network**</span></span>|<span data-ttu-id="56799-169">**Rede de servidor**</span><span class="sxs-lookup"><span data-stu-id="56799-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56799-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-170">IPv4</span></span>  <br/> |<span data-ttu-id="56799-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-172">IPv4</span></span>  <br/> |<span data-ttu-id="56799-173">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-174">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-174">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-176">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-176">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-177">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-178">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-178">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="56799-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-180">IPv6</span></span>  <br/> |<span data-ttu-id="56799-181">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-182">IPv6</span></span>  <br/> |<span data-ttu-id="56799-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="56799-184">Servidor de Mediação/PSTN</span><span class="sxs-lookup"><span data-stu-id="56799-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="56799-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-185"></span></span>

<span data-ttu-id="56799-186">Skype para Business Server não suporta bypass de mídia para telefônica pública comutada (PSTN) de rede chamadas se o tráfego estiver através de uma interface de IPv6.</span><span class="sxs-lookup"><span data-stu-id="56799-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="56799-187">Se o desvio de mídia é necessário, recomendamos que o gateway PSTN seja configurado para IPv4.</span><span class="sxs-lookup"><span data-stu-id="56799-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="56799-188">**Interface principal 1**</span><span class="sxs-lookup"><span data-stu-id="56799-188">**Primary interface 1**</span></span>|<span data-ttu-id="56799-189">**Interface PSTN (no servidor de mediação)**</span><span class="sxs-lookup"><span data-stu-id="56799-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="56799-190">**Configuração do gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="56799-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56799-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-191">IPv4</span></span>  <br/> |<span data-ttu-id="56799-192">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-192">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-194">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-194">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-195">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-195">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-197">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-197">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-198">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-198">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="56799-200">A interface principal é o que se comunica com o Skype para componentes de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="56799-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="56799-201">Comunicações ponto a ponto de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="56799-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="56799-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-202"></span></span>

<span data-ttu-id="56799-203">As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="56799-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="56799-204">**Rede de usuários remotos**</span><span class="sxs-lookup"><span data-stu-id="56799-204">**Remote user network**</span></span>|<span data-ttu-id="56799-205">**Servidor de borda (borda externa)**</span><span class="sxs-lookup"><span data-stu-id="56799-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56799-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-206">IPv4</span></span>  <br/> |<span data-ttu-id="56799-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-208">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-208">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="56799-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="56799-210">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-210">Dual stack</span></span>  <br/> |<span data-ttu-id="56799-211">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-212">IPv6</span></span>  <br/> |<span data-ttu-id="56799-213">Pilha dual</span><span class="sxs-lookup"><span data-stu-id="56799-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="56799-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-214">IPv6</span></span>  <br/> |<span data-ttu-id="56799-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="56799-216">Configuração do pool de Front-Ends e do pool do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="56799-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="56799-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-217"></span></span>

<span data-ttu-id="56799-218">A tabela a seguir mostra a matriz de suporte entre o pool do servidor Front-End e pool de servidores de borda interno.</span><span class="sxs-lookup"><span data-stu-id="56799-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="56799-219">**Matriz de (borda interna) do Pool de borda e de Pool de Front-End**</span><span class="sxs-lookup"><span data-stu-id="56799-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="56799-220">**Pool de borda: IPv4**</span><span class="sxs-lookup"><span data-stu-id="56799-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="56799-221">**Pool de borda: Pilha dual**</span><span class="sxs-lookup"><span data-stu-id="56799-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="56799-222">**Pool de borda: IPv6**</span><span class="sxs-lookup"><span data-stu-id="56799-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56799-223">**Pool de Front-Ends: IPv4**</span><span class="sxs-lookup"><span data-stu-id="56799-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="56799-224">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-224">Yes</span></span>  <br/> |<span data-ttu-id="56799-225">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-225">Yes</span></span>  <br/> |<span data-ttu-id="56799-226">Não</span><span class="sxs-lookup"><span data-stu-id="56799-226">No</span></span>  <br/> |
|<span data-ttu-id="56799-227">**Pool de Front-Ends: Pilha dual**</span><span class="sxs-lookup"><span data-stu-id="56799-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="56799-228">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-228">Yes</span></span>  <br/> |<span data-ttu-id="56799-229">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-229">Yes</span></span>  <br/> |<span data-ttu-id="56799-230">Não</span><span class="sxs-lookup"><span data-stu-id="56799-230">No</span></span>  <br/> |
|<span data-ttu-id="56799-231">**Pool de Front-Ends: IPv6**</span><span class="sxs-lookup"><span data-stu-id="56799-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="56799-232">Não</span><span class="sxs-lookup"><span data-stu-id="56799-232">No</span></span>  <br/> |<span data-ttu-id="56799-233">Não</span><span class="sxs-lookup"><span data-stu-id="56799-233">No</span></span>  <br/> |<span data-ttu-id="56799-234">Sim\*</span><span class="sxs-lookup"><span data-stu-id="56799-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="56799-235">\*Use essa combinação somente em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="56799-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="56799-236">A tabela a seguir descreve a matriz de combinações suportadas das interfaces de borda interna e externa.</span><span class="sxs-lookup"><span data-stu-id="56799-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="56799-237">**Pool de borda (borda interna) e borda (borda externa) matriz do pool**</span><span class="sxs-lookup"><span data-stu-id="56799-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="56799-238">**Pool de borda (Borda externa): IPv4**</span><span class="sxs-lookup"><span data-stu-id="56799-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="56799-239">**Pool de borda (Borda externa): Pilha dual**</span><span class="sxs-lookup"><span data-stu-id="56799-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="56799-240">**Pool de borda (Borda externa): IPv6**</span><span class="sxs-lookup"><span data-stu-id="56799-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56799-241">**Pool de borda (Borda interna): IPv4**</span><span class="sxs-lookup"><span data-stu-id="56799-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="56799-242">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-242">Yes</span></span>  <br/> |<span data-ttu-id="56799-243">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-243">Yes</span></span>  <br/> |<span data-ttu-id="56799-244">Não</span><span class="sxs-lookup"><span data-stu-id="56799-244">No</span></span>  <br/> |
|<span data-ttu-id="56799-245">**Pool de borda (Borda interna): Pilha dual**</span><span class="sxs-lookup"><span data-stu-id="56799-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="56799-246">Não</span><span class="sxs-lookup"><span data-stu-id="56799-246">No</span></span>  <br/> |<span data-ttu-id="56799-247">Sim</span><span class="sxs-lookup"><span data-stu-id="56799-247">Yes</span></span>  <br/> |<span data-ttu-id="56799-248">Não</span><span class="sxs-lookup"><span data-stu-id="56799-248">No</span></span>  <br/> |
|<span data-ttu-id="56799-249">**Pool de borda (Borda interna): IPv6**</span><span class="sxs-lookup"><span data-stu-id="56799-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="56799-250">Não</span><span class="sxs-lookup"><span data-stu-id="56799-250">No</span></span>  <br/> |<span data-ttu-id="56799-251">Não</span><span class="sxs-lookup"><span data-stu-id="56799-251">No</span></span>  <br/> |<span data-ttu-id="56799-252">Sim\*</span><span class="sxs-lookup"><span data-stu-id="56799-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="56799-253">\*Use essa combinação somente em um ambiente de laboratório.</span><span class="sxs-lookup"><span data-stu-id="56799-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="56799-254">Suporte avançado do Enterprise Voice para IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="56799-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-255"></span></span>

<span data-ttu-id="56799-p109">Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou passagem livre de mídia devem ser configurados como implementações somente IPv4 ou de pilha dual. Pontos de extremidade usando apenas IPv6 não podem usar nenhum desses recursos.</span><span class="sxs-lookup"><span data-stu-id="56799-p109">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation. Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56799-258">Em uma implantação de pilha dupla, mesmo se um Skype para cliente Business Server se conecta a um Skype para Business Server usando o IPv6, Skype para Business Server fará um melhor esforço para mapear um endereço IPv4 apropriado para suportar o E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="56799-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="56799-259">Serviço de informações de local com endereços IPv6 não é suportado.</span><span class="sxs-lookup"><span data-stu-id="56799-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="56799-p110">O Unified Messaging (UM) do Exchange não suporta IPv6. Para o UM do Exchange, certifique-se de que a resolução do DNS não retorna um endereço IPv6. A utilização de IPv6 pode provocar falhas ao enviar chamadas para correios de voz.</span><span class="sxs-lookup"><span data-stu-id="56799-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="56799-263">Outro Skype para suporte de recurso do servidor de negócios para IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="56799-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-264"></span></span>

<span data-ttu-id="56799-265">Além dos recursos e componentes mencionados anteriormente, Skype para Business Server oferece suporte a IPv6 para os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="56799-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="56799-266">**Chat Persistente**</span><span class="sxs-lookup"><span data-stu-id="56799-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="56799-267">Configurar o IPv6 para o Chat persistente usando o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="56799-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="56799-268">Para obter detalhes sobre a configuração de Chat persistente, consulte a documentação de implantação do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="56799-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="56799-269">**Relatórios de CDR (registro de detalhes de chamada) e QoE (Qualidade de experiência)**</span><span class="sxs-lookup"><span data-stu-id="56799-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="56799-270">Os relatórios de monitoramento incluem o endereço IP conforme é armazenado no banco de dados do Servidor de Monitoramento, independente de ser do tipo IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="56799-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="56799-271">Requisitos técnicos para IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="56799-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-272"></span></span>

<span data-ttu-id="56799-273">Se você planeja configurar Skype para Business Server para IPv6, lembre-se os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="56799-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="56799-274">Para usar endereços IPv6 com Skype para Business Server, você precisará criar sistema de nomes de domínio (DNS) registra para registros que devem ser descobertos e resolvidos para um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="56799-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="56799-275">O DNS IPv6 usa um registros de host AAAA (quad-A).</span><span class="sxs-lookup"><span data-stu-id="56799-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="56799-276">Se você usar o IPv4 e o IPv6 na sua implantação, é melhor configurar e manter os registros de host A para IPv4 e registros de host AAAA para IPv6.</span><span class="sxs-lookup"><span data-stu-id="56799-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="56799-277">Mesmo quando passar totalmente sua implantação para o IPv6, você ainda pode precisar de registros de host DNS IPv4 para usuários externos que ainda usam IPv4.</span><span class="sxs-lookup"><span data-stu-id="56799-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="56799-p113">É possível implantar registros de host DNS IPv6 antes de iniciar a usar o IPv6. Se o cliente ou servidor não usar IPv6, o registro não será referenciado. As tecnologias transicionais tomarão a decisão sobre qual registro usar, com base na configuração de tecnologia de transição e políticas.</span><span class="sxs-lookup"><span data-stu-id="56799-p113">You can deploy IPv6 DNS host records before you start using IPv6. If the client or server doesn't use IPv6, the record will not be referenced. Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="56799-281">Cada endereço IPv6 possui um escopo.</span><span class="sxs-lookup"><span data-stu-id="56799-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="56799-282">Os três escopos que você pode usar para o endereçamento IPv6 são endereços IPv6 globais (semelhantes aos endereços IPv4 públicos), exclusivo locais endereços IPv6 (semelhantes aos intervalos de endereços IPv4 privados) e endereços IPv6 de link local (semelhantes ao automáticos endereços IP privados em Windows Server para IPv4).</span><span class="sxs-lookup"><span data-stu-id="56799-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="56799-283">Todos os servidores em um pool devem ter endereços IPv6 com o mesmo escopo.</span><span class="sxs-lookup"><span data-stu-id="56799-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="56799-284">IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe da rede e seu provedor de Internet para ajudar a garantir que os endereços que você atribuir no nível do Windows Server e no Skype para nível Business Server funcionam conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="56799-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="56799-285">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="56799-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="56799-286">Considerações de migração e de coexistência para IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="56799-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-287"></span></span>

<span data-ttu-id="56799-288">IP versão 6 (IPv6) não é suportado no Lync Server 2010 ou o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="56799-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="56799-289">Para fins de teste-piloto, você pode testar o Lync Server 2010 e do Skype para coexistência de pilha dupla Business Server.</span><span class="sxs-lookup"><span data-stu-id="56799-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="56799-290">Recomendamos que todos os pools para um determinado site central são atualizados para Skype para Business Server antes de habilitar IPv6 (rede de pilha dupla) para qualquer um dos pools.</span><span class="sxs-lookup"><span data-stu-id="56799-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="56799-291">Se for necessário configurar um pool apenas para IPv6, recomendamos que você defina um pool somente de IPv6 em seu ambiente de laboratório para testes.</span><span class="sxs-lookup"><span data-stu-id="56799-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="56799-292">Os cenários a seguir são suportados durante a migração e coexistência:</span><span class="sxs-lookup"><span data-stu-id="56799-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="56799-293">Skype para pools Business Server, Lync Server 2013 e Lync Server 2010 em modo IPv4, coexistindo com o Skype para Business Server no modo de pilha dupla.</span><span class="sxs-lookup"><span data-stu-id="56799-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="56799-294">Skype para pool de servidores de negócios no modo apenas IPv6, se o pool apenas IPv6 estiver em silo.</span><span class="sxs-lookup"><span data-stu-id="56799-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56799-295">Ver também</span><span class="sxs-lookup"><span data-stu-id="56799-295">See also</span></span>
<span data-ttu-id="56799-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="56799-296"></span></span>

#### 

[<span data-ttu-id="56799-297">Configurar tipos de endereço IP no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="56799-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)
#### 

[<span data-ttu-id="56799-298">Arquitetura de endereçamento do IP versão 6</span><span class="sxs-lookup"><span data-stu-id="56799-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="56799-299">Formato de endereço Unicast Global de IPv6</span><span class="sxs-lookup"><span data-stu-id="56799-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="56799-300">Endereços de Unicast IPv6 locais exclusivo</span><span class="sxs-lookup"><span data-stu-id="56799-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)

