---
title: Perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="47976-102">Perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47976-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47976-103">_**Tópico da última modificação:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="47976-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="47976-104">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="47976-104">Frequently Asked Questions</span></span>

<span data-ttu-id="47976-105">Aqui estão algumas perguntas frequentes sobre a ferramenta de stress e desempenho do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47976-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="47976-106">É possível executar o LyncPerfTool. exe na produção?</span><span class="sxs-lookup"><span data-stu-id="47976-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="47976-107">Não recomendamos isso.</span><span class="sxs-lookup"><span data-stu-id="47976-107">We do not recommend this.</span></span> <span data-ttu-id="47976-108">Essa ferramenta afetará o desempenho do servidor, a segurança e a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="47976-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="47976-109">Estou me conectando aos meus usuários pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="47976-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="47976-110">Por que os servidores estão em execução em alta carga?</span><span class="sxs-lookup"><span data-stu-id="47976-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="47976-111">Na primeira vez que os usuários fazem logon, há operações adicionais que ocorrem.</span><span class="sxs-lookup"><span data-stu-id="47976-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="47976-112">Como resultado, o desempenho no servidor back-end do Microsoft SQL Server será degradado.</span><span class="sxs-lookup"><span data-stu-id="47976-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="47976-113">Recomendamos que você execute um teste curto que Registre todos os usuários e reinicie os clientes antes de medir os resultados.</span><span class="sxs-lookup"><span data-stu-id="47976-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="47976-114">Não há suporte para mais de 12 sessões de logon de usuários simultâneas por segundo, mas isso depende da configuração do hardware.</span><span class="sxs-lookup"><span data-stu-id="47976-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="47976-115">Meus clientes estão ficando sem memória.</span><span class="sxs-lookup"><span data-stu-id="47976-115">My clients are running out of memory.</span></span> <span data-ttu-id="47976-116">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="47976-116">What should I do?</span></span>

<span data-ttu-id="47976-117">Se os seus clientes estiverem ficando sem memória, você precisará reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="47976-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="47976-118">Meus clientes estão em 100% de CPU o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="47976-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="47976-119">O que devo fazer?</span><span class="sxs-lookup"><span data-stu-id="47976-119">What should I do?</span></span>

<span data-ttu-id="47976-120">Se seus clientes estiverem sendo executados com uma CPU muito alta depois que todos os usuários estiverem conectados, você precisará reduzir o número de usuários por computador.</span><span class="sxs-lookup"><span data-stu-id="47976-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="47976-121">Altos picos de CPU são aceitáveis, mas se estiverem estáveis, você precisará reduzir a carga.</span><span class="sxs-lookup"><span data-stu-id="47976-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="47976-122">É possível executar a ferramenta no próprio servidor?</span><span class="sxs-lookup"><span data-stu-id="47976-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="47976-123">Não.</span><span class="sxs-lookup"><span data-stu-id="47976-123">No.</span></span> <span data-ttu-id="47976-124">Não há suporte para esse cenário e pode falhar devido a uma incompatibilidade binária.</span><span class="sxs-lookup"><span data-stu-id="47976-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="47976-125">Além disso, como o ponto é medir o consumo de recursos no servidor, executar a ferramenta não renderizaria as medidas sem significado.</span><span class="sxs-lookup"><span data-stu-id="47976-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="47976-126">É possível executar o LyncPerfTool. exe em um servidor virtual ou no Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="47976-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="47976-127">Sim.</span><span class="sxs-lookup"><span data-stu-id="47976-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="47976-128">O que significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="47976-128">What does MPOP mean?</span></span>

<span data-ttu-id="47976-129">MPOP significa vários pontos de presença.</span><span class="sxs-lookup"><span data-stu-id="47976-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="47976-130">Destina-se a simular o cenário em que os usuários estão conectados ao Lync 2013 de várias máquinas.</span><span class="sxs-lookup"><span data-stu-id="47976-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="47976-131">Observe que em LyncPerfTool. exe, cada ponto de extremidade usa o perfil padrão (ou seja, o perfil não é dividido entre os dois pontos de presença).</span><span class="sxs-lookup"><span data-stu-id="47976-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="47976-132">Comecei LyncPerfTool. exe, mas nada está acontecendo.</span><span class="sxs-lookup"><span data-stu-id="47976-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="47976-133">O que está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="47976-133">What’s going on?</span></span>

<span data-ttu-id="47976-134">Verifique o contador total de pontos de extremidade ativos nos clientes para ver se os usuários estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="47976-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="47976-135">Se os usuários não estiverem se conectando, verifique a configuração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47976-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="47976-136">Geralmente, esse problema ocorre porque o nome do servidor, o prefixo do usuário ou a senha estão incorretos.</span><span class="sxs-lookup"><span data-stu-id="47976-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="47976-137">Observe que os clientes externos devem especificar o proxy de acesso como o valor TargetServer.</span><span class="sxs-lookup"><span data-stu-id="47976-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="47976-138">Verifique a porta no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="47976-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="47976-139">Como posso saber se algo está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="47976-139">How do I know something is happening?</span></span>

<span data-ttu-id="47976-140">Os vários contadores de desempenho do LyncPerfTool indicam se os usuários estão se conectando e executando ações.</span><span class="sxs-lookup"><span data-stu-id="47976-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="47976-141">No entanto, uma maneira fácil de verificar é fazer logon em uma das contas usando o Lync 2013 e executando a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="47976-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="47976-142">Tenho ferramentas de planejamento de capacidade do Live Communications Server 2007 R2 e/ou Lync Server 2010 instaladas.</span><span class="sxs-lookup"><span data-stu-id="47976-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="47976-143">Isso é tudo OK?</span><span class="sxs-lookup"><span data-stu-id="47976-143">Is that OK?</span></span>

<span data-ttu-id="47976-144">Não.</span><span class="sxs-lookup"><span data-stu-id="47976-144">No.</span></span> <span data-ttu-id="47976-145">Há problemas de interoperabilidade, e você deve desinstalar todas as versões anteriores deste produto.</span><span class="sxs-lookup"><span data-stu-id="47976-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="47976-146">As ferramentas de stress e desempenho configuram a CAA Call Information Server Topology?</span><span class="sxs-lookup"><span data-stu-id="47976-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="47976-147">Não.</span><span class="sxs-lookup"><span data-stu-id="47976-147">No.</span></span> <span data-ttu-id="47976-148">As ferramentas apenas criam usuários, contatos e listas de distribuição e simulam a carga do usuário.</span><span class="sxs-lookup"><span data-stu-id="47976-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="47976-149">Qual é o número máximo de usuários com suporte para as ferramentas?</span><span class="sxs-lookup"><span data-stu-id="47976-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="47976-150">Criamos até um total de 80.000 usuários e executamos testes totalizando 30.000 usuários, usando essas ferramentas.</span><span class="sxs-lookup"><span data-stu-id="47976-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="47976-151">Sugerimos um máximo de 120.000 usuários, embora as limitações técnicas permitam um valor mais alto, dependendo do hardware do cliente e do servidor disponível.</span><span class="sxs-lookup"><span data-stu-id="47976-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

