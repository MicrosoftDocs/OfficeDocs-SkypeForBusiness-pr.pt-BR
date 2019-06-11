---
title: Teste de escalabilidade do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="85f96-102">Testes de escalabilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85f96-102">Scalability testing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85f96-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="85f96-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="85f96-104">O Lync Server 2013 fornece a infraestrutura de servidor para todas as comunicações em tempo real do Lync Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85f96-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="85f96-105">Isso inclui os recursos que usam os recursos de hardware de um pool do Lync Server 2013 e, portanto, afetam o desempenho e a escala.</span><span class="sxs-lookup"><span data-stu-id="85f96-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="85f96-106">Todas as organizações não usam todos os recursos da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="85f96-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="85f96-107">Por exemplo, algumas organizações podem usar vídeo em conferências muito difíceis enquanto outras podem ter pouco ou nenhum uso de vídeo.</span><span class="sxs-lookup"><span data-stu-id="85f96-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="85f96-108">Algumas organizações preferem o compartilhamento de slides do PowerPoint ao compartilhamento de aplicativos, enquanto outras preferem o oposto.</span><span class="sxs-lookup"><span data-stu-id="85f96-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="85f96-109">Essas organizações que implantam o Enterprise Voice podem ou não usar o aplicativo de grupo de resposta pesadamente.</span><span class="sxs-lookup"><span data-stu-id="85f96-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="85f96-110">A maioria das organizações implanta servidores de monitoramento, mas não muitas delas implantam servidores de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="85f96-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="85f96-111">Além disso, as organizações não têm todas as mesmas infra-estruturas, incluindo capacidades de hardware, capacidades de rede e o número de pools e o tamanho dos pools implantados.</span><span class="sxs-lookup"><span data-stu-id="85f96-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="85f96-112">A diversidade de recursos e infraestruturas apresenta um desafio para testes de escalabilidade – não é possível simular todas as combinações possíveis de recursos e infraestruturas.</span><span class="sxs-lookup"><span data-stu-id="85f96-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="85f96-113">Para determinar o suporte de escalabilidade do Lync Server, realizamos testes usando todos os recursos do Lync Server simultaneamente, com base em um modelo de uso médio (modelo de usuário).</span><span class="sxs-lookup"><span data-stu-id="85f96-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="85f96-114">Para determinar um modelo de usuário apropriado para cargas de trabalho do Lync Server, analisamos muitos pontos de dados, incluindo pesquisas de cliente, comentários do programa de aperfeiçoamento da experiência do usuário da Microsoft, dados de uso do Lync Server do departamento de ti interno da Microsoft, e dados minados pelo nosso serviço de reunião ao vivo.</span><span class="sxs-lookup"><span data-stu-id="85f96-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="85f96-115">Em muitos casos, o modelo de usuário tem um Bias em direção a cargas mais pesadas para fornecer uma margem confortável para uso dentro de uma organização.</span><span class="sxs-lookup"><span data-stu-id="85f96-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="85f96-116">Em nossos testes de escalabilidade, configuramos pools do Lync Server 2013 de acordo com as especificações recomendadas de hardware e software, incluindo componentes de infraestrutura, como os serviços de domínio do Active Directory, saldos de carga de hardware e firewalls.</span><span class="sxs-lookup"><span data-stu-id="85f96-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="85f96-117">Configuramos os ambientes do Lync Server o mais próximo possível para ambientes típicos do mundo real.</span><span class="sxs-lookup"><span data-stu-id="85f96-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="85f96-118">Em seguida, usamos a ferramenta de stress e desempenho do Lync Server 2013 para simular cargas do Lync Server 2013 (com base em nosso modelo de usuário).</span><span class="sxs-lookup"><span data-stu-id="85f96-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="85f96-119">.</span><span class="sxs-lookup"><span data-stu-id="85f96-119"></span></span>

<span data-ttu-id="85f96-120">Fazemos várias iterações de testes de escalabilidade (incluindo várias execuções de teste de três semanas).</span><span class="sxs-lookup"><span data-stu-id="85f96-120">We do multiple iterations of scalability tests (including multiple three-week test runs).</span></span> <span data-ttu-id="85f96-121">Usamos os resultados de todos os testes para ajudar com o ajuste de desempenho e para verificar o suporte para os números de escalabilidade em nosso modelo de usuário.</span><span class="sxs-lookup"><span data-stu-id="85f96-121">We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

