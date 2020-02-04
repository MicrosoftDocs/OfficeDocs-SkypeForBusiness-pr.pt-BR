---
title: 'Lync Server 2013: alterações feitas pela preparação do domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Alterações feitas por preparação do domínio no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2010-10-18_

A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação do domínio cria na raiz do domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ACEs adicionadas à raiz do domínio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-userreadonly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-administradores do useradmin</th>
<th>RTCHSUniversal-serviços</th>
<th>Usuários autenticados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contêiner de leitura (não herdado)</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler propriedades do usuário-User-Restriction-restrições de conta</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler propriedades do usuário pessoal-informações</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler propriedades do usuário – informações gerais-informações</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler as informações públicas de propriedades do usuário</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Ler conjunto de RTCUserSearchProperty de propriedades do usuário</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
</tr>
<tr class="odd">
<td><p>Ler RTCPropertySet de propriedades do usuário</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Gravar endereços de proxy de propriedade de usuário</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Gravar RTCUserSearchProperty de propriedades do usuário-definir</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Gravar usuário do RTCPropertySet de propriedades</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p>Não</p></td>
</tr>
</tbody>
</table>


A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: usuários, computadores e controladores de domínio. Todas as ACEs são herdadas, a menos que indicado de outra forma.

### <a name="aces-added-to-built-in-containers"></a>ACEs adicionadas a contêineres internos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-userreadonly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Contêiner de leitura (não herdado)</p></td>
<td><p><strong>Sim</strong></p></td>
<td><p><strong>Sim</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

