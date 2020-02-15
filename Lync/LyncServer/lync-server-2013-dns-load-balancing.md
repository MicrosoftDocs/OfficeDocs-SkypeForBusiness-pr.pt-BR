---
title: 'Lync Server 2013: balanceamento de carga de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d1efb960e6f60118364193dffdbedcefea94a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Balanceamento de carga de DNS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-01-15_

O Lync Server habilita o balanceamento de carga de DNS, uma solução de software que pode reduzir significativamente a sobrecarga de administração para balanceamento de carga na sua rede. O balanceamento de carga DNS balanceia o tráfego de rede que é exclusivo do Lync Server, como tráfego SIP e tráfego de mídia.

Se você implantar o balanceamento de carga DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada. Além disso, a solução complexa de problemas relacionados à configuração incorreta de balanceadores de carga de tráfego SIP será eliminada. Você também pode impedir as conexões de servidor para que seja possível assumir servidores offline. O balanceamento de carga DNS também garante que os problemas de balanceador de carga de hardware não afetem elementos do tráfego SIP, como o roteamento básico de chamada.

Se você usar o balanceamento de carga DNS, também poderá adquirir os balanceadores de carga de hardware de custo mais baixo do que se usasse os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com o Lync Server. Para obter detalhes sobre o teste de interoperabilidade do balanceador de carga, consulte "parceiros do balanceador de carga do Lync Server 2010" em [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).

O balanceamento de carga DNS é suportado para pools de Front-Ends,  pools de Servidor de Borda, pools do Diretor e pools autônomos do Servidor de Mediação.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Balanceamento de carga DNS em  pools do Diretor e  pools de Front-End

Você pode usar o  balanceamento de carga DNS para o tráfego SIP em pools de Front-End e  pools do Diretor. Com o balanceamento de carga DNS implantado, você precisará usar também os balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente-servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80.

Embora você ainda precisará de balanceadores de carga de hardware para estes pools, sua configuração e administração será principalmente para o tráfego HTTPS, aos quais os administradores dos balanceadores de carga de hardware estão acostumados.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Balanceamento de carga DNS e suporte aos clientes e servidores mais antigos

O balanceamento de carga DNS oferece suporte a failover automático somente para servidores que executam o Lync Server 2013 ou o Lync Server 2010 e para clientes do Lync 2013 e Lync 2010. As versões anteriores de clientes e o Office Communications Server ainda podem se conectar a pools que executam o balanceamento de carga DNS, mas se não puderem estabelecer uma conexão com o primeiro servidor ao qual o balanceamento de carga DNS as referencia, eles não poderão fazer failover para outro servidor no pool .

Além disso, se você estiver usando o UM do Exchange, deverá usar um mínimo de Exchange 2010 SP1 para obter suporte para o balanceamento de carga DNS do Lync Server. Se você usar uma versão anterior do Exchange, seus usuários não terão recursos de failover para esses cenários de UM do Exchange:

  - Reproduzindo a caixa postal do Enterprise no telefone

  - Transferindo chamadas de um Atendedor Automático UM do Exchange

Todos os outros cenários UM do Exchange funcionarão corretamente.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>A implantação do balanceamento de carga DNS em  pools do Diretor e  pools de Front-End

A  implantação do balanceamento DNS de carga nos pools de Front-Ends e  pools do Diretor requer a execução de algumas etapas extras com os registros DNS e FQDNs.

  - Um pool que usa o balanceamento de carga DNS deve ter dois FQDNs: o pool FQDN normal usado pelo balanceamento de carga DNS (como pool01.contoso.com) e resolve para os IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como web01.contoso.com), que resolve para o endereço IP virtual do pool.
    
    No construtor de topologia, se você deseja implantar o balanceamento de carga DNS para um pool, para criar esse FQDN extra para os serviços Web do pool, você deve marcar a caixa de seleção **substituir FQDN do pool de serviços Web internos** e digitar o FQDN, na página **especificar as URLs de serviços Web para este pool** .

  - Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end. Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end. Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Balanceamento de carga DNS em pools de servidor de borda

Você pode implantar o balanceamento de carga DNS em pools de servidor de borda. Se você fizer isso, deve estar ciente de algumas considerações.

Usar o balanceamento de carga DNS nos servidores de borda provoca uma perda da capacidade de failover nos seguintes cenários:

  - Federação com organizações que estão executando versões do Office Communications Server lançadas antes do Lync Server 2010.

  - Troca de mensagens instantâneas com usuários de serviços de mensagens instantâneas (IM\!) AOLand Yahoo, além de provedores e servidores baseados em XMPP, como o Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>O Google Talk atualmente é o único parceiro do XMPP com suporte.</P>
    > <LI>
    > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Esses cenários funcionarão desde que todos os servidores de borda no pool estejam funcionando. Se um servidor de borda estiver disponível, as solicitações enviadas para esses cenários falharão, em vez de rotear para outro servidor de borda.

Se estiver usando um do Exchange, você deve usar um mínimo de Exchange 2013 para obter suporte para o balanceamento de carga DNS do Lync Server no Edge. Se você usar uma versão anterior do Exchange, seus usuários remotos não terão recursos de failover para esses cenários de UM do Exchange:

  - Reproduzindo a caixa postal do Enterprise no telefone

  - Transferindo chamadas de um Atendedor Automático UM do Exchange

Todos os outros cenários UM do Exchange funcionarão corretamente.

A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando o Balanceamento de Carga DNS em Pools de Servidor de Borda

Para implantar o balanceamento de carga DNS na interface externa do seu pool de Servidor de Borda, são necessárias as seguintes entradas DNS:

  - Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso em um dos servidores de borda no pool.

  - Para o serviço de borda de webconferência, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de Webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço de borda de Webconferência em um dos servidores de borda no pool.

  - Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda A/V em um dos servidores de borda no pool.

Para implantar o balanceamento de carga DNS na interface interna do pool de Servidor de Borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do Servidor de Borda para o endereço IP de cada servidor do pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usando o balanceamento de carga DNS em pools do servidor de mediação

Você pode usar um  balanceamento de carga DNS em pools do Servidor de Mediação autônomos. Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga DNS.

Para implantar o balanceamento de carga DNS em um pool do Servidor de Mediação, vcê deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueando o tráfego para um servidor com balanceamento de carga DNS

Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do pool. Você também deve remover a entrada DNS do computador.

Observe que, para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga com reconhecimento de topologia. Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores. Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

