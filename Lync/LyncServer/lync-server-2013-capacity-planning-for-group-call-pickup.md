---
title: 'Lync Server 2013: planejamento de capacidade para recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0fa12b04507e5b42767d551af4b4b9c004175b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="b36e2-102">Planejamento de capacidade para recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36e2-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b36e2-103">_**Última modificação do tópico:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="b36e2-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="b36e2-104">A tabela a seguir descreve o modelo de usuário de recebimento de chamadas de grupo que você pode usar como base para os requisitos de planejamento de capacidade.</span><span class="sxs-lookup"><span data-stu-id="b36e2-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b36e2-105">O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="b36e2-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="b36e2-106">Tenha em mente que, para o planejamento da capacidade de recuperação de desastres, cada pool de um pool emparelhado deve ser capaz de lidar com as cargas de trabalho para serviços de estacionamento de chamadas, incluindo o recebimento de chamadas em grupo, em ambos os pools.</span><span class="sxs-lookup"><span data-stu-id="b36e2-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="b36e2-107">Modelo de usuário de recebimento de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="b36e2-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b36e2-108">Indicador</span><span class="sxs-lookup"><span data-stu-id="b36e2-108">Metric</span></span></th>
<th><span data-ttu-id="b36e2-109">Por pool de front-ends (com 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="b36e2-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="b36e2-110">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b36e2-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b36e2-111">Número recomendado de usuários por grupo</span><span class="sxs-lookup"><span data-stu-id="b36e2-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="b36e2-112">50</span><span class="sxs-lookup"><span data-stu-id="b36e2-112">50</span></span></p></td>
<td><p><span data-ttu-id="b36e2-113">50</span><span class="sxs-lookup"><span data-stu-id="b36e2-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36e2-114">Número recomendado de grupos</span><span class="sxs-lookup"><span data-stu-id="b36e2-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="b36e2-115">500</span><span class="sxs-lookup"><span data-stu-id="b36e2-115">500</span></span></p></td>
<td><p><span data-ttu-id="b36e2-116">60</span><span class="sxs-lookup"><span data-stu-id="b36e2-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36e2-117">Número máximo de usuários por pool habilitado para recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="b36e2-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="b36e2-118">25.000</span><span class="sxs-lookup"><span data-stu-id="b36e2-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="b36e2-119">3.000</span><span class="sxs-lookup"><span data-stu-id="b36e2-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b36e2-120">Taxa máxima de chamadas de entrada para usuários total habilitados para retirada de chamada de grupo por pool por minuto</span><span class="sxs-lookup"><span data-stu-id="b36e2-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="b36e2-121">500</span><span class="sxs-lookup"><span data-stu-id="b36e2-121">500</span></span></p></td>
<td><p><span data-ttu-id="b36e2-122">60</span><span class="sxs-lookup"><span data-stu-id="b36e2-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b36e2-123">Taxa máxima de chamadas recuperadas por usuários com retirada de chamada de grupo por pool por minuto</span><span class="sxs-lookup"><span data-stu-id="b36e2-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="b36e2-124">200</span><span class="sxs-lookup"><span data-stu-id="b36e2-124">200</span></span></p></td>
<td><p><span data-ttu-id="b36e2-125">25</span><span class="sxs-lookup"><span data-stu-id="b36e2-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="b36e2-126">Para pools de front-ends com menos de oito servidores front-end, calcule as métricas linearmente.</span><span class="sxs-lookup"><span data-stu-id="b36e2-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="b36e2-127">Por exemplo, se o seu pool de front-ends tiver um servidor front-end, calcule a carga máxima como 1/8 dos valores mostrados na tabela.</span><span class="sxs-lookup"><span data-stu-id="b36e2-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="b36e2-128">Você pode aumentar ou diminuir o número recomendado de usuários por grupo e número de grupos, desde que não exceda o número máximo de usuários por pool.</span><span class="sxs-lookup"><span data-stu-id="b36e2-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="b36e2-129">Por exemplo, seu servidor Standard Edition pode ter 120 grupos com 25 usuários por grupo porque o número de usuários habilitados para o recebimento de chamadas de grupo ainda está dentro do modelo de usuário máximo (ou seja, 120 grupos de 25 usuários é 3.000 usuários habilitados para o recebimento de chamadas de grupo).</span><span class="sxs-lookup"><span data-stu-id="b36e2-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

