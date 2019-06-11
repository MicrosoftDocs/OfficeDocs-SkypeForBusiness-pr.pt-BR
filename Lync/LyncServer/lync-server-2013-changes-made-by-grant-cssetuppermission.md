---
title: 'Lync Server 2013: alterações feitas pela concessão-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-20_

Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins dessa UO instalem o Lync Server 2013 no especificado domínio sem ser membro do grupo Domain admins.

O cmdlet **Grant-CsSetupPermission** concede as permissões do grupo RTCUniversalServerAdmins em uma UO, conforme especificado na tabela a seguir:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Permissões concedidas a objetos na OU

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>As permissões se aplicam a:</th>
<th>Permissões concedidas são:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Leia servicePrincipalName</p></li>
<li><p>Gravar servicePrincipalName</p></li>
<li><p>Excluir árvore</p></li>
<li><p>Replicando alterações de diretório</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos serviceConnectionPoint do descendant</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Permissões de leitura</p></li>
<li><p>Permissões de gravação</p></li>
<li><p>Criar filho</p></li>
<li><p>Excluir filho</p></li>
<li><p>Conteúdo da lista</p></li>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-Server descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP descendentes-WebComponents</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos descendentes msRTCSIP-MCU</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-MediationServer descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-ApplicationServer descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos descendentes msRTCSIP-ConnectionPoint</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Propriedade de gravação</p></li>
<li><p>Propriedade ler</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos de computador descendentes</p></td>
<td><p>Acesso especial para serviceConnectionPoint:</p>
<ul>
<li><p>Criar objetos filho</p></li>
<li><p>Excluir objetos filho</p></li>
<li><p>Excluir árvore</p></li>
</ul>
<p>Acesso especial para informações públicas:</p>
<ul>
<li><p>Propriedade ler</p></li>
</ul>
<p>Acesso especial para o nome do host DNS:</p>
<ul>
<li><p>Propriedade ler</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

