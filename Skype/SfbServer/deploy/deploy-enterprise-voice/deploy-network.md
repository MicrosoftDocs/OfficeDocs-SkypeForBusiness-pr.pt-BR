---
title: Implantar regiões de rede, sites e sub-redes em Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Criar ou modificar regiões de rede, sites de rede e associar subredes no Skype para Business Server. Todos esses são usados para os recursos avançados do Enterprise Voice: desvio de mídia, chamar o controle de admissão e roteamento baseado no local.'
ms.openlocfilehash: b5de9ed76dcba917a186a6f9060021f51d5abac9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892661"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="577c3-104">Implantar regiões de rede, sites e sub-redes em Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="577c3-105">Criar ou modificar regiões de rede, sites de rede e associar subredes no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="577c3-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="577c3-106">Todos esses são usados para os recursos avançados do Enterprise Voice: desvio de mídia, chamar o controle de admissão e roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="577c3-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="577c3-107">Os recursos avançados do Enterprise Voice são [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), e [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="577c3-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="577c3-108">Esses recursos todos exigem que você crie regiões da rede, sites da redee sub-redes.</span><span class="sxs-lookup"><span data-stu-id="577c3-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="577c3-109">Por exemplo, todos estes recursos requerem que cada sub-rede em sua topologia seja associada a um local de rede específico, e cada site da rede deve ser associado a uma região da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="577c3-110">Para obter mais informações sobre esses termos, consulte [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="577c3-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span></span>

<span data-ttu-id="577c3-111">O controle de admissão de chamada e o E9-1-1 têm requisitos adicionais de configuração para os sites da rede:</span><span class="sxs-lookup"><span data-stu-id="577c3-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="577c3-112">O serviço de controle de admissão de chamadas requer que um perfil de política de largura de banda seja especificado para cada site restrito pelas limitações de largura de banda WAN.</span><span class="sxs-lookup"><span data-stu-id="577c3-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="577c3-113">Se você planeja implantar o controle de admissão de chamada, você deverá [criar perfis de política de largura de banda em Skype para Business Server](create-bandwidth-policy-profiles.md) antes de configurar os locais de rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="577c3-114">O E9-1-1 requer que uma política local seja especificada para cada site.</span><span class="sxs-lookup"><span data-stu-id="577c3-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="577c3-115">Se você pretende implantar o E9-1-1, você deverá [criar políticas de local no Skype para Business Server](create-location-policies.md) antes de configurar os locais de rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="577c3-116">Criar ou modificar uma região da rede</span><span class="sxs-lookup"><span data-stu-id="577c3-116">Create or modify a Network Region</span></span>

<span data-ttu-id="577c3-117">Se você já criou regiões de rede para um desses recursos, você não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usará esses mesmos regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="577c3-p106">No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central.</span><span class="sxs-lookup"><span data-stu-id="577c3-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="577c3-120">Para criar uma região de rede usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="577c3-121">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="577c3-122">Execute o cmdlet New-CsNetworkRegion para criar regiões da rede:</span><span class="sxs-lookup"><span data-stu-id="577c3-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="577c3-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="577c3-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="577c3-124">Neste exemplo, você criou uma região de rede chamada "NorthAmerica" que é associado a um site central com a ID de site CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="577c3-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="577c3-125">Para concluir a criação das regiões de rede para sua topologia, repita a etapa 2 com as configurações para cada região da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="577c3-126">Para criar uma região de rede usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577c3-127">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="577c3-128">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="577c3-129">Clique em **Região**.</span><span class="sxs-lookup"><span data-stu-id="577c3-129">Click **Region**.</span></span>

4. <span data-ttu-id="577c3-130">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="577c3-130">Click **New**.</span></span>

5. <span data-ttu-id="577c3-131">Na página **Nova Região**, clique em **Nome** e digite um nome para a região da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="577c3-132">Clique em **Site central** e, em seguida, clique em um site central na lista.</span><span class="sxs-lookup"><span data-stu-id="577c3-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="577c3-133">Como opção, clique em **Descrição** e digite as informações adicionais para descrever esse site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="577c3-134">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="577c3-134">Click **Commit**.</span></span>

