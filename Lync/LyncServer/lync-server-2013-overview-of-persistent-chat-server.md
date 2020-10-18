---
title: 'Lync Server 2013: visão geral do servidor de chat persistente'
description: 'Lync Server 2013: visão geral do servidor de chat persistente.'
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
ms.openlocfilehash: bbcb396522611aca52bd2093f2fd49f376341356
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577307"
---
# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4496b-103">Visão geral do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4496b-103">Overview of Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4496b-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4496b-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4496b-105">Lync Server 2013, servidor de chat persistente permite que os usuários participem de conversas com vários tópicos, com base em tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="4496b-105">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="4496b-106">O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4496b-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="4496b-107">Melhorar a comunicação entre equipes geograficamente dispersas e multifuncionais.</span><span class="sxs-lookup"><span data-stu-id="4496b-107">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="4496b-108">Usando o chat persistente, o Teams pode compartilhar informações, ideias e decisões com eficiência entre si.</span><span class="sxs-lookup"><span data-stu-id="4496b-108">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="4496b-109">As mensagens postadas para salas de chat (fóruns de discussão) podem persistir (ou seja, podem estar disponíveis com o tempo), para que pessoas de diferentes locais e departamentos possam participar, mesmo quando não estiverem simultaneamente online.</span><span class="sxs-lookup"><span data-stu-id="4496b-109">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="4496b-110">Quando um usuário se conecta a uma sala de chat, o backchat (um número configurável de mensagens de histórico de chat) é carregado automaticamente na sala de chat para fornecer ao usuário um contexto para a conversa.</span><span class="sxs-lookup"><span data-stu-id="4496b-110">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="4496b-111">Melhorar o reconhecimento de informações.</span><span class="sxs-lookup"><span data-stu-id="4496b-111">Improve information awareness.</span></span> <span data-ttu-id="4496b-112">Usando filtros do lado do cliente, os usuários podem definir condições, como palavras-chave no conteúdo da mensagem, ou o valor do campo "de" em uma mensagem, para receber notificações quando essas condições forem atendidas em mensagens instantâneas de chat persistente ou mensagens de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="4496b-112">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="4496b-113">Dessa forma, os usuários podem permanecer atualizados com o conteúdo que está mais de interesse.</span><span class="sxs-lookup"><span data-stu-id="4496b-113">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="4496b-114">Melhorar a comunicação com sua organização estendida.</span><span class="sxs-lookup"><span data-stu-id="4496b-114">Improve communication with their extended organization.</span></span> <span data-ttu-id="4496b-115">Ao facilitar a colaboração em tópicos de execução longa com outras pessoas na organização e fornecer um local persistente para compartilhar informações, o chat persistente ajuda a melhorar a comunicação.</span><span class="sxs-lookup"><span data-stu-id="4496b-115">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="4496b-116">Reduzir a sobrecarga de informações.</span><span class="sxs-lookup"><span data-stu-id="4496b-116">Reduce information overload.</span></span> <span data-ttu-id="4496b-117">Os usuários podem seguir as salas de chat e as mensagens da maioria dos interesses usando filtros do lado do cliente e podem adicionar salas de chat que desejam seguir à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="4496b-117">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="4496b-118">Aumentar a dispersão de conhecimento e informações importantes.</span><span class="sxs-lookup"><span data-stu-id="4496b-118">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="4496b-119">Documentos e links podem ser incluídos em conversas para acesso por todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="4496b-119">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="4496b-120">Ao postar perguntas para uma equipe mais ampla, os usuários podem se beneficiar de respostas por especialistas no assunto.</span><span class="sxs-lookup"><span data-stu-id="4496b-120">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="4496b-121">A integração com outros sistemas de informações permite que dados corporativos importantes sejam facilmente comunicados a grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="4496b-121">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="4496b-122">Para habilitar as salas de chat no Lync Server 2013, implante o Lync Server 2013 chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4496b-122">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="4496b-123">Para obter informações sobre como habilitar salas de chat, consulte a ajuda de chat persistente em <https://go.microsoft.com/fwlink/p/?linkid=270945> .</span><span class="sxs-lookup"><span data-stu-id="4496b-123">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="4496b-124">Se os usuários estiverem habilitados para o Lync Server e o suporte do Lync Server for implantado, os usuários poderão instalar e usar o chat persistente do Lync 2013 para fornecer suporte à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="4496b-124">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="4496b-125">Se sua organização for necessária para acompanhar as regulamentações de conformidade, você pode opcionalmente implantar o serviço de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4496b-125">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

