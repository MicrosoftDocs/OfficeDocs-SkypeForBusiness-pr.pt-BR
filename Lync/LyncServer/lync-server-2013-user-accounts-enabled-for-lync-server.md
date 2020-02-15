---
title: 'Lync Server 2013: contas de usuário habilitadas para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d51f72f586ab6d5b5094c61ae09d8ac316350b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Contas de usuário habilitadas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-18_

Os tópicos desta seção fornecem procedimentos passo a passo para definir as configurações do usuário que você pode executar usando o painel de controle do Lync Server 2013.

<div>


> [!IMPORTANT]  
> Você não pode usar o painel de controle do Lync Server para gerenciar usuários que são membros do grupo Administradores de domínio do Active Directory. Para usuários de administradores de domínio, você pode usar o painel de controle do Lync Server somente para realizar operações de pesquisa somente leitura. Para realizar operações de gravação em usuários de administradores de domínio (por exemplo, habilitar ou desabilitar o painel de controle do Lync Server, alterar as atribuições de grupo ou política, configurações de telefonia, endereço SIP), você deve usar cmdlets do Windows PowerShell enquanto estiver conectado como um usuário admins. Para obter detalhes sobre como usar cmdlets do Windows PowerShell para gerenciar usuários, consulte <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.



</div>

Quando você realiza qualquer tarefa administrativa do Lync Server 2013 que envolve a pesquisa de um usuário ou filtragem de resultados de pesquisa de usuário, há algumas propriedades de usuário que existem como atributos nos serviços de domínio do Active Directory, mas que não são replicadas para o catálogo global até que o Microsoft Exchange Server seja implantado. O Microsoft Exchange, não o Lync Server, marca os seguintes atributos para replicação para o catálogo global quando ele é instalado:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informações de usuário</th>
<th>Endereço e Telefone</th>
<th>Organização</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iniciais</p></td>
<td><p>Endereço</p>
<p>País/região</p>
<p>Pager</p>
<p>Fax</p>
<p>Mobile</p></td>
<td><p>Cargo</p>
<p>Empresa</p>
<p>Departamento</p>
<p>Escritório</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Nesta seção

  - [Exibindo informações sobre contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Habilitando e desabilitando usuários para o Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gerenciando o Enterprise Voice para usuários no Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modificando Propriedades da conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Cmdlets de gerenciamento de usuário no Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Gerenciando usuários no Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

