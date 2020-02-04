---
title: 'Lync Server 2013: Visão geral dos cenários de criação do fluxo de trabalho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="04754-102">Visão geral dos cenários de criação do fluxo de trabalho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04754-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04754-103">_**Tópico da última modificação:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="04754-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="04754-104">Ao criar um fluxo de trabalho, há duas possibilidades de cenário:</span><span class="sxs-lookup"><span data-stu-id="04754-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="04754-105">**O Administrador cria e configura o fluxo de trabalho** — O membro da função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.</span><span class="sxs-lookup"><span data-stu-id="04754-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="04754-p101">**O Administrador cria o fluxo de trabalho e o Gerente configura as opções** — O membro da função CsResponseGroupAdministrator (ou equivalente) define o o URI do SIP principal, Nome de exibição, atribui um membro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer logon e editar a configuração do fluxo de trabalho criando grupos de agente e também atribui o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.</span><span class="sxs-lookup"><span data-stu-id="04754-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04754-p102">Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="04754-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

