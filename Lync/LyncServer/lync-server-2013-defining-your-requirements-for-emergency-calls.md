---
title: 'Lync Server 2013: Definindo seus requisitos para chamadas de emergência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53543d815519dc440ba038999e5fc531173551f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="34716-102">Definindo seus requisitos para chamadas de emergência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34716-103">_**Tópico da última modificação:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="34716-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="34716-104">Antes de começar uma implantação do Microsoft Lync Server 2013 E9-1-1, você deve primeiro poder responder às perguntas detalhadas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="34716-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="34716-105">O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência).</span><span class="sxs-lookup"><span data-stu-id="34716-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="34716-106">A tabela a seguir identifica as seções desta apostila de planejamento que você precisará consultar para cada uma dessas soluções.</span><span class="sxs-lookup"><span data-stu-id="34716-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="34716-107">Planejando as etapas por tipo de solução E9-1-1</span><span class="sxs-lookup"><span data-stu-id="34716-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34716-108">Provedor de serviços de tronco SIP</span><span class="sxs-lookup"><span data-stu-id="34716-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="34716-109">Gateway ELIN</span><span class="sxs-lookup"><span data-stu-id="34716-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34716-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34716-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definindo os elementos de rede usados para determinar o local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definindo os elementos de rede usados para determinar o local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34716-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Permitindo que os usuários do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Permitindo que os usuários do E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34716-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gerenciando locais para gateways do ELIN no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34716-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34716-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Criando o tronco SIP para E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-121"><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34716-122"><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-123"><a href="lync-server-2013-defining-the-location-policy.md">Definindo a política de localização do Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34716-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Escolher um provedor de serviços E9-1-1 para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="34716-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo o escopo da política de localização no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34716-126"><a href="lync-server-2013-defining-the-location-policy.md">Definindo a política de localização do Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34716-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo o escopo da política de localização no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34716-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="34716-128">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="34716-128">In This Section</span></span>

  - [<span data-ttu-id="34716-129">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="34716-130">Definindo os elementos de rede usados para determinar o local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="34716-131">Permitindo que os usuários do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="34716-132">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="34716-133">Gerenciando locais para gateways do ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="34716-134">Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="34716-135">Criando o tronco SIP para E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="34716-136">Incluindo a central de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="34716-137">Escolher um provedor de serviços E9-1-1 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="34716-138">Definindo a política de localização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="34716-139">Atribuindo o escopo da política de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34716-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

