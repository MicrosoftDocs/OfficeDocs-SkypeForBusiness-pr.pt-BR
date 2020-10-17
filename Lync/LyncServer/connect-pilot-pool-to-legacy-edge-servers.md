---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d12a67b0ba102fdacea66b6196bafe32d89c9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503098"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Após implantar o Lync Server 2013, você precisará configurar uma rota de Federação para seu site. Para usar a rota federada que está sendo usada pelo Lync Server 2010, o Lync Server 2013 deve ser configurado para usar essa rota.

Para habilitar o site do Lync Server 2013 para usar o diretor e o servidor de borda da implantação do Lync Server 2010, use o construtor de topologia para associar o pool de borda herdado.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de Borda herdado usando o Construtor de Topologia

1.  Abra o **Construtor de Topologia**.

2.  Selecione seu local, que está diretamente abaixo do nó do **Lync Server**.

3.  No menu **Ações**, clique em **Editar Propriedades**.

4.  No painel esquerdo, selecione **Rota de federação**.

5.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do Lync Server 2010 ou o servidor de borda do Lync Server 2010, se nenhum diretor estiver listado.
    
    ![Editar propriedades, página de rota de Federação](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propriedades, página de rota de Federação")  

6.  Clique em **OK** para fechar a página **Editar Propriedades**.

7.  No construtor de topologias, no nó Lync Server 2013, navegue até o **servidor Standard Edition** ou **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.

8.  Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**.

9.  Na lista, selecione o Servidor de Borda herdado.
    
    ![Caixa de diálogo Editar propriedades, selecionando a borda herdada](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Caixa de diálogo Editar propriedades, selecionando a borda herdada")  

10. Clique em **OK** para fechar a página **Editar Propriedades**.

11. No **Construtor de Topologias**, selecione o nó superior, **Lync Server**.

12. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.

13. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

