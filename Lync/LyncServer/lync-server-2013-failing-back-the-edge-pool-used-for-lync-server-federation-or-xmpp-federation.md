---
title: Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Após um pool de Borda em falha usado para hospedar a federação entre o retorno online, use este procedimento para realizar um fail back da rota de federação do Lync Server e/ou a rota de federação XMPP para usar novamente este pool de Borda restaurado.

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>Failing Back da federação para um pool de borda restaurado

1.  No pool de Borda disponível novamente, inicie os Serviços de Borda.

2.  Se você deseja realizar o fail back da rota de federação do Lync Server para usar o Servidor de Borda restaurado, faça o seguinte:
    
      - No servidor de front-end, abra o Construtor de Topologia. Expanda **Pools de borda**, clique com o botão direito no servidor de Borda ou pool do servidor de Borda atualmente configurado para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.
    
      - Expanda **Pools de borda**, clique com o botão direito no servidor de Borda original ou pool de servidor de Borda que você deseja usar novamente para Federação. Selecione **Editar propriedades**.
    
      - Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.
    
      - Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.
    
      - No servidor de Borda, abra o assistente de Implantação do Lync Server. Clique em **Instalar ou atualizar o sistema do Lync Server**, clique em **Instalar ou remover componentes do Lync Server**. Clique em **Executar novamente**.
    
      - Em Instalar componentes do Lync Server, clique em **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.

3.  Se você deseja realizar o fail back da rota de federação XMPP para usar o Servidor de Borda restaurado, faça o seguinte:
    
      - Execute o seguinte cmdlet para reapontar a rota de federação XMPP para o pool de Borda que irá hospedar agora a federação XMPP (neste exemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        Neste exemplo, Site1 é o local contendo o pool de Borda que irá agora hospedar a rota de federação XMPP e EdgeServer1.contoso.com é o FQDN de um Servidor de Borda no pool.
    
      - Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolve o pool de Borda que hospedará a federação XMPP, você deve adicioná-lo, conforme no exemplo a seguir. Este registro SRV deve ter um valor de porta de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - No servidor DNS externo, altere o registro DNS A para federação XMPP apontar para o EdgeServer2.contoso.com.
    
      - Verifique se o pool de Borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.

4.  Se os pools de front-end permanecem executando no site contendo o pool de Borda que falhou e foi restaurado, você deve atualizar o Serviço de Conferência da Web e o Serviço de Conferência A/V nestes pools de front-end para usar novamente os pools de Borda em seu site local. Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

5.  Se o pool de front-end no mesmo site possui um pool de Borda em falha que também falhou, é possível agora usar Invoke–CsPoolFailback para fazer o fail back do pool de front-end.

</div>

<div>

## <a name="see-also"></a>Confira também


[Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[Failover do pool de borda usado para Federação XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Recuperação de desastre do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

