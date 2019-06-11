---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar números de acesso de discagem

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Migrar números de acesso discado do Lync Server 2010 para o Lync Server 2013 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato. Durante o período de coexistência do Lync Server 2010 e Lync Server 2013, os números de acesso discado que você criou no Lync Server 2013 se comportam de forma semelhante aos números de acesso de discagem que você cria no Lync Server 2010, conforme descrito nesta seção.

Os números de acesso discado que você criou no Lync Server 2010, mas movido para o Lync Server 2013 ou que você criou no Lync Server 2013 antes, durante ou após a migração têm as seguintes características:

  - Não aparecem nos convites para reunião do Office Communications Server 2007 R2 e na página número de acesso discada.

  - Aparecem nos convites para reunião do Lync Server 2010 e na página número de acesso discada.

  - Aparecem nos convites para reunião do Lync Server 2013 e na página número de acesso discada.

  - Não pode ser exibido ou modificado na ferramenta administrativa do Office Communications Server 2007 R2.

  - Pode ser visualizado e modificado no painel de controle do Lync Server 2010 e no Shell de gerenciamento do Lync Server 2010.

  - Pode ser visualizado e modificado no painel de controle do Lync Server 2013 e no Shell de gerenciamento do Lync Server 2013.

  - Pode ser resequenciado na região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.

Você deve concluir a migração dos números de acesso à discagem que apontam para um pool do Lync Server 2010 antes de encerrar o pool do Lync Server 2010. Se você não concluir a migração do número de acesso discado conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.

<div>


> [!IMPORTANT]  
> Você deve executar esse procedimento antes de descomissionar o pool do Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Recomendamos que você mova números de acesso discada quando o uso de rede for baixo, caso haja um curto período de interrupção do serviço.



</div>

**Para identificar e mover números de acesso discado**

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Para mover cada número de acesso à discagem para um pool hospedado no Lync Server 2013, a partir da linha de comando, execute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Abra o Painel de Controle do Lync Server.

4.  Na barra de navegação esquerda, clique em **Conferência**.

5.  Clique na guia **número de acesso** à discagem.

6.  Verifique se os números de acesso de discagem permanecem para o pool do Lync Server 2010 do qual você está migrando.
    
    <div>
    

    > [!NOTE]  
    > Quando todos os números de acesso discado apontam para o pool do Lync Server 2013, você pode encerrar o pool do Lync Server 2010.

    
    </div>

**Verifique a migração do número de acesso discada usando o painel de controle do Lync Server**

1.  Em uma conta de usuário que é atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador na sua implantação interna.

2.  Abra o Painel de Controle do Lync Server.

3.  Na barra de navegação esquerda, clique em **Conferência**.

4.  Clique na guia **número de acesso** à discagem.

5.  Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.

**Verificar a migração do número de acesso discado usando o Shell de gerenciamento do Lync Server**

1.  Abra o Shell de Gerenciamento do Lync Server.

2.  Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando executar:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

