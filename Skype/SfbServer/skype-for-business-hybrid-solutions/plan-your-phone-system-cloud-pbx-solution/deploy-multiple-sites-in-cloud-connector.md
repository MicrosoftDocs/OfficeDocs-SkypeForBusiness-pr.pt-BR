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
description: Saiba mais sobre a implantação de vários sites PSTN no Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358917"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="5cda1-103">Implantar vários sites no Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="5cda1-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="5cda1-104">O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="5cda1-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="5cda1-105">Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="5cda1-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="5cda1-106">Saiba mais sobre a implantação de vários sites PSTN no Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="5cda1-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="5cda1-107">Esta seção descreve como implantar vários sites PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="5cda1-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="5cda1-108">Os sites são implantados um por vez usando as mesmas etapas que a implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="5cda1-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="5cda1-109">Este tópico descreve as considerações e as diferenças entre sites em uma implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="5cda1-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="5cda1-110">Vários sites PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="5cda1-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="5cda1-111">Veja a seguir um exemplo de configuração para implantar o Skype for Business Cloud Connector Edition para diferentes sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cda1-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="5cda1-112">Verifique se as definições de configuração estão corretas antes de iniciar uma implantação.</span><span class="sxs-lookup"><span data-stu-id="5cda1-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="5cda1-113">Site PSTN 1</span><span class="sxs-lookup"><span data-stu-id="5cda1-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="5cda1-114">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="5cda1-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="5cda1-115">Para cada site PSTN que você deseja adicionar, siga as etapas em [implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5cda1-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5cda1-116">A pasta compartilhada para preparação de alta disponibilidade (HA) é por site PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cda1-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="5cda1-117">A pasta compartilhada **deve** ser diferente entre os sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cda1-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="5cda1-118">Não use a mesma pasta compartilhada para vários sites. ></span><span class="sxs-lookup"><span data-stu-id="5cda1-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="5cda1-119">Único site com alta disponibilidade (HA) comparado a implantações de vários sites</span><span class="sxs-lookup"><span data-stu-id="5cda1-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="5cda1-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="5cda1-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="5cda1-121">A tabela a seguir lista as diferenças entre um único site com suporte para alta disponibilidade e uma implantação de vários sites.</span><span class="sxs-lookup"><span data-stu-id="5cda1-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="5cda1-122">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="5cda1-122">**Category**</span></span>|<span data-ttu-id="5cda1-123">**Item**</span><span class="sxs-lookup"><span data-stu-id="5cda1-123">**Item**</span></span>|<span data-ttu-id="5cda1-124">**Único site com alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="5cda1-124">**Single-Site with HA**</span></span>|<span data-ttu-id="5cda1-125">**Vários sites**</span><span class="sxs-lookup"><span data-stu-id="5cda1-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5cda1-126">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-126">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-127">Nome do host do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5cda1-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="5cda1-128">**Diferentes** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-129">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-130">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-130">Setup</span></span>  <br/> |<span data-ttu-id="5cda1-131">Pasta compartilhada</span><span class="sxs-lookup"><span data-stu-id="5cda1-131">Shared folder</span></span>  <br/> |<span data-ttu-id="5cda1-132">Requer a **mesma** pasta compartilhada entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="5cda1-133">Requer uma pasta compartilhada **diferente** entre dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="5cda1-134">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-134">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="5cda1-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="5cda1-136">Requer o **mesmo** domínio nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="5cda1-137">Requer o **mesmo** domínio nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-138">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-138">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="5cda1-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="5cda1-140">Os nomes de domínio e a ordem devem ser os **mesmos** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-141">Os nomes de domínio e a ordem devem ser os **mesmos** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-142">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-142">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-143">Nome do site</span><span class="sxs-lookup"><span data-stu-id="5cda1-143">Site name</span></span>  <br/> |<span data-ttu-id="5cda1-144">**Mesmo** Nome do site nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="5cda1-145">**Diferentes** Nome do site nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-146">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-146">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-147">Nomes de servidor</span><span class="sxs-lookup"><span data-stu-id="5cda1-147">Server names</span></span>  <br/> |<span data-ttu-id="5cda1-148">**Diferentes** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-149">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-150">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-150">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-151">FQDNs do pool interno</span><span class="sxs-lookup"><span data-stu-id="5cda1-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="5cda1-152">**Mesmo** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-153">**Mesmo** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-154">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-154">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-155">IPs internos</span><span class="sxs-lookup"><span data-stu-id="5cda1-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="5cda1-156">**Diferentes** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-157">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-158">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-158">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-159">FQDN externo</span><span class="sxs-lookup"><span data-stu-id="5cda1-159">External FQDN</span></span>  <br/> |<span data-ttu-id="5cda1-160">**Mesmo** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-161">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-162">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-162">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-163">IPs externos</span><span class="sxs-lookup"><span data-stu-id="5cda1-163">External IPs</span></span>  <br/> |<span data-ttu-id="5cda1-164">**Diferentes** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-165">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-166">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-166">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-167">Configurações de GW PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="5cda1-168">**Mesmo** nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cda1-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="5cda1-169">**Diferentes** nos sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5cda1-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="5cda1-170">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-170">Configure</span></span>  <br/> |<span data-ttu-id="5cda1-171">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="5cda1-171">DNS record</span></span>  <br/> |<span data-ttu-id="5cda1-172">Adicionar registros com os **mesmos** FQDNs de acesso externo e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="5cda1-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="5cda1-173">Adicionar registros com FQDNs de acesso externo **diferentes** e endereços IP **diferentes**</span><span class="sxs-lookup"><span data-stu-id="5cda1-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="5cda1-174">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-174">Setup</span></span>  <br/> |<span data-ttu-id="5cda1-175">Locatário híbrido</span><span class="sxs-lookup"><span data-stu-id="5cda1-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="5cda1-176">Definir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="5cda1-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="5cda1-177">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="5cda1-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="5cda1-178">Definir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="5cda1-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="5cda1-179">Definir PeerDestination para fallback</span><span class="sxs-lookup"><span data-stu-id="5cda1-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="5cda1-180">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-180">Setup</span></span>  <br/> |<span data-ttu-id="5cda1-181">Gateway</span><span class="sxs-lookup"><span data-stu-id="5cda1-181">Gateway</span></span>  <br/> |<span data-ttu-id="5cda1-182">Mapeamento **M:N** do MS GW neste site</span><span class="sxs-lookup"><span data-stu-id="5cda1-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="5cda1-183">Os gateways PSTN em cada site PSTN devem se conectar apenas ao (s) servidor (es) de mediação no mesmo site</span><span class="sxs-lookup"><span data-stu-id="5cda1-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="5cda1-184">Configurar</span><span class="sxs-lookup"><span data-stu-id="5cda1-184">Setup</span></span>  <br/> |<span data-ttu-id="5cda1-185">User</span><span class="sxs-lookup"><span data-stu-id="5cda1-185">User</span></span>  <br/> |<span data-ttu-id="5cda1-186">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="5cda1-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="5cda1-187">Definir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="5cda1-187">Set UserPSTNSettings</span></span>  <br/> |
   

