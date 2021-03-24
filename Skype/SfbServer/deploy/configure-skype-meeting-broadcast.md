---
title: Configurar sua implantação local para Transmissão de Reunião do Skype
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
description: 'Resumo: saiba mais sobre as etapas que você precisa executar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida do Skype for Business Server local.'
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103687"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="9aa82-103">Configurar sua implantação local para Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="9aa82-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="9aa82-104">**Resumo:** Saiba mais sobre as etapas que você precisa executar para configurar a Transmissão de Reunião do Skype para sua implantação híbrida local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9aa82-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="9aa82-105">Transmissão de Reunião do Skype é um serviço online que faz parte do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9aa82-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="9aa82-106">Se você estiver executando o Skype for Business Server local e quiser usar a Transmissão de Reunião do Skype em seu ambiente, você precisará seguir as etapas de configuração neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9aa82-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="9aa82-107">Antes de começar, seu ambiente precisa ser configurado para híbrido com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9aa82-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="9aa82-108">Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="9aa82-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="9aa82-109">Configurar seu ambiente híbrido para Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="9aa82-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="9aa82-110">Você precisará fazer o seguinte para preparar seu ambiente para Transmissão de Reunião do Skype:</span><span class="sxs-lookup"><span data-stu-id="9aa82-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="9aa82-111">Configurar federação com recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9aa82-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="9aa82-112">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="9aa82-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="9aa82-113">Configurar federação com recursos do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9aa82-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="9aa82-114">Para habilitar a federação com recursos do Skype for Business Online, você precisa configurar o Acesso Externo para um Provedor Federado SIP.</span><span class="sxs-lookup"><span data-stu-id="9aa82-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="9aa82-115">Para fazer isso usando o Painel de Controle do Skype for Business Server, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9aa82-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="9aa82-116">Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="9aa82-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="9aa82-117">Selecione **Provedores Federados SIP e** clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9aa82-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="9aa82-118">Configure o novo provedor com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="9aa82-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="9aa82-119">**Habilitar comunicações com este provedor:**</span><span class="sxs-lookup"><span data-stu-id="9aa82-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="9aa82-120">Selecionado</span><span class="sxs-lookup"><span data-stu-id="9aa82-120">Selected</span></span>  <br/> |
|<span data-ttu-id="9aa82-121">**Nome do provedor:**</span><span class="sxs-lookup"><span data-stu-id="9aa82-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="9aa82-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="9aa82-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="9aa82-123">**Serviço de Borda de Acesso (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="9aa82-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="9aa82-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="9aa82-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="9aa82-125">**Nível de verificação padrão:**</span><span class="sxs-lookup"><span data-stu-id="9aa82-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="9aa82-126">Permitir que os usuários se comuniquem com todos que usam esse provedor.</span><span class="sxs-lookup"><span data-stu-id="9aa82-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="9aa82-127">Você também pode habilitar a federação com recursos do Skype for Business Online executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="9aa82-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="9aa82-128">Configurar domínios federados SIP</span><span class="sxs-lookup"><span data-stu-id="9aa82-128">Configure SIP federated domains</span></span>

<span data-ttu-id="9aa82-129">Em seguida, você precisa adicionar domínios federados SIP à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="9aa82-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="9aa82-130">Repita estas etapas para cada um dos domínios listados, criando 4 novos domínios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="9aa82-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="9aa82-131">Esses domínios incluem os data centers regionais usados no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9aa82-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="9aa82-132">Inicie o Painel de Controle do Skype for Business Server e selecione **Acesso Externo** à esquerda.</span><span class="sxs-lookup"><span data-stu-id="9aa82-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="9aa82-133">Selecione **Domínios Federados SIP** e clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9aa82-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="9aa82-134">Para o **nome de domínio (ou FQDN):**, insira o domínio, repetindo este procedimento para cada um dos seguintes domínios:</span><span class="sxs-lookup"><span data-stu-id="9aa82-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="9aa82-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="9aa82-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="9aa82-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="9aa82-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="9aa82-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="9aa82-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="9aa82-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="9aa82-138">resources.lync.com</span></span>
    
<span data-ttu-id="9aa82-139">Você também pode configurar o acesso externo para domínios federados SIP executando os seguintes cmdlets no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="9aa82-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="9aa82-140">Depois de concluir essas etapas de configuração, você pode começar a usar a Transmissão de Reunião do Skype em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9aa82-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="9aa82-141">Para obter mais informações sobre Transmissão de Reunião do Skype, consulte O que é uma Transmissão de Reunião do [Skype?](https://go.microsoft.com/fwlink/?LinkId=617071) e Guia de Administração de Transmissão de Reunião do [Skype.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="9aa82-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).</span></span>
