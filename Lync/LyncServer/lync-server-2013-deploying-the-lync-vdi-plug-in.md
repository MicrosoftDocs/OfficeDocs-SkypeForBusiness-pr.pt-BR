---
title: 'Lync Server 2013: Implantando o plug-in do Lync VDI'
description: 'Lync Server 2013: Implantando o plug-in do Lync VDI.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3addecb07f269e4524f3da835f479439639935ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557797"
---
# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="73047-103">Implantando o plug-in do Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73047-103">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73047-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="73047-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="73047-105">O cliente Lync 2013 oferece suporte a áudio e vídeo em um ambiente de infraestrutura de área de trabalho virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="73047-105">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="73047-106">Um usuário pode conectar um dispositivo de áudio ou vídeo (por exemplo, um fone de ouvido ou uma câmera) ao computador local (por exemplo, um computador cliente fino ou realocado).</span><span class="sxs-lookup"><span data-stu-id="73047-106">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="73047-107">O usuário pode se conectar à máquina virtual, entrar no cliente do Lync 2013 que está sendo executado na máquina virtual e participar de comunicações de áudio e vídeo em tempo real, como se o cliente estivesse sendo executado localmente.</span><span class="sxs-lookup"><span data-stu-id="73047-107">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="73047-108">O plug-in de VDI do Lync é um aplicativo autônomo que é instalado no computador local e permite o uso de dispositivos de áudio e vídeo locais com o cliente Lync 2013 em execução na máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="73047-108">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="73047-109">O plug-in não requer o Lync para ser instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="73047-109">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="73047-110">Depois que o usuário entrar no cliente do Lync 2013 que está sendo executado na máquina virtual, o Lync solicitará que o usuário insira novamente suas credenciais para estabelecer uma conexão com o plug-in VDI do Lync em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="73047-110">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="73047-111">Depois de estabelecer a conexão, o usuário está pronto para fazer e receber chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="73047-111">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73047-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="73047-112">In This Section</span></span>

  - [<span data-ttu-id="73047-113">Pré-requisitos do plug-in VDI do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73047-113">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="73047-114">Preparando seu ambiente do Lync Server 2013 para VDI</span><span class="sxs-lookup"><span data-stu-id="73047-114">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="73047-115">Entrar e usar o Lync 2013 na máquina virtual</span><span class="sxs-lookup"><span data-stu-id="73047-115">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="73047-116">Solucionando problemas do plug-in do Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73047-116">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="73047-117">Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73047-117">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

