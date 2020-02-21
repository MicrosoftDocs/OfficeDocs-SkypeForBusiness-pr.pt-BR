---
title: 'Lync Server 2013: Configurando largura de banda de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8995f47ff1059921c324d71cbaca26fa47c50ca0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="54c11-102">Configurando largura de banda de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c11-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c11-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="54c11-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="54c11-104">O Lync Server 2013 inclui várias configurações para o gerenciamento de vídeo para chamadas de duas partes e conferências com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="54c11-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="54c11-105">Ao implantar o Lync Server 2013, você deve avaliar se as configurações padrão são apropriadas para sua organização e modificá-las conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="54c11-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="54c11-p102">Os parâmetros descritos nesta seção se aplicam tanto a conferências de dois grupos quanto de vários grupos. Visualize ou modifique tais configurações utilizando um dos cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="54c11-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="54c11-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="54c11-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="54c11-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="54c11-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="54c11-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="54c11-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="54c11-111">Verifique as configurações a seguir na sua política de conferência:</span><span class="sxs-lookup"><span data-stu-id="54c11-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="54c11-112">**VideoBitRateKb**   esta configuração especifica a taxa máxima de bits de vídeo em kilobits por segundo (Kbps) usada para o vídeo enviado por um usuário.</span><span class="sxs-lookup"><span data-stu-id="54c11-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="54c11-113">O valor padrão é 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="54c11-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="54c11-114">Valores válidos vão de 0 a 50000.</span><span class="sxs-lookup"><span data-stu-id="54c11-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="54c11-115">Essa configuração aplica-se separadamente a um vídeo principal e vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="54c11-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="54c11-116">Exemplo: se você especificar 2000 Kbps, o Lync Server pode enviar 2000 kbps para o fluxo de vídeo principal e 2000 kbps para o fluxo de vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="54c11-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c11-117">A largura de banda de rede de vídeo máxima para um ponto de extremidade do Lync 2013 é de 8000 kbps para o vídeo principal e 2500 kbps para o vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="54c11-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="54c11-118">Esses valores máximos são alcançados apenas se vários vídeos são recebidos ou enviados.</span><span class="sxs-lookup"><span data-stu-id="54c11-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="54c11-119">Para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54c11-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="54c11-120">Essa seção lista a largura de banda máxima e típica para fluxo de vídeo para todas as resoluções suportadas.</span><span class="sxs-lookup"><span data-stu-id="54c11-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="54c11-121">**TotalReceiveVideoBitRateKb**   essa configuração, que é nova no Lync Server 2013, especifica a taxa de bits máxima permitida (em kilobits por segundo) para todos os fluxos de vídeo recebidos por um cliente.</span><span class="sxs-lookup"><span data-stu-id="54c11-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="54c11-122">Isto é, especifica o total combinado para todos os fluxos de vídeo, exceto fluxos de vídeo panorâmico, que o cliente pode receber.</span><span class="sxs-lookup"><span data-stu-id="54c11-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="54c11-123">Por exemplo, se você especificar 1500 kbps, então um cliente poderá receber até 1500 kbps de vídeo, o que pode consistir de vários fluxos de vídeo ou um único fluxo.</span><span class="sxs-lookup"><span data-stu-id="54c11-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="54c11-124">Essa configuração se aplica somente aos clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54c11-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="54c11-p106">O valor padrão para **TotalReceiveVideoBitRateKb** é 50000 kbps. Se a configuração **EnableMultiviewJoin** para o Modo de exibiçãod e Galeria estiver definido como Verdadeiro, **TotalReceiveVideoBitRateKb** não deverá ser definido em menos de 420 kbps. Se a configuração **EnableMultiviewJoin** para o Modo de exibição de Galeria for definido como Falso, **TotalReceiveVideoBitRateKb** não deverá ser definido para menos de 100 kbps. Se **EnableMultiviewJoin** estiver definido como Verdadeiro e você define o valor para abaixo de 420 kbps, os valores se tornarão padrão para o valor limite. Esse limiar ajuda a evitar uma desconfiguração acidental que pode resultar de uma experiência de usuário pobre.</span><span class="sxs-lookup"><span data-stu-id="54c11-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c11-130">Para obter detalhes sobre a configuração do <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54c11-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="54c11-131">**MaxVideoConferencingResolution**   este parâmetro não é mais usado para clientes do Lync Server 2013 no Lync Server 2013 conferências.</span><span class="sxs-lookup"><span data-stu-id="54c11-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="54c11-132">As conferências do Lync Server 2013 usam os controles de taxa de bits descritos anteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="54c11-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="54c11-133">Essa configuração ainda é usada para clientes herdados que participam de uma conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54c11-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="54c11-134">Esse parâmetro determina a resolução máxima permitida para clientes herdados em conferências organizadas por usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54c11-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="54c11-135">Ou seja, os clientes herdados são tratados da mesma forma que estavam em versões anteriores do Lync Server ou do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="54c11-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="54c11-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span><span class="sxs-lookup"><span data-stu-id="54c11-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="54c11-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="54c11-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="54c11-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="54c11-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="54c11-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="54c11-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="54c11-141">Verify the following setting:</span><span class="sxs-lookup"><span data-stu-id="54c11-141">Verify the following setting:</span></span>

  - <span data-ttu-id="54c11-142">**MaxVideoRateAllowed**   esta configuração por pool especifica a taxa máxima na qual os sinais de vídeo serão transferidos nos pontos de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="54c11-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="54c11-143">Aplica-se apenas às versões anteriores dos clientes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54c11-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c11-144">Os clientes do Lync Server 2013 ignoram essa configuração e usam a configuração TotalReceiveVideoBitRateKb na política de conferência.</span><span class="sxs-lookup"><span data-stu-id="54c11-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="54c11-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span><span class="sxs-lookup"><span data-stu-id="54c11-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="54c11-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span><span class="sxs-lookup"><span data-stu-id="54c11-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="54c11-148">Os procedimentos a seguir são exemplos de como usar o Shell de gerenciamento do Lync Server para modificar as configurações descritas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="54c11-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="54c11-149">To modify conferencing policy for video settings</span><span class="sxs-lookup"><span data-stu-id="54c11-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="54c11-150">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="54c11-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="54c11-151">At the command line, run the following cmdlet to edit conferencing policy:</span><span class="sxs-lookup"><span data-stu-id="54c11-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="54c11-152">To modify media configuration for legacy clients</span><span class="sxs-lookup"><span data-stu-id="54c11-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="54c11-153">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="54c11-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="54c11-154">At the command line, run the following cmdlet to edit the media configuration:</span><span class="sxs-lookup"><span data-stu-id="54c11-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

