---
title: Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013
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
ms.openlocfilehash: f6c4a9909bfecd8157fe3afe9f653a684fe1053b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="c1910-102">Perguntas frequentes sobre a ferramenta de desempenho e stress do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1910-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1910-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c1910-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c1910-104">Perguntas Frequentes</span><span class="sxs-lookup"><span data-stu-id="c1910-104">Frequently Asked Questions</span></span>

<span data-ttu-id="c1910-105">Aqui estão algumas perguntas frequentes sobre a ferramenta de estresse e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1910-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="c1910-106">Posso executar o LyncPerfTool. exe em produção?</span><span class="sxs-lookup"><span data-stu-id="c1910-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="c1910-107">Não recomendamos isso.</span><span class="sxs-lookup"><span data-stu-id="c1910-107">We do not recommend this.</span></span> <span data-ttu-id="c1910-108">Essa ferramenta afetará o desempenho do servidor, segurança e experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1910-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="c1910-109">Estou fazendo logon em meus usuários pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c1910-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="c1910-110">Por que os servidores estão sendo executados em alta carga?</span><span class="sxs-lookup"><span data-stu-id="c1910-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="c1910-111">Na primeira vez que os usuários fazem logon, há operações adicionais que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="c1910-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="c1910-112">Como resultado, o desempenho no servidor back-end do Microsoft SQL Server será degradado.</span><span class="sxs-lookup"><span data-stu-id="c1910-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="c1910-113">Recomendamos que você execute um teste curto que faça logon em todos os usuários e reinicie os clientes antes de medir os resultados.</span><span class="sxs-lookup"><span data-stu-id="c1910-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="c1910-114">Não há suporte para mais de 12 sessões de logon de usuário simultâneas por segundo, mas isso depende da configuração do hardware.</span><span class="sxs-lookup"><span data-stu-id="c1910-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="c1910-115">Meus clientes estão ficando sem memória.</span><span class="sxs-lookup"><span data-stu-id="c1910-115">My clients are running out of memory.</span></span> <span data-ttu-id="c1910-116">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="c1910-116">What should I do?</span></span>

<span data-ttu-id="c1910-117">Se os seus clientes estiverem ficando sem memória, você precisa reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="c1910-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="c1910-118">Meus clientes estão em 100% de CPU o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="c1910-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="c1910-119">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="c1910-119">What should I do?</span></span>

<span data-ttu-id="c1910-120">Se os seus clientes estiverem em execução com uma CPU muito alta depois que todos os usuários estiverem conectados, você precisará reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="c1910-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="c1910-121">Altos picos de CPU são aceitos, mas se estiverem estáveis, você precisará reduzir a carga.</span><span class="sxs-lookup"><span data-stu-id="c1910-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="c1910-122">Posso executar a ferramenta no próprio servidor?</span><span class="sxs-lookup"><span data-stu-id="c1910-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="c1910-123">Não.</span><span class="sxs-lookup"><span data-stu-id="c1910-123">No.</span></span> <span data-ttu-id="c1910-124">Este cenário não é suportado e pode falhar devido a uma incompatibilidade binária.</span><span class="sxs-lookup"><span data-stu-id="c1910-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="c1910-125">Além disso, como o ponto é medir o consumo de recursos no servidor, a execução da ferramenta não renderizaria as medições sem sentido.</span><span class="sxs-lookup"><span data-stu-id="c1910-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="c1910-126">Posso executar o LyncPerfTool. exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="c1910-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="c1910-127">Sim.</span><span class="sxs-lookup"><span data-stu-id="c1910-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="c1910-128">O que significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="c1910-128">What does MPOP mean?</span></span>

<span data-ttu-id="c1910-129">MPOP significa vários pontos de presença.</span><span class="sxs-lookup"><span data-stu-id="c1910-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="c1910-130">Destina-se a simular o cenário em que os usuários estão conectados ao Lync 2013 de várias máquinas.</span><span class="sxs-lookup"><span data-stu-id="c1910-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="c1910-131">Observe que, no LyncPerfTool. exe, cada ponto de extremidade usa o perfil padrão (ou seja, o perfil não é dividido entre os dois pontos de presença).</span><span class="sxs-lookup"><span data-stu-id="c1910-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="c1910-132">Iniciei o LyncPerfTool. exe, mas nada aconteceu.</span><span class="sxs-lookup"><span data-stu-id="c1910-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="c1910-133">O que está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="c1910-133">What’s going on?</span></span>

<span data-ttu-id="c1910-134">Verifique o contador total de pontos de extremidade ativos nos clientes para ver se os usuários estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="c1910-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="c1910-135">Se os usuários não estiverem se conectando, verifique a configuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1910-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="c1910-136">Esse problema geralmente ocorre porque o nome do servidor, o prefixo do usuário ou a senha está incorreto.</span><span class="sxs-lookup"><span data-stu-id="c1910-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="c1910-137">Observe que os clientes externos devem especificar o proxy de acesso como o valor TargetServer.</span><span class="sxs-lookup"><span data-stu-id="c1910-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="c1910-138">Verifique a porta no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="c1910-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="c1910-139">Como saber se algo está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="c1910-139">How do I know something is happening?</span></span>

<span data-ttu-id="c1910-140">Os vários contadores de desempenho do LyncPerfTool indicam se os usuários estão se conectando e executando ações.</span><span class="sxs-lookup"><span data-stu-id="c1910-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="c1910-141">No entanto, uma maneira fácil de verificar é fazer logon em uma das contas usando o Lync 2013 e executando a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="c1910-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="c1910-142">Possuo ferramentas de planejamento de capacidade do Live Communications Server 2007 R2 e/ou o Lync Server 2010 instalado.</span><span class="sxs-lookup"><span data-stu-id="c1910-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="c1910-143">Isso é tudo certo?</span><span class="sxs-lookup"><span data-stu-id="c1910-143">Is that OK?</span></span>

<span data-ttu-id="c1910-144">Não.</span><span class="sxs-lookup"><span data-stu-id="c1910-144">No.</span></span> <span data-ttu-id="c1910-145">Há problemas de interoperabilidade, e você deve desinstalar todas as versões anteriores deste produto.</span><span class="sxs-lookup"><span data-stu-id="c1910-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="c1910-146">As ferramentas de estresse e desempenho definirão a topologia do servidor de informações de chamadas do CAA?</span><span class="sxs-lookup"><span data-stu-id="c1910-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="c1910-147">Não.</span><span class="sxs-lookup"><span data-stu-id="c1910-147">No.</span></span> <span data-ttu-id="c1910-148">As ferramentas apenas criam usuários, contatos e listas de distribuição e simulam a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1910-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="c1910-149">Qual é o número máximo de usuários que as ferramentas dão suporte?</span><span class="sxs-lookup"><span data-stu-id="c1910-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="c1910-150">Nós criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários, usando essas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="c1910-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="c1910-151">Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor maior, dependendo do hardware do cliente e do servidor disponível.</span><span class="sxs-lookup"><span data-stu-id="c1910-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

