---
title: 'Lync Server 2013: Planejamento de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aff3eef21ca150f4ad6fc9bb2358c2ac81680fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="bc018-102">Planejamento de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-102">Planning for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc018-103">_**Tópico da última modificação:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="bc018-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="bc018-104">O Lync Server 2013 oferece um conjunto avançado de recursos de conferência:</span><span class="sxs-lookup"><span data-stu-id="bc018-104">Lync Server 2013 offers a rich set of conferencing capabilities:</span></span>

  - <span data-ttu-id="bc018-105">Conferência na Web, que inclui colaboração de documentos, compartilhamento de aplicativos e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bc018-105">Web conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span> <span data-ttu-id="bc018-106">O Lync Server 2013 usa o Office Web Apps e o Office Web Apps Server para lidar com o compartilhamento e a renderização de apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bc018-106">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="bc018-107">Para obter detalhes sobre como instalar e configurar o Office Web Apps Server, consulte Configurando a [integração com o Office Web Apps Server e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="bc018-107">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="bc018-108">Conferência de áudio/vídeo (A/V), que permite que os usuários tenham conferências de áudio ou vídeo em tempo real sem a necessidade de serviços externos, como o serviço Microsoft Live Meeting ou uma ponte de áudio de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bc018-108">Audio/video (A/V) conferencing, which enables users to have real-time audio or video conferences without the need for external services such as the Microsoft Live Meeting service or a third-party audio bridge.</span></span>

  - <span data-ttu-id="bc018-109">Conferência discada, que permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem precisar de um provedor de serviços de audioconferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bc018-109">Dial-in conferencing, which allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring a third-party audio conferencing provider.</span></span>

  - <span data-ttu-id="bc018-110">Conferência de mensagens instantâneas (IM), em que mais de duas partes se comunicam em uma única sessão de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="bc018-110">Instant messaging (IM) conferencing, in which more than two parties communicate in a single IM session.</span></span> <span data-ttu-id="bc018-111">Para obter detalhes sobre a conferência de mensagem instantânea, consulte [planejando servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="bc018-111">For details about IM conferencing, see [Planning for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="bc018-112">O Lync Server 2013 suporta conferências programadas e conferências improvisadas.</span><span class="sxs-lookup"><span data-stu-id="bc018-112">Lync Server 2013 supports both scheduled conferences and impromptu conferences.</span></span>

<span data-ttu-id="bc018-113">Ao implantar o Lync Server 2013, o servidor front-end, você pode escolher se deseja implantar também a Webconferência, conferência A/V e recursos de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="bc018-113">When you deploy Lync Server 2013, Front End Server, you can choose whether to also deploy the web conferencing, A/V conferencing, and dial-in conferencing capabilities.</span></span> <span data-ttu-id="bc018-114">Os recursos de conferência de mensagem instantânea são sempre implantados automaticamente com os recursos de conversa de mensagem instantânea nos servidores front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc018-114">IM conferencing capabilities are always automatically deployed along with IM conversation capabilities on Lync Server 2013 Front End Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc018-115">Se sua implantação incluir reuniões organizadas usando os clientes do Office Communicator 2007 R2 (incluindo o console do Live Meeting ou o suplemento de conferência para o Microsoft Office Outlook), as reuniões terão as seguintes limitações após serem migradas para o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bc018-115">If your deployment includes meetings organized using Office Communicator 2007 R2 clients (including the Live Meeting console or Conferencing Add-in for Microsoft Office Outlook), the meetings will have the following limitations after they are migrated to Lync Server 2013:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bc018-116">Os usuários na reunião não poderão usar os recursos de colaboração de dados, incluindo a colaboração de documentos, o compartilhamento de aplicativos e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bc018-116">Users in the meeting will not be able to use data collaboration features, including document collaboration, application sharing, and desktop sharing.</span></span></P>
> <LI>
> <P><span data-ttu-id="bc018-117">Problemas de estabilidade podem surgir porque os clientes do Office Communicator 2007 R2 não são compatíveis com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc018-117">Stability issues may arise since Office Communicator 2007 R2 clients are not supported with Lync Server 2013.</span></span></P></LI></UL><span data-ttu-id="bc018-118">Para evitar esses problemas, reagende todas as reuniões organizadas usando o Office Communicator 2007 R2 clients with Outlook 2010 ou o Outlook 2013 usando o suplemento de reunião online do Lync 2010 ou o suplemento de reunião online para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bc018-118">To avoid these issues, reschedule any meeting organized using Office Communicator 2007 R2 clients with Outlook 2010 or Outlook 2013 using either the Online Meeting Add-in for Lync 2010 or Online Meeting Add-in for Lync 2013.</span></span>



</div>

<span data-ttu-id="bc018-119">As seções a seguir descrevem o que é necessário para implantar os vários tipos de recursos de conferência, incluindo o processo de planejamento, componentes, requisitos de hardware e software e o processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="bc018-119">The following sections describe what is required to deploy the various types of conferencing capabilities, including the planning process, components, hardware and software requirements, and the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc018-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bc018-120">In This Section</span></span>

  - [<span data-ttu-id="bc018-121">Visão geral de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-121">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)

  - [<span data-ttu-id="bc018-122">Definindo seus requisitos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-122">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [<span data-ttu-id="bc018-123">Componentes e topologias para conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-123">Components and topologies for conferencing in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [<span data-ttu-id="bc018-124">Requisitos técnicos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-124">Technical requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-conferencing.md)

  - [<span data-ttu-id="bc018-125">Lista de verificação de implantação para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-125">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [<span data-ttu-id="bc018-126">Suporte a reuniões grandes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc018-126">Support for large meetings in Lync Server 2013</span></span>](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

