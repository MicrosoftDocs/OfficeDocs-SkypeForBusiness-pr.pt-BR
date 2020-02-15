---
title: Lync Server 2013 visão geral de conferência A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd73e1356e42aca8dc4159143287371dd66f0688
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="9436e-102">Visão geral da Conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9436e-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9436e-103">_**Última modificação do tópico:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="9436e-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="9436e-p101">A conferência A/V permite comunicações de áudio de vídeo em tempo real entre seus usuários. Ao implantar a conferência, você pode escolher habilitar e usar a Webconferência e a conferência A/V, ou apenas a Webconferência.</span><span class="sxs-lookup"><span data-stu-id="9436e-p101">A/V conferencing enables real-time audio and video communications between your users. When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="9436e-p102">Para planejar a conferência A/V, você precisa saber a largura de banda de rede necessária para o tipo de mídia de conferência que sua organização requer. Isso pode incluir áudio, vídeo e vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="9436e-p102">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires. This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="9436e-108">Antes de habilitar os usuários para conferência A/V, verifique se a rede pode lidar com a carga resultante.</span><span class="sxs-lookup"><span data-stu-id="9436e-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="9436e-109">Sem largura de banda de rede suficiente, a experiência do usuário pode ser seriamente degradada.</span><span class="sxs-lookup"><span data-stu-id="9436e-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="9436e-110">Você pode usar o CAC (controle de admissão de chamadas) para gerenciar a largura de banda da rede usada por conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="9436e-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="9436e-111">Isso é importante para redes restritas, como links limitados de largura de banda entre os sites central e de filial.</span><span class="sxs-lookup"><span data-stu-id="9436e-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="9436e-112">Para obter detalhes, consulte [Overview of Call Admission Control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="9436e-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="9436e-113">Para obter detalhes sobre os requisitos de largura de banda de mídia, consulte [requisitos de largura de banda de rede para tráfego de mídia no Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="9436e-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="9436e-114">Se você implantar uma conferência de áudio na sua rede, os usuários precisarão de dispositivos de áudio, como fones de ouvido, para participar em uma conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="9436e-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="9436e-115">Se você implantar conferência de vídeo, será necessário implantar dispositivos de vídeo, como webcams, para os usuários.</span><span class="sxs-lookup"><span data-stu-id="9436e-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="9436e-116">Recomendamos que você use dispositivos UC (comunicações unificadas) certificados pela Microsoft para todos os tipos de dispositivos, para garantir uma experiência ideal para o usuário.</span><span class="sxs-lookup"><span data-stu-id="9436e-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="9436e-117">Para obter detalhes sobre dispositivos certificados para UC, consulte "telefones e dispositivos para Lync" [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)em.</span><span class="sxs-lookup"><span data-stu-id="9436e-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="9436e-118">Para dispositivos de áudio e vídeo, a implantação de vídeo e treinamento do usuário são etapas importantes a serem consideradas e planejadas.</span><span class="sxs-lookup"><span data-stu-id="9436e-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="9436e-119">As seções a seguir descrevem os recursos para conferência de áudio e vídeo, incluindo informações sobre gerenciamento de largura de banda e seleção de clientes apropriados.</span><span class="sxs-lookup"><span data-stu-id="9436e-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="9436e-120">Recursos de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="9436e-120">Audio Conferencing Features</span></span>

<span data-ttu-id="9436e-121">O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de conferência de áudio para o usuário, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9436e-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="9436e-122">**Tirar o áudio sem som**   o apresentador pode usar essa configuração para desativar todos os participantes de áudio na conferência e colocar a conferência em um estado em que os não-presenteres não podem desativar o mudo.</span><span class="sxs-lookup"><span data-stu-id="9436e-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="9436e-123">**Comunicados de entrada/saída de conferência**   se você habilitou a conferência discada, os apresentadores podem usar essa configuração para ativar ou desativar anúncios de entrada e saída para minimizar distrações enquanto uma conferência estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="9436e-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="9436e-124">**Adicionar um usuário discando**   os apresentadores e participantes que receberam permissão, pode adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.</span><span class="sxs-lookup"><span data-stu-id="9436e-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="9436e-125">Recursos de videoconferência</span><span class="sxs-lookup"><span data-stu-id="9436e-125">Video Conferencing Features</span></span>

<span data-ttu-id="9436e-126">O Lync Server 2013 fornece vários recursos que você pode usar para configurar a experiência de conferência de vídeo do usuário, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9436e-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="9436e-127">**Modo de exibição**   de galeria em conferências de vídeo com mais de duas pessoas, os usuários veem automaticamente todos na conferência.</span><span class="sxs-lookup"><span data-stu-id="9436e-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="9436e-128">Se a conferência tiver mais que cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida.</span><span class="sxs-lookup"><span data-stu-id="9436e-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="9436e-129">O vídeo de vários participantes está ativado como padrão.</span><span class="sxs-lookup"><span data-stu-id="9436e-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="9436e-130">Para obter detalhes sobre como configurar ou desativar o vídeo com vários participantes, confira [Configurando a largura de banda de vídeo no Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="9436e-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="9436e-131">**Vídeo panorâmico se**   um dispositivo de conferência de vídeo redonda estiver instalado na sala de conferência, este recurso fornece uma visão de 360 graus de tamanho completo da sala de conferência.</span><span class="sxs-lookup"><span data-stu-id="9436e-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="9436e-132">A faixa de vídeo panorâmico está disponível apenas em dispositivos de mesa redonda.</span><span class="sxs-lookup"><span data-stu-id="9436e-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="9436e-133">**Apresentador somente modo**   de vídeo os apresentadores podem configurar a reunião para que apenas o vídeo do apresentador seja mostrado.</span><span class="sxs-lookup"><span data-stu-id="9436e-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="9436e-134">Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e travadas para diferentes fontes.</span><span class="sxs-lookup"><span data-stu-id="9436e-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="9436e-135">Esse modo também é aplicado ao vídeo capturado e fornecido por dispositivos de mesa redonda.</span><span class="sxs-lookup"><span data-stu-id="9436e-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="9436e-136">\*\*\*\*   Os usuários de vídeo HD podem experimentar resoluções de até HD 1080p em chamadas de duas partes e conferências com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="9436e-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="9436e-137">\*\*\*\*   Os apresentadores de Spotlight de vídeo podem configurar a reunião para que apenas o vídeo de um participante selecionado que é uma fonte de vídeo seja visto pelos outros participantes da conferência.</span><span class="sxs-lookup"><span data-stu-id="9436e-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="9436e-138">Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos de mesa redonda de vídeo panorâmico.</span><span class="sxs-lookup"><span data-stu-id="9436e-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

