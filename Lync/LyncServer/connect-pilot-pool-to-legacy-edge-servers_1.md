---
title: Conectar pool piloto aos Servidores de Borda herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Conectar pool piloto aos Servidores de Borda herdados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Após implantar o Lync Server 2013, uma rota de Federação para este site não é configurada. Para usar a rota federada que está sendo usada pelo Office Communications Server 2007 R2, o Lync Server 2013 deve ser configurado para usar essa rota.

Para habilitar o site do Lync Server 2013 a usar o diretor e o servidor de borda da BackCompatSite, use o construtor de topologias para associar o pool de bordas herdado.

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Para associar o pool de bordas herdado usando o construtor de topologias

1.  Abra a topologia do pool piloto no construtor de topologias.

2.  Selecione seu site do Lync Server 2013.

3.  No menu **ação** , clique em **Editar propriedades**.

4.  Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, selecione o diretor do office Communications Server 2007 R2 ou o servidor de borda do office Communications Server 2007 R2 se nenhum diretor estiver listado.
    
    ![Caixa de diálogo Editar propriedades, página rota de Federação] (images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")  

5.  Clique em **OK** para fechar a página **Editar propriedades** .

6.  No construtor de topologias, no nó do Lync Server 2013, navegue até os pools do **servidor Standard Edition** ou do **front-end da edição Enterprise**, clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

7.  Em **associações**, marque a caixa de seleção ao lado de **associar o pool de bordas (para componentes de mídia)**.

8.  Na lista, selecione a interface do servidor de borda para o BackCompatSite.
    
    ![Caixa de diálogo Editar propriedades, página Geral] (images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")  

9.  Clique em **OK** para fechar a página **Editar propriedades** .

10. No **Construtor**de topologias, selecione o nó mais alto, **Lync Server**.

11. No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.

12. Quando o **Assistente de publicação** for concluído, clique em **concluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

