---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62ea7da56e77264a7d8c730d44e7a6ca0372d3f8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503078"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Após implantar o Lync Server 2013, uma rota de Federação para este site não é configurada. Para usar a rota federada que está sendo usada pelo Office Communications Server 2007 R2, o Lync Server 2013 deve ser configurado para usar essa rota.

Para habilitar o site do Lync Server 2013 para usar o diretor e o servidor de borda do BackCompatSite, use o construtor de topologia para associar o pool de borda herdado.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de Borda herdado usando o Construtor de Topologia

1.  Abra a topologia do pool piloto no construtor de topologias.

2.  Selecione seu site do Lync Server 2013.

3.  No menu **ação** , clique em **Editar propriedades**.

4.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do office Communications Server 2007 R2 ou o servidor de borda do office Communications Server 2007 R2 se nenhum diretor estiver listado.
    
    ![Caixa de diálogo Editar propriedades, página rota de Federação](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")  

5.  Clique em **OK** para fechar a página **Editar Propriedades**.

6.  No construtor de topologias, no nó Lync Server 2013, navegue até o **servidor Standard Edition** ou **pools de front-ends Enterprise Edition**, clique com o botão direito do mouse no pool e clique em **Editar propriedades**.

7.  Em **Associações**, marque a caixa de seleção próxima ao **Associar pool de Borda (para componentes de mídia)**.

8.  Na lista, selecione a interface do servidor de borda para o BackCompatSite.
    
    ![Caixa de diálogo Editar propriedades, página Geral](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")  

9.  Clique em **OK** para fechar a página **Editar Propriedades**.

10. No **Construtor de Topologias**, selecione o nó superior, **Lync Server**.

11. No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.

12. Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

