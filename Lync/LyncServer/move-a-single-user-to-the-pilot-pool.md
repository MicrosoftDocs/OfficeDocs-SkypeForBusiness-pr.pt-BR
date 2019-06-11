---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um único usuário para o pool piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

Você pode mover um usuário do pool do Lync Server 2010 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. No exemplo a seguir, na coluna pool de registradores, **pool01.contoso.net** é o pool do Lync Server 2010 e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Lync Server 2013 usando o painel de controle do Lync Server 2013 e o Shell de gerenciamento do Lync Server.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover um usuário usando o painel de controle do Lync Server 2013

**Lista de usuários no painel de controle do Lync Server 2013**

![Painel de controle do Lync Server, caixa de diálogo mover usuário] (images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Painel de controle do Lync Server, caixa de diálogo mover usuário")

1.  Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.

2.  Abra o **Painel de Controle do Lync Server**.

3.  Clique em **Usuários**, em Pesquisar e em **Localizar**.

4.  Selecione o usuário que você deseja mover para o pool do Lync Server 2013. Neste exemplo, moveremos a usuária Sara Davis.

5.  No menu **Ação**, selecione **Mover usuários selecionados para o pool**.

6.  Na lista suspensa, selecione o pool do Lync Server 2013.

7.  Clique em **Ação** e em **Mover usuários selecionados para o pool**. Clique em **OK**.
    
    ![Caixa de diálogo mover usuários, pool de registradores de destino] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Caixa de diálogo mover usuários, pool de registradores de destino")  

8.  Verifique se a coluna do **pool** de registradores do usuário agora contém o pool do Lync Server 2013, que indica que o usuário foi movido com êxito.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover um usuário usando o Shell de gerenciamento do Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Em seguida, na linha de comando, digite o seguinte:
    
        Get-CsUser -Identity "David Pelton"

4.  A identidade **RegistrarPool** agora aponta para o pool do Lync Server 2013. A presença dessa identidade confirma que o usuário foi movido com êxito.
    
    ![Saída do cmdlet Get-CsUser com filtro de identidade] (images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Saída do cmdlet Get-CsUser com filtro de identidade")  
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre o cmdlet <STRONG>Get-CsUser</STRONG> , execute: <STRONG>Get-Help Get-CsUser – detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