9. <span data-ttu-id="577c3-135">Para concluir a criação das regiões da rede para sua topologia, repita as etapas 4 a 8 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="577c3-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="577c3-136">Para modificar uma região de rede usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="577c3-137">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="577c3-138">Execute o cmdlet Set-CsNetworkRegion para modificar uma região da rede existente:</span><span class="sxs-lookup"><span data-stu-id="577c3-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="577c3-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="577c3-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="577c3-140">Neste exemplo, você modificou uma região de rede existente chamada "NorthAmerica" (criado usando os procedimentos, anteriormente neste tópico), alterando a descrição.</span><span class="sxs-lookup"><span data-stu-id="577c3-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="577c3-141">Se uma descrição existia para a área de "NorthAmerica", este comando a substituiria por esse valor; Se não tiver sido definida, esse comando define-lo.</span><span class="sxs-lookup"><span data-stu-id="577c3-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="577c3-142">Para modificar outras regiões da rede, repita a etapa 2 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="577c3-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="577c3-143">Para modificar uma região de rede usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577c3-144">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="577c3-145">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="577c3-146">Clique no botão de navegação **Região**.</span><span class="sxs-lookup"><span data-stu-id="577c3-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="577c3-147">Na tabela, clique na região da rede que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="577c3-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="577c3-148">Clique em **Editar** e, em seguida, clique em **Mostrar detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="577c3-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="577c3-149">Na página **Editar região** , altere os valores para as configurações dessa região de rede conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="577c3-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="577c3-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="577c3-150">Click **Commit**.</span></span>

8. <span data-ttu-id="577c3-151">Para concluir a modificação das regiões da rede, repita as etapas 4 a 7 com as configurações de outras regiões.</span><span class="sxs-lookup"><span data-stu-id="577c3-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="577c3-152">Criar ou modificar um site da rede</span><span class="sxs-lookup"><span data-stu-id="577c3-152">Create or modify a network site</span></span>

<span data-ttu-id="577c3-153">Se você já criou sites de rede para um desses recursos, você não precisará criar novos sites de rede; outros recursos avançados do Enterprise Voice usará os mesmos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="577c3-154">Você pode, porém, precisar modificar uma definição de site da rede existente para aplicar configurações específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="577c3-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="577c3-155">Por exemplo, se você criou um site da rede para o E9-1-1, você precisa modificar o site da rede durante a implantação do serviço de controle de admissão de chamadas para aplicar um perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="577c3-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="577c3-156">Para criar um site de rede usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="577c3-157">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="577c3-158">Execute o cmdlet do New-CsNetworkSite para criar sites da rede:</span><span class="sxs-lookup"><span data-stu-id="577c3-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="577c3-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="577c3-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="577c3-160">Neste exemplo, você criou um site de rede chamado "Chicago" que está na região de rede "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="577c3-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="577c3-161">A região da rede NorthAmerica já deve existir para que esse comando seja executado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="577c3-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="577c3-162">Para concluir a criação de sites da rede para a sua topologia, repita a etapa 2 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="577c3-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="577c3-163">Para criar um site de rede usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577c3-164">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="577c3-165">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="577c3-166">Clique no botão de navegação **Site**.</span><span class="sxs-lookup"><span data-stu-id="577c3-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="577c3-167">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="577c3-167">Click **New**.</span></span>

5. <span data-ttu-id="577c3-168">Na página **Novo Site**, clique em **Nome** e depois digite um nome para o site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="577c3-169">Clique em **Região**, e depois clique em uma região na lista.</span><span class="sxs-lookup"><span data-stu-id="577c3-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="577c3-170">De modo opcional, clique em **Política de largura de banda**, e depois clique em uma das larguras de banda da lista.</span><span class="sxs-lookup"><span data-stu-id="577c3-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="577c3-171">A política de largura de banda é solicitada apenas se você implantar o serviço de controle de admissão de chamadas no site.</span><span class="sxs-lookup"><span data-stu-id="577c3-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="577c3-172">De modo opcional, clique em **Política de Local**, depois clique em uma política de local na lista.</span><span class="sxs-lookup"><span data-stu-id="577c3-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="577c3-173">A política de local é solicitada se você implantar E9-1-1 no site.</span><span class="sxs-lookup"><span data-stu-id="577c3-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="577c3-174">Como opção, clique em **Descrição**, em seguida, digite as informações adicionais para descrever esse site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="577c3-175">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="577c3-175">Click **Commit**.</span></span>

