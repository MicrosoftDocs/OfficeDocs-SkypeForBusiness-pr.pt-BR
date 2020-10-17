---
title: 'Lync Server 2013: definindo seus requisitos para chamadas de emergência'
description: 'Lync Server 2013: definindo seus requisitos para chamadas de emergência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545397"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="020b1-103">Definindo seus requisitos para chamadas de emergência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-103">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="020b1-104">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="020b1-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="020b1-105">Antes de começar uma implantação do Microsoft Lync Server 2013 E9-1-1, você deve primeiro responder as perguntas detalhadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="020b1-105">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="020b1-106">O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência).</span><span class="sxs-lookup"><span data-stu-id="020b1-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="020b1-107">A tabela a seguir identifica as seções desta apostila de planejamento que você precisará consultar para cada uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="020b1-107">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="020b1-108">Planejando as etapas por tipo de solução E9-1-1</span><span class="sxs-lookup"><span data-stu-id="020b1-108">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="020b1-109">Provedor de serviços de tronco SIP</span><span class="sxs-lookup"><span data-stu-id="020b1-109">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="020b1-110">Gateway ELIN</span><span class="sxs-lookup"><span data-stu-id="020b1-110">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="020b1-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020b1-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir os elementos de rede usados para determinar o local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definir os elementos de rede usados para determinar o local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020b1-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitando usuários para E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Habilitando usuários para E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020b1-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gerenciando locais para gateways do ELIN no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020b1-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definir a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020b1-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Projetando o tronco SIP para E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-122"><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020b1-123"><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-123"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-124"><a href="lync-server-2013-defining-the-location-policy.md">Definir a política de local para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-124"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020b1-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Escolher um provedor de serviços E9-1-1 para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="020b1-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo escopo de política de local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="020b1-127"><a href="lync-server-2013-defining-the-location-policy.md">Definir a política de local para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-127"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="020b1-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo escopo de política de local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="020b1-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="020b1-129">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="020b1-129">In This Section</span></span>

  - [<span data-ttu-id="020b1-130">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-130">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="020b1-131">Definir os elementos de rede usados para determinar o local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-131">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="020b1-132">Habilitando usuários para E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-132">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="020b1-133">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-133">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="020b1-134">Gerenciando locais para gateways do ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-134">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="020b1-135">Definir a experiência do usuário para adquirir manualmente um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-135">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="020b1-136">Projetando o tronco SIP para E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-136">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="020b1-137">Incluindo a central de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-137">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="020b1-138">Escolher um provedor de serviços E9-1-1 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-138">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="020b1-139">Definir a política de local para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-139">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="020b1-140">Atribuindo escopo de política de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="020b1-140">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

