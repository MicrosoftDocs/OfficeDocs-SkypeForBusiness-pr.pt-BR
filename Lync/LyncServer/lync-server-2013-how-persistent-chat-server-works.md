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
ms.openlocfilehash: 4a88bdad2a73022468297d73dd10bff0d26a3fee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="35518-102">Como funciona o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35518-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35518-103">_**Última modificação do tópico:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="35518-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="35518-104">Lync Server 2013, servidor de chat persistente permite que você participe de conversas com vários tópicos, com base em tópico que persistem ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="35518-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="35518-105">O servidor de chat persistente pode ajudar sua organização a fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="35518-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="35518-106">Melhorar a comunicação entre equipes geograficamente distante e multifuncionais</span><span class="sxs-lookup"><span data-stu-id="35518-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="35518-107">Ampliar a conscientização e participação da informação</span><span class="sxs-lookup"><span data-stu-id="35518-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="35518-108">Melhorar a comunicação com sua organização estendida</span><span class="sxs-lookup"><span data-stu-id="35518-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="35518-109">Reduzir sobrecarga informacional</span><span class="sxs-lookup"><span data-stu-id="35518-109">Reduce information overload</span></span>

  - <span data-ttu-id="35518-110">Melhorar a conscientização da informação</span><span class="sxs-lookup"><span data-stu-id="35518-110">Improve information awareness</span></span>

  - <span data-ttu-id="35518-111">Melhorar a dispersão de informações e conhecimentos importantes</span><span class="sxs-lookup"><span data-stu-id="35518-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="35518-112">Você pode implantar o servidor de chat persistente como uma função opcional com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35518-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="35518-113">Os serviços de chat persistente são executados em um pool dedicado, e um pool de servidor de chat persistente depende de um pool do Lync Server para encaminhar mensagens para ele.</span><span class="sxs-lookup"><span data-stu-id="35518-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="35518-114">Os clientes utilizam eXtensible Chat Communication Over SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="35518-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="35518-115">Os servidores front-end do Lync Server são configurados para rotear o tráfego para um pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="35518-116">Arquitetura de alto nível</span><span class="sxs-lookup"><span data-stu-id="35518-116">High-Level Architecture</span></span>

<span data-ttu-id="35518-117">Os diagramas a seguir fornecem perspectivas de alto nível da arquitetura e dos serviços do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="35518-118">**Arquitetura de alto nível de servidor de bate-papo persistente**</span><span class="sxs-lookup"><span data-stu-id="35518-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="35518-119">![Arquitetura do servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitetura do servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="35518-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="35518-120">**Serviços de alto nível de servidor de bate-papo persistente**</span><span class="sxs-lookup"><span data-stu-id="35518-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="35518-121">![Componentes do servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes do servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="35518-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="35518-122">Dois serviços são executados nos servidores de front-end do servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="35518-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="35518-123">Bate-papo persistente (canal)</span><span class="sxs-lookup"><span data-stu-id="35518-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="35518-124">Conformidade</span><span class="sxs-lookup"><span data-stu-id="35518-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="35518-125">Serviço de bate-papo (canal) persistente</span><span class="sxs-lookup"><span data-stu-id="35518-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="35518-126">O serviço de chat persistente (canal) é o principal serviço responsável pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="35518-127">Este serviço fornece as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="35518-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="35518-128">Aceita as mensagens recebidas</span><span class="sxs-lookup"><span data-stu-id="35518-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="35518-129">Registra e lista os participantes online em uma sala de chat persistente</span><span class="sxs-lookup"><span data-stu-id="35518-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="35518-130">Retransmite mensagens a outros assinantes do canal</span><span class="sxs-lookup"><span data-stu-id="35518-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="35518-131">Implementa lógica para gerenciamento de canal, convite para sala de bate-papo, busca e notificações de novo conteúdo</span><span class="sxs-lookup"><span data-stu-id="35518-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="35518-132">O serviço de chat persistente (canal) armazena e acessa o conteúdo da sala de chat e outros metadados do sistema (regras de autorização e assim por diante) usando o repositório de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="35518-133">Este serviço armazena arquivos que são carregados em salas de chat no repositório de arquivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="35518-134">Serviços de conformidade</span><span class="sxs-lookup"><span data-stu-id="35518-134">Compliance Service</span></span>

