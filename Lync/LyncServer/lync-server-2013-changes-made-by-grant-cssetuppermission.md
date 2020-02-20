---
title: 'Lync Server 2013: alterações feitas por Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-20_

Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio sem ser membro do grupo de administradores de domínio.

O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em um OU, conforme especificado na tabela a seguir:

### <a name="permissions-granted-to-objects-in-the-ou"></a>Permissões concedidas para Objetos no OU

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>As permissões aplicam-se:</th>
<th>As permissões concedidas são:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Ler servicePrincipalName</p></li>
<li><p>Gravar servicePrincipalName</p></li>
<li><p>Excluir árvore</p></li>
<li><p>Replicando mudanças de diretório</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos do serviceConnectionPoint descendente</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Permissões de leitura</p></li>
<li><p>Permissões de gravação</p></li>
<li><p>Criar filho</p></li>
<li><p>Excluir filho</p></li>
<li><p>Conteúdo da lista</p></li>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-Server descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-WebComponents descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-MCU descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-MediationServer descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos msRTCSIP-ApplicationServer descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objetos msRTCSIP-ConnectionPoint descendentes</p></td>
<td><p>Acesso especial:</p>
<ul>
<li><p>Gravar propriedade</p></li>
<li><p>Ler propriedade</p></li>
<li><p>Excluir árvore</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objetos do computador descendentes</p></td>
<td><p>Acesso especial para serviceConnectionPoint:</p>
<ul>
<li><p>Criar objetos filhos</p></li>
<li><p>Excluir objetos filhos</p></li>
<li><p>Excluir árvore</p></li>
</ul>
<p>Acesso especial para informação pública:</p>
<ul>
<li><p>Ler propriedade</p></li>
</ul>
<p>Acesso especial para nome de host DNS:</p>
<ul>
<li><p>Ler propriedade</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

