---
title: Habilitando e desabilitando o bypass de mídia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Painel de Controle do Skype for Business Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816491"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="79af0-103">Habilitar e desabilitar bypass de mídia no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79af0-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="79af0-104">Use os procedimentos neste artigo para habilitar ou desabilitar o bypass de mídia usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="79af0-105">Habilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="79af0-105">Enable network media bypass</span></span> 

<span data-ttu-id="79af0-106">As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="79af0-107">O desvio de mídia permite que chamadas ignorem o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="79af0-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="79af0-108">Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plano para bypass de mídia.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="79af0-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="79af0-109">Você pode habilitar e configurar o bypass de mídia do Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="79af0-110">Para habilitar e configurar o desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="79af0-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="79af0-111">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="79af0-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79af0-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="79af0-113">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**</span><span class="sxs-lookup"><span data-stu-id="79af0-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="79af0-p102">Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.</span><span class="sxs-lookup"><span data-stu-id="79af0-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="79af0-116">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="79af0-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="79af0-117">Na página **Editar Configuração Global**, clique na opção **Habilitar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="79af0-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="79af0-118">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="79af0-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="79af0-119">**Sempre ignorar**   Selecione essa opção para tentar o bypass de mídia em todas as chamadas.</span><span class="sxs-lookup"><span data-stu-id="79af0-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="79af0-120">Esta opção estará indisponível se o controle de admissão de chamadas (CAC) estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="79af0-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="79af0-121">Se o CAC não estiver habilitado, selecione esta opção nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="79af0-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="79af0-122">Não existe a necessidade de controle de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="79af0-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="79af0-123">Não existe a necessidade de uma configuração refinada para determinar quando o desvio deve acontecer.</span><span class="sxs-lookup"><span data-stu-id="79af0-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="79af0-124">Existe conectividade total entre gateways e clientes.</span><span class="sxs-lookup"><span data-stu-id="79af0-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="79af0-125">**Usar a configuração de sites e região**   Se o CAC estiver habilitado, essa opção será selecionada por padrão e não poderá ser alterada.</span><span class="sxs-lookup"><span data-stu-id="79af0-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="79af0-126">Quando esta opção está selecionada, a configuração de rede de sites e regiões será usada para determinar quando o desvio de mídia será possível.</span><span class="sxs-lookup"><span data-stu-id="79af0-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="79af0-127">Se esta opção for selecionada, você pode optar por habilitar o desvio para sites que não estão mapeados.</span><span class="sxs-lookup"><span data-stu-id="79af0-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="79af0-128">Clique na opção **Habilitar desvio para sites não mapeados** somente se você tiver um ou mais sites grandes associados à mesma região, que não possuem restrições de largura de banda (por exemplo, um site central grande) e se tiver também alguns sites de filial associados à mesma região que executa as restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="79af0-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="79af0-129">Ao habilitar o desvio para sites não mapeados, a configuração é eficiente porque somente as sub-redes associadas aos sites de filial são especificadas, em vez da necessidade de especificas todas as sub-redes associadas as todos os sites.</span><span class="sxs-lookup"><span data-stu-id="79af0-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="79af0-130">É recomendável não selecionar a opção **Habilitar desvio para sites não mapeados** se o CAC estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="79af0-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="79af0-131">Clique em **Confirmar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="79af0-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="79af0-132">Desabilitar bypass de mídia de rede</span><span class="sxs-lookup"><span data-stu-id="79af0-132">Disable network media bypass</span></span>

<span data-ttu-id="79af0-133">As configurações de bypass de mídia se aplicam globalmente em uma implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="79af0-134">O desvio de mídia permite que chamadas ignorem o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="79af0-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="79af0-135">Para obter detalhes sobre quando usar o bypass de mídia, consulte [Plano para bypass de mídia.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="79af0-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="79af0-136">Você pode desabilitar o bypass de mídia do Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="79af0-137">Para desativar o desvio de mídia</span><span class="sxs-lookup"><span data-stu-id="79af0-137">To disable media bypass</span></span>

1.  <span data-ttu-id="79af0-138">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="79af0-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79af0-139">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79af0-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="79af0-140">Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Global.**</span><span class="sxs-lookup"><span data-stu-id="79af0-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="79af0-p106">Na página **Global**, clique na configuração **Global**. Sempre existe somente uma configuração, sempre chamada Global.</span><span class="sxs-lookup"><span data-stu-id="79af0-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="79af0-143">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="79af0-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="79af0-144">Na página **Editar Configuração Global**, desmarque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="79af0-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="79af0-145">Clique em **Confirmar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="79af0-145">Click **Commit** to save your changes.</span></span>

  
