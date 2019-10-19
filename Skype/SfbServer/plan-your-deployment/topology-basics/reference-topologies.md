---
title: Topologias de referência para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologias de referência para o Skype for Business Server, incluindo diagramas e decisões para organizações grandes, médias e pequenas.
ms.openlocfilehash: 7f284b141da25175e3a41545349a0e61f6036019
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37028278"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologias de referência para o Skype for Business Server

Topologias de referência para o Skype for Business Server, incluindo diagramas e decisões para organizações grandes, médias e pequenas.

A melhor topologia do Skype for Business Server para você depende do tamanho da sua organização, das cargas de trabalho que você deseja implantar e de suas preferências de alta disponibilidade versus custo do investimento.

Esta seção descreve três exemplos de topologias de referência, incluindo o raciocínio por trás de muitas das decisões levadas em consideração em cada topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia de referência para organização de pequeno porte

A topologia de referência para pequenas organizações mostra como você pode implantar uma solução robusta e altamente disponível implantando apenas três servidores que executam o Skype for Business Server.

**Topologia de referência em pequenas organizações**

![Topologia de referência implantando três servidores diagrama](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implantados** Esta organização tem os usuários do 4.000 em seu site central. Eles implantaram dois servidores de edição padrão e emparelharam-os para permitir alta disponibilidade e recuperação de desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obter mais informações sobre alta disponibilidade e recursos de recuperação de desastre no Skype for Business Server, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **A implantação de um servidor de borda é recomendada.** Embora não seja necessário ter um servidor de borda para mensagens instantâneas internas, presença e conferência, nós o recomendamos até mesmo para pequenas implantações. Você pode maximizar seu investimento no Skype for Business Server implantando um servidor de borda para fornecer serviço para os usuários que estão fora dos firewalls da sua organização. Veja alguns dos benefícios:

  - Os próprios usuários da sua organização podem usar a funcionalidade do Skype for Business Server, se estiverem trabalhando em casa ou estiverem em trânsito.

  - Os usuários da sua organização poderão convidar outros usuários para reuniões.

  - Se você tiver uma organização de parceiro, fornecedor ou cliente que também usa o Skype for Business Server, você pode formar uma relação federada com essa organização. A implantação do Skype for Business Server reconhece os usuários da organização federada, que levava a melhor colaboração.

  - Os usuários da sua organização poderão trocar mensagens instantâneas com usuários de alguns serviços públicos de mensagens instantâneas.

- **Sobrevivência do site de filial.** Esta organização está executando um programa piloto do recurso Enterprise Voice do Skype for Business Server. Alguns usuários estão usando o Skype for Business Server como uma única solução de voz. Alguns desses usuários pilotos do Enterprise Voice estão localizados no site da filial. O site de filial não tem um link de rede de longa distância (WAN) confiável para o site central, para que um aparelho de ramificação sobreviventes seja implantado. Com essa implantação, mesmo que o link de WAN fique inativo, os usuários do site de filial ainda poderão fazer e receber chamadas (tanto chamadas dentro da organização quanto chamadas PSTN), contar com a funcionalidade de caixa postal e comunicar-se por mensagens instantâneas entre duas partes. Os usuários também poderão ser autenticados quando o link de WAN estiver indisponível. Para obter mais informações, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Implantação de UM do Exchange.** Esta topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia de referência para organização de médio porte

A topologia de referência com alta disponibilidade e um único data center é projetada para organizações de pequeno a médio porte com um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 20.000 usuários.

**Topologia de referência para organizações de médio porte**

![Topologia de referência para um único diagrama de data center](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Acomodar mais usuários com a adição de mais servidores front-end.** A topologia exata desse diagrama tem três servidores front-end para dar suporte a 20.000 usuários. Se tiver um único site central e mais usuários, você poderá simplesmente adicionar mais servidores front-end ao pool. O máximo de usuários por pool é 80.000, com doze servidores front-end.

    No entanto, a topologia de site único pode dar suporte a ainda mais usuários com a adição de outro pool de front-ends ao site.

- **O recurso de recuperação de desastres pode ser adicionado.** Para esta organização, a alta disponibilidade dos serviços do Skype for Business Server é um recurso necessário, mas a recuperação de desastres não é. O pool de servidores front-end que ele implantou fornece alta disponibilidade.

    Se quiser adicionar a capacidade de recuperação de desastres, a organização pode considerar estabelecer outro data center e adicionar outro pool de front-ends, emparelhando-o com o pool de front-ends no data center atual. Assim, caso um desastre afete o pool primário, os administradores poderão fazer o failover dos usuários no pool de backup.

- Os **servidores back-end são espelhados** Para fornecer mais disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de servidores de back-end para cada pool de front-ends.

- **Monitorando opções de banco de dados do servidor.** Esta organização implantou o monitoramento para garantir a qualidade das chamadas Enterprise Voice e das conferências A/V. O monitoramento é implantado em todos os servidores de front-ends, e o banco de dados de monitoramento é colocado com os servidores back-end. Também damos suporte a topologias nas quais o banco de dados de monitoramento está localizado em outro servidor.

- **Alta disponibilidade do servidor de borda** Neste exemplo, a organização com usuários do 20.000, apenas um servidor de borda seria suficiente para o desempenho. No entanto, há um pool de dois servidores de borda implantado para fornecer alta disponibilidade.

- **Opções de implantação de site de filiais.** A organização nessa topologia tem o Enterprise Voice implantado como sua solução de voz. O site de filial 1 não tem um link de rede de longa distância (WAN) resistente para o site central, portanto, ele tem um aparelho de ramificação sobreviventes implantado para manter muitos recursos do Skype for Business Server, caso o link de WAN para o site central fique inativo. Já o Site de filial 2 tem um link de WAN resiliente e, portanto, requer apenas um gateway PSTN (rede telefônica pública comutada). Como o gateway PSTN implantado dá suporte para bypass de mídia, o Site de filial 2 não requer nenhum Servidor de Mediação. Para obter mais informações, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Balanceamento de carga do DNS.** O pool de front-ends e o pool de servidores de borda têm balanceamento de carga do DNS para tráfego SIP implantado. Isso elimina a necessidade de balanceadores de carga de hardware para os servidores de borda e reduz significativamente a configuração e a manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter mais informações, consulte [balanceamento de carga de DNS](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implantação de UM do Exchange.** Esta topologia de referência inclui um servidor de UM (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

- **Os diretores podem ser adicionados.** Se quiser ajudar a aumentar a segurança contra ataques de negação de serviço, a organização também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional separada no Skype for Business Server que não conta contas de usuário, nem fornece serviços de presença ou conferência. Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou o servidor primário do usuário. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a proteger servidores de front-end contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor.

- **O System Center Operations Manager é recomendado.** Recomendamos que você monitore a integridade da implantação do Skype for Business Server para ajudar a garantir a disponibilidade do serviço para usuários finais. Você pode usar o pacote de gerenciamento do System Center Operations Manager para o Skype for Business que está disponível como um download gratuito da Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. Isso ajuda a responder com proatividade a problemas em sua implantação, antes que os usuários finais os percebam.

## <a name="reference-topology-for-a-large-organization"></a>Topologia de referência para organização de grande porte

A topologia de referência para uma organização de grande porte com suporte a vários data centers destina-se a organizações de todos os tamanhos que tenham mais de um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 50.000 usuários, sendo 20.000 usuários no Site central A, 20.000 no Site central B e 10.000 no Site central C e nos sites de filiais. O tipo de topologia mostrado neste diagrama pode acomodar organizações com qualquer número de usuários.

Além da alta disponibilidade fornecida por pools de servidores front-end, essa topologia adiciona suporte à recuperação de desastres. Os pools de front-ends nos sites centrais A e B estão combinados juntos. Se um desses pools ficar inativo, o administrador poderá mudar os serviços dos usuários afetados para o pool emparelhado no site não afetado.

Essa topologia é mostrada em vários diagramas, com uma visão geral seguida por exibições detalhadas dos sites centrais.

**Visão geral da topologia de referência para grandes organizações com vários data centers**

![Topologia de referência para vários data centers](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central A**

![Topology 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central B**

![Topology 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central C**

![Topology 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Os pools front-ends são emparelhados para permitir a recuperação de desastres.** Os pools de front-end no site A e no site B são emparelhados uns com os outros, para fornecer suporte à recuperação de desastres. Se o pool em um site falhar, o administrador poderá fazer failover dos usuários desse site para o pool de front-end emparelhado no outro site, com uma interrupção mínima de serviço para os usuários. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obter mais informações, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- Os **servidores back-end são espelhados** Para fornecer mais disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de servidores de back-end para cada pool de front-ends. Essa é uma topologia opcional, e você pode optar por implantar um único servidor back-end em vez disso. SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Usar o servidor Standard Edition em um site de filial.** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. Se ele foi implantado no Skype for Business Server como um site de filiais, a mídia dessas conferências seria executada na WAN (rede de longa distância) e em um site central que tenha um servidor front-end implantado. Para evitar essa carga de largura de banda potencial, ela instalou um par de servidores de edição padrão neste site, que hospedará essas conferências. E como os servidores de edição padrão são instalados, o Skype for Business Server, por definição, considera-o um site central, e ele é tratado como tal no construtor de topologias e na ferramenta de planejamento.

    Apenas um servidor de edição padrão seria suficiente para o desempenho aqui, mas a organização implantou dois e os emparelha juntos para fornecer alta disponibilidade em caso de um servidor ficar inativo.

    Embora o Site C seja considerado um site central, não é necessário implantar servidores de borda nele. Nesse exemplo, o Local C usa os Servidores de Borda implantados no Local A.

- **Monitoramento e arquivamento** Esta organização implantou o monitoramento e o arquivamento. Quando você implanta esses dois recursos, eles são executados em todos os servidores front-end. Os bancos de dados desses recursos podem ser colocados com o banco de dados back-end ou em outro servidor. Essa organização colocou esses bancos de dados em um servidor separado dos servidores back-end, no Site central B. Nesse caso, os bancos de dados recebem dados do monitoramento e arquivamento dos servidores front-end em todos os sites.

- **Opções de implantação de site de filiais.** Essa organização realmente tem mais de 50 sites de ramificação, apenas dois dos quais são exibidos nos diagramas detalhados. O site de ramificação 1 não tem um link de WAN resistente para o site central, portanto, eles têm aparelhos de ramificação sobreviventes implantados para fornecer serviço telefônico, caso o link de WAN para o site central fique inativo. No entanto, o site de filial 2 tem um link de rede de longa distância adaptável, portanto, ele precisa apenas de um gateway PSTN (rede telefônica pública comutada). Como o gateway PSTN implantado dá suporte para bypass de mídia, o Site de filial 2 não requer nenhum Servidor de Mediação. Para obter detalhes sobre como decidir o que instalar em um site de filial, consulte [planejar a resiliência do Enterprise Voice no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Tronco SIP e Servidor de Mediação.** Observe que no Site central B, o Servidor de Mediação não está colocado com os servidores front-end. Isso acontece porque recomenda-se usar um Servidor de Mediação independente para sites que usam o tronco SIP. Na maioria das demais instâncias, recomendamos colocar o Servidor de Mediação com o servidor front-end. Para obter mais informações sobre as topologias do Servidor de Mediação, consulte [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) na documentação de planejamento.

- **O chat persistente está implantado.** Essa organização implantou os servidores necessários para habilitar o chat persistente. Ela implantou vários servidores front-end de chat persistente para lidar com a carga do número de usuários no pool e proporcionar alta disponibilidade. Ela também implantou conformidade para chat persistente e colocou o repositório do chat persistente e o repositório de conformidade do chat persistente em servidores separados. Esses repositórios podem ser colocados e até mesmo colocados com o servidor back-end, mas a organização optou por separá-los para proporcionar desempenho melhor.

    > [!NOTE]
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.

- **Balanceamento de carga do DNS.** O pool de front-ends e o pool de servidores de borda usam balanceamento de carga do DNS. Isso elimina a necessidade de balanceadores de carga de hardware para a interface interna dos servidores de borda e reduz significativamente o tempo necessário para configuração e manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter mais informações, consulte (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implantação de UM do Exchange.** O Skype for Business Server funciona com implantações locais da Unificação de mensagens (UM) do Exchange e hospedadas do Exchange UM. Site central A inclui um servidor de um (Unificação de mensagens) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server. A funcionalidade de UM do Exchange para o Skype for Business Server é executada no pool de front-ends.

    O Site central B usa o Exchange hospedado. Portanto, a funcionalidade do servidor de UM do Exchange também é hospedada.

    Para obter detalhes sobre o Exchange UM, consulte [integração de Unificação de mensagens do Exchange local](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [integração de Unificação de mensagens do Exchange hospedada](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) na documentação de planejamento.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. Você pode implantar um único farm de servidores do Office Web Apps em um site que sirva tráfego de todos os sites ou implantá-lo em cada site. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

- **Os diretores podem ser adicionados.** Se quiser aumentar a segurança contra ataques de negação de serviço, a organização também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional separada no Skype for Business Server que não conta contas de usuário, nem fornece serviços de presença ou conferência. Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos. O diretor autentica as solicitações de entrada e as redireciona para o pool ou o servidor primário do usuário. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a proteger servidores de front-end contra tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor.

- **O System Center Operations Manager é recomendado.** Recomendamos que você monitore a integridade da implantação do Skype for Business Server para ajudar a garantir a disponibilidade do serviço para usuários finais. Você pode usar o pacote de gerenciamento do System Center Operations Manager para o Skype for Business que está disponível como um download gratuito da Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


