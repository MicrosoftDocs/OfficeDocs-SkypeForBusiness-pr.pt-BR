---
title: 'Lync Server 2013: planejamento para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee463a93afdb32e4c9cd8e90b068a6d03220cb22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="1ff13-102">Planejando o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff13-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff13-103">_**Última modificação do tópico:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="1ff13-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="1ff13-104">No Lync Server 2013, o suporte para cenários de controle de chamada remota permite que os usuários controlem seus telefones de PBX (central privada de comutação telefônica) usando o Lync 2013 em seus computadores desktop.</span><span class="sxs-lookup"><span data-stu-id="1ff13-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="1ff13-105">Esta seção descreve os recursos de controle de chamada remota e os requisitos para a implantação do controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="1ff13-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="1ff13-106">A integração entre um PBX e o Lync Server 2013 torna possível que os usuários habilitados para controle de chamada remota usem a interface de usuário do Lync 2013 (UI) para controlar as chamadas em seus telefones PBX das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="1ff13-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ff13-107">Por fim, os recursos do PBX que hospeda o telefone PBX de um usuário determinam os recursos de controle de chamada remota disponíveis para o usuário.</span><span class="sxs-lookup"><span data-stu-id="1ff13-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="1ff13-108">Fazer uma chamada de saída</span><span class="sxs-lookup"><span data-stu-id="1ff13-108">Make an outgoing call</span></span>

  - <span data-ttu-id="1ff13-109">Atender uma chamada recebida</span><span class="sxs-lookup"><span data-stu-id="1ff13-109">Answer an incoming call</span></span>

  - <span data-ttu-id="1ff13-110">Atender uma chamada com uma mensagem instantânea</span><span class="sxs-lookup"><span data-stu-id="1ff13-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ff13-111">Ou seja, quando o número de telefone do chamador pode ser associado a um endereço de mensagem instantânea na GAL (lista de endereços global) da sua organização, na lista de contatos do Lync do receptor ou em uma organização de um parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="1ff13-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="1ff13-112">Transferir uma chamada</span><span class="sxs-lookup"><span data-stu-id="1ff13-112">Transfer a call</span></span>

  - <span data-ttu-id="1ff13-113">Encaminhar uma chamada de entrada</span><span class="sxs-lookup"><span data-stu-id="1ff13-113">Forward an incoming call</span></span>

  - <span data-ttu-id="1ff13-114">Colocar chamadas em espera</span><span class="sxs-lookup"><span data-stu-id="1ff13-114">Place calls on hold</span></span>

  - <span data-ttu-id="1ff13-115">Alternar entre várias chamadas simultâneas</span><span class="sxs-lookup"><span data-stu-id="1ff13-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="1ff13-116">Atender uma segunda chamada enquanto está em uma chamada (isso é, chamada em espera)</span><span class="sxs-lookup"><span data-stu-id="1ff13-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="1ff13-117">Discar dígitos DTMF</span><span class="sxs-lookup"><span data-stu-id="1ff13-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="1ff13-118">Na janela Conversa, digite observações no programa de anotações Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="1ff13-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="1ff13-119">Além disso, quando um usuário é habilitado para controle de chamada remota, o Lync 2013 fornece ao usuário as seguintes informações de chamada:</span><span class="sxs-lookup"><span data-stu-id="1ff13-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="1ff13-120">Identificação de um chamador por nome quando o número de telefone do chamador existe na lista de contatos de um cliente de mensagens e colaboração do Microsoft Office Outlook habilitado para controle de chamada remota, lista de contatos do Lync ou GAL da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ff13-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="1ff13-121">Chamadas de entrada e saída antigas, que são salvas na pasta Histórico da Conversa no Outlook.</span><span class="sxs-lookup"><span data-stu-id="1ff13-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="1ff13-122">Notificações de chamadas perdidas, que são enviadas para a pasta caixa de entrada do Outlook do usuário, mas são geradas somente se o Lync estiver em execução quando a chamada de entrada for recebida.</span><span class="sxs-lookup"><span data-stu-id="1ff13-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="1ff13-123">Controle de Chamada Remota e Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1ff13-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="1ff13-124">Embora os recursos de controle de chamada remota sejam separados dos recursos do Enterprise Voice e os usuários não possam ser habilitados para ambos, o Enterprise Voice oferece um subconjunto de recursos que também estão disponíveis para os usuários que estão habilitados para controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="1ff13-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="1ff13-125">Se o Enterprise Voice for implantado, os usuários habilitados para controle de chamada remota poderão usar o Lync para acessar os seguintes recursos do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="1ff13-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="1ff13-126">Fazer e receber chamadas de áudio para outro cliente Lync</span><span class="sxs-lookup"><span data-stu-id="1ff13-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="1ff13-127">Ingressar na parte de áudio de uma conferência criada por um usuário habilitado para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1ff13-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ff13-128">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1ff13-128">In This Section</span></span>

  - [<span data-ttu-id="1ff13-129">Tarefas de implantação para o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff13-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

