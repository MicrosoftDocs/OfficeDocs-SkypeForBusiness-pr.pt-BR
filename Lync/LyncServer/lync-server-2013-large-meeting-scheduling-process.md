---
title: 'Lync Server 2013: processo de agendamento de reunião grande'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="e8f2d-102">Processo de agendamento de reunião grande no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8f2d-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8f2d-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e8f2d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e8f2d-104">Como só há suporte para uma reunião grande por vez no pool de reunião grande dedicado, recomendamos implementar um processo de agendamento de reunião grande para ajudar a evitar conflitos de reunião grandes.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="e8f2d-105">A finalidade desse processo de agendamento é facilitar a configuração de reuniões grandes.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="e8f2d-106">Essa funcionalidade não é fornecida diretamente pelo Lync Server ou clientes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="e8f2d-107">Uma forma de implementar tal processo é usar o sistema de tickets da equipe de suporte da sua organização, se disponível.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="e8f2d-108">Para os organizadores de reuniões grandes, agendar uma reunião grande envolve completar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e8f2d-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="e8f2d-p102">O organizador da reunião ou representante determina a hora, a duração e o tamanho da uma próxima reunião, além da lista de apresentadores. Se o tamanho da reunião antecipado excede 250 usuários ou para garantir a melhor experiência do usuário para uma reunião com menos de 250 usuários, o organizador ou representante envia uma solicitação para uma grande reunião.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="e8f2d-p103">A equipe de programação verifica para ver se a data e hora solicitada está disponível. Como suportamos apenas uma única grande reunião em um pool exclusivo por vez, a equipe de programação precisa verificar o calendário de grandes reuniões para determinar se há outra reunião programada para a data e hora solicitada. Se a hora da reunião está disponível, a equipe aprova a solicitação da reunião.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="e8f2d-114">Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o suplemento de reunião online para o Lync 2013 com o Outlook para configurar uma reunião no pool de reunião grande dedicado.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="e8f2d-115">A URL a ser usada para participar da reunião é fornecida ao requisitante como parte do prompt de aprovação.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="e8f2d-p105">O organizador ou representante da reunião usa o Outlook para programar a próxima reunião, adicionando ao convite a URL para participar da reunião. O organizador da reunião ou representante especifica os usuários a serem convidados e envia o convite.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="e8f2d-118">A figura a seguir ilustra um fluxo de trabalho de solicitação e aprovação típico para agendar reuniões grandes.</span><span class="sxs-lookup"><span data-stu-id="e8f2d-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="e8f2d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d] (images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="e8f2d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

