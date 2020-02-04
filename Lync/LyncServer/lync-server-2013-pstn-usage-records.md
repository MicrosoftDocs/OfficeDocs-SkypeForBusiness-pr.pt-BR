---
title: 'Lync Server 2013: Registros de uso de PSTN'
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
ms.openlocfilehash: 5909494b4e4b6901964a7642481302ca221fe086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="8cd85-102">Registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cd85-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd85-103">_**Tópico da última modificação:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="8cd85-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="8cd85-104">O planejamento dos registros de uso de PSTN consiste principalmente em listar todas as permissões de chamadas em uso na organização, desde o CEO até os funcionários temporários, os consultores e a equipe contingente.</span><span class="sxs-lookup"><span data-stu-id="8cd85-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="8cd85-105">Esse processo também oferece uma oportunidade de reexaminar as permissões de chamadas existentes e revisá-las.</span><span class="sxs-lookup"><span data-stu-id="8cd85-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="8cd85-106">Você pode criar registros de uso de PSTN somente para as permissões de chamada que se aplicam aos usuários de Enterprise Voice previstos, mas uma solução de maior alcance pode ser criar registros de uso de PSTN para todas as permissões de chamada, independentemente de talvez alguns não aplicar-se ao grupo de usuários a ser habilitado para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8cd85-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="8cd85-107">Se as permissões de chamada forem alteradas ou novos usuários com permissões de chamada diferentes forem adicionados, você já terá criado os registros de uso de PSTN necessários.</span><span class="sxs-lookup"><span data-stu-id="8cd85-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="8cd85-108">A tabela a seguir mostra um quadro típico de uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="8cd85-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="8cd85-109">Registros de uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="8cd85-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cd85-110">Atributo do telefone</span><span class="sxs-lookup"><span data-stu-id="8cd85-110">Phone attribute</span></span></th>
<th><span data-ttu-id="8cd85-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="8cd85-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cd85-112">Local</span><span class="sxs-lookup"><span data-stu-id="8cd85-112">Local</span></span></p></td>
<td><p><span data-ttu-id="8cd85-113">Chamadas locais</span><span class="sxs-lookup"><span data-stu-id="8cd85-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd85-114">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="8cd85-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="8cd85-115">Chamadas interurbanas</span><span class="sxs-lookup"><span data-stu-id="8cd85-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd85-116">International</span><span class="sxs-lookup"><span data-stu-id="8cd85-116">International</span></span></p></td>
<td><p><span data-ttu-id="8cd85-117">Chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="8cd85-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd85-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="8cd85-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="8cd85-119">Funcionários de Délhi em tempo integral</span><span class="sxs-lookup"><span data-stu-id="8cd85-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd85-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="8cd85-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="8cd85-121">Funcionários de Redmond em tempo integral</span><span class="sxs-lookup"><span data-stu-id="8cd85-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cd85-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="8cd85-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="8cd85-123">Funcionários temporários de Redmond</span><span class="sxs-lookup"><span data-stu-id="8cd85-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cd85-124">Zurich</span><span class="sxs-lookup"><span data-stu-id="8cd85-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="8cd85-125">Funcionários de Zurique em tempo integral</span><span class="sxs-lookup"><span data-stu-id="8cd85-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8cd85-p102">Sozinhos, os registros de uso do PSTN não fazem nada. Para que funcionem, é necessário associá-los ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="8cd85-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="8cd85-128">Políticas de voz, que são atribuídas a usuários.</span><span class="sxs-lookup"><span data-stu-id="8cd85-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="8cd85-129">Rotas, que são atribuídas a números de telefone.</span><span class="sxs-lookup"><span data-stu-id="8cd85-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="8cd85-130">Para obter detalhes sobre políticas e rotas de voz, consulte [políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md) e [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="8cd85-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="8cd85-131">Para obter detalhes sobre como criar e configurá-los, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="8cd85-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

