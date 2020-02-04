---
title: 'Lync Server 2013: Visão geral do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b856b4c5199acacd0ed7a3fdf41ed5ab92f59d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="886dd-102">Visão geral do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="886dd-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="886dd-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="886dd-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="886dd-104">Lync Server 2013, servidor de chat persistente permite que os usuários participem de um meio de conversas com base em um tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="886dd-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="886dd-105">O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="886dd-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="886dd-106">Melhore a comunicação entre equipes geograficamente dispersas e de várias funções.</span><span class="sxs-lookup"><span data-stu-id="886dd-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="886dd-107">Ao usar chats persistentes, as equipes podem compartilhar informações, ideias e decisões com eficiência entre si.</span><span class="sxs-lookup"><span data-stu-id="886dd-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="886dd-108">As mensagens postadas para salas de chat (fóruns de discussão) podem persistir (ou seja, podem estar disponíveis ao longo do tempo) para que as pessoas de locais e departamentos diferentes possam participar, mesmo quando não estiverem online simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="886dd-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="886dd-109">Quando um usuário se conecta a uma sala de chat, o backchat (um número configurável de mensagens de histórico de chats) é automaticamente carregado na sala de chat para dar ao usuário um contexto para a conversa.</span><span class="sxs-lookup"><span data-stu-id="886dd-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="886dd-110">Melhorar o reconhecimento de informações.</span><span class="sxs-lookup"><span data-stu-id="886dd-110">Improve information awareness.</span></span> <span data-ttu-id="886dd-111">Usando filtros do lado do cliente, os usuários podem definir condições, como palavras-chave no conteúdo da mensagem ou o valor do campo "de" em uma mensagem, para receber notificações quando essas condições forem atendidas em mensagens instantâneas de chat ou mensagens de chat de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="886dd-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="886dd-112">Dessa forma, os usuários podem ficar atualizados com o conteúdo que mais interessa a eles.</span><span class="sxs-lookup"><span data-stu-id="886dd-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="886dd-113">Melhorar a comunicação com a organização ampliada.</span><span class="sxs-lookup"><span data-stu-id="886dd-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="886dd-114">Ao facilitar a colaboração em tópicos de execução longa com outras pessoas na organização e ao fornecer um local persistente para compartilhar informações, o chat persistente ajuda a melhorar a comunicação.</span><span class="sxs-lookup"><span data-stu-id="886dd-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="886dd-115">Reduzir a sobrecarga de informações.</span><span class="sxs-lookup"><span data-stu-id="886dd-115">Reduce information overload.</span></span> <span data-ttu-id="886dd-116">Os usuários podem seguir as salas de chat e as mensagens da maioria dos juros usando filtros do lado do cliente e podem adicionar salas de chat que desejam acompanhar na lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="886dd-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="886dd-117">Aumente a dispersão de conhecimento e informações importantes.</span><span class="sxs-lookup"><span data-stu-id="886dd-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="886dd-118">Os documentos e links podem ser incluídos nas conversas para acesso por toda a equipe.</span><span class="sxs-lookup"><span data-stu-id="886dd-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="886dd-119">Ao postar perguntas para uma equipe mais ampla, os usuários podem se beneficiar das respostas por especialistas no assunto.</span><span class="sxs-lookup"><span data-stu-id="886dd-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="886dd-120">A integração com outros sistemas de informações permite que dados organizacionais importantes sejam facilmente comunicados a grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="886dd-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="886dd-121">Para habilitar as salas de chat no Lync Server 2013, implante o Lync Server 2013 chat persistente.</span><span class="sxs-lookup"><span data-stu-id="886dd-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="886dd-122">Para obter informações sobre como habilitar salas de chat, consulte a ajuda <http://go.microsoft.com/fwlink/p/?linkid=270945>de chat persistente em.</span><span class="sxs-lookup"><span data-stu-id="886dd-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="886dd-123">Se os usuários estiverem habilitados para o Lync Server e o suporte do Lync Server estiver implantado, os usuários poderão instalar e usar o chat persistente do Lync 2013 para fornecer suporte à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="886dd-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="886dd-124">Se a sua organização for necessária para acompanhar as normas de conformidade, você pode opcionalmente implantar o serviço de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="886dd-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