11. <span data-ttu-id="577c3-176">Para concluir a criação de sites da rede para a sua topologia, repita as etapas 4 a 10 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="577c3-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="577c3-177">Para modificar um site de rede usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="577c3-178">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="577c3-179">Execute o cmdlet Set-CsNetworkSite para modificar os sites da rede:</span><span class="sxs-lookup"><span data-stu-id="577c3-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="577c3-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="577c3-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="577c3-181">Neste exemplo, o site chamado "Albuquerque" é movido para a região de rede "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="577c3-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="577c3-182">Para modificar a configuração do site da rede para implantar o serviço de controle de admissão de chamadas, o E9-1-1 ou desvio de mídia, modifique o site da rede executando o cmdlet Set-CsNetworkSite com os parâmetros do BWPolicyProfileID ou LocationPolicy, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="577c3-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="577c3-p110">Embora o parâmetro do BypassID exista para o desvio de mídia, recomendamos que você não sobreponha IDs de desvio geradas automaticamente. Você não precisa especificar parâmetros adicionais para configurar um site da rede para o desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="577c3-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="577c3-185">Para concluir a modificação dos sites da rede para sua topologia, repita a etapa 2 com as configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="577c3-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="577c3-186">Para modificar um site de rede usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577c3-187">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="577c3-188">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="577c3-189">Clique no botão de navegação **Site**.</span><span class="sxs-lookup"><span data-stu-id="577c3-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="577c3-190">Na tabela, clique no site da rede que você quer modificar.</span><span class="sxs-lookup"><span data-stu-id="577c3-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="577c3-191">Clique em **Editar**e, em seguida, clique em **Mostrar detalhes…**.</span><span class="sxs-lookup"><span data-stu-id="577c3-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="577c3-192">Na página **Editar Site** , altere os valores para configurações do site esta rede conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="577c3-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="577c3-193">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="577c3-193">Click **Commit**.</span></span>

8. <span data-ttu-id="577c3-194">Para concluir a modificação de sites da rede, repita as etapas de 4 a 7 com configurações de outros sites.</span><span class="sxs-lookup"><span data-stu-id="577c3-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="577c3-195">Associar uma subrede a um site da rede</span><span class="sxs-lookup"><span data-stu-id="577c3-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="577c3-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="577c3-196"></span></span>

<span data-ttu-id="577c3-197">Todas as sub-redes da sua rede devem ser associadas a um site da rede específico, pois as informações da sub-rede são usadas para determinar o site da rede em que um ponto de extremidade se encontra quando uma nova sessão é iniciada.</span><span class="sxs-lookup"><span data-stu-id="577c3-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="577c3-198">Quando o local de cada participante em uma sessão é conhecido, advanced Enterprise Voice recursos podem aplicar essas informações para determinar como lidar com a configuração da chamada ou roteamento.</span><span class="sxs-lookup"><span data-stu-id="577c3-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="577c3-199">Todos os endereços IP públicos configurados dos Servidores de Borda de Áudio/Vídeo em sua implantação devem ser adicionados às suas definições de configuração da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="577c3-200">Estes endereços IP são adicionados como sub-redes com uma máscara de 32.</span><span class="sxs-lookup"><span data-stu-id="577c3-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="577c3-201">O site da rede associado deve corresponder ao site da rede configurado adequado.</span><span class="sxs-lookup"><span data-stu-id="577c3-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="577c3-202">Por exemplo, o endereço IP público que corresponde à / serviço de borda de V em site central Chicago seria NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="577c3-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="577c3-203">Para associar uma sub-rede um site de rede usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="577c3-204">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="577c3-205">Execute o cmdlet  **New-CsNetworkSubnet** para associar uma sub-rede a um site da rede:</span><span class="sxs-lookup"><span data-stu-id="577c3-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="577c3-206">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="577c3-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="577c3-207">Neste exemplo, você criou uma associação entre a sub-rede 172.11.12.13 e o site de rede "Chicago".</span><span class="sxs-lookup"><span data-stu-id="577c3-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="577c3-208">Repita a etapa 2 para todas as sub-redes em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="577c3-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="577c3-209">Para associar sub-redes a sites da rede importando um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="577c3-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="577c3-p113">Crie um arquivo CSV que inclui todas as sub-redes que deseja adicionar. Por exemplo, crie um arquivo chamado **subnet.csv** como o seguinte conteúdo:</span><span class="sxs-lookup"><span data-stu-id="577c3-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="577c3-212">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="577c3-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="577c3-213">Execute o seguinte cmdlet para importar o **arquivo Subnet. csv**e armazene seu conteúdo no repositório de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="577c3-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="577c3-214">Para associar uma sub-rede um site de rede usando o Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="577c3-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="577c3-215">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="577c3-216">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="577c3-217">Clique no botão de navegação **Sub-rede**.</span><span class="sxs-lookup"><span data-stu-id="577c3-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="577c3-218">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="577c3-218">Click **New**.</span></span>

