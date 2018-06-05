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
description: 'Resumo: Saiba mais sobre as etapas que necessárias para executar para configurar a transmissão do Skype reunião para o seu Skype local para implantação híbrida do Business Server.'
ms.openlocfilehash: da34ecdf1a83ffb0b2e259756d9124af8e628b9f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568403"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="879fa-103">Configurar sua implantação local para Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="879fa-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="879fa-104">**Resumo:** Saiba mais sobre as etapas que necessárias para executar para configurar a transmissão do Skype reunião para o seu Skype local para implantação híbrida do Business Server.</span><span class="sxs-lookup"><span data-stu-id="879fa-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="879fa-105">Transmissão do Skype reunião é um serviço online que faz parte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="879fa-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="879fa-106">Se você estiver executando o Skype para Business Server local e deseja usar a transmissão do Skype reunião em seu ambiente, você precisará siga as etapas de configuração neste tópico.</span><span class="sxs-lookup"><span data-stu-id="879fa-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="879fa-107">Antes de começar, seu ambiente deve ser configurado para o híbrido com Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="879fa-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="879fa-108">Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a [conectividade híbrida de Deploy entre Skype para Business Server e do Skype para negócios Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="879fa-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="879fa-109">Configurar seu ambiente híbrido para transmissão de reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="879fa-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="879fa-110">Você precisará fazer o seguinte para preparar seu ambiente para transmissão do Skype reunião:</span><span class="sxs-lookup"><span data-stu-id="879fa-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="879fa-111">Configure a federação do Skype para recursos corporativos Online</span><span class="sxs-lookup"><span data-stu-id="879fa-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="879fa-112">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="879fa-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="879fa-113">Configure a federação do Skype para recursos corporativos Online</span><span class="sxs-lookup"><span data-stu-id="879fa-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="879fa-114">Para habilitar a federação com Skype para recursos corporativos Online, você precisará configurar acesso externo para um provedor federado SIP.</span><span class="sxs-lookup"><span data-stu-id="879fa-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="879fa-115">Para fazer isso usando o Skype para o painel de controle do Business Server siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="879fa-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="879fa-116">Inicie o Skype para painel de controle do Business Server e selecione **Acesso externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="879fa-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="879fa-117">Selecione **Provedores federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="879fa-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="879fa-118">Configure o novo provedor da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="879fa-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="879fa-119">**Habilite comunicações com este provedor:**</span><span class="sxs-lookup"><span data-stu-id="879fa-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="879fa-120">Selecionado</span><span class="sxs-lookup"><span data-stu-id="879fa-120">Selected</span></span>  <br/> |
|<span data-ttu-id="879fa-121">**Nome do provedor:**</span><span class="sxs-lookup"><span data-stu-id="879fa-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="879fa-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="879fa-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="879fa-123">**Serviço de Borda de Acesso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="879fa-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="879fa-124">sipfed.Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="879fa-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="879fa-125">**Nível de verificação padrão:**</span><span class="sxs-lookup"><span data-stu-id="879fa-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="879fa-126">Permitir que os usuários se comuniquem com todos que usam este provedor.</span><span class="sxs-lookup"><span data-stu-id="879fa-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="879fa-127">Você também pode habilitar a federação com Skype para recursos corporativos Online executando o seguinte cmdlet no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="879fa-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="879fa-128">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="879fa-128">Configure SIP federated domains</span></span>

<span data-ttu-id="879fa-129">Em seguida, você precisará adicionar domínios SIP federados à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="879fa-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="879fa-130">Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="879fa-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="879fa-131">Incluem esses domínios são para os dados regionais centrais usado no Skype do Business Online.</span><span class="sxs-lookup"><span data-stu-id="879fa-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="879fa-132">Inicie o Skype para painel de controle do Business Server e selecione **Acesso externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="879fa-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="879fa-133">Selecione **Domínios Federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="879fa-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="879fa-134">Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="879fa-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
  - <span data-ttu-id="879fa-135">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="879fa-135">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="879fa-136">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="879fa-136">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="879fa-137">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="879fa-137">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="879fa-138">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="879fa-138">resources.lync.com</span></span>
    
<span data-ttu-id="879fa-139">Você também pode configurar o acesso externo para domínios federados SIP executando os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="879fa-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="879fa-140">Depois de concluir essas etapas de configuração pode começar a usar a transmissão do Skype reunião em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="879fa-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="879fa-141">Para obter mais informações sobre a transmissão do Skype reunião, consulte [o que é uma transmissão do Skype reunião?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guia de Admin de transmissão do Skype reunião](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="879fa-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

