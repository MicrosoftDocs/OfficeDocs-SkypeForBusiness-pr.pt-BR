---
title: 'Lync Server 2013: requisitos técnicos para o aplicativo comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54371acb29bcc7d9b6581cbfd26199888dcfe893
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536098"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="596c1-102">Requisitos técnicos para o aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="596c1-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="596c1-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="596c1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="596c1-104">Esta seção descreve os seguintes requisitos técnicos para o aplicativo de comunicado:</span><span class="sxs-lookup"><span data-stu-id="596c1-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="596c1-105">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="596c1-105">Hardware requirements</span></span>

  - <span data-ttu-id="596c1-106">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="596c1-106">Software requirements</span></span>

  - <span data-ttu-id="596c1-107">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="596c1-107">Port requirements</span></span>

  - <span data-ttu-id="596c1-108">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="596c1-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="596c1-109">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="596c1-109">Hardware Requirements</span></span>

<span data-ttu-id="596c1-110">O aplicativo de comunicado tem os mesmos requisitos de hardware que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="596c1-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="596c1-111">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="596c1-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="596c1-112">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="596c1-112">Software Requirements</span></span>

<span data-ttu-id="596c1-113">O aplicativo de comunicado tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="596c1-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="596c1-114">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="596c1-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="596c1-115">Todos os servidores front-end ou servidores Standard Edition que executam o aplicativo de anúncio devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="596c1-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="596c1-116">Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="596c1-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="596c1-117">O tempo de execução do Windows Media Format ou o Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que o aplicativo de anúncio reproduz para anúncios e música.</span><span class="sxs-lookup"><span data-stu-id="596c1-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="596c1-118">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="596c1-118">Port Requirements</span></span>

<span data-ttu-id="596c1-119">O aplicativo de comunicado usa a seguinte porta:</span><span class="sxs-lookup"><span data-stu-id="596c1-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="596c1-120">**Porta 5071**     Usado para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="596c1-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="596c1-121">Essa porta é a definição padrão, que você pode modificar usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="596c1-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="596c1-122">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="596c1-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="596c1-123">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="596c1-123">Audio File Requirements</span></span>

<span data-ttu-id="596c1-124">O aplicativo de anúncio suporta o formato de arquivo Wave (. wav) e o formato de arquivo de áudio do Windows Media (. WMA) para música e comunicados.</span><span class="sxs-lookup"><span data-stu-id="596c1-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="596c1-125">Os requisitos de arquivo de áudio para o aplicativo de comunicado são os mesmos do aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="596c1-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="596c1-126">Para obter detalhes, consulte [Technical Requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="596c1-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

