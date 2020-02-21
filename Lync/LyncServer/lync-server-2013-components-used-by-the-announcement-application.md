---
title: 'Lync Server 2013: componentes usados pelo aplicativo comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61f0de957889f108ff7b7cec3ad71e984fd61f11
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="bd89e-102">Componentes usados pelo aplicativo comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd89e-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd89e-103">_**Última modificação do tópico:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="bd89e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="bd89e-104">No Lync Server 2013, o aplicativo de anúncio é um componente do aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="bd89e-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="bd89e-105">Ao implantar o Enterprise Voice, o aplicativo de anúncio é automaticamente instalado e ativado junto com o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="bd89e-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="bd89e-106">Esta seção descreve os componentes que dão suporte ao aplicativo comunicado.</span><span class="sxs-lookup"><span data-stu-id="bd89e-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="bd89e-107">Componentes de Aplicativo de Comunicado</span><span class="sxs-lookup"><span data-stu-id="bd89e-107">Announcement Application Components</span></span>

<span data-ttu-id="bd89e-108">Os seguintes componentes do Lync Server oferecem suporte ao aplicativo announcement:</span><span class="sxs-lookup"><span data-stu-id="bd89e-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="bd89e-109">\*\*\*\*   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="bd89e-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="bd89e-110">O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bd89e-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="bd89e-111">**Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bd89e-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="bd89e-112">Quando um intervalo de números de telefone não atribuído é configurado para rotear para um comunicado, o aplicativo grupo de resposta é necessário para rotear as chamadas feitas para o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="bd89e-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="bd89e-113">(O aplicativo grupo de resposta não é necessário se todos os intervalos estiverem configurados para rotear para a Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd89e-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="bd89e-114">\*\*\*\*   Arquivos de áudio os arquivos de áudio são usados para os comunicados.</span><span class="sxs-lookup"><span data-stu-id="bd89e-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="bd89e-115">**Repositório de arquivos**   o aplicativo de comunicado usa o repositório de arquivos para armazenar seus arquivos de áudio.</span><span class="sxs-lookup"><span data-stu-id="bd89e-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="bd89e-116">**Painel de controle do Lync Server**   você pode usar o painel de controle do Lync Server para configurar a tabela de número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="bd89e-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="bd89e-117">**Shell de gerenciamento do Lync Server**   você pode usar os cmdlets do Shell de gerenciamento do Lync Server para definir as configurações de anúncio e a tabela de número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="bd89e-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

