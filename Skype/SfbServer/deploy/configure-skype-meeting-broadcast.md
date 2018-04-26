---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: conheça as etapas que você precisa realizar para configurar a  na sua implantação híbrida local do .'
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="64d3f-103">Configurar sua implantação local para Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="64d3f-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="64d3f-104">Resumo: conheça as etapas que você precisa realizar para configurar a  na sua implantação híbrida local do .</span><span class="sxs-lookup"><span data-stu-id="64d3f-104">Summary: Learn about the steps you need to perform to configure  for your on-premises  hybrid deployment.</span></span>
  
<span data-ttu-id="64d3f-105">A  é um serviço online que faz parte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="64d3f-105"> is an online service that is part of Office 365.</span></span> <span data-ttu-id="64d3f-106">Se você estiver executando o  no local e quiser usar a  no seu ambiente, precisará seguir as etapas de configuração neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64d3f-106">If you are running  on-premises and want to use   in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="64d3f-107">Antes de começar, seu ambiente precisa ser configurado como híbrido no .</span><span class="sxs-lookup"><span data-stu-id="64d3f-107">Before you begin, your environment needs to be configured for hybrid with .</span></span> <span data-ttu-id="64d3f-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="64d3f-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="64d3f-109">Configurar sua implantação local para Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="64d3f-109">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="64d3f-110">É necessário fazer o seguinte para preparar seu ambiente para a :</span><span class="sxs-lookup"><span data-stu-id="64d3f-110">You'll need to do the following to prepare  your environment for :</span></span>
  
- <span data-ttu-id="64d3f-111">Configurar federação com o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="64d3f-111">Configure federation with Skype for Business Online</span></span>
    
- <span data-ttu-id="64d3f-112">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="64d3f-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="64d3f-113">Configurar federação com o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="64d3f-113">Configure federation with Skype for Business Online</span></span>

<span data-ttu-id="64d3f-114">Para habilitar a federação com recursos do , é necessário configurar Acesso Externo para um Provedor federado SIP.</span><span class="sxs-lookup"><span data-stu-id="64d3f-114">To enable federation with  resources, you need to configure  External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="64d3f-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span><span class="sxs-lookup"><span data-stu-id="64d3f-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="64d3f-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span><span class="sxs-lookup"><span data-stu-id="64d3f-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="64d3f-117">Selecione **Provedores federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="64d3f-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="64d3f-118">Configure o novo provedor da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="64d3f-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="64d3f-119">**Habilitar comunicações com este provedor: **</span><span class="sxs-lookup"><span data-stu-id="64d3f-119">**Enable communications with this provider: **</span></span> <br/> |<span data-ttu-id="64d3f-120">Selecionado</span><span class="sxs-lookup"><span data-stu-id="64d3f-120">Selected</span></span>  <br/> |
|<span data-ttu-id="64d3f-121">**Nome do provedor:**</span><span class="sxs-lookup"><span data-stu-id="64d3f-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="64d3f-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="64d3f-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="64d3f-123">**Serviço de Borda de Acesso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="64d3f-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="64d3f-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="64d3f-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="64d3f-125">**Nível de verificação padrão:**</span><span class="sxs-lookup"><span data-stu-id="64d3f-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="64d3f-126">Permitir que os usuários se comuniquem com todos que usam este provedor.</span><span class="sxs-lookup"><span data-stu-id="64d3f-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="64d3f-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="64d3f-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="64d3f-128">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="64d3f-128">Configure SIP federated domains</span></span>

<span data-ttu-id="64d3f-129">Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="64d3f-129">Next, you need to  add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="64d3f-130">Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="64d3f-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="64d3f-131">Esses domínios são para os data centers regionais usados no .</span><span class="sxs-lookup"><span data-stu-id="64d3f-131">These domains include are for the regional data centers used in .</span></span>
  
1. <span data-ttu-id="64d3f-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span><span class="sxs-lookup"><span data-stu-id="64d3f-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="64d3f-133">Selecione **Domínios Federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="64d3f-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="64d3f-134">Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="64d3f-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="64d3f-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="64d3f-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="64d3f-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="64d3f-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="64d3f-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="64d3f-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="64d3f-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="64d3f-138">resources.lync.com</span></span>
    
<span data-ttu-id="64d3f-139">Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no :</span><span class="sxs-lookup"><span data-stu-id="64d3f-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the :</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="64d3f-140">Depois de concluir essas etapas de configuração, você pode começar a usar a Transmissão de Reunião do Skype em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="64d3f-140">Once you've completed these configuration steps, you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="64d3f-141">Para mais informações sobre a Transmissão de Reunião do Skype, consulte [O que é uma Transmissão de Reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071).</span><span class="sxs-lookup"><span data-stu-id="64d3f-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071).</span></span>
  

