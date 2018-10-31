---
title: Implantar vários sites no Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Saiba como implantar vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: 388915d0ab22dc50378d84a82c01291cfd7c99eb
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851487"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="1186c-103">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1186c-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="1186c-104">Saiba como implantar vários sites PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1186c-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1186c-p101">Esta seção descreve como implantar vários sites PSTN (Rede Telefônica Pública Comutada). Os sites são implantados um de cada vez, usando o procedimento de implantação de um único site. Este tópico apresenta considerações e as diferenças entre os sites em uma implantação de vários sites. </span><span class="sxs-lookup"><span data-stu-id="1186c-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="1186c-108">Vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="1186c-109">O exemplo a seguir mostra um exemplo de configuração para implantar Skype para Business Edition do conector de nuvem para diferentes sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="1186c-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="1186c-110">Antes de iniciar a implantação, verifique se a configuração está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="1186c-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="1186c-111">Site PSTN 1</span><span class="sxs-lookup"><span data-stu-id="1186c-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="1186c-112">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="1186c-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="1186c-113">Para cada site PSTN que você deseja adicionar, siga as etapas em [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1186c-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1186c-114">A pasta compartilhada para a preparação de alta disponibilidade refere-se a cada site PSTN.</span><span class="sxs-lookup"><span data-stu-id="1186c-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="1186c-115">As pastas compartilhadas dos sites PSTN **devem** ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="1186c-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="1186c-116">Não use a mesma pasta compartilhada para vários sites. ></span><span class="sxs-lookup"><span data-stu-id="1186c-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="1186c-117">Site único com alta disponibilidade comparado a implantações de vários sites</span><span class="sxs-lookup"><span data-stu-id="1186c-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="1186c-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="1186c-118"></span></span>

<span data-ttu-id="1186c-119">A tabela a seguir lista as diferenças entre a implantação de um único site com suporte para alta disponibilidade e a implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="1186c-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="1186c-120">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="1186c-120">**Category**</span></span>|<span data-ttu-id="1186c-121">**Item**</span><span class="sxs-lookup"><span data-stu-id="1186c-121">**Item**</span></span>|<span data-ttu-id="1186c-122">**Único site com alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="1186c-122">**Single-Site with HA**</span></span>|<span data-ttu-id="1186c-123">**Vários sites**</span><span class="sxs-lookup"><span data-stu-id="1186c-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1186c-124">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-124">Configure</span></span>  <br/> |<span data-ttu-id="1186c-125">Nome de Host do aparelho</span><span class="sxs-lookup"><span data-stu-id="1186c-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="1186c-126">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1186c-127">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-128">Instalação</span><span class="sxs-lookup"><span data-stu-id="1186c-128">Setup</span></span>  <br/> |<span data-ttu-id="1186c-129">Pasta compartilhada</span><span class="sxs-lookup"><span data-stu-id="1186c-129">Shared folder</span></span>  <br/> |<span data-ttu-id="1186c-130">Requer a **mesma** pasta compartilhada entre appliances</span><span class="sxs-lookup"><span data-stu-id="1186c-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="1186c-131">Requer uma pasta compartilhada **diferente** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="1186c-132">Configuração</span><span class="sxs-lookup"><span data-stu-id="1186c-132">Configure</span></span>  <br/> |<span data-ttu-id="1186c-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="1186c-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="1186c-134">Requer o **mesmo** domínio nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="1186c-135">Requer o **mesmo** domínio nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-136">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-136">Configure</span></span>  <br/> |<span data-ttu-id="1186c-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="1186c-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="1186c-138">Ordem e nomes de domínio devem ser o **mesmo** em aparelhos</span><span class="sxs-lookup"><span data-stu-id="1186c-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="1186c-139">Ordem e nomes de domínio devem ser o **mesmo** entre sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-140">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-140">Configure</span></span>  <br/> |<span data-ttu-id="1186c-141">Nome do site</span><span class="sxs-lookup"><span data-stu-id="1186c-141">Site name</span></span>  <br/> |<span data-ttu-id="1186c-142">Nome do Site **igual** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="1186c-143">Nome do Site **diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-144">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-144">Configure</span></span>  <br/> |<span data-ttu-id="1186c-145">Nomes de servidor</span><span class="sxs-lookup"><span data-stu-id="1186c-145">Server names</span></span>  <br/> |<span data-ttu-id="1186c-146">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1186c-147">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-148">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-148">Configure</span></span>  <br/> |<span data-ttu-id="1186c-149">FQDNs de pool interno</span><span class="sxs-lookup"><span data-stu-id="1186c-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="1186c-150">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1186c-151">**Igual** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-152">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-152">Configure</span></span>  <br/> |<span data-ttu-id="1186c-153">IPs internos</span><span class="sxs-lookup"><span data-stu-id="1186c-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="1186c-154">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1186c-155">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-156">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-156">Configure</span></span>  <br/> |<span data-ttu-id="1186c-157">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="1186c-157">External FQDN</span></span>  <br/> |<span data-ttu-id="1186c-158">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1186c-159">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-160">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-160">Configure</span></span>  <br/> |<span data-ttu-id="1186c-161">IPs externos</span><span class="sxs-lookup"><span data-stu-id="1186c-161">External IPs</span></span>  <br/> |<span data-ttu-id="1186c-162">**Diferentes** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1186c-163">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-164">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-164">Configure</span></span>  <br/> |<span data-ttu-id="1186c-165">Configurações de Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="1186c-166">**Iguais** nos vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="1186c-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1186c-167">**Diferente** nos vários sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1186c-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1186c-168">Configurar</span><span class="sxs-lookup"><span data-stu-id="1186c-168">Configure</span></span>  <br/> |<span data-ttu-id="1186c-169">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="1186c-169">DNS record</span></span>  <br/> |<span data-ttu-id="1186c-170">Adicionar registros com o **mesmo** FQDNs de acesso externo e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="1186c-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="1186c-171">Adicionar registros com FQDNs de Acesso Externo **diferentes** e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="1186c-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="1186c-172">Instalação</span><span class="sxs-lookup"><span data-stu-id="1186c-172">Setup</span></span>  <br/> |<span data-ttu-id="1186c-173">Locatário híbrida</span><span class="sxs-lookup"><span data-stu-id="1186c-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="1186c-174">Definir HybridPstnSite</span><span class="sxs-lookup"><span data-stu-id="1186c-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1186c-175">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="1186c-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="1186c-176">Definir HybridPstnSite</span><span class="sxs-lookup"><span data-stu-id="1186c-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1186c-177">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="1186c-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="1186c-178">Instalação</span><span class="sxs-lookup"><span data-stu-id="1186c-178">Setup</span></span>  <br/> |<span data-ttu-id="1186c-179">Gateway</span><span class="sxs-lookup"><span data-stu-id="1186c-179">Gateway</span></span>  <br/> |<span data-ttu-id="1186c-180">Mapeamento de **M:N** do MS GW neste site</span><span class="sxs-lookup"><span data-stu-id="1186c-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="1186c-181">Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site</span><span class="sxs-lookup"><span data-stu-id="1186c-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="1186c-182">Instalação</span><span class="sxs-lookup"><span data-stu-id="1186c-182">Setup</span></span>  <br/> |<span data-ttu-id="1186c-183">Usuário</span><span class="sxs-lookup"><span data-stu-id="1186c-183">User</span></span>  <br/> |<span data-ttu-id="1186c-184">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1186c-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="1186c-185">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1186c-185">Set UserPSTNSettings</span></span>  <br/> |
   

