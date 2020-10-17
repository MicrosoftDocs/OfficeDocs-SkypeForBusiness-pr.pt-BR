---
title: 'Lync Server 2013: failover do pool de borda usado para Federação do Lync Server'
description: 'Lync Server 2013: failover do pool de borda usado para Federação do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e7e13ccd35a653d38174f55ace9dc6637ded04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554907"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

Se o pool de borda no qual a federação do Lync Server está configurada ficar inoperante, você precisará alterar a federação para usar outro Pool de Borda para que ela funcione.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Fazendo failover do pool de borda usado para a federação do Lync Server

1.  Em um servidor front-end, abra o Construtor de Topologias. Expanda **Pools de borda** e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda atualmente configurado para federação. Selecione **Editar propriedades**.

2.  Em **Editar Propriedades** em **Geral**, desmarque **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **OK**.

3.  Expanda **Pools de borda** e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda que agora deseja usar para federação. Selecione **Editar propriedades**.

4.  Em **Editar Propriedades** em **Geral**, marque **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **OK**.

5.  Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.

6.  No servidor de Borda, abra o assistente de Implantação do Lync Server. Clique em **Instalar ou atualizar o sistema do Lync Server**, clique em **Instalar ou remover componentes do Lync Server**. Clique em **Executar novamente**.

7.  Em Instalar componentes do Lync Server, clique em **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.
    
    Se o site que contém o pool de borda com falha contiver servidores front-end que ainda estão em execução, você precisará atualizar o Serviço de Webconferência e o Serviço de Conferência A/V nesses pools de frond-ends para usar um pool de borda em um site remoto que ainda esteja ativo. Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Failover do pool de borda usado para Federação XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Recuperação de desastre do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

