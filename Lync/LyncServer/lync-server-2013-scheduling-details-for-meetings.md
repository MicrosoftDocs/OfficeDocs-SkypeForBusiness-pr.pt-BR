---
title: 'Lync Server 2013: detalhes do agendamento de reuniões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="23733-102">Detalhes de agendamento de reuniões no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23733-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23733-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="23733-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="23733-104">Depois de fazer uma verificação para assegurar que nenhuma outra reunião esteja agendada na hora solicitada, a equipe de suporte a grandes reuniões, que lida com a solicitação, agenda a reunião no pool de grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="23733-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="23733-105">Use o suplemento de reunião online para o Lync que está instalado com o cliente do Lync Server 2013 para executar essa tarefa, usando as credenciais de um usuário habilitado para o Lync Server no pool de reunião longa dedicada.</span><span class="sxs-lookup"><span data-stu-id="23733-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="23733-106">Para assegurar a melhor experiência do usuário, é importante agendar a grande reunião com os níveis de acesso corretos e as configurações da reunião que são apropriadas para as necessidades do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="23733-107">Recomendamos as seguintes configurações de agendamento definidas nas opções de reunião do Lync:</span><span class="sxs-lookup"><span data-stu-id="23733-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="23733-108">Use um novo espaço de reunião para cada grande reunião em vez de reutilizar o espaço dedicado da reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="23733-109">Especifique os níveis de acesso à reunião conforme segue:</span><span class="sxs-lookup"><span data-stu-id="23733-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="23733-110">Se pelo menos um convidado for externo à organização, defina o tipo de acesso à reunião para **qualquer pessoa (sem restrições**).</span><span class="sxs-lookup"><span data-stu-id="23733-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="23733-111">Isso habilita você a evitar o gerenciamento de um possível grande lobby quando a reunião estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="23733-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="23733-112">Se a reunião for somente interna, defina o tipo de acesso à reunião como **Para qualquer pessoa da minha organização**.</span><span class="sxs-lookup"><span data-stu-id="23733-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="23733-113">Evite definir o tipo de acesso à reunião como <STRONG>Pessoas que eu convidar da minha empresa</STRONG>, pois, quando essa configuração é usada, os organizadores devem adicionar todos os endereços de email em uma lista de convidados e você não poderá convidar um grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="23733-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="23733-114">Evite definir o tipo de acesso à reunião como <STRONG>Apenas eu, o organizador da reunião</STRONG>, pois essa configuração exige que todos os participantes da reunião, inclusive os apresentadores, sejam colocados no lobby durante a reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="23733-115">A pessoa responsável pela execução da grande reunião deverá monitorar a escalação do lobby e aceitar os novos usuários que estiverem no lobby.</span><span class="sxs-lookup"><span data-stu-id="23733-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="23733-116">Permita que usuários que ligam de telefones entrem na reunião automaticamente marcando a configuração **Chamadores entram diretamente**.</span><span class="sxs-lookup"><span data-stu-id="23733-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="23733-117">Convide explicitamente os seguintes usuários:</span><span class="sxs-lookup"><span data-stu-id="23733-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="23733-118">Organizador e representante da reunião (solicitante)</span><span class="sxs-lookup"><span data-stu-id="23733-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="23733-119">A lista de apresentadores fornecida pelo solicitante da reunião</span><span class="sxs-lookup"><span data-stu-id="23733-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23733-120">Se o tipo de acesso à reunião estiver definido como <STRONG>Pessoas que eu escolher</STRONG>, será preciso adicionar explicitamente cada participante da grande reunião como convidado da reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="23733-p105">Gerencie explicitamente os apresentadores, em vez de definir a opção de apresentador como um dos valores promovidos automaticamente. Certifique-se de adicionar os seguintes usuários como apresentadores:</span><span class="sxs-lookup"><span data-stu-id="23733-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="23733-123">Organizador e representante da reunião (solicitante)</span><span class="sxs-lookup"><span data-stu-id="23733-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="23733-124">A lista de apresentadores fornecida pelo solicitantes da grande reunião</span><span class="sxs-lookup"><span data-stu-id="23733-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23733-125">Ao gerenciar explicitamente os apresentadores, você pode controlar o número de apresentadores, para que você possa limitar apresentadores a um número pequeno o suficiente para que seja possível ter uma reunião grande em vigor.</span><span class="sxs-lookup"><span data-stu-id="23733-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="23733-126">Se a maioria dos participantes da reunião tiver a função de participante, serão reduzidas as chances de alguém acidentalmente assumir o controle da apresentação, excluir a apresentação do PowerPoint, ativar/desativar o áudio dos apresentadores e outras interrupções na reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="23733-127">Marque a configuração **Desativar o áudio de todos os participantes** para assegurar que apenas os apresentadores possam transmitir áudio para a reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="23733-128">Marque a configuração **Bloquear vídeo dos participantes** para assegurar que apenas os apresentadores possam transmitir vídeo para a reunião.</span><span class="sxs-lookup"><span data-stu-id="23733-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="23733-129">A figura a seguir mostra as configurações recomendadas para o suplemento de reunião online do Lync.</span><span class="sxs-lookup"><span data-stu-id="23733-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="23733-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="23733-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

