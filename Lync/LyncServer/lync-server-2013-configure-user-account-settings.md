---
title: 'Lync Server 2013: definir configurações de conta de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b3c8ea077b6dee724d131ea117aa7bf304e114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Definir configurações de conta de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

Os usuários de discagem digitam o número de telefone ou a extensão e um PIN para ingressar nas conferências como usuários autenticados. O **URI de linha** de telefonia especificado nas contas de usuário do Lync Server é necessário para autenticação.

O procedimento neste tópico descreve como atribuir um **URI de Linha** para uma única conta de usuário. Se você precisar atribuir um **URI da Linha** para várias contas de usuário, poderá criar um script que usa o cmdlet **Set-CsUser**. Para obter detalhes sobre como usar um exemplo de script para atribuir **URI de linha** a várias contas de usuário, consulte "atribuir URIs de [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)linha a vários usuários" em.

<div>

## <a name="to-configure-user-account-settings"></a>Para configurar as definições de conta de usuário

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-UserAdministrator** ou **CsAdministrator**.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  No campo de pesquisa, digite o nome do usuário que você deseja configurar para conferência discada ou clique em **Adicionar filtro** para especificar os campos de pesquisa e clique em **Localizar**.

5.  Clique duas vezes no nome do usuário para abrir a caixa de diálogo **Editar usuário do Lync Server** .

6.  Em **Telefonia**, no campo **URI da Linha**, digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Você pode especificar o <STRONG>URI da linha</STRONG> somente se a <STRONG>telefonia</STRONG> estiver definida <STRONG>como somente PC-PC</STRONG>, <STRONG>Enterprise Voice</STRONG>, controle de <STRONG>chamada remota</STRONG> ou <STRONG>controle de chamada remota</STRONG>.

    
    </div>

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

