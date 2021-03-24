---
title: Criar perfis de política de largura de banda no Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Crie ou modifique políticas de largura de banda, que são usadas Enterprise Voice controle de admissão de chamadas no Skype for Business Server.
ms.openlocfilehash: 9458c5576d2c89254c4ee6477ede33c010cb4a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093239"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="3bc6c-103">Criar perfis de política de largura de banda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bc6c-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="3bc6c-104">Crie ou modifique políticas de largura de banda, que são usadas Enterprise Voice controle de admissão de chamadas no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="3bc6c-105">Políticas de largura de banda definem limitações de uso de largura de banda para modalidades de áudio e vídeo em tempo real.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="3bc6c-106">As políticas de largura de banda são aplicadas aos perfis de política debandwidth, que podem ser aplicados a vários sites de rede para controle de admissão de chamada.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="3bc6c-107">Para diretrizes sobre quais limites de largura de banda você deve definir em sua implantação do CAC, consulte [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="3bc6c-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="3bc6c-p102">As políticas de exemplo criadas no procedimento a seguir definem limites para o tráfego de áudio geral, sessões de áudio individuais, tráfego de vídeo geral e sessões de vídeo individuais. Por exemplo, o perfil de política de largura de banda 5Mb_Link define os seguintes limites:</span><span class="sxs-lookup"><span data-stu-id="3bc6c-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="3bc6c-110">Limite de Áudio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="3bc6c-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="3bc6c-111">Limite de Sessão de Áudio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="3bc6c-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="3bc6c-112">Limite de Vídeo: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="3bc6c-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="3bc6c-113">Limite de Sessão de Vídeo: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="3bc6c-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="3bc6c-p103">O valor mínio para o Limite de Sessão de Áudio é 40 kbps. O valor mínimo para o Limite de Sessão de Vídeo é 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3bc6c-116">Para criar perfis de política de largura de banda usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bc6c-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="3bc6c-117">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="3bc6c-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3bc6c-118">Para cada perfil de política de largura de banda que desejar criar, execute o cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="3bc6c-119">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="3bc6c-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3bc6c-120">Para criar perfis de política de largura de banda usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3bc6c-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3bc6c-121">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="3bc6c-122">Na barra de navegação à esquerda, clique em **Configuração da Rede**.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="3bc6c-123">Clique no botão de navegação **Perfil da Política**.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="3bc6c-124">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-124">Click **New**.</span></span>
    
5. <span data-ttu-id="3bc6c-125">Na página **Novo Perfil de Política**, clique em **Nome** e digite um nome para o perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="3bc6c-126">Clique em **Limite de áudio** e digite o número máximo de kbps a ser permitido para todas as sessões de áudio combinadas.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="3bc6c-127">Clique em **Limite de sessão de áudio** e digite o número máximo de kbps a ser permitido para cada sessão de áudio individual.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="3bc6c-128">Clique em **Limite de vídeo** e digite o número máximo de kbps a ser permitido para todas as sessões de vídeo combinadas.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="3bc6c-129">Clique em **Limite de sessão de vídeo** e digite o número máximo de kbps a ser permitido para cada sessão de vídeo individual.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="3bc6c-130">Opcionalmente, clique em **Descrição** e digite informações adicionais para descrever este perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="3bc6c-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="3bc6c-132">Para concluir a criação de perfis de política de largura de banda para a sua topologia, repita as etapas de 4 a 11 com as configurações para outros perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="3bc6c-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3bc6c-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="3bc6c-133">See also</span></span>

[<span data-ttu-id="3bc6c-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3bc6c-134">New-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="3bc6c-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3bc6c-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="3bc6c-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3bc6c-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="3bc6c-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3bc6c-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)