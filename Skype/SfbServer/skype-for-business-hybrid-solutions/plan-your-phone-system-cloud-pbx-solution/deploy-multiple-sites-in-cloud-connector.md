---
title: Implantar vários sites no Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Saiba como implantar vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: c0e41408b43574fdfd3e8dc6b1d2c8ffc434d8c5
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569523"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="0837f-103">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="0837f-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="0837f-104">Saiba como implantar vários sites PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="0837f-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="0837f-p101">Esta seção descreve como implantar vários sites PSTN (Rede Telefônica Pública Comutada). Os sites são implantados um de cada vez, usando o procedimento de implantação de um único site. Este tópico apresenta considerações e as diferenças entre os sites em uma implantação de vários sites. </span><span class="sxs-lookup"><span data-stu-id="0837f-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="0837f-108">Vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="0837f-109">O exemplo a seguir mostra um exemplo de configuração para implantar Skype para Business Edition do conector de nuvem para diferentes sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="0837f-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="0837f-110">Antes de iniciar a implantação, verifique se a configuração está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="0837f-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="0837f-111">Site PSTN 1</span><span class="sxs-lookup"><span data-stu-id="0837f-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="0837f-112">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="0837f-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="0837f-113">Para cada site PSTN que você deseja adicionar, siga as etapas em [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="0837f-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0837f-114">A pasta compartilhada para a preparação de alta disponibilidade refere-se a cada site PSTN.</span><span class="sxs-lookup"><span data-stu-id="0837f-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="0837f-115">As pastas compartilhadas dos sites PSTN **devem** ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="0837f-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="0837f-116">Não use a mesma pasta compartilhada para vários sites. ></span><span class="sxs-lookup"><span data-stu-id="0837f-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="0837f-117">Site único com alta disponibilidade comparado a implantações de vários sites</span><span class="sxs-lookup"><span data-stu-id="0837f-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="0837f-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="0837f-118"></span></span>

<span data-ttu-id="0837f-119">A tabela a seguir lista as diferenças entre a implantação de um único site com suporte para alta disponibilidade e a implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="0837f-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="0837f-120">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="0837f-120">**Category**</span></span>|<span data-ttu-id="0837f-121">**Item**</span><span class="sxs-lookup"><span data-stu-id="0837f-121">**Item**</span></span>|<span data-ttu-id="0837f-122">**Site único com alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="0837f-122">**Single-Site with HA**</span></span>|<span data-ttu-id="0837f-123">**Vários locais**</span><span class="sxs-lookup"><span data-stu-id="0837f-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0837f-124">Instalação</span><span class="sxs-lookup"><span data-stu-id="0837f-124">Setup</span></span>  <br/> |<span data-ttu-id="0837f-125">Pasta compartilhada</span><span class="sxs-lookup"><span data-stu-id="0837f-125">Shared folder</span></span>  <br/> |<span data-ttu-id="0837f-126">Requer a **mesma** pasta compartilhada entre appliances</span><span class="sxs-lookup"><span data-stu-id="0837f-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="0837f-127">Requer uma pasta compartilhada **diferente** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="0837f-128">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-128">Configure</span></span>  <br/> |<span data-ttu-id="0837f-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="0837f-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="0837f-130">Requer o **mesmo** domínio nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="0837f-131">Requer o **mesmo** domínio nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-132">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-132">Configure</span></span>  <br/> |<span data-ttu-id="0837f-133">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="0837f-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="0837f-134">Ordem e nomes de domínio devem ser o **mesmo** em aparelhos</span><span class="sxs-lookup"><span data-stu-id="0837f-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="0837f-135">Ordem e nomes de domínio devem ser o **mesmo** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-136">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-136">Configure</span></span>  <br/> |<span data-ttu-id="0837f-137">Nome do site</span><span class="sxs-lookup"><span data-stu-id="0837f-137">Site name</span></span>  <br/> |<span data-ttu-id="0837f-138">Nome do Site **igual** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="0837f-139">Nome do Site **diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-140">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-140">Configure</span></span>  <br/> |<span data-ttu-id="0837f-141">Nomes de servidor</span><span class="sxs-lookup"><span data-stu-id="0837f-141">Server names</span></span>  <br/> |<span data-ttu-id="0837f-142">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="0837f-143">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-144">Configure</span></span>  <br/> |<span data-ttu-id="0837f-145">FQDNs de pool interno</span><span class="sxs-lookup"><span data-stu-id="0837f-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="0837f-146">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="0837f-147">**Igual** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-148">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-148">Configure</span></span>  <br/> |<span data-ttu-id="0837f-149">IPs internos</span><span class="sxs-lookup"><span data-stu-id="0837f-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="0837f-150">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="0837f-151">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-152">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-152">Configure</span></span>  <br/> |<span data-ttu-id="0837f-153">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="0837f-153">External FQDN</span></span>  <br/> |<span data-ttu-id="0837f-154">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="0837f-155">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-156">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-156">Configure</span></span>  <br/> |<span data-ttu-id="0837f-157">IPs externos</span><span class="sxs-lookup"><span data-stu-id="0837f-157">External IPs</span></span>  <br/> |<span data-ttu-id="0837f-158">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="0837f-159">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-160">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-160">Configure</span></span>  <br/> |<span data-ttu-id="0837f-161">Configurações de Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="0837f-162">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="0837f-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="0837f-163">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="0837f-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="0837f-164">Configuração</span><span class="sxs-lookup"><span data-stu-id="0837f-164">Configure</span></span>  <br/> |<span data-ttu-id="0837f-165">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="0837f-165">DNS record</span></span>  <br/> |<span data-ttu-id="0837f-166">Adicionar registros com o **mesmo** FQDNs de acesso externo e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="0837f-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="0837f-167">Adicionar registros com FQDNs de Acesso Externo **diferentes** e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="0837f-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="0837f-168">Instalação</span><span class="sxs-lookup"><span data-stu-id="0837f-168">Setup</span></span>  <br/> |<span data-ttu-id="0837f-169">Locatário híbrida</span><span class="sxs-lookup"><span data-stu-id="0837f-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="0837f-170">Definir HybridPstnSite</span><span class="sxs-lookup"><span data-stu-id="0837f-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="0837f-171">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="0837f-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="0837f-172">Definir HybridPstnSite</span><span class="sxs-lookup"><span data-stu-id="0837f-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="0837f-173">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="0837f-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="0837f-174">Instalação</span><span class="sxs-lookup"><span data-stu-id="0837f-174">Setup</span></span>  <br/> |<span data-ttu-id="0837f-175">Gateway</span><span class="sxs-lookup"><span data-stu-id="0837f-175">Gateway</span></span>  <br/> |<span data-ttu-id="0837f-176">Mapeamento de **M:N** do MS GW neste site</span><span class="sxs-lookup"><span data-stu-id="0837f-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="0837f-177">Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site</span><span class="sxs-lookup"><span data-stu-id="0837f-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="0837f-178">Instalação</span><span class="sxs-lookup"><span data-stu-id="0837f-178">Setup</span></span>  <br/> |<span data-ttu-id="0837f-179">Usuário</span><span class="sxs-lookup"><span data-stu-id="0837f-179">User</span></span>  <br/> |<span data-ttu-id="0837f-180">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="0837f-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="0837f-181">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="0837f-181">Set UserPSTNSettings</span></span>  <br/> |
   

