---
title: 'Lync Server 2013: definindo seus requisitos para servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504298"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="17a51-102">Definindo os requisitos de sua organização para o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17a51-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17a51-103">_**Última modificação do tópico:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="17a51-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="17a51-104">Antes de implantar o servidor de chat persistente para sua organização, é essencial considerar as seguintes perguntas importantes para otimizar sua implantação:</span><span class="sxs-lookup"><span data-stu-id="17a51-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="17a51-105">Quem (perfil do usuário) deve ser habilitado para o servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="17a51-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="17a51-106">O servidor de chat persistente está habilitado por uma política que pode ser definida em um nível global, de site, de pool ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="17a51-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="17a51-107">Quantos usuários (escala) devem ser habilitados para o servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="17a51-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="17a51-108">O servidor de chat persistente oferece suporte a 150.000 usuários provisionados (habilitados por política) e um máximo de 80.000 usuários simultâneos usando o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="17a51-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="17a51-109">Um único servidor de chat persistente pode suportar 20.000 usuários conectados e um único pool de servidor de chat persistente pode ter até quatro servidores ativos para um total de 80.000 usuários conectados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="17a51-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="17a51-110">Você está migrando de uma versão anterior do servidor de chat de grupo ou está implantando o servidor de chat persistente pela primeira vez?</span><span class="sxs-lookup"><span data-stu-id="17a51-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="17a51-111">Há requisitos de conformidade?</span><span class="sxs-lookup"><span data-stu-id="17a51-111">Are there compliance requirements?</span></span> <span data-ttu-id="17a51-112">O servidor de chat persistente oferece suporte à conformidade.</span><span class="sxs-lookup"><span data-stu-id="17a51-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="17a51-113">O serviço de conformidade é executado no servidor de front-end do servidor de chat persistente, em oposição ao requisito para um computador separado nas implantações anteriores do servidor de chat de grupo.</span><span class="sxs-lookup"><span data-stu-id="17a51-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="17a51-114">A conformidade é opcional e, se escolhida, requer um banco de dados de conformidade que deve ser configurado para armazenar dados e eventos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="17a51-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="17a51-115">Você também pode configurar um adaptador para obter os dados do banco de dados de conformidade e convertê-los em outro formato (como arquivos XML ou arquivos mortos hospedados no Exchange).</span><span class="sxs-lookup"><span data-stu-id="17a51-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="17a51-p104">Como você deseja controlar escopos, limites éticos e acesso? É possível definir as **Categorias** para segregar esses limites e escolher quem estará habilitado para estar nas salas que forem criadas para cada uma dessas categorias.</span><span class="sxs-lookup"><span data-stu-id="17a51-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="17a51-p105">Como você deseja controlar quem pode criar salas? É possível configurar em **Criadores**, de forma adequada para a suas categorias, quem pode criar salas. Os criadores podem atribuir outros membros como **Gerentes de Sala de Chat** para gerenciamento contínuo das salas (adicionando ou removendo membros adicionais), de acordo com o escopo para **AllowedMembers/DeniedMembers** configurados por categoria.</span><span class="sxs-lookup"><span data-stu-id="17a51-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="17a51-121">Como você deseja criar salas?</span><span class="sxs-lookup"><span data-stu-id="17a51-121">How do you want to create rooms?</span></span> <span data-ttu-id="17a51-122">O servidor de chat persistente fornece um recurso baseado na Web para a criação e o gerenciamento de salas.</span><span class="sxs-lookup"><span data-stu-id="17a51-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="17a51-123">Isso pode ser iniciado no cliente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="17a51-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="17a51-124">Você pode optar por definir uma solução personalizada (usando o Software Development Kit (SDK) do servidor de chat persistente que implementa seus requisitos de negócios e fluxos de trabalho e configura o servidor de chat persistente para direcionar os usuários para sua solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="17a51-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="17a51-125">Que tipo de suplementos você deseja provisionar?</span><span class="sxs-lookup"><span data-stu-id="17a51-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="17a51-126">Os **suplementos** aprimoram a experiência na sala aproveitando o painel de extensibilidade no cliente do Lync 2013 para fornecer contexto relevante à sala.</span><span class="sxs-lookup"><span data-stu-id="17a51-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="17a51-127">É possível escolher quais suplementos gerais podem ser mais úteis (por exemplo, o site da sua empresam documentos de colaboração interna e etc.).</span><span class="sxs-lookup"><span data-stu-id="17a51-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="17a51-128">Os gerentes das salas de chat podem escolher um dos suplementos registrados e associá-lo às salas, se desejado.</span><span class="sxs-lookup"><span data-stu-id="17a51-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="17a51-129">Quais tipos de requisitos de alta disponibilidade e recuperação de desastres você tem?</span><span class="sxs-lookup"><span data-stu-id="17a51-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="17a51-130">O servidor de chat persistente suporta o espelhamento do SQL Server e o cluster do SQL Server para alta disponibilidade e oferece suporte a até 8 servidores (4 ativos e 4 em espera) em um pool estendido com o envio de logs do SQL Server para recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="17a51-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="17a51-131">Há requisitos da regulamentação?</span><span class="sxs-lookup"><span data-stu-id="17a51-131">Are there regulatory requirements?</span></span> <span data-ttu-id="17a51-132">Se sua empresa estiver em um país/região onde os dados precisam ser mantidos no país, talvez você precise implantar vários pools de servidores de chat persistentes, cada local em uma geografia específica.</span><span class="sxs-lookup"><span data-stu-id="17a51-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="17a51-133">Uma sala, uma categoria ou um suplemento não abrange pools, ele pertence a apenas um pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="17a51-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="17a51-134">Você pode gerenciar o conjunto de categorias, suplementos e salas para cada pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="17a51-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="17a51-135">Os usuários podem ser configurados para ter acesso a salas em um ou mais pools usando o escopo Membros permitidos de categoria ou o escopo de associação da sala, dependendo de como projetar suas categorias.</span><span class="sxs-lookup"><span data-stu-id="17a51-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17a51-136">Ter vários pools de servidores de chat persistente não dá mais escala (você ainda pode ter apenas 80.000 usuários conectados simultaneamente em todos os pools de servidores de chat persistentes).</span><span class="sxs-lookup"><span data-stu-id="17a51-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="17a51-137">O principal motivo para o suporte a vários pools de servidores de chat persistente é dar suporte a questões regulamentares.</span><span class="sxs-lookup"><span data-stu-id="17a51-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

