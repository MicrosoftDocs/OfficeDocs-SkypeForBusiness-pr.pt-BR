---
title: Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013
description: Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573537"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="f86e4-103">Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f86e4-103">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f86e4-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f86e4-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f86e4-105">Perguntas Frequentes</span><span class="sxs-lookup"><span data-stu-id="f86e4-105">Frequently Asked Questions</span></span>

<span data-ttu-id="f86e4-106">Aqui estão algumas perguntas frequentes sobre a ferramenta de estresse e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f86e4-106">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="f86e4-107">É possível executar LyncPerfTool.exe em produção?</span><span class="sxs-lookup"><span data-stu-id="f86e4-107">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="f86e4-108">Não recomendamos isso.</span><span class="sxs-lookup"><span data-stu-id="f86e4-108">We do not recommend this.</span></span> <span data-ttu-id="f86e4-109">Essa ferramenta afetará o desempenho do servidor, segurança e experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="f86e4-109">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="f86e4-110">Estou fazendo logon em meus usuários pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f86e4-110">I am logging on my users for the first time.</span></span> <span data-ttu-id="f86e4-111">Por que os servidores estão sendo executados em alta carga?</span><span class="sxs-lookup"><span data-stu-id="f86e4-111">Why are the servers running at such high load?</span></span>

<span data-ttu-id="f86e4-112">Na primeira vez que os usuários fazem logon, há operações adicionais que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="f86e4-112">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="f86e4-113">Como resultado, o desempenho no servidor back-end do Microsoft SQL Server será degradado.</span><span class="sxs-lookup"><span data-stu-id="f86e4-113">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="f86e4-114">Recomendamos que você execute um teste curto que faça logon em todos os usuários e reinicie os clientes antes de medir os resultados.</span><span class="sxs-lookup"><span data-stu-id="f86e4-114">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="f86e4-115">Não há suporte para mais de 12 sessões de logon de usuário simultâneas por segundo, mas isso depende da configuração do hardware.</span><span class="sxs-lookup"><span data-stu-id="f86e4-115">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="f86e4-116">Meus clientes estão ficando sem memória.</span><span class="sxs-lookup"><span data-stu-id="f86e4-116">My clients are running out of memory.</span></span> <span data-ttu-id="f86e4-117">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="f86e4-117">What should I do?</span></span>

<span data-ttu-id="f86e4-118">Se os seus clientes estiverem ficando sem memória, você precisa reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="f86e4-118">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="f86e4-119">Meus clientes estão em 100% de CPU o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="f86e4-119">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="f86e4-120">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="f86e4-120">What should I do?</span></span>

<span data-ttu-id="f86e4-121">Se os seus clientes estiverem em execução com uma CPU muito alta depois que todos os usuários estiverem conectados, você precisará reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="f86e4-121">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="f86e4-122">Altos picos de CPU são aceitos, mas se estiverem estáveis, você precisará reduzir a carga.</span><span class="sxs-lookup"><span data-stu-id="f86e4-122">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="f86e4-123">Posso executar a ferramenta no próprio servidor?</span><span class="sxs-lookup"><span data-stu-id="f86e4-123">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="f86e4-124">Não.</span><span class="sxs-lookup"><span data-stu-id="f86e4-124">No.</span></span> <span data-ttu-id="f86e4-125">Este cenário não é suportado e pode falhar devido a uma incompatibilidade binária.</span><span class="sxs-lookup"><span data-stu-id="f86e4-125">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="f86e4-126">Além disso, como o ponto é medir o consumo de recursos no servidor, a execução da ferramenta não renderizaria as medições sem sentido.</span><span class="sxs-lookup"><span data-stu-id="f86e4-126">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="f86e4-127">É possível executar LyncPerfTool.exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="f86e4-127">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="f86e4-128">Sim.</span><span class="sxs-lookup"><span data-stu-id="f86e4-128">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="f86e4-129">O que significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="f86e4-129">What does MPOP mean?</span></span>

<span data-ttu-id="f86e4-130">MPOP significa vários pontos de presença.</span><span class="sxs-lookup"><span data-stu-id="f86e4-130">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="f86e4-131">Destina-se a simular o cenário em que os usuários estão conectados ao Lync 2013 de várias máquinas.</span><span class="sxs-lookup"><span data-stu-id="f86e4-131">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="f86e4-132">Observe que, em LyncPerfTool.exe, cada ponto de extremidade usa o perfil padrão (ou seja, o perfil não é dividido entre os dois pontos de presença).</span><span class="sxs-lookup"><span data-stu-id="f86e4-132">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="f86e4-133">Iniciei LyncPerfTool.exe mas nada está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="f86e4-133">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="f86e4-134">O que está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="f86e4-134">What’s going on?</span></span>

<span data-ttu-id="f86e4-135">Verifique o contador total de pontos de extremidade ativos nos clientes para ver se os usuários estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="f86e4-135">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="f86e4-136">Se os usuários não estiverem se conectando, verifique a configuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f86e4-136">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="f86e4-137">Esse problema geralmente ocorre porque o nome do servidor, o prefixo do usuário ou a senha está incorreto.</span><span class="sxs-lookup"><span data-stu-id="f86e4-137">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="f86e4-138">Observe que os clientes externos devem especificar o proxy de acesso como o valor TargetServer.</span><span class="sxs-lookup"><span data-stu-id="f86e4-138">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="f86e4-139">Verifique a porta no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="f86e4-139">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="f86e4-140">Como saber se algo está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="f86e4-140">How do I know something is happening?</span></span>

<span data-ttu-id="f86e4-141">Os vários contadores de desempenho do LyncPerfTool indicam se os usuários estão se conectando e executando ações.</span><span class="sxs-lookup"><span data-stu-id="f86e4-141">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="f86e4-142">No entanto, uma maneira fácil de verificar é fazer logon em uma das contas usando o Lync 2013 e executando a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="f86e4-142">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="f86e4-143">Possuo ferramentas de planejamento de capacidade do Live Communications Server 2007 R2 e/ou o Lync Server 2010 instalado.</span><span class="sxs-lookup"><span data-stu-id="f86e4-143">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="f86e4-144">Isso é tudo certo?</span><span class="sxs-lookup"><span data-stu-id="f86e4-144">Is that OK?</span></span>

<span data-ttu-id="f86e4-145">Não.</span><span class="sxs-lookup"><span data-stu-id="f86e4-145">No.</span></span> <span data-ttu-id="f86e4-146">Há problemas de interoperabilidade, e você deve desinstalar todas as versões anteriores deste produto.</span><span class="sxs-lookup"><span data-stu-id="f86e4-146">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="f86e4-147">As ferramentas de estresse e desempenho definirão a topologia do servidor de informações de chamadas do CAA?</span><span class="sxs-lookup"><span data-stu-id="f86e4-147">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="f86e4-148">Não.</span><span class="sxs-lookup"><span data-stu-id="f86e4-148">No.</span></span> <span data-ttu-id="f86e4-149">As ferramentas apenas criam usuários, contatos e listas de distribuição e simulam a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="f86e4-149">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="f86e4-150">Qual é o número máximo de usuários que as ferramentas dão suporte?</span><span class="sxs-lookup"><span data-stu-id="f86e4-150">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="f86e4-151">Nós criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários, usando essas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="f86e4-151">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="f86e4-152">Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor maior, dependendo do hardware do cliente e do servidor disponível.</span><span class="sxs-lookup"><span data-stu-id="f86e4-152">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

