---
title: 'Lync Server 2013: planejamento de capacidade para retirada de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="cb2b9-102">Planejamento de capacidade para retirada de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb2b9-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb2b9-103">_**Tópico da última modificação:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="cb2b9-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="cb2b9-104">A tabela a seguir descreve o modelo de usuário de retirada de chamada de grupo que você pode usar como base para requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb2b9-105">O recebimento de chamadas em grupo é baseado no aplicativo parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="cb2b9-106">Lembre-se de que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de manipular as cargas de trabalho para serviços de Call Park, incluindo o recebimento de chamadas em grupo, em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="cb2b9-107">Modelo de usuário de retirada de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="cb2b9-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb2b9-108">Indicador</span><span class="sxs-lookup"><span data-stu-id="cb2b9-108">Metric</span></span></th>
<th><span data-ttu-id="cb2b9-109">Por pool de front-end (com 8 servidores front end)</span><span class="sxs-lookup"><span data-stu-id="cb2b9-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="cb2b9-110">Por servidor padrão da edição</span><span class="sxs-lookup"><span data-stu-id="cb2b9-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb2b9-111">Número recomendado de usuários por grupo</span><span class="sxs-lookup"><span data-stu-id="cb2b9-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-112">50</span><span class="sxs-lookup"><span data-stu-id="cb2b9-112">50</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-113">50</span><span class="sxs-lookup"><span data-stu-id="cb2b9-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb2b9-114">Número recomendado de grupos</span><span class="sxs-lookup"><span data-stu-id="cb2b9-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-115">500</span><span class="sxs-lookup"><span data-stu-id="cb2b9-115">500</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-116">60</span><span class="sxs-lookup"><span data-stu-id="cb2b9-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb2b9-117">Número máximo de usuários por pool ativado para Recebimento de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="cb2b9-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-118">25.000</span><span class="sxs-lookup"><span data-stu-id="cb2b9-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-119">3.000</span><span class="sxs-lookup"><span data-stu-id="cb2b9-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb2b9-120">Taxa máxima de chamadas recebidas para o total de usuários habilitados para Recebimento de chamada de grupo por pool por minuto</span><span class="sxs-lookup"><span data-stu-id="cb2b9-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-121">500</span><span class="sxs-lookup"><span data-stu-id="cb2b9-121">500</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-122">60</span><span class="sxs-lookup"><span data-stu-id="cb2b9-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb2b9-123">Taxa máxima de chamadas recuperadas por usuários com Recebimento de chamada de grupo por pool por minuto</span><span class="sxs-lookup"><span data-stu-id="cb2b9-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-124">200</span><span class="sxs-lookup"><span data-stu-id="cb2b9-124">200</span></span></p></td>
<td><p><span data-ttu-id="cb2b9-125">25</span><span class="sxs-lookup"><span data-stu-id="cb2b9-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="cb2b9-126">Para pools front-ends com menos de oito servidores front-end, calcule as métricas linearmente.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="cb2b9-127">Por exemplo, se o seu pool de front-ends tiver um servidor front-end, calcule a carga máxima como 1/8 dos valores mostrados na tabela.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="cb2b9-128">Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos desde que você não exceda o número máximo de usuários por pool.</span><span class="sxs-lookup"><span data-stu-id="cb2b9-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="cb2b9-129">Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o recebimento de chamadas em grupo ainda está dentro do modelo de usuário máximo (ou seja, o 120 grupos em que 25 usuários tem 3.000 usuários habilitados para o recebimento de chamadas em grupo).</span><span class="sxs-lookup"><span data-stu-id="cb2b9-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

