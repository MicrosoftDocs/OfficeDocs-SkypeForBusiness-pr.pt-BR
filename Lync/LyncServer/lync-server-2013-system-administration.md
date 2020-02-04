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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="9df92-102">Administração do sistema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9df92-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9df92-103">_**Tópico da última modificação:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="9df92-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="9df92-104">A administração do sistema inclui as tarefas administrativas do dia a dia, planejadas e sob demanda, que são necessárias para manter um sistema de ti operando tranqüilamente.</span><span class="sxs-lookup"><span data-stu-id="9df92-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="9df92-105">Geralmente, as tarefas de administração do sistema são cobertas pelos procedimentos escritos.</span><span class="sxs-lookup"><span data-stu-id="9df92-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="9df92-106">Esses procedimentos ajudam a garantir que as mesmas ferramentas e métodos padrão sejam usados por todos os membros da equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="9df92-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="9df92-107">Em um ambiente do Lync, as tarefas típicas de administração do sistema incluem fazer backup e arquivamento de pools, monitorar logs, criar e gerenciar usuários e atualizar o software antivírus.</span><span class="sxs-lookup"><span data-stu-id="9df92-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="9df92-108">Solução de problemas do sistema</span><span class="sxs-lookup"><span data-stu-id="9df92-108">System troubleshooting</span></span>

<span data-ttu-id="9df92-109">Uma organização deve estar preparada para lidar com problemas inesperados e deve ter um procedimento para gerenciar problemas do ponto em que são reportados até a resolução.</span><span class="sxs-lookup"><span data-stu-id="9df92-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="9df92-110">Informações sobre como a equipe de suporte diagnosticou um problema devem ser gravadas e usadas no futuro para evitar o trabalho concluído de repetição desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="9df92-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="9df92-111">Processo de solução de problemas do sistema</span><span class="sxs-lookup"><span data-stu-id="9df92-111">System troubleshooting process</span></span>

