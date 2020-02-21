---
title: 'Lync Server 2013: suporte a reuniões grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 949e5fb209722d8a0d8476d017bba1b7144561a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="af002-102">Suporte a reuniões grandes usando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af002-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af002-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="af002-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="af002-104">Reuniões grandes não seguem o modelo de teste descrito na seção anterior, pois elas possuem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="af002-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="af002-105">O formato da reunião é uma apresentação de um-para-muitos.</span><span class="sxs-lookup"><span data-stu-id="af002-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="af002-106">Um ou alguns usuários são representados e todos eles participam somente como participantes.</span><span class="sxs-lookup"><span data-stu-id="af002-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="af002-107">O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.</span><span class="sxs-lookup"><span data-stu-id="af002-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="af002-108">O áudio é exigido e o vídeo também pode ser utilizado.</span><span class="sxs-lookup"><span data-stu-id="af002-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="af002-109">Uma pessoa dedicada, geralmente, o organizador da reunião ou um assistente do organizador, define a reunião com antecedência.</span><span class="sxs-lookup"><span data-stu-id="af002-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="af002-110">Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="af002-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="af002-111">Fornecer suporte a reuniões grandes com até 1.000 usuários requer correção de problemas relacionados ao modelo de hardware compartilhado e ao modelo sem reserva.</span><span class="sxs-lookup"><span data-stu-id="af002-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="af002-112">Para ter recursos suficientes de CPU e memória para reuniões de até 1000 usuários, os servidores front-end de hospedagem não devem hospedar nenhuma outra carga de mensagens instantâneas (IM) e presença ou cargas de trabalho do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="af002-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="af002-113">Também não deve hospedar quaisquer outras reuniões, independente do tamanho das outras reuniões.</span><span class="sxs-lookup"><span data-stu-id="af002-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="af002-114">Isso significa que a hospedagem de reuniões de até 1000 usuários exige a configuração de um pool separado do Lync Server dedicado à Hospedagem de grandes reuniões de até 1000 usuários.</span><span class="sxs-lookup"><span data-stu-id="af002-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="af002-115">Um pool do Lync Server dedicado à Hospedagem de grandes reuniões deve hospedar apenas uma reunião de até 1000 usuários ao mesmo tempo, portanto, os tempos de reunião precisam ser reservados antecipadamente por meio de um processo de agendamento fora da banda para garantir o suporte dedicado do serv de front-ends ers.</span><span class="sxs-lookup"><span data-stu-id="af002-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="af002-116">Para suportar mais de uma reunião grande ao mesmo tempo, recomendamos a configuração de vários pool de reuniões grandes dedicados.</span><span class="sxs-lookup"><span data-stu-id="af002-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="af002-p103">Recomendamos que uma pessoa dedicada conduza e monitore uma parte de uma grande reunião online. Essa pessoa deve ser o organizador, delegado do organizador ou apresentador, ou um membro da equipe de suporte à reunião grande dedicada, dependendo das preferências da organização.</span><span class="sxs-lookup"><span data-stu-id="af002-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="af002-119">Nas seções a seguir, descreveremos como implementar um pool dedicado para grandes reuniões, incluindo as práticas recomendadas para usar o Lync Server 2013 para suportar grandes cenários de reunião.</span><span class="sxs-lookup"><span data-stu-id="af002-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="af002-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="af002-120">In This Section</span></span>

  - [<span data-ttu-id="af002-121">Configurando o suporte para grandes reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af002-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="af002-122">Gerenciando grandes reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af002-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

