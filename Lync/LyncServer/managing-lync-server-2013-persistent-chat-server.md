---
title: Gerenciar Lync Server 2013, Servidor de Chat Persistente
description: Gerenciando o Lync Server 2013, servidor de chat persistente.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544577"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="08f0b-103">Gerenciar Lync Server 2013, Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="08f0b-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08f0b-104">_**Última modificação do tópico:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="08f0b-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="08f0b-105">Você pode usar o servidor de chat persistente do Lync Server 2013 para permitir que vários usuários participem de conversas em que eles postam e acessem o conteúdo sobre tópicos específicos, incluindo texto, links e arquivos.</span><span class="sxs-lookup"><span data-stu-id="08f0b-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="08f0b-106">Embora os usuários possam se comunicar em tempo real durante a sessão, o conteúdo de cada sessão é permanente, o que significa que continuarrá disponível depois que a sessão for encerrada.</span><span class="sxs-lookup"><span data-stu-id="08f0b-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="08f0b-107">O conteúdo de salas de chat persistente consiste basicamente de mensagens de texto curtas, embora possa incluir mensagens mais longas, chamadas de *matérias*e também hiperlinks, emoticons e documentos carregados.</span><span class="sxs-lookup"><span data-stu-id="08f0b-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08f0b-108">Não há suporte para carregamento e download de arquivos pelo cliente Lync 2013; no entanto, ainda é suportado pelo Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="08f0b-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="08f0b-109">O cliente de chat de grupo herdado pode publicar e exibir arquivos, mas se a mesma sala de chat for acessada pelo cliente do Lync 2013, não será possível acessar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="08f0b-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="08f0b-110">O acesso à sala de chat é controlado por uma lista de associações.</span><span class="sxs-lookup"><span data-stu-id="08f0b-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="08f0b-111">Todo o histórico da sala de chat está disponível a qualquer membro para revisão cronológica ou busca de todo o texto.</span><span class="sxs-lookup"><span data-stu-id="08f0b-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="08f0b-112">Para obter detalhes sobre como usar o cliente de chat persistente, consulte [Planning for clients in Lync server 2013](lync-server-2013-planning-for-clients.md) na documentação de planejamento e [implantação de clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08f0b-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="08f0b-113">Ao configurar o servidor de chat persistente para sua organização, você especifica a configuração inicial durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="08f0b-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="08f0b-114">No entanto, pode haver momentos em que você deseja alterar a forma como você implementa o suporte do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="08f0b-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="08f0b-115">Por exemplo, talvez seja necessário configurar o suporte de servidor de chat persistente e os controles de forma diferente para uma equipe ou grupo específico em sua organização.</span><span class="sxs-lookup"><span data-stu-id="08f0b-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="08f0b-116">Esta seção fornece informações e procedimentos para ajudá-lo a personalizar sua implantação de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="08f0b-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="08f0b-117">Para obter detalhes sobre os recursos e a funcionalidade que você pode configurar para o servidor de chat persistente, consulte [definindo os requisitos de sua organização para o servidor de chat persistente no Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) na documentação de planejamento e [como o servidor de chat persistente funciona no Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="08f0b-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="08f0b-118">Para obter detalhes sobre como implantar o servidor de chat persistente para o Lync Server 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08f0b-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08f0b-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="08f0b-119">In This Section</span></span>

  - [<span data-ttu-id="08f0b-120">Como funciona o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f0b-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="08f0b-121">Usando categorias para administrar o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="08f0b-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="08f0b-122">Noções básicas sobre associação de chat persistente</span><span class="sxs-lookup"><span data-stu-id="08f0b-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="08f0b-123">Práticas recomendadas do servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="08f0b-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="08f0b-124">Gerenciando categorias, salas e suplementos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f0b-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="08f0b-125">Gerenciando o acesso de usuário de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f0b-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="08f0b-126">Operação e manutenção do sistema de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08f0b-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

