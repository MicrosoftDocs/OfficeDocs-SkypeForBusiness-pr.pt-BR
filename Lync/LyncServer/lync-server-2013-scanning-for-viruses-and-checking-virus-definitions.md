---
title: 'Lync Server 2013: verificando vírus e verificando definições de vírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="1eee1-102">Procurando vírus e verificando definições de vírus no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eee1-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eee1-103">_**Tópico da última modificação:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="1eee1-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="1eee1-104">É altamente recomendável instalar um produto antivírus de nível de mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="1eee1-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="1eee1-105">As mensagens instantâneas são uma fonte bem conhecida para a disseminação rápida de vírus e software mal-intencionado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="1eee1-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="1eee1-106">O Microsoft Forefront® Security para Lync Server oferece verificação de vários mecanismos com vírus, software mal-intencionado, proteção de filtro de arquivo e de palavra-chave e integração perfeita com o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="1eee1-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="1eee1-107">Além do Forefront Security para Lync Server, também é altamente recomendável instalar uma solução de nível de arquivo e antivírus para proteger o sistema de arquivos do servidor.</span><span class="sxs-lookup"><span data-stu-id="1eee1-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="1eee1-108">Manter os mecanismos do scanner e as definições de vírus atualizados é muito importante.</span><span class="sxs-lookup"><span data-stu-id="1eee1-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="1eee1-109">A configuração e o monitoramento da integridade das atualizações garante que as informações de verificação mais recentes sejam usadas para proteger o Office Communications Server e o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1eee1-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1eee1-110">Ao usar um software antivírus de terceiros em nível de arquivo em um servidor que executa o Lync Server 2013 e o Forefront Security para Lync Server, certifique-se de que as pastas nas quais o Forefront Security para Lync Server e o Lync Server estejam instalados não sejam verificadas, para evitar seus danos.</span><span class="sxs-lookup"><span data-stu-id="1eee1-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="1eee1-111">Para obter a lista completa de exclusões, consulte <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span><span class="sxs-lookup"><span data-stu-id="1eee1-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

