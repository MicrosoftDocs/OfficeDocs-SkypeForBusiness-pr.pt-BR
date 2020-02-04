---
title: 'Lync Server 2013: alterações feitas pela concessão-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-20_

Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais do RTC criados pela preparação da floresta possam acessar as UOs sem serem membros do grupo Domain admins.

O cmdlet **Grant-CsOuPermission** concede permissões a objetos na unidade organizacional especificada, conforme especificado nas tabelas a seguir.

<div>

## <a name="granting-permission-for-user-objects"></a>Concedendo permissão para objetos de usuário

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de usuário em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.

### <a name="permissions-granted-for-user-objects"></a>Permissões concedidas para objetos de usuário

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupos</th>
<th>Permissão</th>
<th>Aplica-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando alterações de diretório</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler informações públicas</p>
<p>Leia informações gerais</p>
<p>Ler restrições de conta de usuário</p></td>
<td><p>Objetos de usuário descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escrever RTCUserSearchPropertySet</p>
<p>Escrever msExchUCVoiceMailSettings</p>
<p>Escrever RTCUserProvisioningPropertySet</p>
<p>Escrever RTCPropertySet</p>
<p>Escrever proxyAddresses</p></td>
<td><p>Objetos de usuário descendentes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Concedendo permissão para objetos de computador

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de computador em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.

### <a name="permissions-granted-for-computer-objects"></a>Permissões concedidas para objetos de computador

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupos</th>
<th>Permissão</th>
<th>Aplica-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando alterações de diretório</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler informações públicas</p>
<p>Leitura validada-DNS-nome do host</p></td>
<td><p>Objetos de computador descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Ler informações públicas</p>
<p>Leitura validada-DNS-nome do host</p></td>
<td><p>Objetos de computador descendentes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concedendo permissão para objetos de contato ou AppContact

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de contato ou objetos AppContact em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Permissões concedidas para objetos de contato ou AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupos</th>
<th>Permissão</th>
<th>Aplica-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando alterações de diretório</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler informações públicas</p>
<p>Leia informações gerais</p>
<p>Leia as informações pessoais</p>
<p>Ler restrições de conta de usuário</p></td>
<td><p>Objetos de contato descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escrever RTCUserSearchPropertySet</p>
<p>Escrever otherIpPhone</p>
<p>Escrever displayName</p>
<p>Descrição da gravação</p>
<p>Escrever telephoneNumber</p>
<p>Escrever msExchUCVoiceMailSettings</p>
<p>Escrever RTCUserProvisioningPropertySet</p>
<p>Escrever RTCPropertySet</p>
<p>Escrever proxyAddresses</p></td>
<td><p>Objetos de contato descendentes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Concedendo permissão para objetos de dispositivo

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de dispositivo em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.

### <a name="permissions-granted-for-device-objects"></a>Permissões concedidas para objetos de dispositivo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupos</th>
<th>Permissão</th>
<th>Aplica-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando alterações de diretório</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler informações públicas</p>
<p>Leia as informações pessoais</p>
<p>Leia informações gerais</p>
<p>Ler restrições de conta de usuário</p></td>
<td><p>Objetos de contato descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Criar filho</p>
<p>Excluir filho</p>
<p>Excluir árvore</p></td>
<td><p>Entrando</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escrever displayName</p>
<p>Descrição da gravação</p>
<p>Escrever telephoneNumber</p></td>
<td><p>Objetos de usuário descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escrever RTCUserSearchPropertySet</p>
<p>Escrever otherIpPhone</p>
<p>Escrever displayName</p>
<p>Descrição da gravação</p>
<p>Escrever telephoneNumber</p>
<p>Escrever msExchUCVoiceMailSettings</p>
<p>Escrever RTCUserProvisioningPropertySet</p>
<p>Escrever RTCPropertySet</p>
<p>Escrever proxyAddresses</p></td>
<td><p>Objetos de contato descendentes</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Concedendo permissão para objetos InetOrgPerson

Quando você executa o cmdlet **Grant-CsOuPermission** para objetos inetOrgPerson em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Permissões concedidas para objetos InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupos</th>
<th>Permissão</th>
<th>Aplica-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando alterações de diretório</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Somente este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Leia as informações pessoais</p>
<p>Ler informações públicas</p>
<p>Leia informações gerais</p>
<p>Ler restrições de conta de usuário</p></td>
<td><p>Objetos inetOrgPerson descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Escrever RTCUserSearchPropertySet</p>
<p>Escrever RTCUserProvisioningPropertySet</p>
<p>Escrever RTCPropertySet</p>
<p>Escrever proxyAddresses</p></td>
<td><p>Objetos inetOrgPerson descendentes</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

