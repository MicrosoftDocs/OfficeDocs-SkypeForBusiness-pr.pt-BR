---
title: 'Lync Server 2013: Topologia de referência em grandes organizações com vários data centers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2460378d19f8edb4e845778cacaf01c7141204c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologia de referência para Lync Server 2013 em grandes organizações com vários data centers

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

A topologia de referência para uma organização de grande porte com suporte a vários data centers destina-se a organizações de todos os tamanhos que tenham mais de um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 50.000 usuários, sendo 20.000 usuários no Site central A, 20.000 no Site central B e 10.000 no Site central C e nos sites de filiais. O tipo de topologia mostrado neste diagrama pode acomodar organizações com qualquer número de usuários.

Além da alta disponibilidade fornecida por pools de servidores front-end, essa topologia adiciona suporte à recuperação de desastres. Os pools de front-ends nos sites centrais A e B estão combinados juntos. Se um desses pools ficar inativo, o administrador poderá mudar os serviços dos usuários afetados para o pool emparelhado no site não afetado.

Essa topologia é mostrada em vários diagramas, com uma visão geral seguida por exibições detalhadas dos sites centrais.

**Visão geral da topologia de referência para grandes organizações com vários data centers**

![Topologia de referência para vários data centers] (images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologia de referência para vários data centers")

**Topologia de referência para grandes organizações: Visão detalhada do Local Central A**

![dab33f19-e77b-42da-9047-858fb9851264] (images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologia de referência para grandes organizações: Visão detalhada do Local Central B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f] (images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topologia de referência para grandes organizações: Visão detalhada do Local Central C**

![7238ca40-340c-491f-b497-ddc2665dadb6] (images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **Os pools front-ends são emparelhados para permitir a recuperação de desastres.**    Os pools de front-end no site A e no site B são emparelhados uns com os outros, para fornecer suporte à recuperação de desastres. Se o pool em um site falhar, o administrador poderá fazer failover dos usuários desse site para o pool de front-end emparelhado no outro site, com uma interrupção mínima de serviço para os usuários. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obter mais informações, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Os servidores back-end são espelhados**   para fornecer mais disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de servidores back-end para cada pool de front-ends. Essa é uma topologia opcional, e você pode optar por implantar um único servidor back-end em vez disso.

  - **Usar o servidor Standard Edition em um site de filial.**    Esta organização considera o site C como um site de ramificação porque tem apenas 600 funcionários. However, the users there have many A/V conferences among themselves. Se ele foi implantado no Lync Server como um site de filial, a mídia dessas conferências seria executada na WAN (rede de longa distância) e em um site central que tenha um servidor front-end implantado. Para evitar essa carga de largura de banda potencial, ela instalou um par de servidores de edição padrão neste site, que hospedará essas conferências. E como os servidores de edição padrão são instalados, o Lync Server por definição considera isso um site central, e ele é tratado como tal no construtor de topologias e na ferramenta de planejamento.
    
    Apenas um servidor de edição padrão seria suficiente para o desempenho aqui, mas a organização implantou dois e os emparelha juntos para fornecer alta disponibilidade em caso de um servidor ficar inativo.
    
    Embora o Site C seja considerado um site central, não é necessário implantar servidores de borda nele. Nesse exemplo, o Local C usa os Servidores de Borda implantados no Local A.

  - **Monitorar e arquivar**   esta organização implantou o monitoramento e o arquivamento. Quando você implanta esses dois recursos, eles são executados em todos os servidores front-end. Os bancos de dados desses recursos podem ser colocados com o banco de dados back-end ou em outro servidor. Essa organização colocou esses bancos de dados em um servidor separado dos servidores back-end, no Site central B. Nesse caso, os bancos de dados recebem dados do monitoramento e arquivamento dos servidores front-end em todos os sites.

  - **Opções de implantação de site de ramificação.**    Essa organização tem, na verdade, mais de 50 sites de ramificação, apenas três dos quais são mostrados nos diagramas detalhados. Os sites de filiais 1 e 3 não têm um link de WAN flexível para o site central, portanto, eles têm aparelhos de ramificação sobreviventes implantados para fornecer serviço telefônico, caso o link de WAN para o site central fique inativo. No entanto, o site de ramificação 2 tem um link de rede de longa distância adaptável, portanto você só precisa de um gateway PSTN (rede telefônica pública comutada). O gateway PSTN implantado oferece suporte ao bypass de mídia, portanto, não é necessário servidor de mediação no site de ramificação B. Para obter detalhes sobre como decidir o que instalar em um site de filial, consulte [planejando a resiliência do Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) na documentação de planejamento.

  - **Servidor de entroncamento e mediação SIP.**    Observe que, no site central B, o servidor de mediação não é posicionado com os servidores front end. Isso acontece porque recomenda-se usar um Servidor de Mediação independente para sites que usam o tronco SIP. Na maioria das demais instâncias, recomendamos colocar o Servidor de Mediação com o servidor front-end. Para obter detalhes sobre as topologias do servidor de mediação, consulte [componentes e topologias do servidor de mediação no Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.

  - **O chat persistente é implantado.**    Esta organização implantou os servidores necessários para habilitar o chat persistente. Ela implantou vários servidores front-end de chat persistente para lidar com a carga do número de usuários no pool e proporcionar alta disponibilidade. Ela também implantou conformidade para chat persistente e colocou o repositório do chat persistente e o repositório de conformidade do chat persistente em servidores separados. Esses repositórios podem ser colocados e até mesmo colocados com o servidor back-end, mas a organização optou por separá-los para proporcionar desempenho melhor.

  - **Balanceamento de carga de DNS.**    O pool de front-ends e o pool do servidor de borda. Isso elimina a necessidade de balanceadores de carga de hardware para a interface interna dos servidores de borda e reduz significativamente o tempo necessário para configuração e manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

  - **Implantação de UM do Exchange.**   O Lync Server funciona com implantações *locais* da Unificação de mensagens (um) do Exchange e *hospedadas* do Exchange um. Site central A inclui um servidor de um (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Lync Server. A funcionalidade de UM do Exchange para o Lync Server é executada no pool de front-ends.
    
    O Site central B usa o Exchange hospedado. Portanto, a funcionalidade do servidor de UM do Exchange também é hospedada.
    
    Para obter detalhes sobre o Exchange UM, consulte [planejando a integração de Unificação de mensagens do Exchange no Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e integração de Unificação de [mensagens do Exchange no Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.**   Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. Você pode implantar um único farm de servidores do Office Web Apps em um site que sirva tráfego de todos os sites ou implantá-lo em cada site. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências. Para obter mais informações, consulte Configurando [a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Os directors podem ser adicionados.**   Se essa organização quisesse aumentar a segurança contra ataques de negação de serviço, ele também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional separada no Lync Server que não hospeda contas de usuário nem fornece serviços de presença ou conferência. Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou o servidor primário do usuário. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a proteger servidores de front-end contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor.

  - **O System Center Operations Manager é implantado.**   Recomendamos que você monitore a integridade da implantação do Lync Server para garantir a disponibilidade do serviço para os usuários finais. Você pode monitorar o Lync com o pacote de gerenciamento do System Center Operations Manager para Lync que está disponível como um download gratuito da Microsoft. Com o pacote de gerenciamento do Lync, você pode obter alertas em tempo real em tempo real quando ocorrem problemas, executar transações sintéticas para testar a funcionalidade ponto a ponto do Lync, obter relatórios para a disponibilidade do serviço e assim por diante. This helps you to proactively respond to issues with your deployment before end-users experience them.
    
    Esta organização implantou um servidor do System Center Operations Manager em cada site central.

</div>

<span> </span>

</div>

</div>

</div>

