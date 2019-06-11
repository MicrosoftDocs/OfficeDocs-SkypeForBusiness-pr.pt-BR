---
title: 'Lync Server 2013: Failover do pool de Borda usado para federação do Servidor Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

Se o pool de bordas em que você tem a Federação do Lync Server configurada ficar inativo, você deverá alterar a Federação para usar um pool de bordas diferente para o trabalho de Federação.

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Falha sobre o pool de bordas usado para a Federação do Lync Server

1.  Em um servidor front-end, abra o construtor de topologias. Expanda Pools de **bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação. Selecione **Editar propriedades**.

2.  Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.

3.  Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que você agora deseja usar para a Federação. Selecione **Editar propriedades**.

4.  Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.

5.  Clique em **ação**, selecione **topologia**, selecione **publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação estiver concluída, clique em **concluir**.

6.  No servidor de borda, abra o assistente de implantação do Lync Server. Clique em **instalar ou atualizar o Lync Server System**e, em seguida, clique em **Configurar ou remover componentes do Lync Server**. Clique em **executar novamente**.

7.  Em configurar componentes do Lync Server, clique em **Avançar**. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **concluir** para concluir a implantação.
    
    Se o site que contém o pool de bordas com falha contiver servidores front-end que ainda estão em execução, você deve atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar um pool de bordas em um site remoto que ainda esteja em execução. Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Failover do pool de Borda usado para federação de XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Recuperação de desastres do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

