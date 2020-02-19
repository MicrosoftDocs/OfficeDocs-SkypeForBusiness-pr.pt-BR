---
title: Lync Server 2013 referência de topologia para grandes organizações com vários data centers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2f7f6ed91298e0f6abb8361876a12500903a73
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologia de referência para Lync Server 2013 em grandes organizações com vários data centers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

A topologia de referência para uma organização de grande porte com suporte a vários data centers é para qualquer tamanho de organização com mais de um site central. A topologia exata no diagrama a seguir é para uma organização de 50.000 usuários, com 20.000 usuários no site central A, 20.000 no local central B. e um total de 10.000 no site central C e sites de filial. O tipo de topologia mostrado neste diagrama pode acomodar organizações com qualquer número de usuários.

Além da alta disponibilidade fornecida por pools de servidores front-end, essa topologia adiciona suporte à recuperação de desastres. Os pools de front-ends nos sites centrais A e B são emparelhados juntos. Se um desses pools ficar inativo, o administrador poderá mudar os serviços para os usuários afetados para o pool emparelhado no site não afetado.

Essa topologia é mostrada em vários diagramas, com uma visão geral primeiro seguida por exibições detalhadas dos sites centrais.

**Visão geral da topologia de referência para grandes organizações com vários data centers**

![Topologia de referência para vários data centers](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologia de referência para vários data centers")

**Topologia de referência para grandes organizações: visão detalhada do local central A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologia de referência para grandes organizações: visão detalhada do local central B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topologia de referência para grandes organizações: visão detalhada do local central C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Os pools de front-ends são emparelhados para habilitar a recuperação de desastres.**    Os pools de front-ends no local A e o site B são emparelhados, para fornecer suporte à recuperação de desastres. Se o pool em um site falhar, o administrador pode fazer failover dos usuários desse site para o pool de front-ends emparelhado no outro site, com um mínimo de interrupção de serviço para os usuários. Cada um desses dois pools de front-ends tem seis servidores, o que é suficiente para todos os 40.000 usuários em ambos os pools em caso de failover. Para obter mais informações, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Os servidores**   de back-end são espelhados para oferecer mais alta disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de servidores back-end para cada pool de front-ends. Essa é uma topologia opcional e você pode optar por implantar um único servidor de back-end.

  - **Usando o servidor Standard Edition em um site de filial.**    Esta organização considera o site C como um site de filial, pois ele tem apenas 600 funcionários. No entanto, os usuários têm muitas conferências A/V entre si. Se ele tiver sido implantado no Lync Server como um site de filial, a mídia dessas conferências seria executada na WAN (rede de longa distância) para e a partir de um local central que tenha um servidor front-end implantado. Para evitar essa carga de largura de banda potencial, ela instalou um par de servidores Standard Edition neste site, que hospedará essas conferências. E como os servidores Standard Edition são instalados, o Lync Server por definição considera um site central e é tratado como tal no construtor de topologias e na ferramenta de planejamento.
    
    Apenas um servidor Standard Edition seria suficiente para o desempenho aqui, mas a organização implantou duas e as colocou em conjunto para fornecer alta disponibilidade, caso um servidor fique inativo.
    
    Embora o site C seja considerado um site central, você não precisa implantar os servidores de borda. Neste exemplo, o site C usará os servidores de Borda implantados no site A.

  - **Monitoramento e arquivamento**   esta organização implantou o monitoramento e o arquivamento. Quando você implanta o monitoramento ou arquivamento, ele é executado em todos os servidores front-end. Os bancos de dados desses recursos podem ser colocados com o banco de dados de back-end ou localizados em um servidor separado. Esta organização localizou esses bancos de dados em um servidor separado dos servidores de back-end, no local central B. Os bancos de dados aqui recebem dados de monitoramento e arquivamento dos servidores front-end em todos os sites.

  - **Opções de implantação de site de filial.**    Na verdade, essa organização tem mais de 50 sites de filial, apenas três dos quais são mostrados nos diagramas detalhados. Os sites 1 e 3 de filiais não têm um link de WAN resiliente para o site central, para que eles tenham aparelhos de filial persistente implantados para fornecer serviço telefônico, caso o link de WAN para o site central fique inativo. No entanto, o site de filial 2 tem um link WAN resiliente, portanto, você precisa apenas de um gateway PSTN (rede telefônica pública comutada). O gateway PSTN implantado oferece suporte a bypass de mídia, portanto, nenhum servidor de mediação é necessário no local de filial B. Para obter detalhes sobre como decidir o que instalar em um site de filial, consulte [Planning for Enterprise Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) na documentação de planejamento.

  - **Tronco SIP e servidor de mediação.**    Observe que no local central B, o servidor de mediação não está colocado com os servidores front-end. Isso ocorre porque o servidor de mediação autônomo é recomendado para sites que usam o tronco SIP. Na maioria das outras instâncias, recomendamos colocar o servidor de mediação com o servidor front-end. Para obter detalhes sobre topologias de servidor de mediação, consulte [Components and topologias for Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

  - **O chat persistente está implantado.**    Esta organização implantou os servidores necessários para habilitar o chat persistente. Ela implantou vários servidores front-end de chat persistente para lidar com a carga do número de usuários no pool e para fornecer alta disponibilidade. Ela também implantou a conformidade para chat persistente e localizou o repositório de chat persistente e o repositório de conformidade de chat persistente em servidores separados. Esses repositórios podem ser colocados e podem até ser colocados com o servidor back-end, mas essa organização optou por separá-los para fornecer melhor desempenho.

  - **Balanceamento de carga de DNS.**    O pool de front-ends e o pool do servidor de borda. Isso elimina a necessidade de balanceadores de carga de hardware para a interface interna dos servidores de borda e reduz significativamente a quantidade de tempo que você precisa gastar na configuração e manutenção dos balanceadores de carga de hardware para os outros pools, como a carga de hardware os balanceadores são necessários apenas para tráfego HTTP. Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

  - **Implantação de UM do Exchange.**   O Lync Server funciona com implantações *locais* de um (Unificação de mensagens) do Exchange e um do Exchange *hospedado* . O site central A inclui um servidor de um (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Lync Server. A funcionalidade UM do Exchange para Lync Server é executada no pool de front-ends.
    
    O local central B usa o Exchange hospedado, portanto, a funcionalidade de servidor UM do Exchange também é hospedada.
    
    Para obter detalhes sobre a UM do Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.**   Recomendamos a implantação de um servidor do Office Web Apps ou do farm do servidor do Office Web Apps em todas as organizações que usam a conferência da Web. Você pode implantar um único farm do servidor do Office Web Apps em um site que serve tráfego de todos os sites ou implantá-lo em cada site. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Os diretores podem ser adicionados.**   Se essa organização quisesse aumentar a segurança contra ataques de negação de serviço, também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional e separada no Lync Server que não hospeda contas de usuário, nem fornece serviços de presença ou conferência. Ele serve como um servidor de próximo salto interno para o qual um servidor de Borda roteia o tráfego SIP de entrada destinado a servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou servidor de casa do usuário. A pré-autenticação no diretor permite o descarte de solicitações de contas de usuário desconhecidas para a implantação. Um diretor ajuda a isolar servidores front-end de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse ataque, o tráfego terminará no diretor.

  - **O System Center Operations Manager é implantado.**   Recomendamos que você monitore a integridade da implantação do Lync Server para garantir a disponibilidade do serviço para os usuários finais. Você pode monitorar o Lync com o pacote de gerenciamento do System Center Operations Manager para Lync que está disponível como um download gratuito da Microsoft. Com o pacote de gerenciamento do Lync, é possível obter alertas em tempo real de forma proativa quando ocorrerem problemas, executar transações sintéticas para testar a funcionalidade de ponta a ponta do Lync, obter relatórios de disponibilidade de serviço e assim por diante. Isso ajuda a responder proativamente aos problemas de sua implantação antes que os usuários finais os experimentem.
    
    Esta organização implantou um servidor do System Center Operations Manager em cada site central.

</div>

<span> </span>

</div>

</div>

</div>

