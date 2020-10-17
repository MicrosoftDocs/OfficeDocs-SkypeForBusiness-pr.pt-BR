---
title: 'Lync Server 2013: registros de uso de PSTN'
description: 'Lync Server 2013: registros de uso de PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565577"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="bb745-103">Registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb745-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb745-104">_**Última modificação do tópico:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="bb745-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="bb745-p101">O planejamento dos registros de uso de PSTN consiste principalmente em listar todas as permissões de chamadas em uso na organização, desde o CEO até os funcionários temporários, os consultores e a equipe contingente. Esse processo também oferece uma oportunidade de reexaminar as permissões de chamadas existentes e revisá-las. Você pode criar registros de uso de PSTN somente para as permissões de chamada que se aplicam aos usuários previstos do Enterprise Voice, mas uma solução melhor e de longo alcance pode ser criar registros de PSTN para todas as permissões de chamadas, ainda que algumas delas não se apliquem no momento ao grupo de usuários que será habilitado para o Enterprise Voice. Se as permissões de chamada forem alteradas ou novos usuários com permissões de chamada diferentes forem adicionados, você já terá criado os registros de uso de PSTN necessários.</span><span class="sxs-lookup"><span data-stu-id="bb745-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="bb745-109">A tabela a seguir mostra um quadro típico de uso do PSTN.</span><span class="sxs-lookup"><span data-stu-id="bb745-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="bb745-110">Registros de uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="bb745-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb745-111">Atributo do telefone</span><span class="sxs-lookup"><span data-stu-id="bb745-111">Phone attribute</span></span></th>
<th><span data-ttu-id="bb745-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb745-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb745-113">Local</span><span class="sxs-lookup"><span data-stu-id="bb745-113">Local</span></span></p></td>
<td><p><span data-ttu-id="bb745-114">Chamadas locais</span><span class="sxs-lookup"><span data-stu-id="bb745-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb745-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="bb745-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="bb745-116">Chamadas interurbanas</span><span class="sxs-lookup"><span data-stu-id="bb745-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb745-117">International</span><span class="sxs-lookup"><span data-stu-id="bb745-117">International</span></span></p></td>
<td><p><span data-ttu-id="bb745-118">Chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="bb745-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb745-119">Déli</span><span class="sxs-lookup"><span data-stu-id="bb745-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="bb745-120">Funcionários de Délhi em tempo integral</span><span class="sxs-lookup"><span data-stu-id="bb745-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb745-121">Rio</span><span class="sxs-lookup"><span data-stu-id="bb745-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="bb745-122">Funcionários de Redmond em tempo integral</span><span class="sxs-lookup"><span data-stu-id="bb745-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb745-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="bb745-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="bb745-124">Funcionários temporários de Redmond</span><span class="sxs-lookup"><span data-stu-id="bb745-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb745-125">Zurique</span><span class="sxs-lookup"><span data-stu-id="bb745-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="bb745-126">Funcionários de Zurique em tempo integral</span><span class="sxs-lookup"><span data-stu-id="bb745-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb745-p102">Sozinhos, os registros de uso do PSTN não fazem nada. Para que funcionem, é necessário associá-los ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="bb745-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="bb745-129">Políticas de voz, que são atribuídas a usuários.</span><span class="sxs-lookup"><span data-stu-id="bb745-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="bb745-130">Rotas, que são atribuídas a números de telefone.</span><span class="sxs-lookup"><span data-stu-id="bb745-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="bb745-131">Para obter detalhes sobre políticas e rotas de voz, consulte [políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md) e [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="bb745-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="bb745-132">Para obter detalhes sobre como criar e configurá-los, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="bb745-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

