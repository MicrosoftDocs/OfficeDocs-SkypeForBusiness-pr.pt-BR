---
title: 'Lync Server 2013: Configurando os computadores do Lync Server que serão monitorados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71188be470d6f2d561a068840c3cfee9e3e5ad9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="e8edc-102">Configurando os computadores do Lync Server que serão monitorados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8edc-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8edc-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e8edc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e8edc-104">Como o Lync Server 2013 não usa o processo de descoberta central usado no Microsoft Lync Server 2010, cada computador do Lync Server 2013 que você deseja monitorar deve ser capaz de relatar automaticamente sua existência ao servidor de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="e8edc-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="e8edc-105">Para que isso seja possível, é necessário instalar os arquivos do agente Operations Manager em cada computador a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="e8edc-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="e8edc-106">Após os arquivos do agente serem instalados, será necessário configurar o computador para agir como um proxy do System Center.</span><span class="sxs-lookup"><span data-stu-id="e8edc-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="e8edc-107">Observe que esses procedimentos devem ser executados depois que você instalou e configurou o Lync Server nesses computadores.</span><span class="sxs-lookup"><span data-stu-id="e8edc-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

