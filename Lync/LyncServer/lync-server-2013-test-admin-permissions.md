---
title: 'Lync Server 2013: testar permissões de administrador'
description: 'Lync Server 2013: testar permissões de administrador.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568517"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a>Testar permissões de administrador no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Após a implantação inicial do Lync Server. Conforme necessário se surgirem problemas relacionados à permissão.</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsOUPermission. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Quando você instala o Lync Server 2013 1 das tarefas que foram realizadas pelo programa de instalação fornece ao grupo RTCUniversalUserAdmins permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativos e pessoas do InetOrg. Se você desabilitou a herança de permissão na configuração do Active Directory, não será possível atribuir essas permissões. Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Lync Server. Esses privilégios de gerenciamento só estarão disponíveis para os administradores de domínio.

O cmdlet Test-CsOUPermission verifica se as permissões necessárias necessárias para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory. Se essas permissões não estiverem definidas, você poderá resolver esse problema executando o cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins. Você não pode usar este cmdlet para conceder permissões a um usuário ou grupo arbitrário. Se quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, você deve adicionar esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins.

Para obter mais informações sobre permissões de OU, confira o artigo a [herança de permissões está desabilitada em computadores, usuários ou contêiners inetOrgPerson no Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome distinto do contêiner e pelo tipo de permissões que você está verificando. Por exemplo, este comando verifica se as permissões do usuário estão definidas na OU ou = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e, em seguida, separe-os usando vírgulas. Por exemplo, este comando verifica as permissões de usuário, computador e contato:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se as permissões necessárias já tiverem sido definidas, Test-CsOUPermission retornará uma resposta de um Word:

Verdadeiro.

Se as permissões necessárias não estiverem definidas, Test-CsOUPermission retornará o valor false. Talvez seja necessário pesquisar por um momento para encontrar esse valor. Normalmente, ele será incorporado dentro de vários avisos de acompanhamento. Por exemplo:

Aviso: entrada de controle de acesso (ACE) ATL-cs-001 \\ RTCUniversalUserReadOnlyGroup; permitir; ReadProperty ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

Aviso: as entradas de controle de acesso (ACEs) no objeto "OU = América, DC = ATL-cs-001 \\ DC = litwareinc, DC = com" não estão prontas.

Falso

Aviso: o processamento de "Test-CsOUPermission" foi concluído com avisos. os avisos "2" foram registrados durante esta execução.

Aviso: resultados detalhados podem ser encontrados em "C \\ : \\ usuários \\ admin \\ \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.htmlocal \\

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsOUPermission falhar, normalmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins. Você pode resolver esse problema e atribuir as permissões necessárias, usando o cmdlet Grant-CsOUPermission. Por exemplo, este comando concede permissões de OU para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

