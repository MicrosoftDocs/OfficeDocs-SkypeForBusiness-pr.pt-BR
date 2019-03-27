---
title: Ativação e desativação de bypass de mídia
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Skype para painel de controle do servidor de negócios.
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874278"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="a1e04-103">Habilitar e desabilitar bypass de mídia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a1e04-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="a1e04-104">Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="a1e04-105">Habilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="a1e04-105">Enable network media bypass</span></span> 

<span data-ttu-id="a1e04-106">Definições de desvio de mídia são aplicadas globalmente entre um Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a1e04-107">Bypass de mídia permite que as chamadas para ignorar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a1e04-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a1e04-108">Para obter detalhes sobre quando usar o desvio de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a1e04-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="a1e04-109">Você pode habilitar e configurar o desvio de mídia a partir do Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="a1e04-110">Para habilitar e configurar o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="a1e04-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="a1e04-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a1e04-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1e04-112">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a1e04-113">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.</span><span class="sxs-lookup"><span data-stu-id="a1e04-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a1e04-114">Na página **Global** , clique na configuração **Global** .</span><span class="sxs-lookup"><span data-stu-id="a1e04-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a1e04-115">Sempre existe apenas uma configuração, e ele é chamado sempre Global.</span><span class="sxs-lookup"><span data-stu-id="a1e04-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a1e04-116">No menu **Editar** , clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a1e04-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a1e04-117">Na página **Editar configuração Global** , clique na caixa de seleção **Habilitar bypass de mídia** .</span><span class="sxs-lookup"><span data-stu-id="a1e04-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a1e04-118">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a1e04-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="a1e04-119">**Sempre desviar**   Selecione essa opção para executar uma tentativa de mídia desvio de todas as chamadas.</span><span class="sxs-lookup"><span data-stu-id="a1e04-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="a1e04-120">Essa opção estará disponível se o controle de admissão de chamadas (CAC) estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="a1e04-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="a1e04-121">Se o CAC não estiver habilitado, selecione essa opção nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="a1e04-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="a1e04-122">Não há nenhuma necessidade de controle de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="a1e04-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="a1e04-123">Não há nenhuma necessidade de configração minuciosa determinar quando o desvio deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="a1e04-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="a1e04-124">Existe conectividade total entre gateways e clientes.</span><span class="sxs-lookup"><span data-stu-id="a1e04-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="a1e04-125">**Use os sites e configuração de região**   CAC se estiver habilitado, essa opção é selecionada por padrão e não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="a1e04-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="a1e04-126">Quando essa opção é selecionada, regiões e sites de configuração de rede serão usados para determinar quando o desvio de mídia é possível.</span><span class="sxs-lookup"><span data-stu-id="a1e04-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="a1e04-127">Se você selecionar essa opção, você pode optar por habilitar o desvio para sites que não são mapeadas.</span><span class="sxs-lookup"><span data-stu-id="a1e04-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="a1e04-128">Clique na caixa de seleção **Habilitar desvio de mídia para sites não mapeados** somente se você tiver um ou mais sites grandes associados à região mesma que não tem restrições de largura de banda (por exemplo, um grande site central) e também tiver alguns sites de filiais associados a região mesmo que têm restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="a1e04-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="a1e04-129">Quando você habilita os endereços sites não mapeados, a configuração é dinâmico porque você especificar apenas as sub-redes associadas aos sites de filial em vez de precisar especificar todas as sub-redes associadas com todos os sites.</span><span class="sxs-lookup"><span data-stu-id="a1e04-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="a1e04-130">Recomendamos que você não marque a caixa de seleção **Habilitar desvio de mídia para sites não mapeados** se o CAC esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1e04-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="a1e04-131">Clique em **Confirmar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a1e04-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="a1e04-132">Desabilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="a1e04-132">Disable network media bypass</span></span>

<span data-ttu-id="a1e04-133">Definições de desvio de mídia são aplicadas globalmente entre um Skype para implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a1e04-134">Bypass de mídia permite que as chamadas para ignorar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a1e04-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a1e04-135">Para obter detalhes sobre quando usar o desvio de mídia, consulte [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a1e04-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="a1e04-136">Você pode desabilitar o desvio de mídia a partir do Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="a1e04-137">Para desabilitar o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="a1e04-137">To disable media bypass</span></span>

1.  <span data-ttu-id="a1e04-138">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a1e04-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1e04-139">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="a1e04-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a1e04-140">Na barra de navegação à esquerda, clique em **Configuração de rede**e, em seguida, clique em **Global**.</span><span class="sxs-lookup"><span data-stu-id="a1e04-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a1e04-141">Na página **Global** , clique na configuração **Global** .</span><span class="sxs-lookup"><span data-stu-id="a1e04-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a1e04-142">Sempre existe apenas uma configuração, e ele é chamado sempre Global.</span><span class="sxs-lookup"><span data-stu-id="a1e04-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a1e04-143">No menu **Editar** , clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a1e04-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a1e04-144">Na página **Editar configuração Global** , desmarque a caixa de seleção **Habilitar bypass de mídia** .</span><span class="sxs-lookup"><span data-stu-id="a1e04-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a1e04-145">Clique em **Confirmar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a1e04-145">Click **Commit** to save your changes.</span></span>

  
