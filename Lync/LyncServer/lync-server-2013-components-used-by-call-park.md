---
title: 'Lync Server 2013: componentes usados pelo estacionamento de chamadas'
description: 'Lync Server 2013: componentes usados pelo estacionamento de chamadas.'
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
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576767"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="fa945-103">Componentes usados pelo estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa945-103">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa945-104">_**Última modificação do tópico:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="fa945-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="fa945-105">O aplicativo de estacionamento de chamada é instalado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fa945-105">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fa945-106">Habilite o estacionamento de chamadas Configurando a política de voz.</span><span class="sxs-lookup"><span data-stu-id="fa945-106">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="fa945-107">Os seguintes componentes do Lync Server 2013 suportam o aplicativo de estacionamento de chamada:</span><span class="sxs-lookup"><span data-stu-id="fa945-107">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="fa945-108">**Serviço**     de aplicativo O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="fa945-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="fa945-109">O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fa945-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="fa945-110">Aplicativo de estacionamento de **chamada**     O aplicativo de estacionamento de chamada é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fa945-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="fa945-111">Ele é incluído automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fa945-111">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fa945-112">Parques de estacionamento de chamada e recupera chamadas e gerencia órbitas de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fa945-112">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="fa945-113">Arquivos de música **em espera**     Se a música estiver habilitada, o arquivo de música será tocado enquanto uma chamada estiver estacionada.</span><span class="sxs-lookup"><span data-stu-id="fa945-113">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="fa945-114">Um arquivo de música padrão é incluído quando o aplicativo de estacionamento de chamada é instalado.</span><span class="sxs-lookup"><span data-stu-id="fa945-114">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="fa945-115">**Repositório**     de arquivos O aplicativo de estacionamento de chamada usa o repositório de arquivos para armazenar arquivos de áudio personalizados.</span><span class="sxs-lookup"><span data-stu-id="fa945-115">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="fa945-116">Painel de controle **do Lync Server**     Você pode usar o painel de controle do Lync Server para configurar a tabela de órbita de estacionamento de chamada e para habilitar o estacionamento de chamada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="fa945-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="fa945-117">Shell de gerenciamento **do Lync Server**     Todas as configurações de aplicativo de estacionamento de chamadas podem ser realizadas usando os cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa945-117">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

