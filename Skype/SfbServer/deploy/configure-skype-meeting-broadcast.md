---
title: Configurar sua implantação local para a Transmissão de Reunião do Skype
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
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Resumo: saiba mais sobre as etapas que você precisa executar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida local do Skype for Business Server.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820701"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="1dfcb-103">Configurar sua implantação local para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="1dfcb-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="1dfcb-104">**Resumo:** Saiba mais sobre as etapas que você precisa realizar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="1dfcb-105">A Transmissão de Reunião do Skype é um serviço online que faz parte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="1dfcb-106">Se você estiver executando o Skype for Business Server local e quiser usar a Transmissão de Reunião do Skype em seu ambiente, será necessário seguir as etapas de configuração neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="1dfcb-107">Antes de começar, seu ambiente precisa ser configurado para híbrido com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="1dfcb-108">Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business [Online.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="1dfcb-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="1dfcb-109">Configurar seu ambiente híbrido para a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="1dfcb-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="1dfcb-110">Você precisará fazer o seguinte para preparar seu ambiente para a Transmissão de Reunião do Skype:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="1dfcb-111">Configurar federação com recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1dfcb-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="1dfcb-112">Configurar domínios sip federados</span><span class="sxs-lookup"><span data-stu-id="1dfcb-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="1dfcb-113">Configurar federação com recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1dfcb-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="1dfcb-114">Para habilitar a federação com os recursos do Skype for Business Online, você precisa configurar o Acesso Externo para um Provedor Federado SIP.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="1dfcb-115">Para fazer isso usando o Painel de Controle do Skype for Business Server, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="1dfcb-116">Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="1dfcb-117">Selecione **Provedores Federados SIP e** clique em **Novo.**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="1dfcb-118">Configure o novo provedor com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="1dfcb-119">**Habilita as comunicações com este provedor:**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="1dfcb-120">Selecionado</span><span class="sxs-lookup"><span data-stu-id="1dfcb-120">Selected</span></span>  <br/> |
|<span data-ttu-id="1dfcb-121">**Nome do provedor:**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="1dfcb-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="1dfcb-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="1dfcb-123">**Serviço de Borda de Acesso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="1dfcb-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dfcb-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="1dfcb-125">**Nível de verificação padrão:**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="1dfcb-126">Permitir que os usuários se comuniquem com todos que usam esse provedor.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="1dfcb-127">Você também pode habilitar a federação com recursos do Skype for Business Online executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="1dfcb-128">Configurar domínios sip federados</span><span class="sxs-lookup"><span data-stu-id="1dfcb-128">Configure SIP federated domains</span></span>

<span data-ttu-id="1dfcb-129">Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="1dfcb-130">Repita essas etapas para cada um dos domínios listados, criando 4 novos domínios SIP federados.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="1dfcb-131">Esses domínios incluem os data centers regionais usados no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="1dfcb-132">Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="1dfcb-133">Selecione **Domínios Federados SIP e** clique em **Novo.**</span><span class="sxs-lookup"><span data-stu-id="1dfcb-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="1dfcb-134">Para o **nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="1dfcb-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dfcb-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="1dfcb-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dfcb-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="1dfcb-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dfcb-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="1dfcb-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="1dfcb-138">resources.lync.com</span></span>
    
<span data-ttu-id="1dfcb-139">Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="1dfcb-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="1dfcb-140">Depois de concluir essas etapas de configuração, você poderá começar a usar a Transmissão de Reunião do Skype em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="1dfcb-141">Para obter mais informações sobre a Transmissão de Reunião do Skype, consulte O que é uma Transmissão de Reunião do [Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e o Guia de Administração de Transmissão de Reunião [do Skype.](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="1dfcb-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

