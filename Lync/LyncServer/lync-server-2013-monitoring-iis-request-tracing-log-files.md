---
title: 'Lync Server 2013: monitorando arquivos de log de rastreamento de solicitação IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76e8734c8cef93191c5e7186240c1b78529916fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531918"
---
# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="0ac9f-102">Monitorar arquivos de log de rastreamento de solicitação IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac9f-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac9f-103">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="0ac9f-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="0ac9f-104">Ao habilitar o rastreamento de solicitação dos serviços de informações da Internet (IIS) para o Lync Server Mobility Service (MCX), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia.</span><span class="sxs-lookup"><span data-stu-id="0ac9f-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="0ac9f-105">O registro em log do rastreamento IIS está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0ac9f-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="0ac9f-106">Você deve monitorar os servidores front-end para verificar se eles não ficam sem espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="0ac9f-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="0ac9f-107">Por padrão, o IIS armazena os arquivos de log em% SystemDrive% \\ Inetpub logs de log \\ \\ .</span><span class="sxs-lookup"><span data-stu-id="0ac9f-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="0ac9f-108">Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ac9f-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="0ac9f-109">Para obter detalhes sobre o comando **httpLogging** , consulte [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927) .</span><span class="sxs-lookup"><span data-stu-id="0ac9f-109">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

