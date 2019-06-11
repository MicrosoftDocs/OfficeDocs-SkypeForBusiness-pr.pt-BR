---
title: Gerenciar Lync Server 2013, Servidor de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de49e9843c5243457d1c4d736d9bfeda246f042e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="fabcc-102">Gerenciar Lync Server 2013, Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="fabcc-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fabcc-103">_**Tópico da última modificação:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="fabcc-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="fabcc-104">Você pode usar o Lync Server 2013, o servidor de chat persistente para permitir que vários usuários participem de conversas em que eles publicarem e acessem o conteúdo sobre tópicos específicos, incluindo texto, links e arquivos.</span><span class="sxs-lookup"><span data-stu-id="fabcc-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="fabcc-105">Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que ele continua disponível após o término de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="fabcc-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="fabcc-106">O conteúdo de salas de chat persistente consiste basicamente em breves mensagens de texto, embora possa incluir mensagens mais longas, chamadas como *matérias*e também hiperlinks, emoticons e documentos carregados.</span><span class="sxs-lookup"><span data-stu-id="fabcc-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fabcc-107">O download e o download de arquivos não são compatíveis com o cliente Lync 2013; no entanto, ele ainda tem suporte do Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fabcc-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="fabcc-108">O cliente de chat em grupo herdado pode publicar e exibir arquivos, mas se a mesma sala de chat for acessada pelo cliente do Lync 2013, ele não poderá acessar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="fabcc-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="fabcc-109">O acesso a uma sala de chat é controlado por uma lista de membros.</span><span class="sxs-lookup"><span data-stu-id="fabcc-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="fabcc-110">Todo o histórico de salas de chat está disponível para qualquer membro para análise cronológica ou pesquisa de texto completo.</span><span class="sxs-lookup"><span data-stu-id="fabcc-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="fabcc-111">Para obter detalhes sobre como usar o cliente de chat persistente, consulte [planejando clientes no Lync server 2013](lync-server-2013-planning-for-clients.md) na documentação de planejamento e implantando [clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fabcc-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="fabcc-112">Ao configurar o servidor de chat persistente para a sua organização, você especifica a configuração inicial durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="fabcc-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="fabcc-113">No entanto, pode haver ocasiões em que você queira alterar a maneira de implementar o suporte persistente do chat Server.</span><span class="sxs-lookup"><span data-stu-id="fabcc-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="fabcc-114">Por exemplo, talvez você precise configurar o suporte e os controles persistentes do servidor de chat de forma diferente para uma equipe específica ou um grupo dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="fabcc-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="fabcc-115">Esta seção fornece informações e procedimentos para ajudá-lo a personalizar a implantação do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="fabcc-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="fabcc-116">Para obter detalhes sobre os recursos e funcionalidades que você pode configurar para o servidor de chat persistente, consulte [definindo os requisitos da sua organização para o servidor de chat persistente no Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) na documentação de planejamento e [como o chat persistente O servidor funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="fabcc-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="fabcc-117">Para obter detalhes sobre a implantação do servidor de chat persistente para o Lync Server 2013, consulte Implantando o [servidor de chat persistente no Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fabcc-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fabcc-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fabcc-118">In This Section</span></span>

  - [<span data-ttu-id="fabcc-119">Como o servidor de chat persistente funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabcc-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="fabcc-120">Usando categorias para administrar o Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="fabcc-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="fabcc-121">Entendendo associações do Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="fabcc-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="fabcc-122">Práticas recomendadas do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="fabcc-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="fabcc-123">Gerenciando categotias, salas e suplementos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabcc-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="fabcc-124">Gerenciando acesso do usuário de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabcc-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="fabcc-125">Operação e manutenção do sistema de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fabcc-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

