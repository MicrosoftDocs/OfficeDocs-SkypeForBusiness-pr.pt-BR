---
title: 'Lync Server 2013: alterações de esquema no Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b48cb0d83c12d1db8ec3fc43901d7e28d4288fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Alterações de esquema no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Antes de implantar e operar o Lync Server 2013, você deve preparar os serviços de domínio do Active Directory, estendendo o esquema. As extensões de esquema adicionam as classes e os atributos necessários para o Lync Server 2013.

O Lync Server 2013 requer várias classes e atributos novos e modifica algumas classes e atributos existentes. Além disso, muitas informações de configuração para o Lync Server 2013 são armazenadas no repositório de gerenciamento central, em vez de no AD DS, como nas versões anteriores. As informações a seguir ainda são armazenadas no AD DS no Lync Server 2013:

  - **Extensões de esquema**:
    
      - Extensões do objeto do usuário
    
      - Extensões para o Office Communications Server 2007 e o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores com suporte

<!-- end list -->

  - **Dados** (armazenados no esquema estendido do Lync Server e nas classes de esquema existentes):
    
      - URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário
    
      - Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência
    
      - Um ponteiro para o repositório de gerenciamento central
    
      - Conta de autenticação Kerberos (um objeto de computador opcional)

Este tópico descreve as alterações de esquema do Active Directory exigidas pelo Lync Server 2013. Ela não descreve as alterações de esquema que foram introduzidas por versões anteriores do Office Communications Server. Para obter uma lista de classes e suas descrições, consulte [classes e descrições de esquema no Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Para obter uma lista de atributos e suas descrições, consulte [atributos e descrições de esquema no Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Para obter uma lista de classes com os atributos que eles podem conter, confira [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

O prefixo msRTCSIP identifica classes e atributos específicos do Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Novos atributos do Active Directory

A tabela a seguir descreve os atributos do Active Directory que são adicionados pelo Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Atributos adicionados pelo Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário. Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção. Este atributo é compartilhado com o Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de front-ends.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Classes do Active Directory modificadas

A tabela a seguir descreve as classes do Active Directory modificadas pelo Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Classes modificadas pelo Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Alteração</th>
<th>Classe ou atributo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuário</p></td>
<td><p>add:mayContain</p>
<p>add:mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contato</p></td>
<td><p>add:mayContain</p>
<p>add:mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add:mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

