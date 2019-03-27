---
title: Topologias de referência do Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologias de referência do Skype para Business Server, incluindo diagramas e decisões a serem tomadas grande, médio e pequenas empresas.
ms.openlocfilehash: 6dd4c12d400408d284a21b55d983ba655bfd7bdd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895891"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologias de referência do Skype para Business Server

Topologias de referência do Skype para Business Server, incluindo diagramas e decisões a serem tomadas grande, médio e pequenas empresas.

O Skype recomendada para a topologia de servidor de negócios para você depende do tamanho da sua organização, das cargas de trabalho que você deseja implantar e das suas preferências de alta disponibilidade versus custo do investimento.

Esta seção descreve três exemplos de topologias de referência, incluindo o raciocínio por trás de muitas das decisões levadas em consideração em cada topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia de referência para organização de pequeno porte

A topologia de referência para pequenas organizações mostra como é possível implantar uma solução robusta, altamente disponível Implantando somente três servidores que executam o Skype para Business Server.

**Topologia de referência em pequenas organizações**

![Diagrama de três servidores de implantação da topologia de referência](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implantados** Esta organização tem 4.000 usuários em seu site central. Eles implantaram dois servidores Standard Edition e os pareou para habilitar a alta disponibilidade e recuperação de desastres. Each server homes 2,000 users, but information about all users is synchronized between the two servers. If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users. Para obter mais informações sobre a alta disponibilidade e recursos de recuperação de desastres do Skype para Business Server, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **A implantação de um servidor de borda é recomendada.** Embora não seja necessário ter um servidor de borda para mensagens instantâneas internas, presença e conferência, nós o recomendamos até mesmo para pequenas implantações. Você pode maximizar seu Skype de investimento Business Server Implantando um servidor de borda para oferecer serviço aos usuários atualmente fora dos firewalls da organização. Veja alguns dos benefícios:

  - Os usuários da organização podem usar Skype para a funcionalidade do servidor de negócios, caso ele estejam trabalhando de casa ou se estiverem na estrada.

  - Os usuários da sua organização poderão convidar outros usuários para reuniões.

  - Se você tiver um parceiro, fornecedor ou organização do cliente que também usa Skype para Business Server, é possível formar uma relação federada com essa organização. Sua Skype para implantação de servidor de negócios, em seguida, seria reconhece os usuários dessa organização federada, levando a melhor a colaboração.

  - Os usuários da sua organização poderão trocar mensagens instantâneas com usuários de alguns serviços públicos de mensagens instantâneas.

- **Sobrevivência do site de filial.** Esta organização está executando um programa piloto do recurso do Enterprise Voice do Skype para Business Server. Alguns usuários estão usando Skype para Business Server como sua solução exclusiva de voz. Alguns desses usuários piloto do Enterprise Voice estão localizados no site de filial. O site de filial não tem um link WAN (rede) de longa distância confiável para o site central, um aparelho de filial persistente é implantado lá. Com essa implantação, mesmo que o link de WAN fique inativo, os usuários do site de filial ainda poderão fazer e receber chamadas (tanto chamadas dentro da organização quanto chamadas PSTN), contar com a funcionalidade de caixa postal e comunicar-se por mensagens instantâneas entre duas partes. Os usuários também poderão ser autenticados quando o link de WAN estiver indisponível. Para obter mais informações, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Implantação de UM do Exchange.** Essa topologia de referência inclui um servidor Exchange Unified Messaging (UM), que executa o Microsoft Exchange Server, não Skype para Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia de referência para organização de médio porte

A topologia de referência com alta disponibilidade e um único data center é projetada para organizações de pequeno a médio porte com um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 20.000 usuários.

**Topologia de referência para organizações de médio porte**

![Topologia de referência para um único data center diagrama](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Acomodar mais usuários com a adição de mais servidores front-end.** A topologia exata desse diagrama tem três servidores front-end para dar suporte a 20.000 usuários. Se tiver um único site central e mais usuários, você poderá simplesmente adicionar mais servidores front-end ao pool. O máximo de usuários por pool é 80.000, com doze servidores front-end.

    No entanto, a topologia de site único pode dar suporte a ainda mais usuários com a adição de outro pool de front-ends ao site.

- **O recurso de recuperação de desastres pode ser adicionado.** Para esta organização, alta disponibilidade para seu Skype para serviços de Business Server é um recurso necessário, mas não é de recuperação de desastres. O pool de servidores Front-End que implantaram oferece alta disponibilidade.

    Se quiser adicionar a capacidade de recuperação de desastres, a organização pode considerar estabelecer outro data center e adicionar outro pool de front-ends, emparelhando-o com o pool de front-ends no data center atual. Assim, caso um desastre afete o pool primário, os administradores poderão fazer o failover dos usuários no pool de backup.

- **Servidores back-End são espelhados** Para fornecer mais alta disponibilidade de recursos de usuário básica, a organização implantou um par espelhado de servidores Back-End para cada pool de Front-End.

- **Monitorando opções de banco de dados do servidor.** Esta organização implantou o monitoramento para garantir a qualidade das chamadas do Enterprise Voice e uma / conferências V. O monitoramento é implantado em todos os servidores de front-ends, e o banco de dados de monitoramento é colocado com os servidores back-end. Também damos suporte a topologias nas quais o banco de dados de monitoramento está localizado em outro servidor.

- **Alta disponibilidade do servidor de borda** Este exemplo de organização com 20.000 usuários, apenas um servidor de borda seria suficiente para o desempenho. No entanto, há um pool de dois servidores de borda implantado para fornecer alta disponibilidade.

- **Opções de implantação de site de filiais.** A organização nessa topologia tiver implantado como sua solução de voz do Enterprise Voice. Site de filial 1 não tem um link WAN (rede) resiliente de longa distância no site central, para que ele tenha um aparelho de filial persistente implantados para manter que muitas Skype para recursos de Business Server caso o link da WAN no site central cair. Já o Site de filial 2 tem um link de WAN resiliente e, portanto, requer apenas um gateway PSTN (rede telefônica pública comutada). Como o gateway PSTN implantado dá suporte para bypass de mídia, o Site de filial 2 não requer nenhum Servidor de Mediação. Para obter mais informações, consulte [Plan for Enterprise Voice resiliency in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Balanceamento de carga do DNS.** O pool de front-ends e o pool de servidores de borda têm balanceamento de carga do DNS para tráfego SIP implantado. Isso elimina a necessidade de balanceadores de carga de hardware para os servidores de borda e reduz significativamente a configuração e a manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter mais informações, consulte (… /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implantação de UM do Exchange.** Essa topologia de referência inclui um servidor Exchange Unified Messaging (UM), que executa o Microsoft Exchange Server, não Skype para Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

- **Os diretores podem ser adicionados.** Se quiser ajudar a aumentar a segurança contra ataques de negação de serviço, a organização também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional, separado no Skype para servidor de negócios que não hospeda contas de usuário, ou fornecer serviços de presença ou conferência. Ela serve como um servidor de salto próximo interno para o qual um servidor de borda roteia o tráfego SIP de entrada destinado para servidores internos. O Diretor pré-autentica as solicitações de entrada e redireciona para o pool primário do usuário ou o servidor. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a isolar os servidores Front-End contra tráfego malicioso, como ataques (dos negação) de negação de serviço. Se a rede é inundada com o tráfego externo inválido nesse ataque, o tráfego termina no diretor.

- **Recomenda-se o System Center Operations Manager.** Recomendamos que você monitorar a integridade de seu Skype para implantação de servidor de negócios para ajudar a garantir a disponibilidade do serviço para usuários finais. Você pode usar o pacote de gerenciamento do System Center Operations Manager para Skype for Business que está disponível como um download gratuito da Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. Isso ajuda a responder com proatividade a problemas em sua implantação, antes que os usuários finais os percebam.

## <a name="reference-topology-for-a-large-organization"></a>Topologia de referência para organização de grande porte

A topologia de referência para uma organização de grande porte com suporte a vários data centers destina-se a organizações de todos os tamanhos que tenham mais de um site central. A topologia exata no diagrama a seguir destina-se a uma organização com 50.000 usuários, sendo 20.000 usuários no Site central A, 20.000 no Site central B e 10.000 no Site central C e nos sites de filiais. O tipo de topologia mostrado neste diagrama pode acomodar organizações com qualquer número de usuários.

Além de alta disponibilidade fornecida por pools de servidores Front-End, essa topologia adiciona suporte a recuperação de desastres. Os pools de Front-End em locais centrais A e B são combinados juntos. Se um desses pools ficar inativo, o administrador poderá mudar os serviços dos usuários afetados para o pool emparelhado no site não afetado.

Essa topologia é mostrada em vários diagramas, com uma visão geral seguida por exibições detalhadas dos sites centrais.

**Visão geral da topologia de referência para grandes organizações com vários data centers**

![Topologia de referência para vários data centers](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central A**

![Topologia 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central B**

![Topologia 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia de referência para grandes organizações: Visão detalhada do Local Central C**

![Topologia 3 e 4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Pools de Front-End são combinados para habilitar a recuperação de desastres.** Os pools de Front-End no Site A e B do Site estiver emparelhados com uns aos outros, para oferecer suporte à recuperação de desastres. Se o pool em um site falhar, o administrador pode realizar failover dos usuários do site para o pool de Front-End pareado em outro site, com um mínimo de interrupção do serviço para os usuários. Each of these two Front End pools has six servers, which is enough for all 40,000 users in both pools in case of failover. Para obter mais informações, consulte o [plano de alta disponibilidade e recuperação de desastres em Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

- **Servidores back-End são espelhados** Para fornecer mais alta disponibilidade de recursos de usuário básica, a organização implantou um par espelhado de servidores Back-End para cada pool de Front-End. Isso é uma topologia opcional e você pode optar por implantar um único servidor Back-End em vez disso. SQL clustering and AlwaysOn Availability groups are also supported. For more information, see [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Usando o servidor Standard Edition em um site de filial.** This organization considers Site C as a branch site because it has only 600 employees. However, the users there have many A/V conferences among themselves. Se ela foi implantada no Skype para Business Server como um site de filial, a mídia para essas conferências seria executado através da rede de longa distância (WAN) de e para um site central que tenha um servidor Front-End implantado. Para evitar essa carga potencial de largura de banda, eles instalou um par de servidores Standard Edition neste site, que irá hospedar essas conferências. E porque os servidores Standard Edition são instalados lá, Skype para Business Server, por definição, o considera um site central, e ela será tratada como tal, no construtor de topologias e ferramenta de planejamento.

    Apenas um servidor Standard Edition seria o suficiente para o desempenho aqui, mas a organização tem implantou dois e os pareou para fornecer alta disponibilidade em caso de um servidor cair.

    Embora o Site C seja considerado um site central, não é necessário implantar servidores de borda nele. Nesse exemplo, o Local C usa os Servidores de Borda implantados no Local A.

- **Monitoramento e arquivamento** Esta organização implantou o monitoramento e arquivamento. Quando você implanta esses dois recursos, eles são executados em todos os servidores front-end. Os bancos de dados desses recursos podem ser colocados com o banco de dados back-end ou em outro servidor. Essa organização colocou esses bancos de dados em um servidor separado dos servidores back-end, no Site central B. Nesse caso, os bancos de dados recebem dados do monitoramento e arquivamento dos servidores front-end em todos os sites.

- **Opções de implantação de site de filiais.** Esta organização realmente tem mais de 50 sites de filiais, apenas dois dos quais são mostradas nos diagramas a detalhadas. Site de filial 1 não tem uma WAN resiliente link para o site central, para que eles tenham implantado para fornecer serviços telefônicos caso o link da WAN no site central cair de aparelhos de filial persistente. No entanto, o Site de filial 2 possui um link WAN resistente, então ele precisa de apenas um gateway PSTN (rede) telefônica pública comutada. Como o gateway PSTN implantado dá suporte para bypass de mídia, o Site de filial 2 não requer nenhum Servidor de Mediação. Para obter detalhes sobre como decidir o que instalar em um site de filial, consulte [Planejar a resiliência do Enterprise Voice em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md).

- **Tronco SIP e Servidor de Mediação.** Observe que no Site central B, o Servidor de Mediação não está colocado com os servidores front-end. Isso acontece porque recomenda-se usar um Servidor de Mediação independente para sites que usam o tronco SIP. Na maioria das demais instâncias, recomendamos colocar o Servidor de Mediação com o servidor front-end. Para obter mais informações sobre as topologias do Servidor de Mediação, consulte [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) na documentação de planejamento.

- **O chat persistente está implantado.** Essa organização implantou os servidores necessários para habilitar o chat persistente. Ela implantou vários servidores front-end de chat persistente para lidar com a carga do número de usuários no pool e proporcionar alta disponibilidade. Ela também implantou conformidade para chat persistente e colocou o repositório do chat persistente e o repositório de conformidade do chat persistente em servidores separados. Esses repositórios podem ser colocados e até mesmo colocados com o servidor back-end, mas a organização optou por separá-los para proporcionar desempenho melhor.

    > [!NOTE]
    > Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.

- **Balanceamento de carga do DNS.** O pool de front-ends e o pool de servidores de borda usam balanceamento de carga do DNS. Isso elimina a necessidade de balanceadores de carga de hardware para a interface interna dos servidores de borda e reduz significativamente o tempo necessário para configuração e manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter mais informações, consulte (… /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implantação de UM do Exchange.** Skype para Business Server funciona com ambas as implantações em instalações do Exchange Unified Messaging (UM) e Exchange hospedado. Site central A inclui um servidor Exchange Unified Messaging (UM), que executa o Microsoft Exchange Server, não Skype para Business Server. A funcionalidade de UM do Exchange para Skype para Business Server executa no pool Front-End.

    O Site central B usa o Exchange hospedado. Portanto, a funcionalidade do servidor de UM do Exchange também é hospedada.

    Para obter detalhes sobre UM do Exchange, consulte [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [Hosted Exchange Unified Messaging Integration](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) na documentação de planejamento.

- **Servidor do Office Web Apps.** Recomendamos implantar um servidor ou farm de servidores do Office Web Apps em todas as organizações que usem webconferência. Você pode implantar um único farm do Office Web Apps Server em um site que serve o tráfego de todos os sites ou implantá-lo em cada site. O servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferências.

- **Os diretores podem ser adicionados.** Se quiser aumentar a segurança contra ataques de negação de serviço, a organização também pode implantar um pool de diretores. Um diretor é uma função de servidor opcional, separado no Skype para servidor de negócios que não hospeda contas de usuário, ou fornecer serviços de presença ou conferência. Ela serve como um servidor de salto próximo interno para o qual um servidor de borda roteia o tráfego SIP de entrada destinado para servidores internos. O Diretor pré-autentica as solicitações de entrada e redireciona para o pool primário do usuário ou o servidor. A pré-autenticação no diretor permite descartar solicitações de contas de usuário desconhecidas para implantação. Um diretor ajuda a isolar os servidores Front-End contra tráfego malicioso, como ataques (dos negação) de negação de serviço. Se a rede é inundada com o tráfego externo inválido nesse ataque, o tráfego termina no diretor.

- **Recomenda-se o System Center Operations Manager.** Recomendamos que você monitorar a integridade de seu Skype para implantação de servidor de negócios para ajudar a garantir a disponibilidade do serviço para usuários finais. Você pode usar o pacote de gerenciamento do System Center Operations Manager para Skype for Business que está disponível como um download gratuito da Microsoft. With the Skype for Business Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Skype for Business functionality, get reports for service availability, and so on. This helps you to proactively respond to issues with your deployment before end-users experience them.


