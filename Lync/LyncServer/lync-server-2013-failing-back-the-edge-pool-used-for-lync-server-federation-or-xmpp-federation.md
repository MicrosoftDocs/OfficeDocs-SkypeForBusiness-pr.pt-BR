---
title: Failback do pool de Borda usado para federação do Lync Server ou federação XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Depois que um pool de borda com falha que foi usado para hospedar a Federação foi colocado online novamente, use este procedimento para fazer failback do roteiro de Federação do Lync Server e/ou da rota de Federação do XMPP novamente para usar este pool de bordas restaurado.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Falha ao fazer a Federação para um pool de bordas restaurado

1.  No pool de bordas que agora está disponível novamente, inicie os serviços de borda.

2.  Se você quiser fazer failback da rota de Federação do Lync Server para usar o servidor de borda restaurado, faça o seguinte:
    
      - Em um servidor front-end, abra o construtor de topologias. Expanda Pools de **bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.
    
      - Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda original ou no pool do servidor de borda que você deseja usar novamente para a Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**. Clique em **OK**.
    
      - Clique em **ação**, selecione **topologia**, selecione **publicar**. Quando solicitado em **publicar a topologia**, clique em **Avançar**. Quando a publicação estiver concluída, clique em **concluir**.
    
      - No servidor de borda, abra o assistente de implantação do Lync Server. Clique em **instalar ou atualizar o Lync Server System**e, em seguida, clique em **Configurar ou remover componentes do Lync Server**. Clique em **executar novamente**.
    
      - Em configurar componentes do Lync Server, clique em **Avançar**. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **concluir** para concluir a implantação.

3.  Se você quiser fazer failback na rota de Federação do XMPP para usar o servidor de borda restaurado, faça o seguinte:
    
      - Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para o pool de borda que agora hospeda a Federação XMPP (neste exemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Neste exemplo, site1 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer1.contoso.com é o FQDN de um servidor de borda nesse pool.
    
      - Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir. Esse registro SRV deve ter um valor de porta 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.
    
      - Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.

4.  Se os pools de front-end permanecerem sendo executados no site que contém o pool de borda que falhou e foi restaurado, você deverá atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar novamente os pools de borda em seu site local. Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Se o pool de front-ends no mesmo site do pool de borda com falha também falhar, agora você pode usar Invoke – CsPoolFailback para fazer failback do pool de front-ends.

</div>

<div>

## <a name="see-also"></a>Confira também


[Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Failover do pool de Borda usado para federação de XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Recuperação de desastres do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

