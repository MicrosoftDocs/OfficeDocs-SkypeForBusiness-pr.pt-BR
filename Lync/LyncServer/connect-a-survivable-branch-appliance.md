---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Cada aplicativo de ramificação sobreviventes (SBA) está associado a um pool de front-end que serve como registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-end do Lync Server 2010 enquanto o pool é atualizado, após a migração do pool para o Lync Server 2013, o SBA pode ser novamente associado ao pool de front-end atualizado. Isso envolve excluir o SBA da topologia herdada do Lync Server 2010 no construtor de topologias e, em seguida, adicionar SBA à topologia 2013 do Lync Server. Os usuários hospedados no Lync Server 2010 herdado SBA devem ser movidos para outro pool de front-end antes de remover SBA da topologia. Depois que o SBA é adicionado à topologia do Lync Server 2013, esses usuários podem ser movidos de volta para o SBA. Estas etapas estão resumidas abaixo:

1.  Mova os usuários da ramificação hospedados no SBA do Lync Server 2010 para outro pool de front-ends.

2.  Remova o SBA da topologia herdada do Lync Server 2010 para desconectar o pool de front-ends existente como um registrador de backup.

3.  Adicione SBA à topologia do Lync Server 2013 e configure esse novo pool de front-end como o registrador de backup.

4.  Mova os usuários da ramificação para o novo Lync Server 2013 SBA.

**Adicionar site de ramificação do Lync Server 2010 SBA à sua topologia**

1.  Abrir o **Construtor**de topologias.

2.  No painel esquerdo, clique com o botão direito do mouse em **sites**de ramificação e clique em **novo site de filial**.

3.  Na caixa de diálogo **definir novo site de filial** , clique em **nome**e digite o nome do site de filial.

4.  Adicionais Clique em **Descrição**e digite uma descrição significativa para o site da filial.

5.  Click **Next**.

6.  Adicionais Na caixa de diálogo próximo **definir novo site** de filiais, siga um destes procedimentos:
    
    1.  Clique em **cidade**e digite o nome da cidade na qual o site da filial está localizado.
    
    2.  Clique em **estado/região**e, em seguida, digite o nome do Estado ou da região em que o site da filial está localizado.
    
    3.  Clique em **código do país**e, em seguida, digite o código de chamada de dois dígitos para o país/região no qual o site da filial está localizado.

7.  Clique em **Avançar**e, em seguida, siga um destes procedimentos:
    
    1.  Se você estiver usando um aplicativo ou um aplicativo de ramificação do Lync 2010 que não seja o site, desmarque a opção **abrir o novo assistente para sobreviver quando este assistente fechar a** opção. Clique em **Concluir**.

8.  Para associar a herdada do Lync Server 2010 SBA ao pool de front-ends do Lync Server 2013:
    
    1.  Expanda o site de ramificação que foi criado.
    
    2.  Clique com o botão direito do mouse no **Lync Server 2010** e clique em **novo**.
    
    3.  Clique em **aparelho para ramificação sobreviventes...**

9.  Siga as instruções no assistente que é aberto. Para saber mais sobre os itens do assistente, confira [definir um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Um appliance de ramificação do Lync Server 2010 pode ser associado apenas a uma loja de monitoramento 2010 do Lync Server.

    
    </div>

10. Se você não estiver usando um aplicativo ou aplicativo de ramificação sobreviventes neste site, desmarque a caixa de seleção **abrir o assistente de Nova persistência quando este assistente for fechado** e clique em **concluir**.

11. Repita as etapas anteriores para cada site de ramificação que você deseja adicionar à topologia.

</div>

<span> </span>

</div>

</div>

</div>

