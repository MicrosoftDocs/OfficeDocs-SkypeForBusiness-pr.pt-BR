---
title: 'Lync Server 2013: Iniciando o processo de planejamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513034"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="43ab2-102">Iniciando o processo de planejamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43ab2-102">Beginning the planning process for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43ab2-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="43ab2-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="43ab2-104">Embora o planejamento de uma implantação de comunicações unificadas local possa parecer intimidador, o Lync Server fornece duas ferramentas valiosas para ajudá-lo a:</span><span class="sxs-lookup"><span data-stu-id="43ab2-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="43ab2-105">**A ferramenta de planejamento** é um assistente que apresenta uma série de perguntas sobre sua organização, os recursos do Lync Server que você deseja habilitar e suas necessidades de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="43ab2-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="43ab2-106">Em seguida, ele cria uma topologia de implantação recomendada com base nas suas respostas e produz um diagrama do Microsoft Visio dessa implantação.</span><span class="sxs-lookup"><span data-stu-id="43ab2-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="43ab2-107">O **Construtor de topologias** é um componente de instalação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43ab2-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="43ab2-108">Use o construtor de topologias para criar, ajustar e publicar sua topologia planejada.</span><span class="sxs-lookup"><span data-stu-id="43ab2-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="43ab2-109">Ele também valida sua topologia antes de iniciar as instalações do servidor.</span><span class="sxs-lookup"><span data-stu-id="43ab2-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="43ab2-110">Quando você instala o Lync Server em servidores individuais, os servidores lêem a topologia publicada como parte do processo de instalação e o programa de instalação implanta o servidor conforme indicado na topologia.</span><span class="sxs-lookup"><span data-stu-id="43ab2-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="43ab2-111">Ferramenta de planejamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="43ab2-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="43ab2-112">A ferramenta de planejamento leva suas respostas às perguntas da ferramenta e gera uma topologia com base nas diretrizes e nas práticas recomendadas do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43ab2-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="43ab2-113">Ele também fornece vários modos de exibição de uma implantação com base nas suas respostas.</span><span class="sxs-lookup"><span data-stu-id="43ab2-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="43ab2-114">Ele mostra um modo de exibição global de todos os sites (ou seja, incluindo sites centrais e sites de filial) e exibições detalhadas mostrando os servidores e outros componentes em cada site.</span><span class="sxs-lookup"><span data-stu-id="43ab2-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="43ab2-115">A execução da ferramenta de planejamento não compromete você com nenhuma implantação específica ou inicia nenhum processo.</span><span class="sxs-lookup"><span data-stu-id="43ab2-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="43ab2-116">Na verdade, a execução da ferramenta de planejamento mesmo antes de ter um plano de firma em mente pode ser uma maneira bastante orientada de compreender os tipos de perguntas que você precisa pensar no seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="43ab2-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="43ab2-117">Você pode executar a ferramenta de planejamento várias vezes, respondendo a perguntas de forma diferente e comparando os resultados.</span><span class="sxs-lookup"><span data-stu-id="43ab2-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="43ab2-118">Se você tiver um design com o qual você está mais satisfeito, mas precisar fazer alterações no, poderá retornar à ferramenta de planejamento, carregar o design e fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="43ab2-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="43ab2-119">É necessário cerca de 15 minutos para concluir a ferramenta de planejamento uma vez.</span><span class="sxs-lookup"><span data-stu-id="43ab2-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="43ab2-120">Depois de estar satisfeito, você poderá usar a ferramenta de planejamento para criar um diagrama da implantação planejada.</span><span class="sxs-lookup"><span data-stu-id="43ab2-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="43ab2-121">Você pode usar esse diagrama ao criar a implantação no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="43ab2-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43ab2-122">A ferramenta de planejamento incluída nesta versão do Lync Server 2013 é uma versão de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="43ab2-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="43ab2-123">Observe que os números de planejamento de capacidade na ferramenta de planejamento são preliminares e não têm suporte para a versão final.</span><span class="sxs-lookup"><span data-stu-id="43ab2-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="43ab2-124">Construtor de topologias do Lync Server</span><span class="sxs-lookup"><span data-stu-id="43ab2-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="43ab2-125">Depois de decidir o plano de implantação, use o construtor de topologias para começar a implantar o.</span><span class="sxs-lookup"><span data-stu-id="43ab2-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="43ab2-126">Quando terminar, você usará o construtor de topologias para validar a topologia e, em seguida, se ele passar, você poderá publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="43ab2-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="43ab2-127">Quando você publica a topologia, o Lync Server coloca a topologia no repositório de gerenciamento central, que é criado neste momento, caso ainda não exista.</span><span class="sxs-lookup"><span data-stu-id="43ab2-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="43ab2-128">Ao instalar o Lync Server em cada servidor em sua implantação, o servidor lê a topologia do repositório de gerenciamento central e instala-se para se ajustar à sua função na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="43ab2-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="43ab2-129">Como alternativa, se você estiver familiarizado com o Lync Server e precisar de menos orientações prescritivas, poderá ignorar a ferramenta de planejamento e usar os assistentes no construtor de topologias para o design inicial da sua implantação e também para as etapas de validação e publicação.</span><span class="sxs-lookup"><span data-stu-id="43ab2-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="43ab2-130">O uso do construtor de topologias para planejar e publicar uma topologia é uma etapa obrigatória.</span><span class="sxs-lookup"><span data-stu-id="43ab2-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="43ab2-131">Você não pode ignorar o construtor de topologias e instalar o Lync Server individualmente nos servidores da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="43ab2-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="43ab2-132">Cada servidor deve ler a topologia de uma topologia validada e publicada no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="43ab2-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="43ab2-133">Processo de planejamento de High-Level</span><span class="sxs-lookup"><span data-stu-id="43ab2-133">High-Level Planning Process</span></span>

