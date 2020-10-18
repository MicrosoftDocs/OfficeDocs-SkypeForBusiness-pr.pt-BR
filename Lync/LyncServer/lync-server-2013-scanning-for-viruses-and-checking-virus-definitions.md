---
title: 'Lync Server 2013: verificação de vírus e verificação de definições de vírus'
description: 'Lync Server 2013: verificação de vírus e verificação de definições de vírus.'
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
ms.openlocfilehash: c06b08b5e902857e95cdefc206cdbfa860ef748c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578647"
---
# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="b29bd-103">Verificação de vírus e verificação de definições de vírus no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b29bd-103">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b29bd-104">_**Última modificação do tópico:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="b29bd-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="b29bd-105">É altamente recomendável instalar um produto antivírus de nível de IM.</span><span class="sxs-lookup"><span data-stu-id="b29bd-105">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="b29bd-106">O IM é uma fonte conhecida para espalhar rapidamente os softwares de vírus e mal-intencionados por toda a organização.</span><span class="sxs-lookup"><span data-stu-id="b29bd-106">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="b29bd-107">O Microsoft Forefront® Security para Lync Server oferece verificação de vários mecanismos com vírus, software mal-intencionado, proteção de filtro de arquivo e palavra-chave e integração perfeita com o Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="b29bd-107">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="b29bd-108">Além do Forefront Security para Lync Server, também é altamente recomendável instalar uma solução de nível de arquivo e antivírus para proteger o sistema de arquivos do servidor.</span><span class="sxs-lookup"><span data-stu-id="b29bd-108">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="b29bd-109">Manter os mecanismos de scanner e as definições de vírus atualizados é muito importante.</span><span class="sxs-lookup"><span data-stu-id="b29bd-109">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="b29bd-110">A configuração e o monitoramento da integridade das atualizações garantem que as informações de verificação mais recentes estejam sendo usadas para proteger o Office Communications Server e o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b29bd-110">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b29bd-111">Ao usar um software antivírus de terceiro nível de arquivo em um servidor que executa o Lync Server 2013 e o Forefront Security para Lync Server, certifique-se de que as pastas nas quais o Forefront Security para Lync Server e o Lync Server estão instaladas não sejam verificadas, para evitar a corrupção.</span><span class="sxs-lookup"><span data-stu-id="b29bd-111">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="b29bd-112">Para obter a lista completa de exclusões, consulte <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A> .</span><span class="sxs-lookup"><span data-stu-id="b29bd-112">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

