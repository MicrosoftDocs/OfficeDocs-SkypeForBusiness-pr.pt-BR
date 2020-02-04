---
title: 'Lync Server 2013: Componentes usados pelo Grupo de Respostas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="9c8b9-102">Componentes usados pelo Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c8b9-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c8b9-103">_**Tópico da última modificação:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9c8b9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9c8b9-104">O aplicativo grupo de resposta é habilitado automaticamente quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9c8b9-105">Esta seção descreve os componentes que dão suporte ao aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="9c8b9-106">Componentes do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="9c8b9-106">Response Group Components</span></span>

<span data-ttu-id="9c8b9-107">Os seguintes componentes do Microsoft Lync Server 2013 suportam o aplicativo do grupo de resposta:</span><span class="sxs-lookup"><span data-stu-id="9c8b9-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="9c8b9-108">\*\*\*\*   O serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada, como o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="9c8b9-109">O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="9c8b9-110">**Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicação unificada hospedados pelo serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="9c8b9-111">Ela é incluída automaticamente quando você implanta o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="9c8b9-112">O aplicativo grupo de resposta roteia e enfileira chamadas recebidas para grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="9c8b9-113">**Pacote de idiomas**   um pacote de idiomas é necessário para dar suporte a conversão de texto em fala e reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="9c8b9-114">Essas tecnologias de fala são usadas quando você configura mensagens, como a mensagem de boas-vindas e outros avisos e perguntas e respostas de reação interativas de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="9c8b9-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="9c8b9-115">Por padrão, os 26 pacotes de idiomas com suporte são instalados quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9c8b9-116">**Arquivos de áudio**   os arquivos de áudio são usados para mensagens e música em espera.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="9c8b9-117">\*\*\*\*   Grupo de resposta do repositório de arquivos usa o repositório de arquivos para armazenar arquivos de áudio.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="9c8b9-118">Vários pools de grupos de resposta podem usar a mesma instância do repositório de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="9c8b9-119">**Ferramenta de configuração do grupo de resposta**   a ferramenta de configuração do grupo de resposta é uma ferramenta baseada na Web que é usada para criar e configurar grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="9c8b9-120">A ferramenta de configuração de grupo de resposta é incluída durante a instalação de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="9c8b9-121">**Painel de controle do Microsoft Lync Server 2013**   você pode usar o painel de controle do Lync Server para configurar e configurar filas e grupos de agente para grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="9c8b9-122">**Shell de gerenciamento do Lync Server**   todas as configurações do grupo de resposta podem ser configuradas usando cmdlets do shell do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="9c8b9-123">**Os agentes formais do Microsoft Lync 2013**   (agentes que são necessários para entrar no grupo antes de aceitarem chamadas para o grupo) usam o Lync 2013 para entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="9c8b9-124">Se um grupo de agente estiver configurado para agentes formais, os agentes clicarão em um item de menu no Lync 2013 para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="9c8b9-125">\*\*\*\*   Os serviços Web de serviços Web são necessários para a ferramenta de configuração de grupo de resposta, o console de entrada e de saída dos agentes, o painel de controle do Lync Server e o serviço Web de cliente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="9c8b9-126">\*\*\*\*   Aplicativo de grupo de resposta do serviço Web de cliente de grupo de resposta fornece um serviço Web de cliente, que pode ser usado por aplicativos de terceiros para recuperar informações sobre agentes, associação de grupo de agente, status de entrada do agente, status da chamada para grupos e os grupos que dão suporte a chamadas anônimas.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="9c8b9-127">Lync 2013 e Lync 2010 Attendant use o serviço Web de cliente de grupo de resposta para recuperar a lista de grupos de resposta que os agentes podem usar para fazer chamadas anônimas.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="9c8b9-128">O serviço Web cliente é incluído durante a instalação de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="9c8b9-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

