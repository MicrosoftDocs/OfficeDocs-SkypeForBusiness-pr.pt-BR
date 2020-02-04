---
title: 'Lync Server 2013: Delegando o controle administrativo do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delegando o controle administrativo do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

No Lync Server 2013, as tarefas administrativas são delegadas a usuários usando o novo recurso de controle de acesso baseado em função (RBAC). Quando você instala o Lync Server, várias funções RBAC são criadas para você. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk localizado no contêiner usuários nos serviços de domínio Active Directory. Além disso, cada função RBAC é associada a um conjunto de cmdlets do Windows PowerShell do Lync Server. Esses cmdlets representam as tarefas que podem ser realizadas pelos usuários que receberam a função RBAC fornecida. Por exemplo, a função CsHelpDesk foi atribuída aos cmdlets Lock-CsClientPin e UnlockCsClientPin. Isso significa que os usuários que receberam a função CsHelpDesk podem bloquear e desbloquear números de PIN do usuário. No entanto, a função CsHelpDesk não foi atribuída ao cmdlet New-CsVoicePolicy. Isso significa que os usuários que receberam a função CsHelpDesk não poderão criar novas políticas de voz.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Exibir informações sobre as funções RBAC

Você pode recuperar informações básicas sobre as funções RBAC executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsAdminRole

Lembre-se de que a identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança localizado no contêiner usuários nos serviços de domínio Active Directory.

Para exibir uma lista dos cmdlets que foram atribuídos a uma função, use um comando semelhante a este:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Atribuindo uma função RBAC a um usuário

Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory. Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator. Isso pode ser feito executando o seguinte procedimento:

**Para atribuir um usuário a um grupo de segurança**

1.  Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logon em um computador onde usuários e computadores do Active Directory tenham sido instalados.

2.  Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.

3.  Em usuários e computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner **usuários** .

4.  Clique com o botão direito do mouse no grupo de segurança **CsLocationAdministrator**e, em seguida, clique em **Propriedades**.

5.  Na caixa de diálogo **Propriedades** , na guia **Membros** , clique em **Adicionar**.

6.  Na caixa de diálogo **Selecionar usuários, computadores, contatos ou grupos** , digite o nome de usuário ou o nome para exibição do usuário a ser adicionado ao grupo (por exemplo, **Ken Myer**) na caixa **digite os nomes de objeto a serem selecionados** e clique em **OK**.

7.  Na caixa de diálogo **Propriedades** , clique em **OK**.

Para verificar se a função RBAC foi atribuída, use o cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , passando o cmdlet do sAMAccountName (nome de logon do Active Directory) do usuário. Por exemplo, execute este comando dentro do Shell de gerenciamento do Lync Server:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

