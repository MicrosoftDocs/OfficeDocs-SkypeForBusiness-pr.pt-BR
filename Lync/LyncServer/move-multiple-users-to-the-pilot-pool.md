---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be7fd473b858c6a35b23f8aaa0c525875218d3f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500228"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mover vários usuários para o pool piloto

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Você pode mover vários usuários do pool do Lync Server 2010 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Para mover vários usuários usando o painel de controle do Lync Server 2013

1.  Abra o **Painel de Controle do Lync Server**.

2.  Clique em **Usuários**, em Pesquisar e em **Localizar**.

3.  Selecione dois usuários que você deseja mover para o pool do Lync Server 2013. Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.
    
    ![Mover usuários para o pool de registro específico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuários para o pool de registro específico")  

4.  No menu **Ação**, selecione **Mover usuários selecionados para o pool**.

5.  Na lista suspensa, selecione o pool do Lync Server 2013.

6.  Clique em **Ação** e depois em **Mover usuários selecionados para o pool**. Clique em OK.
    
    ![Caixa de diálogo mover usuários, pool de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Caixa de diálogo mover usuários, pool de registradores de destino")  

7.  Verifique se a coluna **pool do registrador** dos usuários agora contém o pool do Lync Server 2013, que indica que os usuários foram movidos com êxito.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Para mover vários usuários usando o Shell de gerenciamento do Lync Server 2013

1.  Abra o Shell de gerenciamento do Lync Server 2013.

2.  Na linha de comando, digite o seguinte e substitua **Usuário1** e **Usuário2** com nomes de usuário específicos que você deseja mover e substituir o ** \_ FQDN do pool** pelo nome do pool de destino. Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Exemplo de cmdlet Get-CsUser do PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemplo de cmdlet Get-CsUser do PowerShell")  

3.  Na linha de comando, digite o seguinte
    
        Get-CsUser -Identity "User1"

4.  A identidade do **pool do registrador** agora deve apontar para o pool que você especificou como ** \_ FQDN do pool** na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com sucesso. Repita a etapa para verificar se o **User2** foi movido.
    
    ![Saída do cmdlet Get-UsUser-Identity do PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Saída do cmdlet Get-UsUser-Identity do PowerShell")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Lync Server 2013

Neste exemplo, todos os usuários foram retornados para o pool do Lync Server 2010 (pool01.contoso.net). Usando o Shell de gerenciamento do Lync Server 2013, todos os usuários serão movidos ao mesmo tempo para o pool do Lync Server 2013 (pool02.contoso.net).

1.  Abra o **Shell de gerenciamento do Lync Server 2013**.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Cmdlet do PowerShell e resultados no Shell de gerenciamento](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet do PowerShell e resultados no Shell de gerenciamento")  

3.  Depois, execute **Get-CsUser** de um dos usuários piloto.
    
        Get-CsUser -Identity "Hao Chen"

4.  A identidade do **pool de registradores** para cada usuário agora aponta para o pool que você especificou como " \_ FQDN do pool" na etapa anterior. A presença dessa identidade confirma que o usuário foi movido com sucesso.

5.  Além disso, podemos exibir a lista de usuários no painel de controle do Lync Server 2013 e verificar se o valor do pool do registrador agora aponta para o pool do Lync Server 2013.
    
    ![Lista de usuários do painel de controle do Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuários do painel de controle do Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

