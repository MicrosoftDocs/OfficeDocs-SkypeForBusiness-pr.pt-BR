---
title: 'Lync Server 2013: Configurando o Lync Server para usar o repositório unificado de contatos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9875cb075f29f9f2efcb9328d1ac2d39d2f8ae89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configurando o Microsoft Lync Server 2013 para usar o repositório unificado de contatos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

O repositório unificado de contatos permite que os usuários mantenham uma única lista de contatos e, em seguida, tenham esses contatos disponíveis em vários aplicativos, incluindo o Microsoft Lync 2013, o Microsoft Outlook 2013 e o Microsoft Outlook Web App 2013. Quando você habilita o repositório unificado de contatos para um usuário que os contatos do usuário não são armazenados no Microsoft Lync Server 2013 e recuperados usando o protocolo SIP. Em vez disso, seus contatos são armazenados no Microsoft Exchange Server 2013 e recuperados usando os serviços Web do Exchange.

<div>


> [!NOTE]  
> Tecnicamente, as informações de contato são armazenadas em um par de pastas encontradas na caixa de correio do Exchange 2013 do usuário. Os contatos propriamente ditos são armazenados em uma pasta denominada contatos do Lync, que é visível para os usuários finais; os metadados sobre os contatos são armazenados em uma subpasta que não é visível para os usuários finais.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Habilitando o repositório unificado de contatos para um usuário

Se você já configurou a autenticação de servidor para servidor entre o Lync Server 2013 e o Exchange 2013, você também habilitou o uso do repositório unificado de contatos; nenhuma configuração adicional do servidor é necessária. No entanto, será necessária configuração adicional da conta do usuário para transferir os contatos de um usuário para o repositório unificado de contatos. Por padrão, os contatos do usuário são mantidos no Lync Server e não no repositório unificado de contatos.

O acesso ao repositório unificado de contatos é gerenciado usando políticas de serviços de usuário do Lync Server. As políticas de serviços de usuário têm uma única propriedade (UcsAllowed), que é usada para determinar o local onde os contatos de um usuário são armazenados. Se um usuário é gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como true ($True), os contatos do usuário serão armazenados no repositório unificado de contatos. Se o usuário for gerenciado por uma política de serviços de usuário em que o UcsAllowed foi definido como false ($False), seus contatos serão armazenados no Lync Server.

Quando você instala o Lync Server 2013, uma única política de serviços de usuário (configurada no escopo global) também é instalada. O valor UcsAllowed nessa política é definido como true, o que significa que, por padrão, os contatos do usuário serão armazenados no repositório unificado de contatos (supondo que isso tenha sido implantado e configurado). Se você quiser migrar todos os seus contatos de usuário para o repositório unificado de contatos, não será necessário fazer nada.

Se preferir não migrar todos os seus contatos para o repositório unificado de contatos, você poderá desabilitar o repositório unificado de contatos para todos os usuários, definindo a propriedade UcsAllowed na política global como false:

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Depois de desabilitar o repositório unificado de contatos na política global, você pode criar uma política por usuário que permite o uso do repositório unificado de contatos; Isso permite que alguns usuários mantenham seus contatos no repositório unificado de contatos enquanto outros usuários continuam a manter seus contatos no Lync Server. Você pode criar uma política de serviços de usuário por usuário usando um comando semelhante ao seguinte:

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Depois que você tiver criado a nova política, precisará atribuí-la aos usuários que deverão ter acesso ao repositório unificado de contatos. As políticas por usuário podem ser atribuídas aos usuários com o uso de comandos semelhantes ao seguinte:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Depois que a política tiver sido atribuída, o Lync Server começará a migrar os contatos do usuário para o repositório unificado de contatos. Após a conclusão da migração, o usuário terá seus contatos armazenados no Exchange, e não no Lync Server. Se o usuário estiver conectado ao Lync 2013 no momento em que a migração for concluída, uma caixa de mensagem será exibida e ele será solicitado a fazer logoff do Lync e, em seguida, fazer logon novamente para finalizar o processo. Os usuários que não tiverem sido atribuídos essa política por usuário não terão seus contatos migrados para o repositório unificado de contatos. Isso ocorre porque esses usuários estão sendo gerenciados pela política global e o uso do repositório unificado de contatos foi desabilitado na política global.

Você pode verificar se os contatos de um usuário foram migrados com êxito para o repositório unificado de contatos executando o cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) de dentro do Shell de gerenciamento do Lync Server:

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Se Test-CsUnifiedContactStore for bem-sucedido, significa que os contatos do usuário sip:kenmyer@litwareinc.com foram migrados para o repositório unificado de contatos.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Revertendo o repositório unificado de contatos