<span data-ttu-id="35518-135">O serviço de conformidade é um componente opcional do servidor de chat persistente e é responsável por arquivar conteúdo e eventos de chat no repositório de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="35518-136">Se sua organização tem regulamentações que exigem atividade de chat persistente para serem arquivadas, você pode implantar o serviço de conformidade de chat persistente opcional.</span><span class="sxs-lookup"><span data-stu-id="35518-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="35518-137">O serviço de conformidade é instalado em cada servidor de chat persistente em um pool de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="35518-138">Quando configurado, a conformidade do servidor de chat persistente registra as atividades do usuário, como ingressar e sair de salas, e postar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="35518-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="35518-139">O serviço de conformidade armazena arquivos que precisam ser arquivados no repositório de arquivos de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="35518-140">Serviços Web de chat persistente</span><span class="sxs-lookup"><span data-stu-id="35518-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="35518-141">Nos servidores front-end do Lync Server, dois serviços são executados que dependem do IIS (serviços de informações da Internet) e são implementados como componentes da Web:</span><span class="sxs-lookup"><span data-stu-id="35518-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="35518-142">**Serviços Web de chat persistente para upload/download de arquivo** Responsável por postar e recuperar arquivos de salas de chat.</span><span class="sxs-lookup"><span data-stu-id="35518-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="35518-143">**Serviços Web de chat persistente para gerenciamento de salas de chat** Responsável por fornecer aos usuários a capacidade de gerenciar suas salas de chat e criar novas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="35518-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="35518-144">Como começar a usar o servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="35518-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="35518-145">O servidor de chat persistente é uma função de servidor opcional na infraestrutura do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35518-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="35518-146">Se você instalar a função de servidor de chat persistente, todos os usuários que tenham sido habilitados por meio da política por um administrador poderão usar o chat persistente com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="35518-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="35518-147">Para obter detalhes sobre como implantar o servidor de chat persistente e permitir que os usuários aproveitem os recursos por política, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="35518-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="35518-148">Para obter detalhes sobre como definir as configurações na implantação do servidor de chat persistente, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="35518-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="35518-149">Para obter detalhes sobre como habilitar usuários por política, de forma que eles possam aproveitar a funcionalidade de chat persistente no cliente Lync 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) e [Managing Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="35518-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="35518-150">Se você implantou a conformidade de chat persistente, consulte [Managing Lync server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md) para obter detalhes sobre como definir as configurações de conformidade.</span><span class="sxs-lookup"><span data-stu-id="35518-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="35518-151">Fluxos de chamadas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="35518-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="35518-152">O cliente de chat persistente se comunica com o serviço de chat persistente usando o XCCOS.</span><span class="sxs-lookup"><span data-stu-id="35518-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="35518-153">A sequência a seguir descreve o processo de inscrição e assinatura de sala típica e cenário de postagem de mensagem..</span><span class="sxs-lookup"><span data-stu-id="35518-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="35518-154">Entrar</span><span class="sxs-lookup"><span data-stu-id="35518-154">Sign-in</span></span>

<span data-ttu-id="35518-155">As etapas e o diagrama de fluxo de chamadas a seguir descrevem o processo de entrada.</span><span class="sxs-lookup"><span data-stu-id="35518-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="35518-156">**Fluxo de chamadas de entrada de cliente de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="35518-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="35518-157">![Diagrama de fluxo de chamadas do servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de fluxo de chamadas do servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="35518-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="35518-158">O cliente de chat persistente primeiro envia um SIP INSCREVEr-se para recuperar o documento de provisionamento em banda do servidor.</span><span class="sxs-lookup"><span data-stu-id="35518-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="35518-159">Este documento indica se o chat persistente está habilitado ou desabilitado para o usuário e a lista de URIs SIP para o pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="35518-160">O cliente de chat persistente envia uma mensagem de convite SIP para o URI SIP do servidor de chat persistente obtido na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="35518-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="35518-161">A sequência de convite é seguida por 200 OK e ACK, e o cliente de chat persistente agora abriu uma sessão SIP com um ponto de extremidade de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="35518-162">Consequentemente, o cliente de chat persistente se comunica com o servidor de chat persistente enviando mensagens de informações de SIP que contenham mensagens de chat ou comandos solicitando que o servidor execute uma ação.</span><span class="sxs-lookup"><span data-stu-id="35518-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="35518-163">Todas essas mensagens são reconhecidas com 200 OK ou 503 Serviço Não Disponível (isto é, no caso de uma grande carga no servidor).</span><span class="sxs-lookup"><span data-stu-id="35518-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="35518-164">Se o cliente receber uma resposta 503, irá tentar novamente a mensagem.</span><span class="sxs-lookup"><span data-stu-id="35518-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="35518-165">(Este exemplo não inclui uma resposta 503.) Se o servidor aceitar a mensagem ou comando e enviar 200 OK, ele fornecerá uma resposta para o cliente na forma de uma mensagem de informações SIP separada.</span><span class="sxs-lookup"><span data-stu-id="35518-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="35518-166">Essa resposta inclui uma referência ao comando que a originou.</span><span class="sxs-lookup"><span data-stu-id="35518-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="35518-167">O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **GetServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="35518-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="35518-168">Servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém informações sobre a configuração do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="35518-169">O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **getassociations** .</span><span class="sxs-lookup"><span data-stu-id="35518-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="35518-170">O servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém a lista de salas das quais o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="35518-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="35518-171">O cliente de chat persistente repete o comando para recuperar a lista de salas das quais o usuário é um gerente.</span><span class="sxs-lookup"><span data-stu-id="35518-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="35518-172">O cliente de chat persistente Obtém a lista de salas seguidas do documento "presença", onde cada sala seguida é representada por uma categoria "roomSetting".</span><span class="sxs-lookup"><span data-stu-id="35518-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="35518-173">Todas as salas seguintes são reunidas por uma única mensagem SIP INFO que contém o comando XCCOS **bjoin**, que contém a lista de salas URIs.</span><span class="sxs-lookup"><span data-stu-id="35518-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="35518-174">Por a lista de salas subsequentes ser mantida no servidor, qualquer cliente em qualquer computador possui a mesma lista de salas subsequentes para o usuário URI especificado.</span><span class="sxs-lookup"><span data-stu-id="35518-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="35518-175">O cliente de chat persistente também mantém a lista de salas abertas (se essa opção estiver habilitada pelo usuário) no registro do computador local e ingressa em cada uma dessas salas ao entrar enviando uma mensagem SIP que contém o comando XCCOS **Join** para cada sala aberta.</span><span class="sxs-lookup"><span data-stu-id="35518-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="35518-176">Como essa lista é mantida no registro, ela pode ser diferente em dois clientes de chat persistente executados em computadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="35518-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="35518-177">Para cada sala associada, o cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="35518-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="35518-178">O servidor de chat persistente responde com uma nova mensagem de informações de SIP que contém a mensagem de chat mais recente na sala.</span><span class="sxs-lookup"><span data-stu-id="35518-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="35518-179">O cliente de chat persistente envia uma mensagem de informações de SIP que contém um comando XCCOS **getinv** (ou seja, Get convite) para solicitar novos convites de sala que o cliente ainda não tenha visto.</span><span class="sxs-lookup"><span data-stu-id="35518-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="35518-180">Em uma mensagem de informações SIP separada, o servidor de chat persistente retorna uma lista dessas salas.</span><span class="sxs-lookup"><span data-stu-id="35518-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="35518-181">Inscrever-se para uma sala e postar uma mensagem</span><span class="sxs-lookup"><span data-stu-id="35518-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="35518-182">As etapas e o diagrama de fluxo de chamadas a seguir descrevem um cenário típico de assinatura de sala e postagem de mensagem.</span><span class="sxs-lookup"><span data-stu-id="35518-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="35518-183">**Fluxo de chamadas de assinatura e lançamento de mensagens de salas de cliente de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="35518-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="35518-184">![Cenário de assinatura de sala e de postagem de mensagem.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Cenário de assinatura de sala e de postagem de mensagem.")</span><span class="sxs-lookup"><span data-stu-id="35518-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="35518-185">No cliente de chat persistente, o Usuário1 clica em **ingressar em uma sala de chat**, clica em **Pesquisar**e, em seguida, insere alguns critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35518-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="35518-186">O cliente de chat persistente envia uma mensagem de informações de SIP que contém o comando XCCOS **chansrch** (sala de pesquisa), junto com os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35518-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="35518-187">O servidor de chat persistente consulta o banco de dados back-end e responde uma nova mensagem de informações de SIP que contém uma lista de salas disponíveis que atendem aos critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="35518-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="35518-188">O User1 seleciona a sala de bate-papo que deseja participar e, então, clica em **Seguir esta sala**.</span><span class="sxs-lookup"><span data-stu-id="35518-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="35518-189">O cliente de chat persistente envia um servidor de chat persistente uma mensagem de SIP que contém o comando XCCOS **Join** e a ID de sala da sala de chat selecionada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="35518-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="35518-190">O servidor de chat persistente responde com uma mensagem de informações SIP que contém os dados de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="35518-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="35518-191">O cliente de chat persistente envia um servidor de chat persistente uma mensagem de informações SIP que contém o comando XCCOS **bccontext** (contexto de backchat).</span><span class="sxs-lookup"><span data-stu-id="35518-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="35518-192">O servidor de chat persistente recupera o histórico de chat e o retorna ao cliente de chat persistente em uma mensagem de informações SIP separada.</span><span class="sxs-lookup"><span data-stu-id="35518-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="35518-193">Neste ponto, o usuário insere a sala de bate-papo e está pronto para participar.</span><span class="sxs-lookup"><span data-stu-id="35518-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="35518-194">O User1 insere uma nova mensagem e clica em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="35518-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="35518-195">O cliente de chat persistente envia a mensagem para a sala de chat em um comando SIP INFO XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="35518-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="35518-196">O servidor de chat persistente armazena uma cópia dessa nova mensagem no banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="35518-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="35518-197">Servidor de chat persistente envia uma cópia separada da mensagem SIP INFO XCCOS **grpchat** para Usuário2, que já entrou na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="35518-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="35518-198">Fluxos de chamadas de conformidade de chat persistente</span><span class="sxs-lookup"><span data-stu-id="35518-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="35518-199">O servidor de chat persistente usa o enfileiramento de mensagens (também conhecido como MSMQ) e um banco de dados de conformidade adicional (mgccomp) para processar dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="35518-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="35518-200">Como exemplo de como os eventos de conformidade são processados, a sequência de eventos a seguir descreve como um evento de postagem de mensagem é processado.</span><span class="sxs-lookup"><span data-stu-id="35518-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="35518-201">Um usuário posta uma mensagem em uma sala.</span><span class="sxs-lookup"><span data-stu-id="35518-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="35518-202">Servidor de chat persistente coloca informações referentes ao evento em uma fila de enfileiramento de mensagens particular.</span><span class="sxs-lookup"><span data-stu-id="35518-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="35518-203">O servidor de conformidade de chat persistente lê esse evento a partir da fila e o coloca no banco de dados do mgccomp para processamento posterior.</span><span class="sxs-lookup"><span data-stu-id="35518-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="35518-204">Periodicamente, o servidor de conformidade de chat persistente processa um conjunto de eventos no banco de dados e os envia para o adaptador de conformidade de chat persistente para processamento.</span><span class="sxs-lookup"><span data-stu-id="35518-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="35518-205">Se o adaptador processar com êxito os dados, o servidor de conformidade de chat persistente excluirá os eventos do banco de dados do mgccomp.</span><span class="sxs-lookup"><span data-stu-id="35518-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

