---
title: 'Lync Server 2013: verificação de vírus e verificação de definições de vírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bc6704329dbc124bb61f779bf773a1f55bd72d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="d8287-102">Verificação de vírus e verificação de definições de vírus no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8287-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8287-103">_**Última modificação do tópico:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="d8287-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="d8287-104">É altamente recomendável instalar um produto antivírus de nível de IM.</span><span class="sxs-lookup"><span data-stu-id="d8287-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="d8287-105">O IM é uma fonte conhecida para espalhar rapidamente os softwares de vírus e mal-intencionados por toda a organização.</span><span class="sxs-lookup"><span data-stu-id="d8287-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="d8287-106">O Microsoft Forefront® Security para Lync Server oferece verificação de vários mecanismos com vírus, software mal-intencionado, proteção de filtro de arquivo e palavra-chave e integração perfeita com o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="d8287-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="d8287-107">Além do Forefront Security para Lync Server, também é altamente recomendável instalar uma solução de nível de arquivo e antivírus para proteger o sistema de arquivos do servidor.</span><span class="sxs-lookup"><span data-stu-id="d8287-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="d8287-108">Manter os mecanismos de scanner e as definições de vírus atualizados é muito importante.</span><span class="sxs-lookup"><span data-stu-id="d8287-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="d8287-109">A configuração e o monitoramento da integridade das atualizações garantem que as informações de verificação mais recentes estejam sendo usadas para proteger o Office Communications Server e o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d8287-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d8287-110">Ao usar um software antivírus de terceiro nível de arquivo em um servidor que executa o Lync Server 2013 e o Forefront Security para Lync Server, certifique-se de que as pastas nas quais o Forefront Security para Lync Server e o Lync Server estão instaladas não sejam verificadas, para evitar sua corrupção.</span><span class="sxs-lookup"><span data-stu-id="d8287-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="d8287-111">Para obter a lista completa de exclusões, consulte <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span><span class="sxs-lookup"><span data-stu-id="d8287-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