5. <span data-ttu-id="577c3-219">Na página **Nova Sub-rede**, clique em **ID da Sub-rede** e digite o primeiro endereço do intervalo de endereços IP definido pela sub-rede que deseja associar a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="577c3-220">Clique em **Máscara** e digite o bitmask a ser aplicado à sub-rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="577c3-221">Clique em **ID do site da rede** e selecione o ID do site para o qual está adicionando esta sub-rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="577c3-222">Se os sites da rede ainda não estiverem criados, a lista estará vazia.</span><span class="sxs-lookup"><span data-stu-id="577c3-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="577c3-223">Para obter detalhes sobre o procedimento, consulte [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="577c3-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="577c3-224">Você também pode recuperar as IDs do site para sua implantação executando o cmdlet **Get-CsNetworkSite**.</span><span class="sxs-lookup"><span data-stu-id="577c3-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="577c3-225">Para obter detalhes, consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="577c3-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="577c3-226">Opcionalmente, clique em  **Descrição** e digite informações adicionais para descrever esta sub-rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="577c3-227">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="577c3-227">Click **Commit**.</span></span>

<span data-ttu-id="577c3-228">Repita estas etapas para adicionar outras sub-redes a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="577c3-229">Um alerta Key Health Indicator (KHI) é disparado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou à sub-rede que inclui os endereços IP não está associada a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="577c3-230">Este alerta não será disparado mais de uma vez dentro de um período de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="577c3-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="577c3-231">A informação de alerta relevante e um exemplo são como segue:</span><span class="sxs-lookup"><span data-stu-id="577c3-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="577c3-232">**Origem**: Serviço de Política de Largura de Banda CS (Núcleo)</span><span class="sxs-lookup"><span data-stu-id="577c3-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="577c3-233">**Número do evento**: 36034</span><span class="sxs-lookup"><span data-stu-id="577c3-233">**Event number**: 36034</span></span>

 <span data-ttu-id="577c3-234">**Nível**: 2</span><span class="sxs-lookup"><span data-stu-id="577c3-234">**Level**: 2</span></span>

 <span data-ttu-id="577c3-235">**Descrição**: as sub-redes para os seguintes endereços IP: \<lista de endereços IP\> não estão configuradas ou as sub-redes não estão associadas a um Site de rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="577c3-236">**Causa**: as sub-redes para os endereços IP correspondentes estão ausentes nos parâmetros de configuração de rede ou as sub-redes não estão associadas a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="577c3-237">**Solução**: adicione sub-redes correspondentes à lista de endereços IP nas definições de configuração da rede e associe todas as sub-redes a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="577c3-p116">Por exemplo, se a lista de endereços IP no alerta especifica 10.121.248.226 e 10.121.249.20, ou estes endereços IP não estão associados a uma sub-rede ou a sub-rede à qual estão associados não pertence a um site da rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes para estes endereços, você pode resolver o problema da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="577c3-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="577c3-240">Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="577c3-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="577c3-241">Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um site da rede.</span><span class="sxs-lookup"><span data-stu-id="577c3-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="577c3-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="577c3-242">See also</span></span>
<span data-ttu-id="577c3-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="577c3-243"></span></span>


[<span data-ttu-id="577c3-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="577c3-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="577c3-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="577c3-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="577c3-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="577c3-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="577c3-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="577c3-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="577c3-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="577c3-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="577c3-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="577c3-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="577c3-250">Set-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="577c3-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="577c3-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="577c3-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

