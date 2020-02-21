---
title: 'Lync Server 2013: administração do sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="08ac1-102">Administração do sistema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08ac1-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08ac1-103">_**Última modificação do tópico:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="08ac1-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="08ac1-104">A administração do sistema inclui as tarefas administrativas do dia-a-dia, planejadas e sob demanda, que são necessárias para manter um sistema de ti operando sem problemas.</span><span class="sxs-lookup"><span data-stu-id="08ac1-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="08ac1-105">Normalmente, as tarefas de administração do sistema são cobertas por procedimentos escritos.</span><span class="sxs-lookup"><span data-stu-id="08ac1-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="08ac1-106">Esses procedimentos ajudam a garantir que as mesmas ferramentas e métodos padrão sejam usados por toda a equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="08ac1-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="08ac1-107">Em um ambiente do Lync, as tarefas de administração de sistema típicas incluem o backup e o arquivamento de pools, o monitoramento de logs, a criação e o gerenciamento de usuários e a atualização do software antivírus.</span><span class="sxs-lookup"><span data-stu-id="08ac1-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="08ac1-108">Solução de problemas do sistema</span><span class="sxs-lookup"><span data-stu-id="08ac1-108">System troubleshooting</span></span>

<span data-ttu-id="08ac1-109">Uma organização deve estar preparada para lidar com problemas inesperados e deve ter um procedimento para gerenciar problemas do ponto em que eles são relatados até a resolução.</span><span class="sxs-lookup"><span data-stu-id="08ac1-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="08ac1-110">As informações sobre como a equipe de suporte diagnosticou um problema devem ser registradas e usadas no futuro para evitar o trabalho concluído de repetição desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="08ac1-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="08ac1-111">Processo de solução de problemas do sistema</span><span class="sxs-lookup"><span data-stu-id="08ac1-111">System troubleshooting process</span></span>

