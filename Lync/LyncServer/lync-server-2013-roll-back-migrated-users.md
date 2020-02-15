---
title: 'Lync Server 2013: reverter usuários migrados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7398e69e5a02924025d63fc48096244d67c49aeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Reverter usuários migrados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-07_

Se você precisar reverter o recurso de repositório unificado de contatos, reverta os contatos apenas se mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010. Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**. Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada. Por exemplo, se um usuário for revertido porque o Exchange 2013 é revertido para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório unificado de contatos será iniciada novamente sete dias após a reversão, contanto que o repositório unificado de contatos o ainda está habilitado para o usuário na política de serviços de usuário.

<div>


> [!IMPORTANT]  
> O cmdlet <STRONG>move-CsUser</STRONG> reverte automaticamente o repositório de contato do usuário do Exchange 2013 para o Lync Server 2013 nas seguintes situações: 
> <UL>
> <LI>
> <P>Quando os usuários são movidos do Lync Server 2013 para o Lync Server 2010.</P>
> <LI>
> <P>Quando os usuários são migrados entre locais, como quando um usuário é movido do Lync Online para o Lync Server 2013 local ou vice-versa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Importar os dados do repositório de contato unificado de um banco de dados de backup pode causar com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo: 
> <UL>
> <LI>
> <P>Se você exportar as listas de contatos antes que os contatos dos usuários sejam migrados para o Exchange 2013 e, após a migração, importar os mesmos dados, os dados do repositório de contato unificado e as listas de contatos serão corrompidos.</P>
> <LI>
> <P>Se você exportar UserData após migrar usuários para o Exchange 2013, reverter a migração e, por algum motivo, importar os dados de após a migração, os dados do repositório de contato unificado e as listas de contatos serão corrompidos.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve garantir que o administrador do Lync Server primeiro tenha revertido os contatos do usuário do Lync Server do Exchange 2013 para o Lync Server. Para reverter os contatos do repositório unificado de contatos para o Lync Server, consulte Procedure "para reverter os contatos do repositório unificado de contatos do Exchange 2013 para o Lync Server 2013", mais adiante nesta seção.



</div>

O seguinte procedimento descreve como reverter contatos do usuário. Se você usar o cmdlet **move-CsUser** para mover os usuários entre o lync Server 2013 e o lync Server 2010, é possível ignorar essas etapas porque o cmdlet **move-CsUser** automaticamente é revertido unifed o repositório de contatos quando move os usuários do Lync Server 2013 para o Lync Server 2010. O **move-CsUser** não desabilita a política de repositório unificado de contatos, portanto, a migração para o repositório unificado de contatos será recorrente se o usuário for transferido de volta para o Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Para reverter os contatos do usuário do Lync Server 2013 para o Lync Server 2010

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Desabilite o repositório de contato unificado para os usuários serem revertidos se eles não irão ser migrados novamente após a reversão. (Realize esta etapa apenas se desejar garantir que os usuários não serão migrados novamente no futuro.) Para desabilitar o repositório de contato unificado para usuários individuais, na linha de comando, digite:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por exemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Antes de mover um usuário do Lync Server 2013 para o Lync Server 2010, reverta a lista de amigos para os usuários especificados no Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Se esta etapa é omitida, a Lista de Amigos será perdida.

    
    </div>

4.  Reverta os usuários especificados. Na linha de comando, digite:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por exemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Não recomendamos usar a opção –Force para forçar a reversão. Se você usar esta opção, os contatos do usuário serão perdidos.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Para reverter os contatos do repositório unificado de contatos do Exchange 2013 para o Lync Server 2013

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Desabilitar o repositório de contato unificado para que os usuários sejam revertidos de forma que eles não serão migrados novamente após a reversão. Para desabilitar o repositório de contato unificado de usuários individuais, na linha de comando, digite:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por exemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Reverta os usuários especificados. Na linha de comando, digite:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por exemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Primeiro, você deve reverter o usuário do Lync Server e, em seguida, mover a caixa de correio do Exchange 2013. O administrador do Exchange é impedido de reverter o Exchange até que a reversão do Lync Server esteja concluída. Não recomendamos usar a opção –Force para forçar a reversão. Se você usar esta opção, os contatos do usuário serão perdidos.

    
    </div>

4.  Após reverter o usuário para o Lync Server, o administrador do Exchange pode reverter o usuário do Exchange do Exchange 2013 para o Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

