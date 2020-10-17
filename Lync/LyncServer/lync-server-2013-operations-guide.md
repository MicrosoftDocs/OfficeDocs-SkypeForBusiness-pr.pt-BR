---
title: 'Lync Server 2013: guia de operações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212a640577d55e80225a597c9263b7a2573d257f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524528"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="72455-102">Guia de operações do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-102">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72455-103">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="72455-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="72455-104">Este documento descreve os processos, as tarefas e as ferramentas operacionais necessários para manter um ambiente de software de comunicações do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72455-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="72455-105">Ele explica como gerenciar o Lync Server 2013 de acordo com o modelo do Microsoft Operations Framework (MOF) e o ajuda a projetar um ambiente de gerenciamento operacional eficiente, que inclui a implementação de agendas, processos e procedimentos para manter um ambiente de trabalho eficiente.</span><span class="sxs-lookup"><span data-stu-id="72455-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72455-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="72455-106">In This Section</span></span>

<span data-ttu-id="72455-107">As seções a seguir estão incluídas:</span><span class="sxs-lookup"><span data-stu-id="72455-107">The following sections are included:</span></span>

  - [<span data-ttu-id="72455-108">Práticas recomendadas para ambientes do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="72455-109">Tarefas diárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="72455-110">Tarefas semanais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="72455-111">Tarefas mensais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="72455-112">Tarefas necessárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="72455-113">Listas de verificação de operações do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="72455-114">Monitoramento do Lync Server 2013 com o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="72455-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="72455-115">Dependências operacionais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="72455-116">Solução de problemas e principais indicadores de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="72455-117">Presume-se que sua implantação do Microsoft Lync Server 2013 esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="72455-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="72455-118">Se esse não for o caso, consulte o planejamento e implantação de conteúdo do Microsoft Lync Server 2013 antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="72455-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72455-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="72455-119">See Also</span></span>


[<span data-ttu-id="72455-120">Introdução ao Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="72455-121">Planejamento para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="72455-122">Implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="72455-123">Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72455-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