<span data-ttu-id="08ac1-112">O diagrama a seguir mostra o processo de solução de problemas do sistema e as interações com outras funções de operações.</span><span class="sxs-lookup"><span data-stu-id="08ac1-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="08ac1-113">**Fluxograma de solução de problemas do sistema**</span><span class="sxs-lookup"><span data-stu-id="08ac1-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="08ac1-114">![Fluxograma de solução de problemas do sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Fluxograma de solução de problemas do sistema")</span><span class="sxs-lookup"><span data-stu-id="08ac1-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="08ac1-115">**Classificar e priorizar**   essa tarefa geralmente é executada pelo serviço de suporte.</span><span class="sxs-lookup"><span data-stu-id="08ac1-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="08ac1-116">Por exemplo, um problema pode ser agrupado como um problema de software ou de hardware.</span><span class="sxs-lookup"><span data-stu-id="08ac1-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="08ac1-117">O problema é roteado para a equipe de suporte adequada para investigação.</span><span class="sxs-lookup"><span data-stu-id="08ac1-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="08ac1-118">As regras para determinar a prioridade de um problema, junto com o tempo de resposta e o tempo para resolver, normalmente são definidas no SLA.</span><span class="sxs-lookup"><span data-stu-id="08ac1-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="08ac1-119">**Investigue e diagnostique**   a equipe de suporte apropriada diagnostica o problema e propõe alterações para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="08ac1-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="08ac1-120">Se a solução for simples e não exigir controle de alterações, a solução poderá ser aplicada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="08ac1-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="08ac1-121">Se a solução não for fácil, uma solicitação de alteração deverá ser disparada e o trabalho proposto deverá ser gerenciado pelo processo de gerenciamento de alterações, frequentemente sob um procedimento de "rápido controle".</span><span class="sxs-lookup"><span data-stu-id="08ac1-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="08ac1-122">As alterações feitas devem ser registradas usando o processo de gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="08ac1-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="08ac1-123">**Fechar e gravar**   após testar a resolução, o problema deverá ser fechado.</span><span class="sxs-lookup"><span data-stu-id="08ac1-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="08ac1-124">Se houver lições a serem aprendidas do problema, uma entrada deverá ser criada na base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="08ac1-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="08ac1-125">**Revisão e análise**   de tendências as revisões periódicas de problemas recentes devem ser realizadas para identificar tendências de problemas.</span><span class="sxs-lookup"><span data-stu-id="08ac1-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="08ac1-126">Por exemplo, se os usuários estiverem enfrentando problemas freqüentes com logons lentos para seus sites do Lync, os problemas de largura de banda da rede poderão ser a causa.</span><span class="sxs-lookup"><span data-stu-id="08ac1-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="08ac1-127">Os tempos de solução de problemas e o efeito de qualquer paralisação na disponibilidade do sistema devem ser revisados e comparados com o SLA.</span><span class="sxs-lookup"><span data-stu-id="08ac1-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="08ac1-128">A pessoa que liaises com os problemas de serviço do cliente, como um gerente de contas, deve ser informada sobre problemas significativos.</span><span class="sxs-lookup"><span data-stu-id="08ac1-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="08ac1-129">Ferramentas de gerenciamento de problemas</span><span class="sxs-lookup"><span data-stu-id="08ac1-129">Issue management tools</span></span>

<span data-ttu-id="08ac1-130">As ferramentas de suporte técnico permitem que a equipe grave, classifique e Priorize novos problemas.</span><span class="sxs-lookup"><span data-stu-id="08ac1-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="08ac1-131">As ferramentas fornecerão os processos de fluxo de trabalho para gerenciar a solicitação de serviço de problema através de investigação e diagnóstico, geralmente por mais de uma equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="08ac1-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="08ac1-132">Ferramentas, que freqüentemente fornecem relatórios sobre tempos de resolução e tendências históricas, podem também incluir um banco de dados base de conhecimento, que pode ser usado para pesquisar por problemas passados.</span><span class="sxs-lookup"><span data-stu-id="08ac1-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="08ac1-133">A base de dados de conhecimento da Microsoft é um registro útil de problemas de suporte encontrados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08ac1-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="08ac1-134">Para obter mais informações, consulte o site de suporte<https://go.microsoft.com/fwlink/?linkid=14898>da Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="08ac1-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="08ac1-135">Geralmente, o software de terceiros requer personalização para atender às necessidades da organização, como a organização do Teams, os requisitos de relatórios e as medidas necessárias para o SLA.</span><span class="sxs-lookup"><span data-stu-id="08ac1-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="08ac1-136">Administração centralizada vs. descentralizada</span><span class="sxs-lookup"><span data-stu-id="08ac1-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="08ac1-137">Funções e responsabilidades para executar tarefas de administração do sistema dependem se a organização segue um modelo centralizado, um modelo descentralizado ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="08ac1-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="08ac1-138">**Modelo centralizado**   em um modelo centralizado, um ou vários grupos administrativos mantêm o controle total de todo o ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="08ac1-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="08ac1-139">Esse modelo administrativo é semelhante a um Data Center em que todas as tarefas administrativas são realizadas por um único grupo de tecnologia da informação.</span><span class="sxs-lookup"><span data-stu-id="08ac1-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="08ac1-140">As funções e responsabilidades dentro da equipe devem ser definidas de acordo com a experiência e o conhecimento especializado.</span><span class="sxs-lookup"><span data-stu-id="08ac1-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="08ac1-141">**Modelo descentralizado**   as organizações descentralizadas estão localizadas em vários locais geográficos e possuem servidores e equipes do Lync Server funcionando em diferentes locais.</span><span class="sxs-lookup"><span data-stu-id="08ac1-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="08ac1-142">Por exemplo, pode haver uma equipe de administração local e um ou mais servidores que executam o Lync Server 2013 para cada país/região.</span><span class="sxs-lookup"><span data-stu-id="08ac1-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="08ac1-143">Ou, pode haver um pool de servidores que executam o Lync Server 2013 e uma equipe administrativa para a América do Norte e um para a Europa.</span><span class="sxs-lookup"><span data-stu-id="08ac1-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="08ac1-144">Às vezes, convém que os administradores sejam responsáveis apenas por sua própria área geográfica e restrinjam as permissões para administrar recursos em outras áreas.</span><span class="sxs-lookup"><span data-stu-id="08ac1-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="08ac1-145">O Lync Server também permite que você delegue tarefas administrativas específicas para pessoas ou grupos específicos usando o controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="08ac1-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="08ac1-146">O RBAC permite que os administradores deleguem direitos e permissões de usuário específicos a outros administradores para executar um subconjunto das tarefas administrativas possíveis.</span><span class="sxs-lookup"><span data-stu-id="08ac1-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="08ac1-147">Usando o RBAC, a capacidade do usuário de realizar tarefas administrativas específicas depende das funções RBAC atribuídas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="08ac1-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="08ac1-148">O RBAC fornece uma lista de cmdlets que o usuário pode executar com base nas funções RBAC das quais o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="08ac1-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

