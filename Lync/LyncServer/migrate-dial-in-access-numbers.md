---
title: Migrar os números de acesso discado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6401d847c2e0993632ad655fb43f07b0a2731ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503548"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar os números de acesso discado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Migrar números de acesso de discagem do Lync Server 2010 para o Lync Server 2013 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato. Durante o período de coexistência do Lync Server 2010 e do Lync Server 2013, os números de acesso discado que você criou no Lync Server 2013 se comportam de forma semelhante aos números de acesso de discagem que você cria no Lync Server 2010, conforme descrito nesta seção.

Os números de acesso de discagem criados no Lync Server 2010, mas movidos para o Lync Server 2013 ou criados no Lync Server 2013 antes, durante ou após a migração têm as seguintes características:

  - Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página número de acesso de discagem.

  - Aparecem nos convites de reunião do Lync Server 2010 e na página número de acesso de discagem.

  - Aparecem nos convites de reunião do Lync Server 2013 e na página número de acesso de discagem.

  - Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.

  - Pode ser exibido e modificado no painel de controle do Lync Server 2010 e no Shell de gerenciamento do Lync Server 2010.

  - Pode ser exibido e modificado no painel de controle do Lync Server 2013 e no Shell de gerenciamento do Lync Server 2013.

  - Podem ser seqüenciados novamente dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração dos números de acesso de discagem que apontam para um pool do Lync Server 2010 antes de encerrar o pool do Lync Server 2010. Se você não concluir a migração do número de acesso de discagem, conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

<div>


> [!IMPORTANT]  
> Você deve executar esse procedimento antes de encerrar o pool do Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja uma breve interrupção no serviço.



</div>

**Para identificar e mover os números de acesso de discagem**

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Para mover cada número de acesso de discagem para um pool hospedado no Lync Server 2013, na linha de comando, execute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Abra o Painel de Controle do Lync Server.

4.  Na barra de navegação esquerda, clique em **Conferência**.

5.  Clique na guia **número de acesso de discagem** .

6.  Verifique se os números de acesso de discagem permanecem para o pool do Lync Server 2010 do qual você está migrando.
    
    <div>
    

    > [!NOTE]  
    > Quando todos os números de acesso de discagem apontarem para o pool do Lync Server 2013, você poderá encerrar o pool do Lync Server 2010.

    
    </div>

**Verificar a migração do número de acesso de discagem usando o painel de controle do Lync Server**

1.  A partir de uma conta de usuário atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador em sua implantação interna.

2.  Abra o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Conferência**.

4.  Clique na guia **número de acesso de discagem** .

5.  Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.

**Verificar a migração do número de acesso de discagem usando o Shell de gerenciamento do Lync Server**

1.  Abra o Shell de gerenciamento do Lync Server.

2.  Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando, execute:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

