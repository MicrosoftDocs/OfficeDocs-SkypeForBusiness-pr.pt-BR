---
title: 'Lync Server 2013: delegando o controle administrativo do Lync Server'
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
ms.openlocfilehash: 74089690a9c37a753d9dad56fd7246f9d4cb6213
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a>Delegando o controle administrativo do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

No Lync Server 2013, as tarefas administrativas são delegadas aos usuários usando o novo recurso de controle de acesso baseado em função (RBAC). Quando você instala o Lync Server, várias funções do RBAC são criadas para você. Essas funções correspondem a grupos de segurança universais nos serviços de domínio do Active Directory. Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk encontrado no contêiner usuários nos serviços de domínio do Active Directory. Além disso, cada função RBAC é associada a um conjunto de cmdlets do Windows PowerShell do Lync Server. Esses cmdlets representam as tarefas que podem ser executadas por usuários aos quais a função RBAC determinada foi atribuída. Por exemplo, a função CsHelpDesk recebeu os cmdlets Lock-CsClientPin e UnlockCsClientPin. Isso significa que os usuários que receberam a função CsHelpDesk podem bloquear e desbloquear números de PIN do usuário. No entanto, a função CsHelpDesk não recebeu a atribuição do cmdlet New-CsVoicePolicy. Isso significa que os usuários que receberam a função CsHelpDesk não podem criar novas políticas de voz.

<div>

## <a name="viewing-information-about-rbac-roles"></a>Exibindo informações sobre as funções RBAC

Você pode recuperar informações básicas sobre suas funções RBAC executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsAdminRole

Tenha em mente que a identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança encontrado no contêiner usuários nos serviços de domínio do Active Directory.

Para visualizar uma lista de cmdlets que foram designados a uma função, use um comando semelhante a este:

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a>Atribuindo uma função RBAC a um usuário

Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory. Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator. Isso pode ser feito executando o seguinte procedimento:

**Para atribuir um usuário a um grupo de segurança**

1.  Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.

2.  Clique em **Iniciar**, clique em **Todos os Programas**, clique em **Ferramentas Administrativas** e, em seguida, clique em **Usuários e Computadores do Active Directory**.

3.  Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de **Usuários**.

4.  Clique com o botão direito no grupo de segurança **CsLocationAdministrator** e clique em **Propriedades**.

5.  Na caixa de diálogo **Propriedades**, na guia **Membros**, clique em **Adicionar**.

6.  Na caixa de diálogo **Selecionar Usuários, Computadores, Contatos ou Grupos**, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, **Ken Myer**) na caixa **Inserir os nomes de objeto a selecionar** e clique em **OK**.

7.  Na caixa de diálogo **Propriedades**, clique em **OK**.

Para verificar se a função RBAC foi atribuída, use o cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , passando o cmdlet para o sAMAccountName (nome de logon do Active Directory) do usuário. Por exemplo, execute este comando no Shell de gerenciamento do Lync Server:

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

