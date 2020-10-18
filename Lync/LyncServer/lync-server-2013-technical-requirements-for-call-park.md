---
title: 'Lync Server 2013: requisitos técnicos para estacionamento de chamada'
description: 'Lync Server 2013: requisitos técnicos para estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577127"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="eb602-103">Requisitos técnicos para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb602-103">Technical requirements for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb602-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="eb602-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="eb602-105">Esta seção descreve os seguintes requisitos técnicos para estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="eb602-105">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="eb602-106">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="eb602-106">Hardware requirements</span></span>

  - <span data-ttu-id="eb602-107">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="eb602-107">Software requirements</span></span>

  - <span data-ttu-id="eb602-108">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="eb602-108">Port requirements</span></span>

  - <span data-ttu-id="eb602-109">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="eb602-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="eb602-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="eb602-110">Hardware Requirements</span></span>

<span data-ttu-id="eb602-111">O aplicativo de estacionamento de chamada tem os mesmos requisitos de hardware que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="eb602-111">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="eb602-112">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="eb602-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="eb602-113">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="eb602-113">Software Requirements</span></span>

<span data-ttu-id="eb602-114">O aplicativo de estacionamento de chamada tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="eb602-114">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="eb602-115">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="eb602-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="eb602-116">Todos os servidores front-end e servidores Standard Edition onde o aplicativo de estacionamento de chamada é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores que executam o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="eb602-116">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="eb602-117">Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="eb602-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="eb602-118">O tempo de execução do Windows Media Format ou o Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento de música em espera.</span><span class="sxs-lookup"><span data-stu-id="eb602-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="eb602-119">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="eb602-119">Port Requirements</span></span>

<span data-ttu-id="eb602-120">O aplicativo de estacionamento de chamada usa a seguinte porta:</span><span class="sxs-lookup"><span data-stu-id="eb602-120">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="eb602-121">**Porta 5075**     Usado para solicitações de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="eb602-121">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb602-122">Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="eb602-122">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="eb602-123">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb602-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="eb602-124">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="eb602-124">Audio File Requirements</span></span>

<span data-ttu-id="eb602-125">O aplicativo de estacionamento de chamada suporta apenas arquivos de áudio do Windows Media (. WMA) para música em espera.</span><span class="sxs-lookup"><span data-stu-id="eb602-125">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="eb602-126">É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="eb602-126">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="eb602-127">Para baixar o Expression Encoder 4, consulte "Expression Encoder 4" em [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="eb602-127">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="eb602-128">Use a ferramenta para converter o arquivo no formato .wma.</span><span class="sxs-lookup"><span data-stu-id="eb602-128">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="eb602-129">O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="eb602-129">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb602-130">O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="eb602-130">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

