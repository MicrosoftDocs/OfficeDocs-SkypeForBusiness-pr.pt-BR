---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d659e879b821f27c159cee874dae9db0796f079b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover vários usuários para o pool piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Você pode mover vários usuários do pool do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Para mover vários usuários usando o painel de controle do Lync Server 2013

1.  Abrir **Painel de Controle do Lync Server**

2.  Na guia **Pesquisa de Usuário**, clique no botão **Pesquisar**.

3.  Em seguida, clique em **Adicionar filtro**.

4.  Crie um filtro onde o **usuário do Office Communications Server** for igual a **Verdadeiro**.

5.  Clique em **Localizar** para pesquisar usuários herdados do Office Communications Server 2007 R2.

6.  Selecione dois usuários que você deseja mover para o pool do Lync Server 2013. Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.
    
    ![Lista de usuários exibida na pesquisa de usuários do OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Lista de usuários exibida na pesquisa de usuários do OCS")  

7.  No menu **Ação**, selecione **Mover usuários selecionados para o pool**.

8.  Na lista suspensa, selecione o pool do Lync Server 2013.

9.  Clique em **Ação** e depois em **Mover usuários selecionados para o pool**. Clique em OK.
    
    ![Caixa de diálogo mover usuários, pool de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Caixa de diálogo mover usuários, pool de registradores de destino")  

10. Verifique se a coluna **pool do registrador** dos usuários agora contém o pool do Lync Server 2013, que indica que os usuários foram movidos com êxito.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Para mover vários usuários usando o Shell de gerenciamento do Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server 2013.

2.  Na linha de comando, digite o seguinte e substitua **Usuário1** e **Usuário2** com nomes de usuário específicos que você deseja mover e substituir o **FQDN do\_pool** pelo nome do pool de destino. Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de exemplo para mover um usuário herdado](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet de exemplo para mover um usuário herdado")  

3.  Na linha de comando, digite o seguinte
    
        Get-CsUser -Identity "User1"

4.  A identidade do **pool do registrador** agora deve apontar para o pool que você especificou como **FQDN do pool\_** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com sucesso. Repita a etapa para verificar se o **User2** foi movido.
    
    ![Saída do cmdlet Get-UsUser-Identity do PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Saída do cmdlet Get-UsUser-Identity do PowerShell")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Lync Server 2013

Neste exemplo, todos os usuários foram retornados para o pool do Office Communications Server 2007 R2 (pool01.contoso.net). Usando o Shell de gerenciamento do Lync Server 2013, todos os usuários serão movidos ao mesmo tempo para o pool do Lync Server 2013 (pool02.contoso.net).

1.  Abra o **Shell de gerenciamento do Lync Server 2013**.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Cmdlet de exemplo para mover todos os usuários herdados em um pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet de exemplo para mover todos os usuários herdados em um pool")  

3.  Depois, execute **Get-CsUser** de um dos usuários piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  A identidade do **pool de registradores** para cada usuário agora aponta para o pool que você\_especificou como "FQDN do pool" na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com sucesso.

5.  Além disso, podemos exibir a lista de usuários no painel de controle do Lync Server 2013 e verificar se o valor do pool do registrador agora aponta para o pool do Lync Server 2013.
    
    ![Lista de usuários do painel de controle do Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuários do painel de controle do Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

