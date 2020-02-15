---
title: 'Lync Server 2013: failover do pool de borda usado para Federação XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3957f3fc5a315c5b661ddeec4ea83b8e7f0eab0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Failover do pool de borda usado para Federação XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Na sua organização, há um pool de borda designado como o pool para uso da federação XMPP. Se esse pool parar de funcionar, você deve transferir a federação XMPP para usar um pool de borda diferente antes da federação XMPP poder funcionar novamente.

Quando você instala pools de borda e habilita a Federação XMPP, é possível simplificar o processo de recuperação de desastres configurando a criação de registros do servidor DNS externos para todos os seus pools de Borda para a federação XMPP, em vez de apenas um. Cada um destes registros SRV devem ter um conjunto de prioridade diferente. Todo o tráfego da federação XMPP atravessa o pool com o registro SRV com a mais alta prioridade. Para obter mais informações sobre como habilitar e configurar a Federação do XMPP, consulte [setting up XMPP Federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

No procedimento a seguir, o EdgePool1 é o pool no qual a federação XMPP foi originalmente hospedada e o EdgePool2 é o pool no qual a federação XMPP está hospedada agora.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Transferência do pool de borda utilizado para a federação XMPP

1.  Se você ainda não possuir outro pool de borda implantado (além de um não estiver funcionando no momento), implante esse pool. Para obter detalhes, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  Em cada Servidor de Borda no novo pool de borda no qual a federação XMPP estará hospedada no momento (EdgePool2), execute o seguinte cmdlet:
    
        Stop-CsWindowsService

3.  Execute o seguinte cmdlet para redirecionar a rota da federação XMPP para o EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    Neste exemplo, o Site2 é o site contendo o pool de borda no qual a rota da federação XMPP estará hospedada no momento e o EdgeServer2.contoso.com é o FQDN de um Servidor de Borda nesse pool.

4.  No servidor DNS externo, altere o registro A de DNS da federação XMPP para apontar para o EdgeServer2.contoso.com.

5.  Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolva o pool de borda no qual a federação XMPP estará hospedada no momento, é necessário adicioná-lo, conforme no exemplo a seguir. O registro SRV deve ter um valor de porta de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique se o pool de borda no qual a federação XMPP estará hospedada no momento possui uma porta 5269 aberta externamente.

7.  Inicie os serviços em todos os Servidores de Borda no pool de borda no qual a federação XMPP estará hospedada no momento:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

