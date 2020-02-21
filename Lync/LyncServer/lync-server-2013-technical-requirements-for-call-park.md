---
title: 'Lync Server 2013: requisitos técnicos para estacionamento de chamada'
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
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f36b9-102">Requisitos técnicos para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f36b9-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f36b9-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f36b9-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f36b9-104">Esta seção descreve os seguintes requisitos técnicos para estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="f36b9-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="f36b9-105">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="f36b9-105">Hardware requirements</span></span>

  - <span data-ttu-id="f36b9-106">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="f36b9-106">Software requirements</span></span>

  - <span data-ttu-id="f36b9-107">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="f36b9-107">Port requirements</span></span>

  - <span data-ttu-id="f36b9-108">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="f36b9-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f36b9-109">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="f36b9-109">Hardware Requirements</span></span>

<span data-ttu-id="f36b9-110">O aplicativo de estacionamento de chamada tem os mesmos requisitos de hardware que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f36b9-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="f36b9-111">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f36b9-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f36b9-112">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="f36b9-112">Software Requirements</span></span>

<span data-ttu-id="f36b9-113">O aplicativo de estacionamento de chamada tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f36b9-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="f36b9-114">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f36b9-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f36b9-115">Todos os servidores front-end e servidores Standard Edition onde o aplicativo de estacionamento de chamada é implantado devem ter o tempo de execução do Windows Media Format instalado para servidores executando o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores que executam o Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f36b9-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="f36b9-116">Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="f36b9-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="f36b9-117">O tempo de execução do Windows Media Format ou o Microsoft Media Foundation é necessário para arquivos de áudio do Windows Media (. WMA) que chamam o estacionamento de música em espera.</span><span class="sxs-lookup"><span data-stu-id="f36b9-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="f36b9-118">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="f36b9-118">Port Requirements</span></span>

<span data-ttu-id="f36b9-119">O aplicativo de estacionamento de chamada usa a seguinte porta:</span><span class="sxs-lookup"><span data-stu-id="f36b9-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="f36b9-120">**Porta 5075**   usada para solicitações de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="f36b9-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f36b9-121">Esta porta é uma configuração padrão, que pode ser alterado usando o cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f36b9-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="f36b9-122">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f36b9-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="f36b9-123">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="f36b9-123">Audio File Requirements</span></span>

<span data-ttu-id="f36b9-124">O aplicativo de estacionamento de chamada suporta apenas arquivos de áudio do Windows Media (. WMA) para música em espera.</span><span class="sxs-lookup"><span data-stu-id="f36b9-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="f36b9-125">É possível usar o Microsoft Expression Encoder 4 para personalizar arquivos de música em espera.</span><span class="sxs-lookup"><span data-stu-id="f36b9-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="f36b9-126">Para baixar o Expression Encoder 4, consulte "Expression Encoder 4" [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)em.</span><span class="sxs-lookup"><span data-stu-id="f36b9-126">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="f36b9-127">Use a ferramenta para converter o arquivo no formato .wma.</span><span class="sxs-lookup"><span data-stu-id="f36b9-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="f36b9-128">O formato recomendado para arquivos de música de espera do Estacionamento de Chamada é Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span><span class="sxs-lookup"><span data-stu-id="f36b9-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f36b9-129">O arquivo convertido é reproduzido no telefone somente a 16 kHz, mesmo que tenha sido gravado a 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="f36b9-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

