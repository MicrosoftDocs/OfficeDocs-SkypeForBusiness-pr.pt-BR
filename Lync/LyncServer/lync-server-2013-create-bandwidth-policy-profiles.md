---
title: 'Lync Server 2013: criar perfis de política de largura de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="c3dc6-102">Criar perfis de política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3dc6-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3dc6-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c3dc6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c3dc6-p101">*Políticas de largura de banda* definem limitações de uso de largura de banda para modalidades de áudio e vídeo em tempo real. Elas são aplicadas a *perfis de política de largura de banda*, que podem ser aplicados a vários locais de rede para o controle de admissão de chamada.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="c3dc6-106">Para obter diretrizes sobre quais limites de largura de banda você deve definir na sua implantação do CAC, consulte [definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="c3dc6-107">Para obter detalhes sobre como trabalhar com políticas de largura de banda e perfis de política, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c3dc6-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="c3dc6-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c3dc6-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="c3dc6-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c3dc6-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="c3dc6-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c3dc6-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="c3dc6-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c3dc6-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="c3dc6-112">As políticas de exemplo criadas no procedimento a seguir definem limites para o tráfego de áudio geral, sessões de áudio individuais, tráfego de vídeo geral e sessões de vídeo individuais.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="c3dc6-113">Por exemplo, o perfil\_da política de largura de banda do link de 5 MB define os seguintes limites:</span><span class="sxs-lookup"><span data-stu-id="c3dc6-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="c3dc6-114">Limite de Áudio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="c3dc6-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="c3dc6-115">Limite de Sessão de Áudio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="c3dc6-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="c3dc6-116">Limite de Vídeo: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="c3dc6-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="c3dc6-117">Limite de Sessão de Vídeo: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="c3dc6-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c3dc6-p103">O valor mínio para o Limite de Sessão de Áudio é 40 kbps. O valor mínimo para o Limite de Sessão de Vídeo é 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="c3dc6-120">Para criar perfis de política de largura de banda usando o Shell de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="c3dc6-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="c3dc6-121">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c3dc6-122">Para cada perfil de política de largura de banda que desejar criar, execute o cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="c3dc6-123">Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="c3dc6-123">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
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

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="c3dc6-124">Para criar perfis de política de largura de banda usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c3dc6-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c3dc6-125">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c3dc6-126">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c3dc6-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c3dc6-127">Na barra de navegação esquerda, clique em **Configuração de rede**.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="c3dc6-128">Clique no botão de navegação **Perfil da Política**.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="c3dc6-129">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-129">Click **New**.</span></span>

5.  <span data-ttu-id="c3dc6-130">Na página **Novo Perfil de Política**, clique em **Nome** e digite um nome para o perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="c3dc6-131">Clique em **Limite de áudio** e digite o número máximo de kbps a ser permitido para todas as sessões de áudio combinadas.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="c3dc6-132">Clique em **Limite de sessão de áudio** e digite o número máximo de kbps a ser permitido para cada sessão de áudio individual.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="c3dc6-133">Clique em **Limite de vídeo** e digite o número máximo de kbps a ser permitido para todas as sessões de vídeo combinadas.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="c3dc6-134">Clique em **Limite de sessão de vídeo** e digite o número máximo de kbps a ser permitido para cada sessão de vídeo individual.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="c3dc6-135">Opcionalmente, clique em **Descrição** e digite informações adicionais para descrever este perfil de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="c3dc6-136">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-136">Click **Commit**.</span></span>

12. <span data-ttu-id="c3dc6-137">Para concluir a criação de perfis de política de largura de banda para a sua topologia, repita as etapas de 4 a 11 com as configurações para outros perfis de política de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="c3dc6-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

