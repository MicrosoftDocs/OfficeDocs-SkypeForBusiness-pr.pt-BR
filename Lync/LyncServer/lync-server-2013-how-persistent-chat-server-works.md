---
title: 'Lync Server 2013: como funciona o servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="a401d-102">Como o servidor de chat persistente funciona no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a401d-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a401d-103">_**Tópico da última modificação:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="a401d-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="a401d-104">Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários participantes, com base em tópicos que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a401d-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="a401d-105">O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a401d-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="a401d-106">Melhorar a comunicação entre equipes geograficamente dispersas e de várias funções</span><span class="sxs-lookup"><span data-stu-id="a401d-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="a401d-107">Amplie o reconhecimento e a participação em informações</span><span class="sxs-lookup"><span data-stu-id="a401d-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="a401d-108">Melhorar a comunicação com a sua organização estendida</span><span class="sxs-lookup"><span data-stu-id="a401d-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="a401d-109">Reduzir a sobrecarga de informações</span><span class="sxs-lookup"><span data-stu-id="a401d-109">Reduce information overload</span></span>

  - <span data-ttu-id="a401d-110">Melhorar o reconhecimento de informações</span><span class="sxs-lookup"><span data-stu-id="a401d-110">Improve information awareness</span></span>

  - <span data-ttu-id="a401d-111">Aumentar a dispersão de informações e conhecimento importantes</span><span class="sxs-lookup"><span data-stu-id="a401d-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="a401d-112">Você pode implantar o servidor de chat persistente como uma função opcional no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a401d-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="a401d-113">Os serviços de chat persistente são executados em um pool dedicado e um pool de servidores de chat persistentes depende de um pool de servidores do Lync para direcionar mensagens para ele.</span><span class="sxs-lookup"><span data-stu-id="a401d-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="a401d-114">Os clientes usam a comunicação de chat extensível via SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="a401d-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="a401d-115">Os servidores de front-end do Lync Server são configurados para direcionar o tráfego para um pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="a401d-116">Arquitetura de alto nível</span><span class="sxs-lookup"><span data-stu-id="a401d-116">High-Level Architecture</span></span>

<span data-ttu-id="a401d-117">Os diagramas a seguir fornecem perspectivas de alto nível da arquitetura e dos serviços do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="a401d-118">**Arquitetura de alto nível do servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="a401d-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="a401d-119">![Arquitetura de servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitetura de servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="a401d-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="a401d-120">**Serviços de alto nível do servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="a401d-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="a401d-121">![Componentes persistentes do servidor de chat.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes persistentes do servidor de chat.")</span><span class="sxs-lookup"><span data-stu-id="a401d-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="a401d-122">Dois serviços são executados nos servidores de front-end do servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="a401d-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="a401d-123">Chat persistente (canal)</span><span class="sxs-lookup"><span data-stu-id="a401d-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="a401d-124">Conformidade</span><span class="sxs-lookup"><span data-stu-id="a401d-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="a401d-125">Serviço de chat (canal) persistente</span><span class="sxs-lookup"><span data-stu-id="a401d-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="a401d-126">O serviço de chat (canal) persistente é o serviço principal responsável pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="a401d-127">Esse serviço oferece as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="a401d-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="a401d-128">Aceita as mensagens recebidas</span><span class="sxs-lookup"><span data-stu-id="a401d-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="a401d-129">Registra e lista os participantes em uma sala do Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="a401d-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="a401d-130">Retransmite mensagens a outros assinantes do canal</span><span class="sxs-lookup"><span data-stu-id="a401d-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="a401d-131">Implementa a lógica para o gerenciamento de canal, o convite da sala de chat, a pesquisa e novas notificações de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a401d-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="a401d-132">O serviço de chat (canal) persistente armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o repositório de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="a401d-133">Esse serviço armazena arquivos que são carregados em salas de chat no repositório de arquivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="a401d-134">Serviço de conformidade</span><span class="sxs-lookup"><span data-stu-id="a401d-134">Compliance Service</span></span>

