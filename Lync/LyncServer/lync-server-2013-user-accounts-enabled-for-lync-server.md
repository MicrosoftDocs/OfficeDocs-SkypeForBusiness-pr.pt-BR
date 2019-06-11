---
title: 'Lync Server 2013: contas de usuário habilitadas para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Contas de usuário habilitadas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-18_

Os tópicos desta seção fornecem procedimentos passo a passo para configurar as configurações do usuário que você pode executar usando o painel de controle do Lync Server 2013.

<div>


> [!IMPORTANT]  
> Você não pode usar o painel de controle do Lync Server para gerenciar os usuários que são membros do grupo Administradores de domínio do Active Directory. Para usuários de administradores de domínio, você pode usar o painel de controle do Lync Server somente para realizar operações de pesquisa somente leitura. Para realizar operações de gravação em usuários de administradores de domínio (por exemplo, habilitar ou desabilitar o painel de controle do Lync Server, alterar as atribuições de grupo ou política, configurações de telefonia, endereço SIP), você deve usar cmdlets do Windows PowerShell enquanto estiver conectado como um usuário administradores de domínio. Para obter detalhes sobre como usar cmdlets do Windows PowerShell para gerenciar usuários, consulte <A href="lync-server-2013-lync-server-management-shell.md">Shell de gerenciamento do Lync Server 2013</A>.



</div>

Quando você executa qualquer tarefa administrativa do Lync Server 2013 que envolve a pesquisa de um usuário ou filtragem dos resultados da pesquisa de usuário, há algumas propriedades de usuário que existem como atributos nos serviços de domínio Active Directory, mas que não são replicadas para o catálogo global até que o Microsoft Exchange Server seja implantado. Microsoft Exchange, não Lync Server, marca os seguintes atributos de replicação para o catálogo global quando ele é instalado:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Informações do usuário</th>
<th>Endereço e telefone</th>
<th>Organização</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Iniciais</p></td>
<td><p>Endereço da rua</p>
<p>País/Região</p>
<p>Page</p>
<p>Fax</p>
<p>Mobile</p></td>
<td><p>Título</p>
<p>Empresa</p>
<p>Partamentais</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Nesta seção

  - [Exibir informações sobre contas de usuário habilitadas para o Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Habilitando e desabilitando usuários do Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Gerenciando o Enterprise Voice para usuários no Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Modificando Propriedades de conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Como atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Cmdlets de gerenciamento de usuários no Lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Gerenciando usuários no Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

