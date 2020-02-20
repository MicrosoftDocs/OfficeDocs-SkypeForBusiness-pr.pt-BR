---
title: 'Lync Server 2013: processo de agendamento de grandes reuniões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83d5225982817342e6d2361099efb1ce1dcc80a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="fba5d-102">Processo de agendamento de reunião grande no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fba5d-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fba5d-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fba5d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fba5d-104">Como só há suporte para uma grande reunião por vez no pool dedicado de reunião grande, recomendamos a implementação de um grande processo de agendamento de reunião para ajudar a evitar grandes conflitos de reunião.</span><span class="sxs-lookup"><span data-stu-id="fba5d-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="fba5d-105">O objetivo desse processo de agendamento é facilitar a configuração de reuniões grandes.</span><span class="sxs-lookup"><span data-stu-id="fba5d-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="fba5d-106">Esse recurso não é fornecido diretamente por clientes do Lync Server ou do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fba5d-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="fba5d-107">Uma maneira de implementar tal processo é usar o sistema de tíquete da equipe de suporte da sua organização, se disponível.</span><span class="sxs-lookup"><span data-stu-id="fba5d-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="fba5d-108">Para organizadores de grandes reuniões, agendar uma grande reunião envolve concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="fba5d-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="fba5d-109">O organizador ou representante da reunião determina o tempo, a duração e o tamanho de uma reunião futura, além da lista de apresentadores.</span><span class="sxs-lookup"><span data-stu-id="fba5d-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="fba5d-110">Se o tamanho previsto da reunião exceder 250 usuários ou para garantir a melhor experiência do usuário para uma reunião de menos de 250 usuários, o organizador ou o representante enviará uma solicitação para uma reunião grande.</span><span class="sxs-lookup"><span data-stu-id="fba5d-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="fba5d-111">A equipe de agendamento verifica se a data e hora solicitada estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fba5d-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="fba5d-112">Como damos suporte apenas a uma única reunião grande no pool dedicado por vez, a equipe de agendamento precisa verificar o calendário de reunião grande para determinar se há outra reunião agendada para a data e hora solicitadas.</span><span class="sxs-lookup"><span data-stu-id="fba5d-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="fba5d-113">Se a hora solicitada estiver disponível, a equipe aprovará a solicitação de reunião.</span><span class="sxs-lookup"><span data-stu-id="fba5d-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="fba5d-114">Se a solicitação for aprovada, a equipe de agendamento (usando credenciais no pool dedicado) usará o suplemento reunião online para Lync 2013 com o Outlook para configurar uma reunião no pool dedicado de grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="fba5d-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="fba5d-115">A URL a ser usada para ingressar na reunião é fornecida ao solicitante como parte do aviso de aprovação.</span><span class="sxs-lookup"><span data-stu-id="fba5d-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="fba5d-116">O organizador ou representante da reunião usa o Outlook para agendar a próxima reunião, adicionando a URL para participar da reunião ao convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="fba5d-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="fba5d-117">O organizador ou o representante da reunião especificará os usuários a serem convidados e enviarão o convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="fba5d-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="fba5d-118">A figura a seguir ilustra um fluxo de trabalho de solicitação e aprovação típico para agendar grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="fba5d-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="fba5d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="fba5d-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

