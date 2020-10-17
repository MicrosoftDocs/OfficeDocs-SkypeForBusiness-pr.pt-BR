---
title: 'Lync Server 2013: topologia de referência para organizações de médio porte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2549acbf8b5eac2ac909eb213d6d73e8233b0a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536698"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologia de referência para Lync Server 2013 em organizações de médio porte

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

A topologia de referência com alta disponibilidade e um único data center é projetada para uma organização de pequeno a médio porte com um local central. A topologia exata no diagrama a seguir é para uma organização de 20.000 usuários.

**Topologia de referência para organizações de médio porte**

![Topologia de referência para um único diagrama de data center](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Topologia de referência para um único diagrama de data center")

  - **Acomode mais usuários adicionando mais servidores front-end.**     A topologia exata neste diagrama tem três servidores front-end para fornecer suporte a 20.000 usuários. Se você tiver um único site central e mais usuários, poderá simplesmente adicionar mais servidores front-end ao pool. O número máximo de usuários por pool é 80.000, com doze servidores front-end.
    
    No entanto, a topologia de site único pode dar suporte a mais usuários adicionando outro pool de Front-End ao site.

  - A **recuperação de desastre pode ser adicionada.**     Para esta organização, a alta disponibilidade para os serviços do Lync Server é um recurso necessário, mas a recuperação de desastres não. O pool de servidores front-end implantados oferece alta disponibilidade.
    
    Se desejasse adicionar capacidade de recuperação de desastres, eles podem considerar o estabelecimento de outro datacenter e a adição de outro pool de front-ends e ao emparelhamento com o pool de front-ends no datacenter atual. Em seguida, se houvesse um desastre que afete o pool principal, os administradores poderão fazer failover dos usuários para o pool de backup.

  - Os **servidores de back-end são espelhados**     Para fornecer mais alta disponibilidade para recursos de usuário básicos, a organização implantou um par espelhado de servidores back-end para cada pool de front-ends. Esta é uma nova opção de topologia para o Lync Server 2013 e é opcional. Você pode optar por implantar um único servidor back-end.

  - **Opções do banco de dados do Monitoring Server.**     Esta organização implantou o monitoramento para garantir a qualidade das chamadas do Enterprise Voice e conferências A/V. O monitoramento é implantado em todos os servidores front-end, e o banco de dados de monitoramento é colocado com os servidores de back-end. Também damos suporte a topologias nas quais o banco de dados de monitoramento está localizado em um servidor separado.

  - **Alta disponibilidade**     do servidor de borda Neste exemplo de organização com 20.000 usuários, apenas um servidor de borda seria suficiente para o desempenho. No entanto, há um pool de dois servidores de Borda implantados para fornecer alta disponibilidade.

  - **Opções de implantação de site de filial.**     A organização dessa topologia tem o Enterprise Voice implantado como sua solução de voz. O site de filial 1 não tem um link de rede de longa distância (WAN) resistente para o site central e, portanto, tem um aparelho de filial persistente implantado para manter vários recursos do Lync Server, caso o link WAN para o site central fique inativo. No entanto, o Site de Filial 2 tem um link WAN resiliente, portanto, apenas um gateway PSTN (rede telefônica pública comutada) é necessário. O gateway PSTN implantado tem suporte para bypass de mídia, portanto, nenhum Servidor de Mediação é necessário na Filial 2. Para obter detalhes sobre como decidir o que implantar em um site de filial, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.

  - **Balanceamento de carga de DNS.**     O pool de front-ends do pool de servidores do andEdge, com balanceamento de carga de DNS para o tráfego SIP implantado. Isso elimina a necessidade de balanceadores de carga de hardware para os Servidores de Borda e reduz significativamente a configuração e a manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

  - **Implantação do Exchange do UM.** Essa topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, e não o Lync Server.
    
    Para obter detalhes sobre a UM do Exchange, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [Hosted Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.** Recomendamos a implantação de um servidor do Office Web Apps ou do farm do servidor do Office Web Apps em todas as organizações que usam a conferência da Web. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - Os **servidores de borda são recomendados.**     Embora não seja necessário implantar um servidor de borda, recomendamos isso para qualquer tamanho de implantação. Você pode maximizar seu investimento no Lync Server implantando um servidor de borda para fornecer serviço aos usuários fora dos firewalls da sua organização. Os benefícios são os seguintes:
    
      - Os usuários da sua organização podem usar a funcionalidade do Lync Server, se estiverem trabalhando de casa ou estão em trânsito.
    
      - Seus usuários podem convidar usuários de fora para participar de reuniões.
    
      - Se você tiver uma organização de parceiro, fornecedor ou cliente que também usa o Lync Server, você pode formar uma *relação federada* com essa organização. A implantação do Lync Server reconhecerá os usuários dessa organização federada, levando à melhor colaboração.
    
      - Seus usuários podem trocar mensagens instantâneas com usuários de serviços públicos de IM, incluindo qualquer uma das seguintes opções: Windows Live, AOL, Yahoo \! e Google Talk. Uma licença separada pode ser necessária para conectividade de IM pública com esses serviços.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
        > <LI>
        > <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
        > <LI>
        > <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>

        
        </div>

  - Os **diretores podem ser adicionados.**     Se essa organização quisesse ajudar a aumentar a segurança contra ataques de negação de serviço, também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional e separada no Lync Server que não hospeda contas de usuário, nem fornece serviços de presença ou conferência. Ele serve como um servidor de próximo salto interno para o qual um servidor de Borda roteia o tráfego SIP de entrada destinado a servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou servidor de casa do usuário. A pré-autenticação no diretor permite o descarte de solicitações de contas de usuário desconhecidas para a implantação. Um diretor ajuda a isolar servidores front-end de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse ataque, o tráfego terminará no diretor.

  - O **System Center Operations Manager é recomendado.**    Recomendamos que você monitore a integridade da implantação do Lync Server para ajudar a garantir a disponibilidade do serviço para os usuários finais. Você pode monitorar o Lync com o pacote de gerenciamento do System Center Operations Manager para Lync que está disponível como um download gratuito da Microsoft. Com o pacote de gerenciamento do Lync, é possível obter alertas em tempo real de forma proativa quando ocorrerem problemas, executar transações sintéticas para testar a funcionalidade de ponta a ponta do Lync, obter relatórios de disponibilidade de serviço e assim por diante. Isso ajuda a responder proativamente aos problemas de sua implantação antes que os usuários finais os experimentem.

</div>

<span> </span>

</div>

</div>

</div>

