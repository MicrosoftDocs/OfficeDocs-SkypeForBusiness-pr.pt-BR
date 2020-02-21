---
title: 'Lync Server 2013: alterações feitas por Grant-CsOUPermission'
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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-20_

Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem ser membros do grupo Administradores de domínio.

O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme mostrado nas tabelas a seguir.

<div>

## <a name="granting-permission-for-user-objects"></a>Concedendo permissões para objetos do usuário

Ao executar o cmdlet **Grant-CsOuPermission** para objetos do Usuário em um OU, os grupos são concedidos com permissões exibidas na tabela a seguir.

### <a name="permissions-granted-for-user-objects"></a>Permissões concedidas para objetos do usuário

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Permissão</th>
<th>Aplicável a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando mudanças de diretório</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler Public-Information</p>
<p>Ler General-Information</p>
<p>Ler User-Account-Restrictions</p></td>
<td><p>Objetos do usuário descendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Gravara RTCUserSearchPropertySet</p>
<p>Gravar msExchUCVoiceMailSettings</p>
<p>Gravar RTCUserProvisioningPropertySet</p>
<p>Gravar RTCPropertySet</p>
<p>Gravar proxyAddresses</p></td>
<td><p>Objetos do usuário descendente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Conceder permissões para objetos do computador

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de computador em um OU, os grupos são concedidos com as permissões mostradas na tabela a seguir.

### <a name="permissions-granted-for-computer-objects"></a>Permissões concedidas para objetos do computador

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Permissão</th>
<th>Aplicável a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando mudanças de diretório</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler Public-Information</p>
<p>Ler Validated-DNS-Host-Name</p></td>
<td><p>Objetos do computador descendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Ler Public-Information</p>
<p>Ler Validated-DNS-Host-Name</p></td>
<td><p>Objetos do computador descendente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concedendo permissões para contato ou objetos AppContact

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Contato ou AppContact em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Permissões concedidas para os objetos Contato ou AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Permissão</th>
<th>Aplicável a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando mudanças de diretório</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler Public-Information</p>
<p>Ler General-Information</p>
<p>Ler Personal-Information</p>
<p>Ler User-Account-Restrictions</p></td>
<td><p>Objetos de contato descendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Gravar RTCUserSearchPropertySet</p>
<p>Gravar otherIpPhone</p>
<p>Gravar displayName</p>
<p>Descrição de gravação</p>
<p>Gravar telephoneNumber</p>
<p>Gravar msExchUCVoiceMailSettings</p>
<p>Gravar RTCUserProvisioningPropertySet</p>
<p>Gravar RTCPropertySet</p>
<p>Gravar proxyAddresses</p></td>
<td><p>Objetos de contato descendente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Concedendo permissões para objetos de dispositivo

Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Dispositivo em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.

### <a name="permissions-granted-for-device-objects"></a>Permissões concedidos para objetos de Dispositivo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Permissão</th>
<th>Aplicável a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando mudanças de diretório</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler Public-Information</p>
<p>Ler Personal-Information</p>
<p>Ler General-Information</p>
<p>Ler User-Account-Restrictions</p></td>
<td><p>Objetos de contato descendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Criar filho</p>
<p>Excluir filho</p>
<p>Excluir árvore</p></td>
<td><p>Contato</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Gravar displayName</p>
<p>Descrição de gravação</p>
<p>Gravar telephoneNumber</p></td>
<td><p>Objetos do usuário descendente</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Gravar RTCUserSearchPropertySet</p>
<p>Gravar otherIpPhone</p>
<p>Gravar displayName</p>
<p>Descrição de gravação</p>
<p>Gravar telephoneNumber</p>
<p>Gravar msExchUCVoiceMailSettings</p>
<p>Gravar RTCUserProvisioningPropertySet</p>
<p>Gravar RTCPropertySet</p>
<p>Gravar proxyAddresses</p></td>
<td><p>Objetos de contato descendente</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Concedendo permissões para objetos InetOrgPerson

Ao executar o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Permissões concedidas para objetos InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>Permissão</th>
<th>Aplicável a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replicando mudanças de diretório</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Conteúdo da lista</p>
<p>Ler todas as propriedades</p>
<p>Permissões de leitura</p></td>
<td><p>Apenas este objeto</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Ler RTCUserSearchPropertySet</p>
<p>Ler RTCUserProvisioningPropertySet</p>
<p>Ler RTCPropertySet</p>
<p>Ler Personal-Information</p>
<p>Ler Public-Information</p>
<p>Ler General-Information</p>
<p>Ler User-Account-Restrictions</p></td>
<td><p>Objetos inetOrgPerson descendentes</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Gravar RTCUserSearchPropertySet</p>
<p>Gravar RTCUserProvisioningPropertySet</p>
<p>Gravar RTCPropertySet</p>
<p>Gravar proxyAddresses</p></td>
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

