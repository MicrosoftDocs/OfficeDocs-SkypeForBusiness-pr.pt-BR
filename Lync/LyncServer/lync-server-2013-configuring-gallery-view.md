---
title: 'Lync Server 2013: Configurando o modo de exibição de galeria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="765e3-102">Configurando o modo de exibição de galeria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="765e3-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="765e3-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="765e3-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="765e3-104">No Lync Server 2013, configure a Galeria de videoconferência na política de conferência.</span><span class="sxs-lookup"><span data-stu-id="765e3-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="765e3-105">O modo de exibição de galeria está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="765e3-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="765e3-106">Se você não deseja permitir o modo de exibição de galeria ou deseja permitir apenas alguns usuários, é preciso desativar o recurso na política de conferência.</span><span class="sxs-lookup"><span data-stu-id="765e3-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="765e3-107">Quando o vídeo de um participante da conferência não está disponível, a experiência de exibição da galeria dos usuários pode ser aprimorada se você implantar fotos de alta resolução, um novo recurso no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="765e3-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="765e3-108">Fotos de alta resolução fornecem uma alternativa para as fotos de contato de resolução menor e limitada armazenadas nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="765e3-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="765e3-109">Fotos de alta resolução são armazenadas na caixa de correio do Exchange 2013 de um usuário e, portanto, exigem que você integre o Lync Server 2013 com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="765e3-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="765e3-110">Para obter detalhes, consulte o artigo sobre o blog NextHop, "integrando o Exchange 2013 e o [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Lync Server 2013", em.</span><span class="sxs-lookup"><span data-stu-id="765e3-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="765e3-111">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="765e3-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="765e3-112">Você pode exibir ou modificar os parâmetros do modo de exibição de galeria usando o painel de controle do Lync Server 2013 ou usando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="765e3-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="765e3-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="765e3-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="765e3-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="765e3-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="765e3-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="765e3-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="765e3-116">Configurar o modo de exibição de galeria com as seguintes configurações de política de conferência:</span><span class="sxs-lookup"><span data-stu-id="765e3-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="765e3-117">**AllowMultiview**   esse parâmetro controla se um usuário tem permissão para organizar a galeria e exibir conferências de vídeo.</span><span class="sxs-lookup"><span data-stu-id="765e3-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="765e3-118">Esse parâmetro se aplica a reuniões agendadas e ad hoc criadas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="765e3-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="765e3-119">Exemplos</span><span class="sxs-lookup"><span data-stu-id="765e3-119">Examples:</span></span>
    
      - <span data-ttu-id="765e3-120">Esse parâmetro é definido como true para o usuário A, que é hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="765e3-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="765e3-121">Reuniões organizadas pelo usuário A permitem que os usuários ingressem e recebam vários fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="765e3-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="765e3-122">Esse parâmetro é definido como false para o usuário B, que é hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="765e3-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="765e3-123">As reuniões organizadas pelo usuário B têm um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="765e3-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="765e3-124">Esse parâmetro determina quem pode organizar reuniões que permitem vários fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="765e3-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="765e3-125">Participantes em reuniões que permitem vários fluxos de vídeo podem ou não ter permissão para receber vários fluxos de vídeo com base em suas permissões individuais (consulte a descrição para o parâmetro EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="765e3-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="765e3-126">**EnableMultiviewJoin**   esse parâmetro controla se um participante de uma reunião recebe a experiência de exibição de vídeo de galeria em reuniões que o permitem.</span><span class="sxs-lookup"><span data-stu-id="765e3-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="765e3-127">Esse parâmetro controla a experiência do usuário em qualquer reunião na qual ele ou ela participa.</span><span class="sxs-lookup"><span data-stu-id="765e3-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="765e3-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="765e3-128">Examples:</span></span>
    
      - <span data-ttu-id="765e3-129">Esse parâmetro é definido como true para o usuário C. o usuário C pode receber vários fluxos de vídeo ao participar de uma reunião organizada ou iniciada pelo usuário A. o usuário C recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010 quando participar de uma reunião organizada ou iniciada pelo usuário B.</span><span class="sxs-lookup"><span data-stu-id="765e3-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="765e3-130">Esse parâmetro é definido como false para o usuário D. o usuário D recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010 quando estiver participando de qualquer reunião organizada pelo usuário A ou o usuário B.</span><span class="sxs-lookup"><span data-stu-id="765e3-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="765e3-131">O procedimento a seguir é um exemplo de como usar o Shell de gerenciamento do Lync Server para habilitar a conferência de vídeo do modo de exibição de galeria.</span><span class="sxs-lookup"><span data-stu-id="765e3-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="765e3-132">Para modificar a política de conferência para a Galeria exibir videoconferência</span><span class="sxs-lookup"><span data-stu-id="765e3-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="765e3-133">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="765e3-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="765e3-134">Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:</span><span class="sxs-lookup"><span data-stu-id="765e3-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

