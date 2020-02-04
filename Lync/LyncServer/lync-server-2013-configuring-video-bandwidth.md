---
title: 'Lync Server 2013: Configurando a largura de banda do vídeo'
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
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="f9d59-102">Configurando a largura de banda do vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9d59-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9d59-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f9d59-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f9d59-104">O Lync Server 2013 inclui várias configurações para o gerenciamento de vídeo para chamadas de dois participantes e conferências de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="f9d59-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="f9d59-105">Ao implantar o Lync Server 2013, você deve avaliar se as configurações padrão são adequadas para sua organização e modificá-las conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f9d59-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="f9d59-106">Os parâmetros descritos nesta seção se aplicam às duas chamadas de terceiros e à conferência de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="f9d59-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="f9d59-107">Exiba ou modifique essas configurações usando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f9d59-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="f9d59-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="f9d59-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="f9d59-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="f9d59-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="f9d59-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="f9d59-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="f9d59-111">Verifique as seguintes configurações na política de conferência:</span><span class="sxs-lookup"><span data-stu-id="f9d59-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="f9d59-112">**VideoBitRateKb**   essa configuração especifica a taxa máxima de bits de vídeo em kilobits por segundo (Kbps) usada para vídeo enviado por um usuário.</span><span class="sxs-lookup"><span data-stu-id="f9d59-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="f9d59-113">O valor padrão é 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="f9d59-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="f9d59-114">Os valores válidos são de 0 a 50000.</span><span class="sxs-lookup"><span data-stu-id="f9d59-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="f9d59-115">Essa configuração aplica-se separadamente ao vídeo principal e ao vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="f9d59-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="f9d59-116">Exemplo: se você especificar 2000 Kbps, o Lync Server poderá enviar 2000 kbps para o fluxo de vídeo principal e 2000 kbps para o fluxo de vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="f9d59-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9d59-117">O máximo de largura de banda de rede de vídeo de um ponto de extremidade do Lync 2013 é de 8000 kbps para o vídeo principal e 2500 kbps para o vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="f9d59-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="f9d59-118">Esses valores máximos serão atingidos somente se vários vídeos forem recebidos ou enviados.</span><span class="sxs-lookup"><span data-stu-id="f9d59-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="f9d59-119">Para obter detalhes, consulte a seção "uso da rede de tráfego de mídia" em <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de largura de banda de rede para o tráfego de mídia no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9d59-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="f9d59-120">Esta seção lista a largura de banda máxima e típica de fluxo de vídeo para todas as resoluções compatíveis.</span><span class="sxs-lookup"><span data-stu-id="f9d59-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="f9d59-121">**TotalReceiveVideoBitRateKb**   essa configuração, que é nova no Lync Server 2013, especifica a taxa de bits máxima permitida (em quilobits por segundo) para todos os fluxos de vídeo recebidos por um cliente.</span><span class="sxs-lookup"><span data-stu-id="f9d59-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="f9d59-122">Ou seja, ele especifica o total combinado para todos os fluxos de vídeo, exceto fluxos de vídeo panorâmicos, que um cliente pode receber.</span><span class="sxs-lookup"><span data-stu-id="f9d59-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="f9d59-123">Por exemplo, se você especificar 1500 Kbps, um cliente pode receber até 1500 kbps de vídeo, que pode consistir em vários fluxos de vídeo ou um único fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f9d59-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="f9d59-124">Essa configuração se aplica somente aos clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9d59-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="f9d59-125">O valor padrão para **TotalReceiveVideoBitRateKb** é de 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="f9d59-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="f9d59-126">Se a configuração **EnableMultiviewJoin** para o modo de exibição de galeria estiver definida como true, **TotalReceiveVideoBitRateKb** não deverá ser definido abaixo de 420 kbps.</span><span class="sxs-lookup"><span data-stu-id="f9d59-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="f9d59-127">Se a configuração **EnableMultiviewJoin** para o modo de exibição de galeria estiver definida como false, **TotalReceiveVideoBitRateKb** não deverá ser definido abaixo de 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="f9d59-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="f9d59-128">Se **EnableMultiviewJoin** for definido como true e você definir o valor abaixo de 420 Kbps, os valores serão padrão para o valor limite.</span><span class="sxs-lookup"><span data-stu-id="f9d59-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="f9d59-129">Esse limite ajuda a evitar problemas de configuração acidentais que podem resultar em má experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="f9d59-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9d59-130">Para obter detalhes sobre a configuração <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">Configurando o modo de exibição de galeria no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9d59-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="f9d59-131">**MaxVideoConferencingResolution**   este parâmetro não está mais sendo usado para clientes do Lync Server 2013 no Lync Server 2013 conferências.</span><span class="sxs-lookup"><span data-stu-id="f9d59-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="f9d59-132">Conferências do Lync Server 2013 use os controles de taxa de bits descritos anteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="f9d59-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="f9d59-133">Essa configuração ainda é usada para clientes herdados que participam de uma conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9d59-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="f9d59-134">Esse parâmetro determina a resolução máxima permitida para clientes herdados em conferências organizadas por usuários que são hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9d59-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="f9d59-135">Ou seja, os clientes herdados são tratados da mesma forma que estavam nas versões anteriores do Lync Server ou Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="f9d59-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="f9d59-136">Além das configurações de política de conferência que se aplicam aos usuários, avalie as configurações de configuração de mídia.</span><span class="sxs-lookup"><span data-stu-id="f9d59-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="f9d59-137">Exiba ou modifique essas configurações usando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f9d59-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="f9d59-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f9d59-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="f9d59-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f9d59-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="f9d59-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="f9d59-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="f9d59-141">Verifique a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="f9d59-141">Verify the following setting:</span></span>

  - <span data-ttu-id="f9d59-142">**MaxVideoRateAllowed**   a configuração por pool especifica a taxa máxima em que os sinais de vídeo serão transferidos nos pontos de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="f9d59-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="f9d59-143">Aplica-se apenas às versões anteriores dos clientes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9d59-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9d59-144">Os clientes do Lync Server 2013 ignoram essa configuração e usam a configuração TotalReceiveVideoBitRateKb na política de conferência em vez disso.</span><span class="sxs-lookup"><span data-stu-id="f9d59-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="f9d59-145">O valor padrão é HD720P.</span><span class="sxs-lookup"><span data-stu-id="f9d59-145">The default value is HD720P.</span></span> <span data-ttu-id="f9d59-146">Os valores válidos são HD720p15M, VGA600K e CIF250K.</span><span class="sxs-lookup"><span data-stu-id="f9d59-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="f9d59-147">Exemplo: se você especificar 1500 Kbps, todos os clientes herdados do pool poderão receber até 1500 kbps de vídeo em conferências de dois participantes ou de vários participantes.</span><span class="sxs-lookup"><span data-stu-id="f9d59-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="f9d59-148">Os procedimentos a seguir são exemplos de como usar o Shell de gerenciamento do Lync Server para modificar as configurações descritas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="f9d59-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="f9d59-149">Para modificar a política de conferência para configurações de vídeo</span><span class="sxs-lookup"><span data-stu-id="f9d59-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="f9d59-150">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9d59-151">Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:</span><span class="sxs-lookup"><span data-stu-id="f9d59-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="f9d59-152">Para modificar a configuração de mídia para clientes herdados</span><span class="sxs-lookup"><span data-stu-id="f9d59-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="f9d59-153">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f9d59-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9d59-154">Na linha de comando, execute o cmdlet a seguir para editar a configuração de mídia:</span><span class="sxs-lookup"><span data-stu-id="f9d59-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

