---
title: 'Lync Server 2013: contratos de nível de serviço'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8c4b827cf2b82eb315ec166bcabb2452e7d8bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="f1221-102">Contratos de nível de serviço no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1221-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1221-103">_**Tópico da última modificação:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f1221-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f1221-104">O SLA é um documento que define os serviços que seu cliente espera.</span><span class="sxs-lookup"><span data-stu-id="f1221-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="f1221-105">A complexidade e o conteúdo deste documento dependem principalmente se os clientes são internos (dentro do seu ambiente) ou externos.</span><span class="sxs-lookup"><span data-stu-id="f1221-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="f1221-106">Clientes externos</span><span class="sxs-lookup"><span data-stu-id="f1221-106">External Customers</span></span>

<span data-ttu-id="f1221-107">Se o seu cliente for externo, o SLA poderá fazer parte de um contrato legal com incentivos financeiros e penalidades para o desempenho que está dentro ou fora dos níveis definidos de serviço.</span><span class="sxs-lookup"><span data-stu-id="f1221-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="f1221-108">A definição desses níveis de serviço deve fazer parte da negociação geral do contrato.</span><span class="sxs-lookup"><span data-stu-id="f1221-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="f1221-109">Como em todos os contratos, é importante que ambas as partes compreendam as expectativas.</span><span class="sxs-lookup"><span data-stu-id="f1221-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="f1221-110">O SLA define essas expectativas.</span><span class="sxs-lookup"><span data-stu-id="f1221-110">The SLA defines these expectations.</span></span> <span data-ttu-id="f1221-111">O conteúdo do documento deve ser alterado com pouca frequência e apenas por meio de negociações com o cliente.</span><span class="sxs-lookup"><span data-stu-id="f1221-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="f1221-112">Clientes internos</span><span class="sxs-lookup"><span data-stu-id="f1221-112">Internal Customers</span></span>

<span data-ttu-id="f1221-113">Se o seu cliente for interno, você ainda poderá definir os serviços que são esperados das equipes de operações e dos sistemas de ti.</span><span class="sxs-lookup"><span data-stu-id="f1221-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="f1221-114">O SLA pode ser criado pela equipe de operações e tem como objetivo um conjunto de metas para a disponibilidade de serviços de ti dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f1221-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="f1221-115">Ou os níveis de desempenho podem ser definidos pelo gerenciamento e usados como benchmarks ao avaliar o desempenho da equipe.</span><span class="sxs-lookup"><span data-stu-id="f1221-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="f1221-116">Critérios típicos</span><span class="sxs-lookup"><span data-stu-id="f1221-116">Typical Criteria</span></span>

<span data-ttu-id="f1221-117">Os SLAs incluem seções que definem critérios de níveis mínimos de disponibilidade, suporte e capacidade.</span><span class="sxs-lookup"><span data-stu-id="f1221-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="f1221-118">**Disponibilidade**   defina as horas e os sistemas operacionais nos quais os sites e outros serviços do Lync estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f1221-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="f1221-119">Qualquer manutenção de rotina que afete a disponibilidade do serviço deve ser definida.</span><span class="sxs-lookup"><span data-stu-id="f1221-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="f1221-120">Defina fatores externos que afetam o serviço, por exemplo, a perda de conectividade com a Internet.</span><span class="sxs-lookup"><span data-stu-id="f1221-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="f1221-121">**Suporte**   defina as horas em que o suporte a um sistema estará disponível.</span><span class="sxs-lookup"><span data-stu-id="f1221-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="f1221-122">Especifique métodos para os clientes entrarem em contato com a equipe de suporte, como os incidentes são agrupados e o tempo de destino para responder e resolver o incidente.</span><span class="sxs-lookup"><span data-stu-id="f1221-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="f1221-123">Defina a frequência e o conteúdo do comentário para o cliente.</span><span class="sxs-lookup"><span data-stu-id="f1221-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="f1221-124">**A capacidade**   define o tamanho máximo habilitado de sites do Lync e as etapas a serem seguidas se o limite for excedido.</span><span class="sxs-lookup"><span data-stu-id="f1221-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="f1221-125">Defina o tempo máximo permitido para executar tarefas padrão, como o tempo para recuperar um documento de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f1221-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="f1221-126">Defina o número máximo de usuários por pool do Lync e concorde com um processo para aumentar a capacidade se mais usuários forem adicionados.</span><span class="sxs-lookup"><span data-stu-id="f1221-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

