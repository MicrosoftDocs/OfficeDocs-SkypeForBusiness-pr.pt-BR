---
title: 'Lync Server 2013: Configurando a exibição da Galeria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68b4d884671de3ad4e46c7022df8ae0b3d5da09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="d1b81-102">Configurando o modo de exibição de galeria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1b81-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b81-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d1b81-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d1b81-104">No Lync Server 2013, configure a Galeria exibir videoconferência em política de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1b81-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="d1b81-105">O Modo de exibição de Galeria é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="d1b81-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="d1b81-106">Se você não deseja permitir o Modo de exibição de Galeria ou deseja permitir para alguns usuários apenas, você precisa desativar esse recurso na política de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1b81-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="d1b81-107">Quando o vídeo de um participante de conferência não está disponível, a experiência de exibição da Galeria de usuários pode ser aprimorada se você implantar fotos de alta resolução, um novo recurso no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b81-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="d1b81-108">As fotos de alta resolução fornecem uma alternativa para as fotos de contato de resolução menor e limitada armazenadas nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1b81-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="d1b81-109">As fotos de alta resolução são armazenadas na caixa de correio do Exchange 2013 de um usuário e, portanto, exigem que você integre o Lync Server 2013 com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b81-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="d1b81-110">Para obter detalhes, consulte o artigo de blog NextHop, "integrando o Exchange 2013 e o Lync [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)Server 2013" em.</span><span class="sxs-lookup"><span data-stu-id="d1b81-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1b81-111">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="d1b81-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="d1b81-112">Você pode exibir ou modificar os parâmetros de exibição da Galeria usando o painel de controle do Lync Server 2013 ou usando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d1b81-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="d1b81-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d1b81-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d1b81-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d1b81-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d1b81-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="d1b81-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="d1b81-116">Configure o Modo de exibição de Galeria com uma das configurações de política de conferência a seguir:</span><span class="sxs-lookup"><span data-stu-id="d1b81-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="d1b81-117">**AllowMultiview**   este parâmetro controla se um usuário tem permissão para organizar a Galeria exibir conferências de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d1b81-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="d1b81-118">Este parâmetro se aplica a reuniões programadas e ad-hoc criadas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="d1b81-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="d1b81-119">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="d1b81-119">Examples:</span></span>
    
      - <span data-ttu-id="d1b81-120">Esse parâmetro é definido como true para o usuário A, que é hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b81-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="d1b81-121">Reuniões organizadas pelo Usuário A permitem que os usuários participem e recebam diversos fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d1b81-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="d1b81-122">Esse parâmetro é definido como false para o usuário B, que é hospedado em um pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b81-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="d1b81-123">As reuniões organizadas pelo usuário B têm um único fluxo de vídeo semelhante à experiência de conferência de vídeo fornecida pelo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d1b81-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="d1b81-p106">Este parâmetro determina quem pode organizar reuniões que permitem vários fluxos de vídeo. Os participantes nas reuniões que permitem vários fluxos de vídeo podem ou não ter permissão para receber vários fluxos de vídeo, com base nas permissões individuais (consulte a descrição para o parâmetro EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="d1b81-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="d1b81-126">**EnableMultiviewJoin**   esse parâmetro controla se um participante de uma reunião recebe a experiência de vídeo da galeria em reuniões que o permitem.</span><span class="sxs-lookup"><span data-stu-id="d1b81-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="d1b81-127">Este parâmetro controla a experiência do usuário em qualquer reunião o qual ele participe.</span><span class="sxs-lookup"><span data-stu-id="d1b81-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="d1b81-128">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="d1b81-128">Examples:</span></span>
    
      - <span data-ttu-id="d1b81-129">Esse parâmetro é definido como true para o usuário C. o usuário C pode receber vários fluxos de vídeo ao participar de uma reunião organizada ou iniciada pelo usuário A. o usuário C recebe um único fluxo de vídeo semelhante à experiência de conferência de vídeo fornecida pelo Lync Server 2010 quando participar de uma reunião organizada ou iniciada pelo usuário B.</span><span class="sxs-lookup"><span data-stu-id="d1b81-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="d1b81-130">Esse parâmetro é definido como false para o usuário D. o usuário D recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecido pelo Lync Server 2010 ao participar de qualquer reunião organizada pelo usuário A ou usuário B.</span><span class="sxs-lookup"><span data-stu-id="d1b81-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="d1b81-131">O procedimento a seguir é um exemplo de uso do Shell de gerenciamento do Lync Server para habilitar a visualização da conferência de vídeo pela galeria.</span><span class="sxs-lookup"><span data-stu-id="d1b81-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="d1b81-132">Para modificar a política de conferência para conferência de vídeo no Modo de exibição de Galeria</span><span class="sxs-lookup"><span data-stu-id="d1b81-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="d1b81-133">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d1b81-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d1b81-134">Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:</span><span class="sxs-lookup"><span data-stu-id="d1b81-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

