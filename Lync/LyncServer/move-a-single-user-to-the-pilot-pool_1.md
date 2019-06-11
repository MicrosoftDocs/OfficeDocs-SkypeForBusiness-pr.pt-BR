---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Mover um único usuário para o pool piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Você pode mover um usuário do pool do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. No exemplo a seguir, na coluna pool de registradores, ** \<o Office\> Communications Server** é o pool do Office Communications Server 2007 R2 e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Lync Server 2013 usando o painel de controle do Lync Server 2013 e o Shell de gerenciamento do Lync Server.

![Pesquisar usuários do OCS no painel de controle do Lync Server] (images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Pesquisar usuários do OCS no painel de controle do Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Para mover um usuário usando o painel de controle do Lync Server 2013

1.  Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.

2.  Abra o Painel de Controle do Lync Server.

3.  Clique em **usuários**.

4.  Na guia **pesquisa de usuário** , clique no botão **Pesquisar** .

5.  Em seguida, clique em **Adicionar filtro**.

6.  Crie um filtro onde o **usuário do Office Communications Server** é igual a **true**.

7.  Clique em **Localizar** para pesquisar usuários herdados do Office Communications Server 2007 R2.
    
    ![Pesquisar usuários do OCS no painel de controle do Lync Server] (images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Pesquisar usuários do OCS no painel de controle do Lync Server")  

8.  Selecione o usuário que você deseja mover para o pool do Lync Server 2013. Neste exemplo, moveremos a usuária Sara Davis.

9.  No menu **Ação**, selecione **Mover usuários selecionados para o pool**.

10. Na lista suspensa, selecione o pool do Lync Server 2013.

11. Clique em **Ação** e em **Mover usuários selecionados para o pool**. Clique em **OK**.
    
    ![Configurando o pool de destino na caixa de diálogo mover usuários] (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configurando o pool de destino na caixa de diálogo mover usuários")  

12. Verifique se a coluna do **pool** de registradores do usuário agora contém o pool do Lync Server 2013, que indica que o usuário foi movido com êxito

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Para mover um usuário usando o Shell de gerenciamento do Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

