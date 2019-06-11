---
title: 'Lync Server 2013: balanceamento de carga de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4248815c2e896c6c4ce36d22fd6544c298527766
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Balanceamento de carga de DNS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-01-15_

O Lync Server habilita o balanceamento de carga de DNS, uma solução de software que pode reduzir significativamente a sobrecarga de administração de balanceamento de carga na sua rede. O balanceamento de carga de DNS equilibra o tráfego de rede exclusivo para o Lync Server, como tráfego SIP e tráfego de mídia.

Se você implantar o balanceamento de carga de DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada. Além disso, a solução de problemas complexa de problemas relacionados à configuração incorreta de balanceadores de carga para tráfego SIP será eliminada. Você também pode evitar conexões do servidor para que você possa colocar servidores offline. O balanceamento de carga de DNS também garante que os problemas de balanceador de carga de hardware não afetem os elementos do tráfego SIP, como roteamento de chamadas básicas.

Se você usa o balanceamento de carga de DNS, também é possível comprar saldos de carga de hardware de baixo custo do que se você usava os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com o Lync Server. Para obter detalhes sobre o teste de interoperabilidade do balanceamento de carga, consulte "parceiros do balanceador [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)de carga do Lync Server 2010" em.

O balanceamento de carga de DNS tem suporte para pools front-end, pools do servidor de borda, pools de diretor e pools autônomos do servidor de mediação.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Balanceamento de carga de DNS em pools front-end e pools de diretor

Você pode usar o balanceamento de carga de DNS para o tráfego SIP em pools de front-end e em pools de diretor. Com o balanceamento de carga de DNS implantado, você ainda precisará usar balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente para servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80.

Embora você ainda precise de balanceadores de carga de hardware para esses pools, a configuração e a Administração serão principalmente para tráfego HTTPS, para o qual os administradores de balanceamento de carga de hardware estão acostumados.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Balanceamento de carga de DNS e suporte a clientes e servidores mais antigos

O balanceamento de carga de DNS suporta failover automático somente para servidores que executam o Lync Server 2013 ou o Lync Server 2010 e para clientes do Lync 2013 e Lync 2010. As versões anteriores dos clientes e do Office Communications Server ainda podem se conectar a pools que executam o balanceamento de carga de DNS, mas se não puderem fazer uma conexão com o primeiro servidor ao qual o balanceamento de carga de DNS a referencia, eles não poderão fazer failover para outro servidor no pool .

Além disso, se você estiver usando o Exchange UM, deverá usar no mínimo o Exchange 2010 SP1 para obter suporte para o balanceamento de carga de DNS do Lync Server. Se você usar uma versão anterior do Exchange, os usuários não terão recursos de failover para estes cenários do Exchange UM:

  - Reproduzindo a caixa postal do Enterprise Voice em seu telefone

  - Transferindo chamadas de um atendedor automático do Exchange UM

Todos os outros cenários do Exchange UM funcionarão corretamente.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implantando o balanceamento de carga de DNS em pools front-end e pools de diretor

Implantar o balanceamento de carga de DNS nos pools front-end e nos pools de diretor exige que você execute algumas etapas adicionais com FQDNs e registros DNS.

  - Um pool que usa o balanceamento de carga de DNS deve ter dois FQDNs: o FQDN do pool regular que é usado pelo balanceamento de carga de DNS (como pool01.contoso.com) e é resolvido para o IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como web01.contoso.com), que é resolvido para o endereço IP virtual do pool.
    
    Em Construtor de topologia, se você quiser implantar o balanceamento de carga de DNS para um pool, para criar esse FQDN adicional para os serviços Web do pool, você deve selecionar a caixa de seleção **substituir o FQDN do pool de serviços Web internos** e digitar o FQDN em **especificar as URLs de serviços Web para Esta** página de pool.

  - Para dar suporte ao FQDN usado pelo balanceamento de carga de DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão implantados no momento.
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Balanceamento de carga de DNS nos pools do servidor de borda

Você pode implantar o balanceamento de carga de DNS nos pools do servidor de borda. Se fizer isso, você deve estar ciente de algumas considerações.

Usar o balanceamento de carga de DNS em seus servidores de borda causa uma perda de capacidade de failover nos seguintes cenários:

  - Federação com organizações que estão executando versões do Office Communications Server lançadas antes do Lync Server 2010.

  - Troca de mensagens de chat com usuários de serviços de mensagens instantâneas (IM\!) AOLand Yahoo, além de provedores e servidores baseados no XMPP, como o Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>No momento, o Google Talk é o único parceiro XMPP com suporte.</P>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Esses cenários funcionarão se todos os servidores de borda do pool estiverem em execução, mas se um servidor de borda estiver indisponível, todas as solicitações para esses cenários enviados a ele falharão, em vez de roteamento para outro servidor de borda.

Se estiver usando o Exchange UM, você deve usar no mínimo o Exchange 2013 para obter suporte para o balanceamento de carga de DNS do Lync Server no Edge. Se você usar uma versão anterior do Exchange, os usuários remotos não terão recursos de failover para estes cenários do Exchange UM:

  - Reproduzindo a caixa postal do Enterprise Voice em seu telefone

  - Transferindo chamadas de um atendedor automático do Exchange UM

Todos os outros cenários do Exchange UM funcionarão corretamente.

As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando o balanceamento de carga de DNS nos pools do servidor de borda

Para implantar o balanceamento de carga de DNS na interface externa do pool do servidor de borda, você precisa das seguintes entradas de DNS:

  - Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso em um dos servidores de borda do pool.

  - Para o serviço da borda de webconferência, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de Webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço Web de Webconferência em um dos servidores de borda no pool.

  - Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda A/V em um dos servidores de borda do pool.

Para implantar o balanceamento de carga de DNS na interface interna do pool do servidor de borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do servidor de borda para o endereço IP de cada servidor do pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usar o balanceamento de carga de DNS nos pools do servidor de mediação

Você pode usar o balanceamento de carga de DNS em pools de servidores de mediação autônomos. Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga de DNS.

Para implantar o balanceamento de carga de DNS em um pool do servidor de mediação, você deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueando o tráfego para um servidor com balanceamento de carga de DNS

Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador.

Observe que, para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga compatível com topologia. Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores. Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

