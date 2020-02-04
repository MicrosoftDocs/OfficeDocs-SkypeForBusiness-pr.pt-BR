---
title: Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Para cada servidor front-end do Lync Server 2013 ou Standard Edition no pool piloto, você deve atualizar a lista de servidores internos que têm autorização para se conectar ao servidor do Office Communications Server 2007 R2 Edge Server. Sem essas atualizações, a conferência de áudio/visual (A/V) externa para usuários que ingressarem usando o servidor de borda herdada não funcionará.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Para autorizar a conexão com o servidor de borda do Office Communications Server 2007 R2

1.  No servidor do Office Communications Server 2007 R2 Edge, a partir do grupo **Ferramentas administrativas** , abra o snap-in **Gerenciamento do computador** .

2.  Na árvore de console, expanda **serviços e aplicativos**.

3.  Clique com o botão direito do mouse em **Office Communications Server 2007 R2**e, em seguida, clique em **Propriedades**.

4.  Clique na guia **interno** .

5.  Em **Adicionar servidor**, clique em **Adicionar**.

6.  Na caixa de diálogo **Adicionar o Office Communications Server** , insira as informações apropriadas:
    
      - Especifique o nome de domínio totalmente qualificado (FQDN) de cada servidor front-end do Lync Server 2013 ou do servidor Standard Edition e do Lync Server 2013 pool.
    
      - Especifique o FQDN do diretor do Lync Server 2013 se você configurou uma rota estática no pool que especifica o próximo nó do computador pelo seu FQDN.

7.  Depois de adicionar uma entrada para cada Lync Server 2013, servidor front-end, servidor Standard Edition, pool e diretor, clique em **aplicar** e, em seguida, clique em **OK** para fechar a página Propriedades.

</div>

</div>

<span> </span>

</div>

</div>

</div>

