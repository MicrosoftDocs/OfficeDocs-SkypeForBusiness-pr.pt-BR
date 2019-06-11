---
title: 'Lync Server 2013: Recursos de Unificação de Mensagens integrada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="cd88e-102">Recursos de Unificação de Mensagens integrada e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd88e-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd88e-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cd88e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cd88e-104">Lync Server 2013, o Enterprise Voice usa a infraestrutura de Unificação de mensagens do Exchange para fornecer atendimento de chamada, notificação de chamada, acesso de voz (incluindo caixa postal) e serviços de atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="cd88e-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="cd88e-105">Atendimento de Chamadas</span><span class="sxs-lookup"><span data-stu-id="cd88e-105">Call Answering</span></span>

<span data-ttu-id="cd88e-106">O atendimento de chamadas é o recebimento das mensagens de voz em favor dos usuários cujas ligações não são atendidas ou estão ocupados.</span><span class="sxs-lookup"><span data-stu-id="cd88e-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="cd88e-107">Ele inclui uma saudação pessoal, a gravação de uma mensagem e seu envio ao Transporte de Hub do Exchange Server para ficar na fila de entrega à caixa de correio do usuário, que está armazenada no servidor de caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="cd88e-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="cd88e-p102">Se o chamador deixar uma mensagem, está é roteada até a Caixa de entrada do usuário. Se o chamador optar por não deixar uma mensagem, uma notificação de chamada perdida será armazenada na caixa de correio do usuário. Os usuários podem, então, acessar sua Caixa de entrada usando o cliente de mensagem e de colaboração do Microsoft Outlook, o Outlook Web Access, a tecnologia Exchange ActiveSync ou o Outlook Voice Access. O assunto e a prioridade das chamadas podem ser exibidos de uma maneira muito semelhante àquela do e-mail.</span><span class="sxs-lookup"><span data-stu-id="cd88e-p102">If a caller leaves a message, the message is routed to the user's Inbox. If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox. Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access. The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="cd88e-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="cd88e-112">Outlook Voice Access</span></span>

<span data-ttu-id="cd88e-113">O Outlook Voice Access permite que um usuário do Enterprise Voice tenha acesso não apenas à caixa postal, mas também à caixa de entrada do Exchange, incluindo email, calendário e contatos de uma interface de telefonia.</span><span class="sxs-lookup"><span data-stu-id="cd88e-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="cd88e-114">O número de acesso do assinante é atribuído por um administrador de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="cd88e-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="cd88e-115">Atendedor automático</span><span class="sxs-lookup"><span data-stu-id="cd88e-115">Auto Attendant</span></span>

<span data-ttu-id="cd88e-116">O atendedor automático é um recurso do Exchange UM que pode ser usado para configurar um número de telefone que os usuários externos podem discar para acessar os representantes da empresa.</span><span class="sxs-lookup"><span data-stu-id="cd88e-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="cd88e-117">Especificamente, ele fornece uma série de avisos de voz que auxiliam um chamador externo a navegar por um sistema de menus.</span><span class="sxs-lookup"><span data-stu-id="cd88e-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="cd88e-118">A lista de opções disponíveis é configurada no servidor do Exchange UM pelo administrador de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="cd88e-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="cd88e-119">Serviços de fax</span><span class="sxs-lookup"><span data-stu-id="cd88e-119">Fax Services</span></span>

<span data-ttu-id="cd88e-120">O Exchange UM inclui recursos de fax, que permitem que os usuários recebam faxes de entrada nas caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="cd88e-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="cd88e-121">Para obter detalhes, consulte "Unified Messaging" na documentação do Microsoft Exchange [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)Server em.</span><span class="sxs-lookup"><span data-stu-id="cd88e-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd88e-122">Os serviços de fax fornecidos pelo Exchange UM servidor não estão disponíveis nas implantações do Lync Server integradas ao Microsoft Exchange Server 2010, Exchange 2010 com o Service Pack mais recente ou Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="cd88e-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

