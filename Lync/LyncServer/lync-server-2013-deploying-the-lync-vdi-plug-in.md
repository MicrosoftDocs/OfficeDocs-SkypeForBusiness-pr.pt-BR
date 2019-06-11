---
title: 'Lync Server 2013: Implantando o plug-in Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b2e7ce89fe021c23da81f075aec3d1ce90e7b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="aa033-102">Implantando o plug-in Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa033-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa033-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="aa033-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="aa033-104">O cliente do Lync 2013 dá suporte a áudio e vídeo em um ambiente VDI (infraestrutura de área de trabalho virtual).</span><span class="sxs-lookup"><span data-stu-id="aa033-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="aa033-105">Um usuário pode conectar um dispositivo de áudio ou de vídeo (por exemplo, um fone de ouvido com microfone ou uma câmera) ao computador local (por exemplo, um cliente leve ou um computador redefinido).</span><span class="sxs-lookup"><span data-stu-id="aa033-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="aa033-106">O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está em execução na máquina virtual e participar de comunicações de áudio e vídeo em tempo real, como se o cliente estivesse em execução localmente.</span><span class="sxs-lookup"><span data-stu-id="aa033-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="aa033-107">O plug-in VDI do Lync é um aplicativo autônomo que é instalado no computador local e permite o uso de dispositivos de áudio e vídeo locais com o cliente Lync 2013 em execução na máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="aa033-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="aa033-108">O plug-in não requer que o Lync seja instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="aa033-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="aa033-109">Depois que o usuário entra no cliente do Lync 2013 em execução na máquina virtual, o Lync solicita que o usuário digite novamente suas credenciais para estabelecer uma conexão com o plug-in VDI do Lync que está em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="aa033-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="aa033-110">Depois que essa conexão for estabelecida, o usuário estará pronto para fazer e receber chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="aa033-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa033-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="aa033-111">In This Section</span></span>

  - [<span data-ttu-id="aa033-112">Pré-requisitos do plug-in Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa033-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="aa033-113">Preparando seu ambiente no Lync Server 2013 para VDI</span><span class="sxs-lookup"><span data-stu-id="aa033-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="aa033-114">Entrando e usando o Lync 2013 na máquina virtual</span><span class="sxs-lookup"><span data-stu-id="aa033-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="aa033-115">Solução de problemas do plug-in VDI do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa033-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="aa033-116">Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa033-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

