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

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Definindo seus requisitos para chamadas de emergência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-06_

Antes de começar uma implantação do Microsoft Lync Server 2013 E9-1-1, você deve primeiro poder responder às perguntas detalhadas nas seções a seguir. O planejamento necessário dependerá do tipo de solução E9-1-1 que você optar por implantar: um provedor de serviços E9-1-1 de tronco SIP ou um gateway ELIN (número de identificação de local de emergência). A tabela a seguir identifica as seções desta apostila de planejamento que você precisará consultar para cada uma dessas soluções.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>Planejando as etapas por tipo de solução E9-1-1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Provedor de serviços de tronco SIP</th>
<th>Gateway ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definindo os elementos de rede usados para determinar o local no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Definindo os elementos de rede usados para determinar o local no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Permitindo que os usuários do E9-1-1 no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Permitindo que os usuários do E9-1-1 no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gerenciando locais para gateways do ELIN no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Criando o tronco SIP para E9-1-1 no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Incluindo a central de segurança no Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definindo a política de localização do Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Escolher um provedor de serviços E9-1-1 para o Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo o escopo da política de localização no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Definindo a política de localização do Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Atribuindo o escopo da política de localização no Lync Server 2013</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Nesta seção

  - [Definindo o escopo da implantação do E9-1-1 no Lync Server 2013](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Definindo os elementos de rede usados para determinar o local no Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Permitindo que os usuários do E9-1-1 no Lync Server 2013](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Gerenciando locais para gateways do ELIN no Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Definindo a experiência do usuário para adquirir manualmente um local no Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Criando o tronco SIP para E9-1-1 no Lync Server 2013](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Incluindo a central de segurança no Lync Server 2013](lync-server-2013-including-the-security-desk.md)

  - [Escolher um provedor de serviços E9-1-1 para o Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Definindo a política de localização do Lync Server 2013](lync-server-2013-defining-the-location-policy.md)

  - [Atribuindo o escopo da política de localização no Lync Server 2013](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

