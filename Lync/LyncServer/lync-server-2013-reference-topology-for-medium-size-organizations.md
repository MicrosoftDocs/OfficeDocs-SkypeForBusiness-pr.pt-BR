---
title: 'Lync Server 2013: Topologia de referência em organizações de médio porte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologia de referência para Lync Server 2013 em organizações de médio porte

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

A topologia de referência com alta disponibilidade e um único data center é projetada para organizações de pequeno a médio porte com um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 20.000 usuários.

**Topologia de referência para organizações de médio porte**

![Topologia de referência para um único diagrama de data center] (images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Topologia de referência para um único diagrama de data center")

  - **Acomode mais usuários adicionando mais servidores de front-end.**    A topologia exata nesse diagrama tem três servidores front-end para fornecer suporte a usuários do 20.000. Se tiver um único site central e mais usuários, você poderá simplesmente adicionar mais servidores front-end ao pool. O máximo de usuários por pool é 80.000, com doze servidores front-end.
    
    No entanto, a topologia de site único pode dar suporte a ainda mais usuários com a adição de outro pool de front-ends ao site.

  - **A recuperação de desastres pode ser adicionada.**    Para esta organização, a alta disponibilidade dos serviços do Lync Server é um recurso necessário, mas a recuperação de desastres não é. O pool de servidores front-end que ele implantou fornece alta disponibilidade.
    
    Se quiser adicionar a capacidade de recuperação de desastres, a organização pode considerar estabelecer outro data center e adicionar outro pool de front-ends, emparelhando-o com o pool de front-ends no data center atual. Assim, caso um desastre afete o pool primário, os administradores poderão fazer o failover dos usuários no pool de backup.

  - **Os servidores back-end são espelhados**   para fornecer mais disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de servidores back-end para cada pool de front-ends. Esta é uma nova opção de topologia do Lync Server 2013 e é opcional. Você pode optar por implantar um único servidor back-end em vez disso.

  - **Opções de banco de dados do Monitoring Server.**    Esta organização implantou o monitoramento para garantir a qualidade das chamadas Enterprise Voice e das conferências A/V. O monitoramento é implantado em todos os servidores de front-ends, e o banco de dados de monitoramento é colocado com os servidores back-end. Também damos suporte a topologias nas quais o banco de dados de monitoramento está localizado em outro servidor.

  - **Alta disponibilidade do servidor de borda**    Neste exemplo, a organização com usuários do 20.000, apenas um servidor de borda seria suficiente para o desempenho. No entanto, há um pool de dois servidores de Borda implantados para fornecer alta disponibilidade.

  - **Opções de implantação de site de ramificação.**    A organização nessa topologia tem o Enterprise Voice implantado como sua solução de voz. O site de ramificação 1 não tem um link de rede de longa distância resistente para o site central, portanto, ele tem um aplicativo de ramificação sobreviventes implantado para manter muitos recursos do Lync Server, caso o link de WAN para o site central fique inativo. Já o Site de filial 2 tem um link de WAN resiliente e, portanto, requer apenas um gateway PSTN (rede telefônica pública comutada). Como o gateway PSTN implantado dá suporte para bypass de mídia, o Site de filial 2 não requer nenhum Servidor de Mediação. Para obter detalhes sobre como decidir o que implantar em um site de filial, consulte [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) na documentação de planejamento.

  - **Balanceamento de carga de DNS.**    O pool do front-end andEdge pool de servidores, com balanceamento de carga de DNS para tráfego SIP implantado. Isso elimina a necessidade de balanceadores de carga de hardware para os servidores de borda e reduz significativamente a configuração e a manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

  - **Implantação de UM do Exchange.** Esta topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Lync Server.
    
    Para obter detalhes sobre o Exchange UM, consulte [planejando a integração de Unificação de mensagens do Exchange no Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e integração de Unificação de [mensagens do Exchange no Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) na documentação de planejamento.

  - **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências. Para obter mais informações, consulte Configurando [a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Os servidores de borda são recomendados.**    Embora a implantação de um servidor de borda não seja necessária, recomendamos que ele para qualquer tamanho de implantação. Você pode maximizar o investimento do Lync Server implantando um servidor de borda para fornecer serviço para os usuários que estão fora de firewalls da sua organização. Veja alguns dos benefícios:
    
      - Os próprios usuários da sua organização podem usar a funcionalidade do Lync Server, se estiverem trabalhando em casa ou estiverem em trânsito.
    
      - Os usuários da sua organização poderão convidar outros usuários para reuniões.
    
      - Se você tiver um parceiro, fornecedor ou organização do cliente que também usa o Lync Server, você pode formar uma *relação federada* com essa organização. A implantação do Lync Server reconheceria os usuários dessa organização federada, levando a uma melhor colaboração.
    
      - Seus usuários podem trocar mensagens de chat com usuários de serviços públicos de mensagens de chat, incluindo qualquer um dos itens a seguir ou todos eles\!: Windows Live, AOL, Yahoo e Google Talk. Uma licença separada pode ser necessária para conectividade de IM pública com esses serviços.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
        > <LI>
        > <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
        > <LI>
        > <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>

        
        </div>

  - **Os directors podem ser adicionados.**    Se essa organização quisesse ajudar a aumentar a segurança contra ataques de negação de serviço, ele também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional separada no Lync Server que não hospeda contas de usuário nem fornece serviços de presença ou conferência. Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou o servidor primário do usuário. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a proteger servidores de front-end contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor.

  - **O System Center Operations Manager é recomendado.**   Recomendamos que você monitore a integridade da implantação do Lync Server para ajudar a garantir a disponibilidade do serviço para os usuários finais. Você pode monitorar o Lync com o pacote de gerenciamento do System Center Operations Manager para Lync que está disponível como um download gratuito da Microsoft. Com o pacote de gerenciamento do Lync, você pode obter alertas em tempo real em tempo real quando ocorrem problemas, executar transações sintéticas para testar a funcionalidade ponto a ponto do Lync, obter relatórios para a disponibilidade do serviço e assim por diante. This helps you to proactively respond to issues with your deployment before end-users experience them.

</div>

<span> </span>

</div>

</div>

</div>

