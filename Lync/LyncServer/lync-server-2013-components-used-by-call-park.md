---
title: 'Lync Server 2013: Componentes usados pelo Estacionamento de Chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="e3596-102">Componentes usados pelo Estacionamento de Chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3596-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3596-103">_**Tópico da última modificação:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="e3596-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="e3596-104">O aplicativo de estacionamento de chamadas é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e3596-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e3596-105">Para habilitar o estacionamento de chamadas, configure a política de voz.</span><span class="sxs-lookup"><span data-stu-id="e3596-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="e3596-106">Os seguintes componentes do Lync Server 2013 suportam o aplicativo de estacionamento de chamadas:</span><span class="sxs-lookup"><span data-stu-id="e3596-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="e3596-107">\*\*\*\*   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="e3596-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="e3596-108">O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e3596-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="e3596-109">**Aplicativo de estacionamento de chamadas**   o aplicativo de estacionamento de chamadas é um dos aplicativos de comunicação unificada hospedados pelo serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e3596-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="e3596-110">Ela é incluída automaticamente durante a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e3596-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e3596-111">Ligue para parques e recupere chamadas e gerencie órbitas de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="e3596-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="e3596-112">**Música-em reter-arquivo**   se a música estiver habilitada, o arquivo de música será reproduzido enquanto uma chamada estiver estacionada.</span><span class="sxs-lookup"><span data-stu-id="e3596-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="e3596-113">Um arquivo de música padrão é incluído quando o aplicativo de estacionamento de chamada é instalado.</span><span class="sxs-lookup"><span data-stu-id="e3596-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="e3596-114">**Repositório de arquivos**   o aplicativo parque de chamadas usa o repositório de arquivos para armazenar arquivos de áudio personalizados.</span><span class="sxs-lookup"><span data-stu-id="e3596-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="e3596-115">**Painel de controle do Lync Server**   você pode usar o painel de controle do Lync Server para configurar a tabela órbita do estacionamento de chamada e habilitar o parque de chamadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e3596-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="e3596-116">**Shell de gerenciamento do Lync Server**   todas as configurações de aplicativo para estacionamento de chamadas podem ser realizadas usando cmdlets do shell do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3596-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

