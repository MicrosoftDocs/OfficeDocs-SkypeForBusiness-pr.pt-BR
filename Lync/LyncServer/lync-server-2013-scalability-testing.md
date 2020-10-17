---
title: Teste de escalabilidade do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511008"
---
# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="d0e4a-102">Testes de escalabilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0e4a-102">Scalability testing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0e4a-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d0e4a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d0e4a-104">O Lync Server 2013 fornece a infraestrutura de servidor para todas as comunicações em tempo real do Lync Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="d0e4a-105">Isso inclui todos os recursos que usam os recursos de hardware de um pool do Lync Server 2013 e, portanto, afetam o desempenho e a escala.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="d0e4a-106">Todas as organizações não usam os mesmos recursos.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="d0e4a-107">Por exemplo, algumas organizações podem usar vídeo em conferências muito pesadas enquanto outros podem não ter ou quase não ter uso de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="d0e4a-108">Algumas organizações preferem compartilhamento de slides do PowerPoint ao compartilhamento de aplicativos, enquanto outros preferem o oposto.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="d0e4a-109">As organizações que implantam o Enterprise Voice podem ou não usar o aplicativo de grupo de resposta de muitas pessoas.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="d0e4a-110">A maioria das organizações implanta servidores de monitoramento, mas não muitos deles implantam servidores de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="d0e4a-111">Além disso, as organizações não têm a mesma infraestrutura, incluindo capacidade de hardware, capacidade de rede e número de pools e tamanho dos pools implantados.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="d0e4a-112">A diversidade dos recursos e infraestrutura é um desafio para o teste de escalabilidade – não é possível simular todas as combinações possíveis de recursos e infraestruturas.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="d0e4a-113">Para determinar o suporte de escalabilidade para o Lync Server, realizamos testes usando todos os recursos do Lync Server simultaneamente, com base em um modelo de uso médio (modelo de usuário).</span><span class="sxs-lookup"><span data-stu-id="d0e4a-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="d0e4a-114">Para determinar um modelo de usuário apropriado para cargas de trabalho do Lync Server, analisamos muitos pontos de dados, incluindo pesquisas de clientes, comentários do programa de aperfeiçoamento da experiência do usuário da Microsoft, dados de uso do Lync Server do departamento de ti interno da Microsoft e dados minados de nosso serviço do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="d0e4a-115">Em vários casos, o modelo do usuário tem uma tendência em relação às cargas pesadas para oferecer uma margem confortável de uso dentro de uma organização.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="d0e4a-116">Em nossos testes de escalabilidade, configuramos pools do Lync Server 2013 de acordo com as especificações recomendadas de hardware e software, incluindo componentes de infraestrutura, como serviços de domínio do Active Directory, balanceadores de carga de hardware e firewalls.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="d0e4a-117">Configuramos os ambientes do Lync Server o mais próximo possível dos ambientes reais típicos.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="d0e4a-118">Em seguida, usamos a ferramenta de estresse e desempenho do Lync Server 2013 para simular cargas do Lync Server 2013 (com base no nosso modelo de usuário).</span><span class="sxs-lookup"><span data-stu-id="d0e4a-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="d0e4a-119">.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-119">.</span></span>

<span data-ttu-id="d0e4a-p105">Realizamos várias iterações de testes de escalabilidade (incluindo várias execuções de testes de três semanas). Usamos os resultados de todos os testes para ajudar com a sintonização do desempenho e verificar o suporte para os números de escalabilidade em nosso modelo do usuário.</span><span class="sxs-lookup"><span data-stu-id="d0e4a-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

