---
title: Distribuição de carga de conferência do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66cfdab2f59ca29022435a1f7863e8fce79075e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="84e1c-102">Distribuição de carga de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84e1c-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84e1c-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="84e1c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="84e1c-104">Diferentemente de outras soluções de conferência dedicadas, a arquitetura do Lync Server é um modelo de hardware compartilhado.</span><span class="sxs-lookup"><span data-stu-id="84e1c-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="84e1c-105">Isto significa que o mesmo hardware é compartilhado por muitos componentes de software, cada um dos quais suporta diferentes comunicações em tempo real.</span><span class="sxs-lookup"><span data-stu-id="84e1c-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="84e1c-106">Cada tipo de comunicações em tempo real coloca cargas específicas sobre os servidores.</span><span class="sxs-lookup"><span data-stu-id="84e1c-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="84e1c-107">Por exemplo, o servidor front-end pode executar os componentes de roteamento do protocolo SIP, aplicativos Web (como pesquisa do catálogo de endereços), serviço de webconferência, serviço de conferência A/V, aplicativos do Enterprise Voice (por exemplo, aplicativo de atendedor de conferência e aplicativo de grupo de resposta) e servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="84e1c-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="84e1c-108">Um conjunto de bancos de dados no servidor front-end também fornece armazenamento e processamento para o usuário, contato, presença, conferência e dados de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="84e1c-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="84e1c-109">Com esse compartilhamento de hardware, os componentes, os serviços e os processos competem com os recursos de CPU e memória, dessa forma, as cargas de trabalho que não sejam de conferência não têm um impacto direto sobre a escala do servidor..</span><span class="sxs-lookup"><span data-stu-id="84e1c-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="84e1c-110">Em comparação com outras soluções de conferência baseadas em portas de hardware, a arquitetura de conferência do Lync Server é um modelo sem reserva.</span><span class="sxs-lookup"><span data-stu-id="84e1c-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="84e1c-111">Quando um usuário agenda uma reunião, o Lync Server cria um registro no banco de dados de conferência, que armazena dados de conferência, mas não reserva nenhum recurso de hardware para a reunião agendada antes do tempo.</span><span class="sxs-lookup"><span data-stu-id="84e1c-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="84e1c-112">Em vez disso, o Lync Server tem lógica de balanceamento de carga interna para alocar dinamicamente recursos de conferência em servidores front-end, de forma que distribua cargas igualmente entre todos os servidores front-end do pool.</span><span class="sxs-lookup"><span data-stu-id="84e1c-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="84e1c-113">Isso provisiona e utiliza de forma eficaz os recursos de hardware, mas dificulta o fornecimento de suporte para as reuniões muito grandes (especialmente sem um planejamento adequado).</span><span class="sxs-lookup"><span data-stu-id="84e1c-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="84e1c-114">Por exemplo, quando um pool do Lync Server 2013 está sendo executado próximo à sua capacidade máxima, cada servidor de front-end pode hospedar aproximadamente 125 reuniões de tamanho médio.</span><span class="sxs-lookup"><span data-stu-id="84e1c-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="84e1c-115">Adicionar outra pequena reunião não seria um problema, mas adicionar uma reunião para 1000 os usuários seria um problema, pois os servidores de front-end provavelmente não seriam capazes de oferecer suporte a uma reunião grande, ao mesmo tempo que as outras reuniões de 125.</span><span class="sxs-lookup"><span data-stu-id="84e1c-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