<span data-ttu-id="9df92-112">O diagrama a seguir mostra o processo de solução de problemas do sistema e as interações com outras funções de operações.</span><span class="sxs-lookup"><span data-stu-id="9df92-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="9df92-113">**Fluxograma de solução de problemas do sistema**</span><span class="sxs-lookup"><span data-stu-id="9df92-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="9df92-114">![Fluxograma de solução de problemas do sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Fluxograma de solução de problemas do sistema")</span><span class="sxs-lookup"><span data-stu-id="9df92-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="9df92-115">**Classificar e priorizar**   essa tarefa geralmente é realizada pela mesa do serviço.</span><span class="sxs-lookup"><span data-stu-id="9df92-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="9df92-116">Por exemplo, um problema pode ser agrupado como um problema de software ou de hardware.</span><span class="sxs-lookup"><span data-stu-id="9df92-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="9df92-117">O problema é encaminhado para a equipe de suporte apropriada para investigação.</span><span class="sxs-lookup"><span data-stu-id="9df92-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="9df92-118">As regras para determinar a prioridade de um problema, em conjunto com o tempo de resposta e tempo para resolver, geralmente são definidas no SLA.</span><span class="sxs-lookup"><span data-stu-id="9df92-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="9df92-119">**Investigue e diagnostique**   a equipe de suporte apropriada diagnostica o problema e propõe mudanças para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="9df92-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="9df92-120">Se a solução for simples e não exigir controle de alterações, a solução poderá ser aplicada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9df92-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="9df92-121">Se a solução não for fácil, uma solicitação de alteração deve ser gerada e o trabalho proposto deve ser gerenciado pelo processo de gerenciamento de alterações, frequentemente sob um procedimento de "controle rápido".</span><span class="sxs-lookup"><span data-stu-id="9df92-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="9df92-122">Todas as alterações feitas devem ser gravadas usando o processo de gerenciamento de configuração.</span><span class="sxs-lookup"><span data-stu-id="9df92-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="9df92-123">**Fechar e gravar**   após testar a resolução, o problema deve ser fechado.</span><span class="sxs-lookup"><span data-stu-id="9df92-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="9df92-124">Se houver aulas a serem aprendidas a partir do problema, uma entrada deve ser criada na base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="9df92-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="9df92-125">\*\*\*\*   Análises de análise de tendências e análises periódicas de problemas recentes devem ser realizadas para identificar as tendências dos problemas.</span><span class="sxs-lookup"><span data-stu-id="9df92-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="9df92-126">Por exemplo, se os usuários estiverem experimentando problemas frequentes com logons lentos para seus sites do Lync, problemas de largura de banda de rede podem ser a causa.</span><span class="sxs-lookup"><span data-stu-id="9df92-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="9df92-127">Problemas de resolução de problemas e o efeito de qualquer paralisação na disponibilidade do sistema deve ser revisado e comparado com o SLA.</span><span class="sxs-lookup"><span data-stu-id="9df92-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="9df92-128">A pessoa que liaises com os problemas de serviço do cliente, como um gerente de contas, deve ser informada sobre problemas significativos.</span><span class="sxs-lookup"><span data-stu-id="9df92-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="9df92-129">Ferramentas de gerenciamento de problemas</span><span class="sxs-lookup"><span data-stu-id="9df92-129">Issue management tools</span></span>

<span data-ttu-id="9df92-130">As ferramentas de suporte do serviço permitem que a equipe Registre, classifique e Priorize novos problemas.</span><span class="sxs-lookup"><span data-stu-id="9df92-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="9df92-131">Em seguida, as ferramentas fornecerão os processos de fluxo de trabalho para gerenciar a solicitação de serviço de problemas por meio de investigação e diagnóstico, muitas vezes por mais de uma equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="9df92-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="9df92-132">Ferramentas, que freqüentemente fornecem relatórios sobre tempos de resolução e tendências históricas também podem incluir um banco de dados base de conhecimento, que pode ser usado para pesquisar por problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="9df92-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="9df92-133">A base de dados de conhecimento Microsoft é um registro útil de problemas de suporte encontrados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9df92-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="9df92-134">Para obter mais informações, consulte o site de suporte<http://go.microsoft.com/fwlink/?linkid=14898>da Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="9df92-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="9df92-135">Geralmente, o software de terceiros exige a personalização para atender às necessidades da organização, como a organização de equipes, os requisitos de relatórios e as medidas necessárias para o SLA.</span><span class="sxs-lookup"><span data-stu-id="9df92-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="9df92-136">Administração centralizada versus descentralizada</span><span class="sxs-lookup"><span data-stu-id="9df92-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="9df92-137">Funções e responsabilidades para executar tarefas de administração do sistema dependem se a organização segue um modelo centralizado, um modelo descentralizado ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="9df92-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="9df92-138">**O modelo**   centralizado em um modelo centralizado, um ou vários grupos administrativos mantém o controle total de todo o ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9df92-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="9df92-139">Esse modelo administrativo é semelhante a um data center onde todas as tarefas de administração são realizadas por um único grupo de tecnologia da informação.</span><span class="sxs-lookup"><span data-stu-id="9df92-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="9df92-140">As funções e responsabilidades dentro da equipe devem ser definidas de acordo com a experiência e a experiência.</span><span class="sxs-lookup"><span data-stu-id="9df92-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="9df92-141">**Modelo descentralizado**   as organizações descentralizadas estão localizadas em diversos locais geográficos e têm servidores do Lync Server em funcionamento e equipes de administradores em diferentes locais.</span><span class="sxs-lookup"><span data-stu-id="9df92-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="9df92-142">Por exemplo, pode haver um pessoal de administração local e um ou mais servidores que executam o Lync Server 2013 para cada país/região.</span><span class="sxs-lookup"><span data-stu-id="9df92-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="9df92-143">Ou, pode haver um pool de servidores executando o Lync Server 2013 e uma equipe administrativa para a América do Norte e outro para a Europa.</span><span class="sxs-lookup"><span data-stu-id="9df92-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="9df92-144">Às vezes, você pode querer que os administradores sejam responsáveis apenas por sua própria área geográfica e restrinja permissões para administrar recursos em outras áreas.</span><span class="sxs-lookup"><span data-stu-id="9df92-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="9df92-145">O Lync Server também permite que você delegue tarefas administrativas específicas para pessoas ou grupos específicos usando o controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="9df92-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="9df92-146">O RBAC permite que os administradores deleguem direitos de usuário específicos e permissões a outros administradores executem um subconjunto de tarefas administrativas possível.</span><span class="sxs-lookup"><span data-stu-id="9df92-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="9df92-147">Ao usar o RBAC, a capacidade de o usuário executar tarefas administrativas específicas depende das funções RBAC atribuídas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="9df92-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="9df92-148">RBAC fornece uma lista de cmdlets que o usuário pode executar com base nas funções RBAC das quais o usuário é membro.</span><span class="sxs-lookup"><span data-stu-id="9df92-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

