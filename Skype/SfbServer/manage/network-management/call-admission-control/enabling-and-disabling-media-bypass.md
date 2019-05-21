---
title: Habilitando e desabilitando o bypass de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel de controle do Skype for Business Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279582"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="c56e8-103">Habilitar e desabilitar bypass de mídia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c56e8-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="c56e8-104">Use os procedimentos deste artigo para habilitar ou desabilitar o bypass de mídia usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="c56e8-105">Habilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="c56e8-105">Enable network media bypass</span></span> 

<span data-ttu-id="c56e8-106">As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="c56e8-107">O bypass de mídia permite que as chamadas ignorem o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c56e8-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="c56e8-108">Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejar a bypass de mídia](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="c56e8-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="c56e8-109">Você pode habilitar e configurar o bypass de mídia no painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="c56e8-110">Para habilitar e configurar o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="c56e8-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="c56e8-111">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c56e8-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c56e8-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c56e8-113">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **global**.</span><span class="sxs-lookup"><span data-stu-id="c56e8-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="c56e8-114">Na página **global** , clique em configuração **global** .</span><span class="sxs-lookup"><span data-stu-id="c56e8-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="c56e8-115">Sempre existe apenas uma configuração, e ela é sempre chamada de global.</span><span class="sxs-lookup"><span data-stu-id="c56e8-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="c56e8-116">No menu **Editar** , clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c56e8-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="c56e8-117">Na página **Editar configuração global** , clique na caixa de seleção **habilitar bypass de mídia** .</span><span class="sxs-lookup"><span data-stu-id="c56e8-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="c56e8-118">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c56e8-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="c56e8-119">**Sempre ignorar**   Selecione esta opção para tentar ignorar a mídia em todas as chamadas.</span><span class="sxs-lookup"><span data-stu-id="c56e8-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="c56e8-120">Essa opção não estará disponível se o controle de admissão de chamadas (CAC) estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="c56e8-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="c56e8-121">Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="c56e8-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="c56e8-122">Não há necessidade de controle de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c56e8-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="c56e8-123">Não é preciso ter uma configuração refinada para determinar quando bypass deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="c56e8-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="c56e8-124">Há conectividade total entre gateways e clientes.</span><span class="sxs-lookup"><span data-stu-id="c56e8-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="c56e8-125">**Usar a configuração**   de sites e regiões se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada.</span><span class="sxs-lookup"><span data-stu-id="c56e8-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="c56e8-126">Quando essa opção estiver selecionada, os sites de configuração de rede e regiões serão usados para determinar quando o bypass de mídia é possível.</span><span class="sxs-lookup"><span data-stu-id="c56e8-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="c56e8-127">Se você selecionar essa opção, poderá optar por habilitar o bypass para sites que não estão mapeados.</span><span class="sxs-lookup"><span data-stu-id="c56e8-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="c56e8-128">Marque a caixa de seleção **Permitir bypass para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região que não têm restrições de largura de banda (por exemplo, um site central grande) e também tem alguns sites de filiais associados ao mesma região que tem restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c56e8-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="c56e8-129">Quando você habilita o bypass para sites não mapeados, a configuração é simplificada porque você especifica somente as sub-redes associadas a sites de ramificação, em vez de precisar especificar todas as sub-redes associadas a todos os sites.</span><span class="sxs-lookup"><span data-stu-id="c56e8-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="c56e8-130">Recomendamos que você não marque a caixa de seleção **Permitir bypass para sites não mapeados** se o CAC estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="c56e8-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="c56e8-131">Clique em **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c56e8-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="c56e8-132">Desabilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="c56e8-132">Disable network media bypass</span></span>

<span data-ttu-id="c56e8-133">As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="c56e8-134">O bypass de mídia permite que as chamadas ignorem o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c56e8-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="c56e8-135">Para obter detalhes sobre quando usar o bypass de mídia, consulte [planejar a bypass de mídia](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="c56e8-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="c56e8-136">Você pode desativar o bypass de mídia no painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="c56e8-137">Para desativar o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="c56e8-137">To disable media bypass</span></span>

1.  <span data-ttu-id="c56e8-138">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c56e8-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c56e8-139">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c56e8-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c56e8-140">Na barra de navegação à esquerda, clique em **configuração de rede**e, em seguida, clique em **global**.</span><span class="sxs-lookup"><span data-stu-id="c56e8-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="c56e8-141">Na página **global** , clique em configuração **global** .</span><span class="sxs-lookup"><span data-stu-id="c56e8-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="c56e8-142">Sempre existe apenas uma configuração, e ela é sempre chamada de global.</span><span class="sxs-lookup"><span data-stu-id="c56e8-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="c56e8-143">No menu **Editar** , clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c56e8-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="c56e8-144">Na página **Editar configuração global** , desmarque a caixa de seleção **habilitar bypass de mídia** .</span><span class="sxs-lookup"><span data-stu-id="c56e8-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="c56e8-145">Clique em **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c56e8-145">Click **Commit** to save your changes.</span></span>

  