Se você precisar remover os contatos de um usuário do repositório unificado de contatos (por exemplo, se o usuário precisar ser rehospedado no Microsoft Lync Server 2010 e não puder mais usar o repositório unificado de contatos), você deverá fazer duas coisas. Primeiro, você deve atribuir ao usuário uma nova política de serviços de usuário, que proíba o armazenamento de contatos no repositório unificado de contatos. (Ou seja, uma política na qual a propriedade UcsAllowed foi definida como $False.) Se você não tem essa política, você pode criar uma usando um comando semelhante a este:

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Em seguida, você pode atribuir essa nova política por usuário (NoUnifiedContactStore) usando um comando como o seguinte:

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

O comando anterior atribui a nova política ao usuário Ken Myer e também impede que os contatos de Ken sejam migrados para o repositório unificado de contatos.

<div>


> [!NOTE]  
> Em alguns casos, é possível obter o mesmo efeito simplesmente cancelando a atribuição da política de serviços de usuário atual do usuário. Por exemplo, suponha que Ken Myer tenha uma política de serviços de usuário por usuário que habilita o repositório unificado de contatos, mas sua política global proíbe o uso do repositório unificado de contatos. Nesse caso, você pode cancelar a atribuição da política de serviços por usuário de Ken. Quando você fizer isso, Ken será automaticamente gerenciado pela política global e deixará de ter acesso ao repositório unificado de contatos.<BR>Para cancelar a atribuição de uma política por usuário atribuída anteriormente, use o mesmo comando mostrado antes, mas, desta vez, defina o parâmetro PolicyName para um valor nulo:<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –NomedaPolítica $Null



</div>

É importante lembrar-se da frase "impede que os contatos de Ken sejam migrados para o repositório unificado de contatos" ao trabalhar com o repositório unificado de contatos. Simplesmente atribuir uma nova política de serviços de usuário a Ken não removerá seus contatos do repositório unificado de contatos. Quando um usuário faz logon no Lync Server 2013, o sistema verifica a política de serviços de usuário do usuário para ver se seus contatos devem ser mantidos no repositório unificado de contatos. Se a resposta for sim (ou seja, se a propriedade UcsAllowed estiver definida como $True), esses contatos serão migrados para o repositório unificado de contatos (pressupondo que eles ainda não estejam no repositório unificado de contatos). Se a resposta for não, o Lync Server simplesmente ignora os contatos do usuário e se move para a próxima tarefa. Isso significa que o Lync Server não moverá automaticamente os contatos de um usuário do repositório unificado de contatos, independentemente do valor da propriedade UcsAllowed.

Isso também significa que, após a atribuição do usuário a uma nova política de serviços de usuário, você deverá executar o cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) para mover os contatos do usuário para fora do Exchange 2013 e de volta para o Lync Server 2013. Por exemplo, após atribuir uma nova política de serviços de usuário a Ken Myer, você poderá remover seus contatos do repositório unificado de contatos usando o seguinte comando:

    Invoke-CsUcsRollback -Identity "Ken Myer"

Se você alterar a política de serviços de usuário, mas não executar o cmdlet Invoke-CsUcsRollback, os contatos de Ken não serão removidos do repositório unificado de contatos. E se você executar o Invoke-CsUcsRollback, mas não alterar a política de serviços de usuário de Ken Myer? Nesse caso, os contatos de Ken serão temporariamente removidos do repositório unificado de contatos. É importante atentar ao fato de que essa remoção é temporária. Após os contatos de Ken terem sido removidos do repositório unificado de contatos, o Lync Server 2013 aguardará 7 dias e verificará qual política de serviços de usuário foi atribuída a Ken. Se uma política que permite o uso do repositório unificado de contatos ainda estiver atribuída a Ken, seus contatos serão automaticamente transferidos de volta para o repositório de contatos. Para remover permanentemente os contatos do repositório unificado de contatos, você precisa alterar a política de serviços de usuário e também executar o cmdlet Invoke-CsUcsRollback.

Devido ao grande número de variáveis que podem afetar a migração, é difícil estimar quanto tempo levará para que as contas sejam totalmente migradas para o repositório unificado de contatos. No entanto, como regra geral, a migração não tem efeito imediato: mesmo ao migrar um pequeno número de contatos, pode levar 10 minutos ou mais antes da conclusão da movimentação.

</div>

</div>

<span> </span>

</div>

</div>

</div>

