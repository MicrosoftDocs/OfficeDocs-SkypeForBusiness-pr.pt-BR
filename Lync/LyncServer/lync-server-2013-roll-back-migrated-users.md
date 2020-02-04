---
title: 'Lync Server 2013: Reverter usuários migrados'
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
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Reverter usuários migrados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-07_

Se você precisar reverter o recurso de repositório de contatos unificado, reverta os contatos apenas se mover o usuário de volta para o Exchange 2010 ou o Lync Server 2010. Para reverter, desabilite a política do usuário e execute o cmdlet **Invoke-CsUcsRollback**. Apenas executar o **Invoke-CsUcsRollback** não é suficiente para garantir uma reversão permanente, porque a migração do repositório de contato unificado será iniciada novamente se a política não estiver desabilitada. Por exemplo, se um usuário for revertido porque o Exchange 2013 é revertido para o Exchange 2010 e, em seguida, a caixa de correio do usuário é movida para o Exchange 2013, a migração do repositório de contatos unificado será iniciada novamente sete dias após a reversão, desde que o repositório de contatos unificado ainda está habilitado para o usuário na política de serviços de usuário.

<div>


> [!IMPORTANT]  
> O cmdlet <STRONG>move-CsUser</STRONG> retorna automaticamente a loja de contatos do usuário do Exchange 2013 para o Lync Server 2013 nas seguintes situações: 
> <UL>
> <LI>
> <P>Quando os usuários forem movidos do Lync Server 2013 para o Lync Server 2010.</P>
> <LI>
> <P>Quando os usuários são migrados de forma cruzada, como quando um usuário é movido do Lync Online para o Lync Server 2013 local ou vice-versa.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Importar os dados do repositório de contato unificado de um banco de dados de backup pode fazer com que os dados do repositório de contato unificado e os dados do usuário sejam corrompidos se o modo do repositório de contato unificado mudar entre a exportação e a importação. Por exemplo: 
> <UL>
> <LI>
> <P>Se você exportar listas de contatos antes de os contatos dos usuários serem migrados para o Exchange 2013 e depois, após a migração, importar os mesmos dados, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.</P>
> <LI>
> <P>Se você exportar UserData depois de migrar os usuários para o Exchange 2013, reverta a migração e, por algum motivo, importar os dados após a migração, os dados do repositório de contatos unificado e as listas de contatos serão corrompidos.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Antes de mover uma caixa de correio do Exchange do Exchange 2013 para o Exchange 2010, o administrador do Exchange deve certificar-se de que o administrador do Lync Server primeiro reverteu os contatos do usuário do servidor do Lync do Exchange 2013 para o Lync Server. Para reverter contatos do repositório de contatos unificados para o Lync Server, consulte procedimento "para reverter contatos do repositório de contatos unificados do Exchange 2013 para o Lync Server 2013", posteriormente nesta seção.



</div>

O seguinte procedimento descreve como reverter contatos do usuário. Se você usar o cmdlet **move-CsUser** para mover os usuários entre o lync Server 2013 e o lync Server 2010, poderá ignorar essas etapas porque o cmdlet **move-CsUser** é revertido automaticamente unifed o repositório de contatos quando ele move os usuários do Lync Server 2013 para o Lync Server 2010. **Move-CsUser** não desabilita a política de repositório de contatos unificado, portanto, a migração para o repositório de contatos unificado será recorrente se o usuário for movido de volta para o Lync Server 2013.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Para reverter contatos do usuário do Lync Server 2013 para o Lync Server 2010

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Desabilite o repositório de contatos unificado para que os usuários sejam revertidos para que eles não sejam migrados novamente após a reversão. (Execute esta etapa somente se desejar garantir que os usuários não serão remigrados no futuro.) Para desabilitar o repositório de contatos unificado para usuários individuais, na linha de comando, digite:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por exemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Antes de mover um usuário do Lync Server 2013 para o Lync Server 2010, reverta a lista de amigos dos usuários especificados no Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Se essa etapa for omitida, a lista de amigos será perdida.

    
    </div>

4.  Reverter os usuários especificados. Na linha de comando, digite:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por exemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Não recomendamos usar a opção – Force para forçar a reversão. Se você usar essa opção, os contatos dos usuários serão perdidos.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Para reverter os contatos do repositório de contatos unificado do Exchange 2013 para o Lync Server 2013

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Desabilite o repositório de contatos unificado para que os usuários sejam revertidos para que eles não sejam migrados novamente após a reversão. Para desabilitar o repositório de contatos unificado para usuários individuais, na linha de comando, digite:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Por exemplo:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Reverter os usuários especificados. Na linha de comando, digite:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Por exemplo:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Primeiro, você deve reverter o usuário do Lync Server e, em seguida, mover a caixa de correio do Exchange 2013. O administrador do Exchange está bloqueado para reverter o Exchange até que a reversão do Lync Server seja concluída. Não recomendamos usar a opção – Force para forçar a reversão. Se você usar essa opção, os contatos dos usuários serão perdidos.

    
    </div>

4.  Depois de reverter o usuário para o Lync Server, o administrador do Exchange pode reverter o usuário do Exchange do Exchange 2013 para o Exchange 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

