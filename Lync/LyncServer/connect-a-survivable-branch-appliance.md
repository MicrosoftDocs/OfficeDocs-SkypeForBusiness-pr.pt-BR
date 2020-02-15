---
title: Conectar um aparelho de filial persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>Conectar um aparelho de filial persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Cada aparelho de filial persistente (SBA) é associado a um pool de front-ends que serve como um registrador de backup para o SBA. Quando o pool de front-ends é migrado para o Lync Server 2013, o SBA deve ser desassociado do pool de front-ends do Lync Server 2010 enquanto o pool é atualizado, após o pool ter sido migrado para o Lync Server 2013, o SBA pode ser novamente associado ao pool de front-ends atualizado. Isso envolve excluir o SBA da topologia herdada do Lync Server 2010 no construtor de topologia e, em seguida, adicionar o SBA à topologia 2013 do Lync Server. Os usuários hospedados no Lync Server 2010 herdado SBA devem ser movidos primeiro para outro pool de front-ends antes da remoção do SBA da topologia. Depois que o SBA é adicionado à topologia do Lync Server 2013, esses usuários podem ser movidos de volta para o SBA. Essas etapas estão resumidas abaixo:

1.  Mover usuários de filial hospedados no SBA Lync Server 2010 herdado para outro pool de front-ends.

2.  Remova o SBA da topologia herdada do Lync Server 2010 para desconectar o pool de front-ends existente como um registrador de backup.

3.  Adicione SBA à topologia do Lync Server 2013 e configure esse novo pool de front-ends como o registrador de backup.

4.  Mova os usuários da filial para o novo Lync Server 2013 SBA.

**Adicione Lync Server 2010 SBA Branch Site à sua topologia**

1.  Abra o **Construtor de Topologias**.

2.  No painel esquerdo, clique com o botão direito do mouse em **Locais ramificados** e clique em **Novo local ramificado**.

3.  Na caixa de diálogo **Definir Novo Site de Filial**, clique em **Nome** e digite o nome do site de filial.

4.  (Opcional) Clique em **Descrição** e digite uma descrição significativa para o site de filial.

5.  Clique em **Avançar**.

6.  (Opcional) Na próxima caixa de diálogo **Definir Novo Site de Filial**, execute uma das seguintes ações:
    
    1.  Clique em **Cidade** e digite o nome da cidade na qual o site de filial está localizado.
    
    2.  Clique em **Estado/Região** e digite o nome do estado ou região na qual o site de filial está localizado.
    
    3.  Clique em **Código do País** e digite o código de chamada de dois dígitos para o país/região no qual o site de filial está localizado.

7.  Clique em **Avançar** e execute uma das seguintes ações:
    
    1.  Se você estiver usando um Aparelho de Filial Persistente  Lync 2010 ou Servidor nesse site, certifique-se de desmarcar a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.

8.  Para associar o SBA herdado do Lync Server 2010 ao pool de front-ends do Lync Server 2013:
    
    1.  Expanda o local ramificado que foi criado.
    
    2.  Clique com o botão direito do mouse em **Lync Server 2010** e clique em **Novo**.
    
    3.  Clique em **Aparelho de Filial Persistente**

9.  Siga as instruções no assistente que abrir. Para obter informações sobre itens de assistente, consulte [definir um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Um aparelho de filial persistente do Lync Server 2010 só pode ser associado a um repositório de monitoramento do Lync Server 2010.

    
    </div>

10. Se você não estiver usando um Aparelho de Filial Persistente ou Servidor nesse site, desmarque a caixa de seleção **Abrir o Novo Assistente Persistente quando este assistente fechar** e clique em **Concluir**.

11. Repita as etapas anteriores para cada site de filial que você deseja adicionar à topologia.

</div>

<span> </span>

</div>

</div>

</div>

