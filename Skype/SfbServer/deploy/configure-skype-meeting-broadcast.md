---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: Saiba mais sobre as etapas que você precisa executar para configurar a transmissão de reunião do Skype para sua implantação híbrida do Skype for Business Server local.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002801"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="3222f-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="3222f-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="3222f-104">**Resumo:** Saiba mais sobre as etapas que você precisa executar para configurar a transmissão de reunião do Skype para sua implantação híbrida local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3222f-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="3222f-105">A transmissão de reunião do Skype é um serviço online que faz parte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3222f-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="3222f-106">Se você estiver executando o Skype for Business Server no local e quiser usar a transmissão de reunião do Skype no seu ambiente, será necessário seguir as etapas de configuração deste tópico.</span><span class="sxs-lookup"><span data-stu-id="3222f-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="3222f-107">Antes de começar, o ambiente precisa estar configurado para híbrido com o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3222f-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="3222f-108">Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3222f-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="3222f-109">Configurar seu ambiente híbrido para a transmissão de reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="3222f-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="3222f-110">Você precisará fazer o seguinte para preparar seu ambiente para a transmissão de reunião do Skype:</span><span class="sxs-lookup"><span data-stu-id="3222f-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="3222f-111">Configurar a Federação com os recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3222f-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="3222f-112">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="3222f-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="3222f-113">Configurar a Federação com os recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3222f-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="3222f-114">Para habilitar a Federação com os recursos do Skype for Business Online, você precisa configurar o acesso externo para um provedor de federado SIP.</span><span class="sxs-lookup"><span data-stu-id="3222f-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="3222f-115">Para fazer isso usando o painel de controle do Skype for Business Server, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3222f-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="3222f-116">Inicie o painel de controle do Skype for Business Server e selecione **acesso externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="3222f-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3222f-117">Selecione **Provedores federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3222f-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="3222f-118">Configure o novo provedor da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3222f-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="3222f-119">**Habilitar comunicações com este provedor:**</span><span class="sxs-lookup"><span data-stu-id="3222f-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="3222f-120">Selecionado</span><span class="sxs-lookup"><span data-stu-id="3222f-120">Selected</span></span>  <br/> |
|<span data-ttu-id="3222f-121">**Nome do provedor:**</span><span class="sxs-lookup"><span data-stu-id="3222f-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="3222f-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="3222f-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="3222f-123">**Serviço de Borda de Acesso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="3222f-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="3222f-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3222f-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="3222f-125">**Nível de verificação padrão:**</span><span class="sxs-lookup"><span data-stu-id="3222f-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="3222f-126">Permitir que os usuários se comuniquem com todos que usam este provedor.</span><span class="sxs-lookup"><span data-stu-id="3222f-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="3222f-127">Você também pode habilitar a Federação com os recursos do Skype for Business online executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="3222f-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="3222f-128">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="3222f-128">Configure SIP federated domains</span></span>

<span data-ttu-id="3222f-129">Em seguida, você precisa adicionar domínios federados do SIP à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="3222f-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="3222f-130">Repita essas etapas para cada um dos quatro domínios listados, criando quatro novos domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="3222f-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="3222f-131">Esses domínios são para os centros de dados regionais usados no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3222f-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="3222f-132">Inicie o painel de controle do Skype for Business Server e selecione **acesso externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="3222f-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3222f-133">Selecione **Domínios Federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3222f-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="3222f-134">Para o **Nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="3222f-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="3222f-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3222f-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="3222f-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3222f-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="3222f-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3222f-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="3222f-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3222f-138">resources.lync.com</span></span>
    
<span data-ttu-id="3222f-139">Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="3222f-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="3222f-140">Depois de concluir essas etapas de configuração, você pode começar a usar a transmissão de reunião do Skype na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="3222f-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="3222f-141">Para obter mais informações sobre a transmissão de reunião do Skype, consulte [o que é uma transmissão de reunião do Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guia de administração de transmissão de reunião do Skype](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="3222f-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

