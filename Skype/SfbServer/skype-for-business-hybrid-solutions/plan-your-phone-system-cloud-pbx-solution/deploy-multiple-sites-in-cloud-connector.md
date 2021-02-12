---
title: Implantar vários sites no Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Saiba como implantar vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358917"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="b8a6f-103">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="b8a6f-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="b8a6f-104">O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="b8a6f-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="b8a6f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="b8a6f-106">Saiba como implantar vários sites PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="b8a6f-107">Esta seção descreve como implantar vários sites PSTN (Rede Telefônica Pública Comucionária).</span><span class="sxs-lookup"><span data-stu-id="b8a6f-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="b8a6f-108">Os sites são implantados um de cada vez usando as mesmas etapas da implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="b8a6f-109">Este tópico descreve as considerações e as diferenças entre sites em uma implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="b8a6f-110">Vários sites PSTN (Rede Telefônica Pública Comucionária)</span><span class="sxs-lookup"><span data-stu-id="b8a6f-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="b8a6f-111">O exemplo a seguir mostra uma configuração de exemplo para implantar o Skype for Business Cloud Connector Edition para diferentes sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="b8a6f-112">Certifique-se de que suas definições de configuração estão corretas antes de iniciar uma implantação.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="b8a6f-113">Site PSTN 1</span><span class="sxs-lookup"><span data-stu-id="b8a6f-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="b8a6f-114">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="b8a6f-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="b8a6f-115">Para cada site PSTN que você deseja adicionar, siga as etapas em [Implantar um único site no Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="b8a6f-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b8a6f-116">A pasta compartilhada para preparar alta disponibilidade é por site PSTN.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="b8a6f-117">A pasta compartilhada **deve** ser diferente entre sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="b8a6f-118">Não use a mesma pasta compartilhada para vários sites.></span><span class="sxs-lookup"><span data-stu-id="b8a6f-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="b8a6f-119">Site único com alta disponibilidade (HA) em comparação com implantações de vários sites</span><span class="sxs-lookup"><span data-stu-id="b8a6f-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="b8a6f-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="b8a6f-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="b8a6f-121">A tabela a seguir lista as diferenças entre um único site com suporte para ha e uma implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="b8a6f-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="b8a6f-122">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="b8a6f-122">**Category**</span></span>|<span data-ttu-id="b8a6f-123">**Item**</span><span class="sxs-lookup"><span data-stu-id="b8a6f-123">**Item**</span></span>|<span data-ttu-id="b8a6f-124">**Site único com ha**</span><span class="sxs-lookup"><span data-stu-id="b8a6f-124">**Single-Site with HA**</span></span>|<span data-ttu-id="b8a6f-125">**Vários sites**</span><span class="sxs-lookup"><span data-stu-id="b8a6f-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8a6f-126">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-126">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-127">Nome do Host do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="b8a6f-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="b8a6f-128">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-129">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-130">Setup</span></span>  <br/> |<span data-ttu-id="b8a6f-131">Pasta compartilhada</span><span class="sxs-lookup"><span data-stu-id="b8a6f-131">Shared folder</span></span>  <br/> |<span data-ttu-id="b8a6f-132">Requer a **mesma pasta** compartilhada entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-133">Requer uma **pasta** compartilhada diferente entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="b8a6f-134">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-134">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="b8a6f-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="b8a6f-136">Requer o **mesmo domínio** em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-137">Requer o **mesmo domínio** em sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-138">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-138">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="b8a6f-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="b8a6f-140">Os nomes de domínio e a ordem devem ser **os mesmos em** vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-141">Os nomes de domínio e a ordem devem ser **os mesmos** em sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-142">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-143">Nome do site</span><span class="sxs-lookup"><span data-stu-id="b8a6f-143">Site name</span></span>  <br/> |<span data-ttu-id="b8a6f-144">**Mesmo** Nome do Site entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-145">**Diferente** Nome do Site nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-146">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-146">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-147">Nomes de servidor</span><span class="sxs-lookup"><span data-stu-id="b8a6f-147">Server names</span></span>  <br/> |<span data-ttu-id="b8a6f-148">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-149">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-150">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-150">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-151">FQDNs do pool interno</span><span class="sxs-lookup"><span data-stu-id="b8a6f-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="b8a6f-152">**Mesmo** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-153">**Mesmo** em sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-154">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-154">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-155">IPs internos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="b8a6f-156">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-157">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-158">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-158">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-159">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="b8a6f-159">External FQDN</span></span>  <br/> |<span data-ttu-id="b8a6f-160">**Mesmo** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-161">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-162">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-162">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-163">IPs externos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-163">External IPs</span></span>  <br/> |<span data-ttu-id="b8a6f-164">**Diferentes** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-165">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-166">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-166">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-167">Configurações de GW PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="b8a6f-168">**Mesmo** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8a6f-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="b8a6f-169">**Diferente** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="b8a6f-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="b8a6f-170">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-170">Configure</span></span>  <br/> |<span data-ttu-id="b8a6f-171">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="b8a6f-171">DNS record</span></span>  <br/> |<span data-ttu-id="b8a6f-172">Adicionar registros com os **mesmos** FQDNs de Acesso Externo e **endereços** IP diferentes</span><span class="sxs-lookup"><span data-stu-id="b8a6f-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="b8a6f-173">Adicionar registros  com FQDNs de Acesso Externo diferentes e **endereços** IP diferentes</span><span class="sxs-lookup"><span data-stu-id="b8a6f-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="b8a6f-174">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-174">Setup</span></span>  <br/> |<span data-ttu-id="b8a6f-175">Locatário híbrido</span><span class="sxs-lookup"><span data-stu-id="b8a6f-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="b8a6f-176">Definir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="b8a6f-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="b8a6f-177">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="b8a6f-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="b8a6f-178">Definir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="b8a6f-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="b8a6f-179">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="b8a6f-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="b8a6f-180">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-180">Setup</span></span>  <br/> |<span data-ttu-id="b8a6f-181">Gateway</span><span class="sxs-lookup"><span data-stu-id="b8a6f-181">Gateway</span></span>  <br/> |<span data-ttu-id="b8a6f-182">Mapeamento MS GW **M:N** neste site</span><span class="sxs-lookup"><span data-stu-id="b8a6f-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="b8a6f-183">Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site</span><span class="sxs-lookup"><span data-stu-id="b8a6f-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="b8a6f-184">Configurar</span><span class="sxs-lookup"><span data-stu-id="b8a6f-184">Setup</span></span>  <br/> |<span data-ttu-id="b8a6f-185">Usuário</span><span class="sxs-lookup"><span data-stu-id="b8a6f-185">User</span></span>  <br/> |<span data-ttu-id="b8a6f-186">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="b8a6f-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="b8a6f-187">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="b8a6f-187">Set UserPSTNSettings</span></span>  <br/> |
   

