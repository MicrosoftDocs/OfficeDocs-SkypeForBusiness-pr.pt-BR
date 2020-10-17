---
title: Migrar o Servidor de Mediação
description: Migrar servidor de mediação.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31cc4c95f0e9c86b48594238218db22f3ec1a387
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570327"
---
# <a name="migrate-mediation-server"></a><span data-ttu-id="efd1d-103">Migrar o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="efd1d-103">Migrate Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efd1d-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="efd1d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="efd1d-105">Seu servidor de mediação é mesclado na topologia piloto do Lync Server 2013 quando você executa o assistente de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="efd1d-105">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="efd1d-106">No entanto, você configura o servidor de mediação do Lync Server 2013, depois que todos os usuários são migrados porque um pool do Office Communications Server 2007 R2 não pode se comunicar com um servidor de mediação 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efd1d-106">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="efd1d-107">Durante a migração lado a lado, o pool do Lync Server 2013 se comunica com o servidor de mediação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="efd1d-107">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="efd1d-108">Ao configurar seu servidor de mediação do Lync Server 2013, você também deve atualizar ou substituir seus gateways do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="efd1d-108">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="efd1d-109">Os gateways do Office Communications Server 2007 R2 não oferecem suporte ao Lync Server 2013 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="efd1d-109">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="efd1d-110">Você precisa implantar gateways certificados para o Lync Server 2013 e associá-los ao servidor de mediação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efd1d-110">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="efd1d-111">Esta etapa é necessária para que você possa encerrar completamente sua implantação do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="efd1d-111">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="efd1d-112">Os tópicos desta seção descrevem tarefas de configuração que você precisa realizar depois de concluir a migração do servidor de mediação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efd1d-112">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="efd1d-113">A transição do Servidor de mediação colocado para um Servidor de mediação independente é uma tarefa opcional.</span><span class="sxs-lookup"><span data-stu-id="efd1d-113">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="efd1d-114">Configurar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="efd1d-114">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="efd1d-115">Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efd1d-115">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="efd1d-116">Fazer a transição de um servidor de mediação posicionado para um servidor de mediação autônomo (opcional)</span><span class="sxs-lookup"><span data-stu-id="efd1d-116">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

