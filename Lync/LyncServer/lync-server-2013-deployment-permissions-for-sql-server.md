---
title: 'Lync Server 2013: Permissões de implantação para Servidor SQL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea0334c7070ae3aadb3191da4bf036a978878688
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a>Permissões de implantação para Servidor SQL no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

O Microsoft SQL Server 2012 tem requisitos específicos durante a instalação e a implantação do Lync Server 2013. Como o Windows e o SQL Server definem a segurança de forma diferente, fazer logon como administrador no domínio do Active Directory não concede implicitamente permissões para o SQL Server. Você também deve ser membro da entidade sysadmin no servidor baseado no SQL Server que você está configurando.

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a>Permissões necessárias para a instalação do banco de dados e do Lync Server

As opções a seguir detalham três permissões e associações de associação a grupos para a instalação de arquivos do Lync Server 2013 e bancos de dados do SQL Server. Escolha o cenário que melhor atenda aos requisitos da sua organização.

### <a name="permissions-and-group-membership-associations"></a>Permissões e associações de associação a grupos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função do SQL Server ou do Lync Server 2013</th>
<th>Função-permissões típicas do SQL Server e associação a um grupo</th>
<th>Função-permissões típicas do Lync Server 2013 e associação a um grupo</th>
<th>Resultado das permissões</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Administrador do Lync Server 2013</p></td>
<td><p>Deve ser concedida a associação do grupo de segurança Administradores do SQL Server e membro do grupo de administradores locais do SQL Server</p></td>
<td><p>Deve ser um membro do grupo RTCUniversalServerAdmins</p></td>
<td><p>O administrador do Lync Server 2013 tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</p></td>
</tr>
<tr class="even">
<td><p>Administrador do SQL Server</p></td>
<td><p>Membro do grupo sysadmin do SQL Server (ou equivalente) e membro do grupo de administradores locais do SQL Server</p></td>
<td><p>Deve ser um membro do grupo RTCUniversalServerReadOnly</p></td>
<td><p>O administrador do SQL Server tem as permissões adequadas para instalar os bancos de dados do Lync Server 2013 e do SQL Server.</p></td>
</tr>
<tr class="odd">
<td><p>Os dois administradores compartilham os direitos de instalação</p></td>
<td><p>O administrador do SQL Server é membro do grupo sysadmins (ou equivalente) e membro do grupo de administradores locais do SQL Server</p></td>
<td><p>O administrador do Lync Server 2013 é membro de RTCUniversalServerAdmins</p></td>
<td><p>O administrador do Lync Server 2013 pode instalar o Lync Server 2013, mas não pode instalar os bancos de dados. O administrador do SQL Server usa o Shell de gerenciamento do Lync Server e cmdlets do Windows PowerShell fornecidos pelo administrador do Lync Server 2013 para instalar os bancos de dados. O Shell de gerenciamento do Lync Server 2013 usado pelo administrador do SQL Server é instalado no servidor front-end. Isso elimina a necessidade de instalar as ferramentas administrativas do Lync Server 2013 no servidor baseado no SQL Server.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