<span data-ttu-id="a401d-135">O serviço de conformidade é um componente opcional do servidor de chat persistente e é responsável por arquivar conteúdo e eventos de chat no repositório de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="a401d-136">Se a sua organização tiver regulamentos que exigem que a atividade de Chat Persistente seja arquivada, você pode implantar o serviço opcional de Conformidade de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="a401d-137">O serviço de conformidade está instalado em cada servidor de chat persistente em um pool de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="a401d-138">Quando configurado, a conformidade do servidor de chat persistente registra atividades do usuário, como ingressar e sair de salas, e postar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="a401d-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="a401d-139">O serviço de conformidade armazena arquivos que precisam ser arquivados no repositório de arquivos de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="a401d-140">Serviços Web de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a401d-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="a401d-141">Nos servidores de front-end do Lync Server, dois serviços executados dependem dos serviços de informações da Internet (IIS) e são implementados como componentes Web:</span><span class="sxs-lookup"><span data-stu-id="a401d-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="a401d-142">**Serviços Web de chat persistentes para carregamento/download de arquivo** Responsável por publicar e recuperar arquivos de salas de chat.</span><span class="sxs-lookup"><span data-stu-id="a401d-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="a401d-143">**Serviços Web persistentes de chat para gerenciamento de salas de chat** Responsável por fornecer aos usuários a capacidade de gerenciar salas de chat e criar novas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="a401d-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="a401d-144">Como começo a usar o servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="a401d-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="a401d-145">O servidor de chat persistente é uma função de servidor opcional na infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a401d-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="a401d-146">Se você instalar a função de servidor de chat persistente, todos os usuários que foram habilitados por meio da política por um administrador poderão usar o chat persistente com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="a401d-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="a401d-147">Para obter detalhes sobre como implantar o servidor de chat persistente e habilitar os usuários a aproveitar os recursos por política, consulte [implantando o servidor de chat persistente no Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="a401d-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="a401d-148">Para obter detalhes sobre como definir as configurações na sua implantação do servidor de chat persistente, consulte [implantando o servidor de chat persistente no Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Gerenciando o Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="a401d-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="a401d-149">Para obter detalhes sobre como habilitar os usuários por política, para que eles possam aproveitar a funcionalidade de chat persistente no cliente do Lync 2013, consulte [implantação do servidor de chat persistente no Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Gerenciamento do Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="a401d-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="a401d-150">Se você implantou a conformidade persistente com o chat, consulte [Gerenciando o Lync server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) para obter detalhes sobre como definir as configurações de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a401d-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="a401d-151">Fluxos de chamadas de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="a401d-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="a401d-152">O cliente de chat persistente se comunica com o serviço de chat persistente usando XCCOS.</span><span class="sxs-lookup"><span data-stu-id="a401d-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="a401d-153">As seqüências a seguir descrevem o processo de entrada e um cenário típico de assinatura de sala e mensagem de postagem de mensagem.</span><span class="sxs-lookup"><span data-stu-id="a401d-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="a401d-154">Entrada</span><span class="sxs-lookup"><span data-stu-id="a401d-154">Sign-in</span></span>

<span data-ttu-id="a401d-155">As etapas e o diagrama de fluxo de chamadas a seguir descrevem o processo de entrada.</span><span class="sxs-lookup"><span data-stu-id="a401d-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="a401d-156">**Fluxo de chamadas de entrada do cliente de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="a401d-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="a401d-157">![Diagrama de fluxo de chamadas de servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de fluxo de chamadas de servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="a401d-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="a401d-158">O cliente de chat persistente primeiro envia uma assinatura SIP para recuperar o documento de provisionamento em banda do servidor.</span><span class="sxs-lookup"><span data-stu-id="a401d-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="a401d-159">Este documento indica se o chat persistente está habilitado ou desabilitado para o usuário e a lista de URIs SIP do pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="a401d-160">O cliente de chat persistente envia uma mensagem de convite SIP para o URI SIP do servidor de chat persistente que obteve na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="a401d-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="a401d-161">A sequência de convite é seguida por 200 OK e ACK, e o cliente de chat persistente agora abriu uma sessão SIP com um ponto de extremidade de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="a401d-162">Consequentemente, o cliente de chat persistente se comunica com o servidor de chat persistente enviando mensagens de informações SIP que contêm mensagens de chat ou comandos solicitando que o servidor execute uma ação.</span><span class="sxs-lookup"><span data-stu-id="a401d-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="a401d-163">Todas essas mensagens são confirmadas com o serviço do 200 OK ou do 503 indisponível (ou seja, no caso de carga excessiva do servidor).</span><span class="sxs-lookup"><span data-stu-id="a401d-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="a401d-164">Se o cliente receber uma resposta 503, ele tentará novamente a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a401d-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="a401d-165">(Este exemplo não inclui uma resposta 503.) Se o servidor aceitar a mensagem ou o comando e enviar 200 OK, ele fornecerá uma resposta para o cliente na forma de uma mensagem de informações SIP separada.</span><span class="sxs-lookup"><span data-stu-id="a401d-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="a401d-166">Esta resposta inclui uma referência para o comando de origem.</span><span class="sxs-lookup"><span data-stu-id="a401d-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="a401d-167">O cliente de chat persistente envia uma mensagem SIP INFO que contém o comando XCCOS **GetServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="a401d-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="a401d-168">O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém informações sobre a configuração do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="a401d-169">O cliente de chat persistente envia uma mensagem SIP INFO que contém o comando XCCOS **getassociations** .</span><span class="sxs-lookup"><span data-stu-id="a401d-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="a401d-170">O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém a lista de salas dos quais o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="a401d-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="a401d-171">O cliente de chat persistente repete o comando para recuperar a lista de salas das quais o usuário é um gerente.</span><span class="sxs-lookup"><span data-stu-id="a401d-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="a401d-172">O cliente de chat persistente Obtém a lista de salas seguidas do documento "presença", em que cada sala acompanhada é representada por uma categoria "roomSetting".</span><span class="sxs-lookup"><span data-stu-id="a401d-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="a401d-173">Todas as salas seguidas são unidas por uma única mensagem SIP que contém o comando XCCOS **bPara participar** que contém a lista de URIs de sala.</span><span class="sxs-lookup"><span data-stu-id="a401d-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="a401d-174">Como a lista de salas seguidas é mantida no servidor, qualquer cliente em qualquer computador tem a mesma lista de salas seguidas para o URI de usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="a401d-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="a401d-175">O cliente de chat persistente também mantém a lista de salas abertas (se essa opção estiver habilitada pelo usuário) no registro do computador local e ingressar em cada uma dessas salas na entrada, enviando uma mensagem SIP INFO que contém o comando XCCOS **Join** para cada sala aberta.</span><span class="sxs-lookup"><span data-stu-id="a401d-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="a401d-176">Como essa lista é mantida no registro, ela pode ser diferente em dois clientes de chat persistentes em execução em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="a401d-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="a401d-177">Para cada sala unida, o cliente de chat persistente envia uma mensagem de informações SIP que contém o comando XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="a401d-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="a401d-178">O servidor de chat persistente responde com uma nova mensagem de informações SIP que contém a mensagem de chat mais recente na sala.</span><span class="sxs-lookup"><span data-stu-id="a401d-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="a401d-179">O cliente de chat persistente envia uma mensagem SIP INFO que contém um comando XCCOS **getinv** (ou seja, Get convite) para solicitar novos convites de sala que o cliente ainda não viu.</span><span class="sxs-lookup"><span data-stu-id="a401d-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="a401d-180">Em uma mensagem de informações SIP separada, o servidor de chat persistente retorna uma lista dessas salas.</span><span class="sxs-lookup"><span data-stu-id="a401d-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="a401d-181">Assinar uma sala e postar uma mensagem</span><span class="sxs-lookup"><span data-stu-id="a401d-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="a401d-182">As etapas e o diagrama de fluxo de chamadas a seguir descrevem um cenário típico de assinatura de sala e de postagem de mensagem.</span><span class="sxs-lookup"><span data-stu-id="a401d-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="a401d-183">**Assinatura da sala de chat persistente do cliente de chat e fluxo de chamadas de lançamento de mensagens**</span><span class="sxs-lookup"><span data-stu-id="a401d-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="a401d-184">![Licença da sala e cenário de postagem de mensagem.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Licença da sala e cenário de postagem de mensagem.")</span><span class="sxs-lookup"><span data-stu-id="a401d-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="a401d-185">No cliente de chat persistente, o Usuário1 clica em **ingressar em uma sala de chat**, clica em **Pesquisar**e, em seguida, insere critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a401d-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="a401d-186">O cliente de chat persistente envia uma mensagem SIP INFO que contém o comando XCCOS **chansrch** (localização da sala), juntamente com os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a401d-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="a401d-187">O servidor de chat persistente consulta o banco de dados back-end e responde em uma nova mensagem de informações SIP que contém uma lista de salas disponíveis que atendem aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a401d-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="a401d-188">Usuário1 seleciona a sala de chat que deseja participar e, em seguida, clica em **acompanhar esta sala**.</span><span class="sxs-lookup"><span data-stu-id="a401d-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="a401d-189">O cliente de chat persistente envia uma mensagem de informações SIP do servidor de chat persistente que contém o comando XCCOS **Join** e a ID da sala da sala de chat que o usuário selecionou.</span><span class="sxs-lookup"><span data-stu-id="a401d-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="a401d-190">O servidor de chat persistente responde com uma mensagem de informações SIP que contém os dados de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="a401d-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="a401d-191">O cliente de chat persistente envia uma mensagem de informação SIP a um servidor de chat persistente que contém o comando XCCOS **bccontext** (contexto de chat).</span><span class="sxs-lookup"><span data-stu-id="a401d-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="a401d-192">O servidor de chat persistente recupera o histórico de chats e retorna-o ao cliente de chat persistente em uma mensagem de informações SIP separada.</span><span class="sxs-lookup"><span data-stu-id="a401d-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="a401d-193">Nesse ponto, o usuário entra na sala de chat e está pronto para participar.</span><span class="sxs-lookup"><span data-stu-id="a401d-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="a401d-194">Usuário1 insere uma nova mensagem e, em seguida, clica em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a401d-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="a401d-195">O cliente de chat persistente envia a mensagem para a sala de chat em um comando XCCOS **grpchat** do SIP info.</span><span class="sxs-lookup"><span data-stu-id="a401d-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="a401d-196">O servidor de chat persistente armazena uma cópia dessa nova mensagem no banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a401d-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="a401d-197">Servidor de chat persistente envia uma cópia separada da mensagem XCCOS **grpchat** do SIP info para Usuário2, que já entrou na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="a401d-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="a401d-198">Fluxos de chamadas de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a401d-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="a401d-199">O servidor de chat persistente usa o serviço de enfileiramento de mensagens (também conhecido como MSMQ) e um banco de dados de conformidade adicional (mgccomp) para processar dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a401d-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="a401d-200">Como um exemplo de como os eventos de conformidade são processados, a sequência de eventos a seguir descreve como um evento de postagem de mensagem é processado.</span><span class="sxs-lookup"><span data-stu-id="a401d-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="a401d-201">Um usuário publica uma mensagem em uma sala.</span><span class="sxs-lookup"><span data-stu-id="a401d-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="a401d-202">O servidor de chat persistente coloca as informações pertinentes ao evento em uma fila particular do enfileiramento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="a401d-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="a401d-203">O servidor de conformidade de chat persistente lê esse evento da fila e o coloca no banco de dados do mgccomp para processamento posterior.</span><span class="sxs-lookup"><span data-stu-id="a401d-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="a401d-204">Periodicamente, o servidor de conformidade de chat persistente processa um conjunto de eventos no banco de dados e envia-o ao adaptador de conformidade de chat persistente para processamento.</span><span class="sxs-lookup"><span data-stu-id="a401d-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="a401d-205">Se o adaptador processar com êxito os dados, o servidor de conformidade de chat persistente excluirá os eventos do banco de dados do mgccomp.</span><span class="sxs-lookup"><span data-stu-id="a401d-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