<span data-ttu-id="43ab2-134">Recomendamos o seguinte processo geral para usar a documentação e a ferramenta de planejamento para planejar a implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43ab2-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="43ab2-135">Se você estiver familiarizado com versões anteriores do Lync Server, leia os [novos recursos no Lync server 2013](lync-server-2013-new-features.md) para se familiarizar com os novos recursos e requisitos no lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43ab2-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="43ab2-136">Leia os outros tópicos nesta seção da documentação: [noções básicas de topologia que você deve saber antes de planejar o Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), as [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md), as [decisões iniciais de planejamento do Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [clientes para Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="43ab2-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="43ab2-137">Observe as decisões de planejamento representadas em [topologias de referência no Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="43ab2-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="43ab2-138">Agora que você está mais familiarizado com os recursos do Lync Server e os tipos de perguntas que devem ser respondidas, execute a ferramenta de planejamento e visualize a topologia resultante e seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="43ab2-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="43ab2-139">Certifique-se de que a topologia atenda aos requisitos exclusivos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="43ab2-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="43ab2-140">Se houver cargas de trabalho ou recursos específicos nos quais você está interessado ou precisar de mais informações, leia as seções apropriadas de [planejamento do Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="43ab2-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="43ab2-141">Execute a ferramenta de planejamento novamente.</span><span class="sxs-lookup"><span data-stu-id="43ab2-141">Run the Planning Tool again.</span></span> <span data-ttu-id="43ab2-142">Você pode começar com a implantação que você criou na etapa 3 e modificar os resultados ou recomeçar desde o início.</span><span class="sxs-lookup"><span data-stu-id="43ab2-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="43ab2-143">Se necessário, execute a ferramenta de planejamento uma terceira vez e repita até que esteja satisfeito com a saída.</span><span class="sxs-lookup"><span data-stu-id="43ab2-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="43ab2-144">Depois de finalizar o plano de topologia, use a ferramenta de planejamento para criar e imprimir um diagrama do Visio da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="43ab2-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="43ab2-145">Você pode usar essa impressão ao trabalhar com o construtor de topologias para inserir sua topologia.</span><span class="sxs-lookup"><span data-stu-id="43ab2-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="43ab2-146">Antes de começar a implantação, leia [determinando os requisitos de sistema do Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) para se familiarizar com os pré-requisitos e a infraestrutura necessária para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43ab2-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="43ab2-147">Além disso, certifique-se de ter lido todas as seções de [planejamento do Lync Server 2013](lync-server-2013-planning.md) que se aplicam às cargas de trabalho e aos recursos que você planeja implantar.</span><span class="sxs-lookup"><span data-stu-id="43ab2-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="43ab2-148">Migrando de versões anteriores</span><span class="sxs-lookup"><span data-stu-id="43ab2-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="43ab2-149">Se você estiver migrando para o Lync Server a partir de uma versão anterior, consulte a documentação de [migração](migration.md) para obter instruções específicas para sua migração e implantação.</span><span class="sxs-lookup"><span data-stu-id="43ab2-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

