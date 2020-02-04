---
title: 'Lync Server 2013: Preparando seu ambiente para VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a3fb2563e287f24d49c23a468b4a44528707b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="05f6b-102">Preparando seu ambiente no Lync Server 2013 para VDI</span><span class="sxs-lookup"><span data-stu-id="05f6b-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05f6b-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="05f6b-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="05f6b-104">Para preparar o ambiente para o plug-in VDI do Lync, o administrador deve executar as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="05f6b-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="05f6b-105">No Lync Server 2013, certifique-se de que EnableMediaRedirection está definido como TRUE para todos os usuários do VDI.</span><span class="sxs-lookup"><span data-stu-id="05f6b-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="05f6b-106">Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="05f6b-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="05f6b-107">No computador do Data Center, instale o cliente do Lync 2013 em todas as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="05f6b-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="05f6b-108">Nos computadores locais, instale o plug-in VDI do Lync.</span><span class="sxs-lookup"><span data-stu-id="05f6b-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

