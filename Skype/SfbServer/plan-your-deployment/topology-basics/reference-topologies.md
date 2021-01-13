---
title: Topologias de referência do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
description: Topologias de referência do Skype for Business Server, incluindo diagramas e decisões a tomar para grandes, médias e pequenas organizações.
ms.openlocfilehash: 958f6630faf295a16aebe7513ee9e5c98daeeaa5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831731"
---
# <a name="reference-topologies-for-skype-for-business-server"></a>Topologias de referência do Skype for Business Server

Topologias de referência do Skype for Business Server, incluindo diagramas e decisões a tomar para grandes, médias e pequenas organizações.

A melhor topologia do Skype for Business Server para você depende do tamanho da sua organização, das cargas de trabalho que você deseja implantar e das suas preferências de alta disponibilidade versus custo de investimento.

Esta seção descreve três topologias de referência de exemplo, incluindo o raciocínio por trás de muitas das decisões que foram fatoradas em cada topologia.

## <a name="reference-topology-for-a-small-organization"></a>Topologia de referência para uma organização pequena

A topologia de referência para pequenas organizações mostra como você pode implantar uma solução robusta e altamente disponível implantando apenas três servidores executando o Skype for Business Server.

**Topologia de referência para pequenas organizações**

![Topologia de referência implantando diagrama de três servidores](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology1.jpg)

- **Par de servidores Standard Edition implantados** Essa organização tem 4.000 usuários em seu site central. Eles implantaram dois servidores Standard Edition e os emparelham para habilitar a alta disponibilidade e a recuperação de desastres. Cada servidor tem 2.000 usuários, mas as informações sobre todos os usuários são sincronizadas entre os dois servidores. Se um falhar, um administrador poderá fazer fail over desses usuários para ser servido pelo outro servidor, com um mínimo de interrupção para os usuários. Para obter mais informações sobre recursos de alta disponibilidade e recuperação de desastres no Skype for Business Server, consulte Plano para alta disponibilidade e recuperação de desastres [no Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **A implantação de um Servidor de Borda é recomendada.** Embora não seja necessário ter um Servidor de Borda para IM, presença e conferência, nós o recomendamos até mesmo para pequenas implantações. Você pode maximizar o investimento do Skype for Business Server implantando um Servidor de Borda para fornecer serviço aos usuários que estão fora dos firewalls da sua organização. Os benefícios são os seguintes:

  - Os usuários da sua própria organização podem usar a funcionalidade do Skype for Business Server, se eles estão trabalhando em casa ou na estrada.

  - Seus usuários podem convidar usuários de fora para participar de reuniões.

  - Se você tiver uma organização parceira, fornecedora ou cliente que também use o Skype for Business Server, poderá formar um relacionamento federado com essa organização. Sua implantação do Skype for Business Server reconheceria os usuários dessa organização federada, levando a uma melhor colaboração.

  - Seus usuários podem trocar mensagens instantâneas com usuários de alguns serviços públicos de IM.

- **Sobrevivência do site filial.** Esta organização está executando um programa piloto do recurso Enterprise Voice do Skype for Business Server. Alguns usuários estão usando o Skype for Business Server como única solução de voz. Alguns desses usuários piloto do Enterprise Voice estão localizados no site de filial. O site de filial não tem um link confiável de rede de área ampla (WAN) para o site central, portanto, um Aparelho de Filial Confiável é implantado lá. Com isso implantado, se o link WAN cair, os usuários no site de filial ainda poderão fazer e receber chamadas (tanto chamadas dentro da organização quanto chamadas PSTN), ter funcionalidade de caixa postal e se comunicar com mensagens instantâneas (IM) de duas partes. Os usuários ainda podem ser autenticados quando um link WAN estiver indisponível. Para obter mais informações, [consulte Plano para resiliência](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)do Enterprise Voice no Skype for Business Server.

- **Implantação do Exchange do UM.** Essa topologia de referência inclui um Servidor de Unificação de Mensagens (UM) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um Servidor do Office Web Apps ou um farm do Servidor do Office Web Apps em todas as organizações que usam webconferência. O Servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferência.

## <a name="reference-topology-for-a-medium-organization"></a>Topologia de referência para uma organização média

A topologia de referência com alta disponibilidade e um único data center é projetada para uma organização de pequeno a médio porte com um local central. A topologia exata no diagrama a seguir é para uma organização de 20.000 usuários.

**Topologia de referência para organizações de médio porte**

![Topologia de referência para diagrama de data center único](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology2.jpg)

- **Acomodar mais usuários, adicionando mais Servidores Front-End.** A topologia exata neste diagrama tem três Servidores front-end para dar suporte a 20.000 usuários. Se você tiver um único site central e mais usuários, basta adicionar mais Servidores Front End ao pool. O número máximo de usuários por pool é 80.000, com doze Servidores Front-End.

    No entanto, a topologia de site único pode dar suporte a mais usuários adicionando outro pool de Front-End ao site.

- **A Recuperação de Desastre pode ser adicionada.** Para essa organização, a alta disponibilidade dos serviços do Skype for Business Server é um recurso necessário, mas a recuperação de desastres não é. O pool de Servidores front-end implantado fornece alta disponibilidade.

    Se quiser adicionar a capacidade de recuperação de desastres, considere estabelecer outro datacenter e adicionar outro pool de Front-End e emparelhá-lo com o pool de Front-End em seu datacenter atual. Em seguida, se houver um desastre que afete seu pool primário, os administradores poderão fazer fail over de usuários para o pool de backup.

- **Servidores back-end são espelhados** Para fornecer mais alta disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de Servidores back-end para cada pool de Front-End.

- **Opções de banco de dados do Monitoring Server.** Essa organização implantou o Monitoramento para garantir a qualidade das chamadas do Enterprise Voice e conferências A/V. O monitoramento é implantado em todos os Servidores Front-End e o banco de dados de Monitoramento é alocado com os Servidores back-end. Também damos suporte a topologias nas quais o banco de dados de Monitoramento está localizado em um servidor separado.

- **Alta disponibilidade do Servidor de Borda** Nesta organização de exemplo com 20.000 usuários, apenas um Servidor de Borda seria suficiente para o desempenho. No entanto, eles implantaram um pool de dois Servidores de Borda implantados para fornecer alta disponibilidade.

- **Opções de implantação de site de filiais.** A organização nesta topologia tem o Enterprise Voice implantado como sua solução de voz. O Site de Filial 1 não tem um link wan (rede de área ampla) resiliente para o site central, portanto, ele tem um Aparelho de Filial Persistente implantado para manter muitos recursos do Skype for Business Server caso o link WAN para o site central cai. No entanto, o Site de Filial 2 tem um link WAN resiliente, portanto, apenas um gateway PSTN (rede telefônica pública comutada) é necessário. O gateway PSTN implantado tem suporte para bypass de mídia, portanto, nenhum Servidor de Mediação é necessário na Filial 2. Para obter mais informações, [consulte Plano para resiliência](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)do Enterprise Voice no Skype for Business Server.

- **Balanceamento de carga do DNS.** O pool de Front-End e o pool de Servidores de Borda têm balanceamento de carga DNS para tráfego SIP implantado. Isso elimina a necessidade de balanceadores de carga de hardware para os Servidores de Borda e reduz significativamente a configuração e a manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários somente para tráfego HTTP. Para obter mais informações, consulte [balanceamento de carga DNS.](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)

- **Implantação do Exchange do UM.** Essa topologia de referência inclui um Servidor de Unificação de Mensagens (UM) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server.

- **Servidor do Office Web Apps.** Recomendamos implantar um Servidor do Office Web Apps ou um farm do Servidor do Office Web Apps em todas as organizações que usam webconferência. O Servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferência.

- **Os Diretores podem ser adicionados.** Se essa organização quisesse ajudar a aumentar a segurança contra ataques de negação de serviço, ela também poderia implantar um pool de Diretores. Um Diretor é uma função de servidor separada e opcional no Skype for Business Server que não home contas de usuário, ou fornece serviços de presença ou conferência. Ele serve como um servidor de próximo salto interno para o qual um Servidor de Borda encaminha o tráfego SIP de entrada destinado a servidores internos. O Diretor pré-autentica solicitações de entrada e as redireciona para o pool ou servidor principal do usuário. A pré-autenticação no Diretor permite o cancelamento de solicitações de contas de usuário desconhecidas para a implantação. Um Diretor ajuda a isolar servidores front-end de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido em tal ataque, o tráfego terminará no Diretor.

- **O System Center Operations Manager é recomendado.** Recomendamos que você monitore a saúde da implantação do Skype for Business Server para ajudar a garantir a disponibilidade do serviço para os usuários finais. Você pode usar o Pacote de Gerenciamento do System Center Operations Manager para Skype for Business que está disponível como download gratuito da Microsoft. Com o Pacote de Gerenciamento do Skype for Business, você pode receber alertas proativamente em tempo real quando ocorrerem problemas, executar transações sintéticas para testar a funcionalidade do Skype for Business de ponta a ponta, obter relatórios de disponibilidade do serviço e assim por diante. Isso ajuda você a responder proativamente a problemas com sua implantação antes que os usuários finais os experimentem.

## <a name="reference-topology-for-a-large-organization"></a>Topologia de referência para uma grande organização

A topologia de referência para uma organização de grande porte com suporte a vários data centers é para qualquer tamanho de organização com mais de um site central. A topologia exata no diagrama a seguir é para uma organização de 50.000 usuários, com 20.000 usuários no Site Central A, 20.000 no Site Central B e um total de 10.000 no Site Central C e em sites de filial. O tipo de topologia mostrado neste diagrama pode acomodar organizações com qualquer número de usuários.

Além da alta disponibilidade fornecida pelos pools de Servidores Front-End, essa topologia adiciona suporte à recuperação de desastres. Os pools de Front-End nos Sites Centrais A e B são emparelhados. Se um desses pools cair, o administrador pode transferir os serviços dos usuários afetados para o pool emparelhado no site não afetado.

Essa topologia é mostrada em vários diagramas, com uma visão geral seguida de visualizações detalhadas dos sites centrais.

**Visão geral da topologia de referência para grandes organizações com vários data centers**

![Topologia de referência para vários data centers](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-1-new.jpg)

**Topologia de referência para grandes organizações: Exibição detalhada do Site Central A**

![Topologia 3-2](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-2.jpg)

**Topologia de referência para grandes organizações: Exibição detalhada do Site Central B**

![Topologia 3-3](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-3.jpg)

**Topologia de referência para grandes organizações: Exibição detalhada do Site Central C**

![Topologia 3-4](../../media/LyncServer2013_Planning_ReferenceTopologies_Topology3-4.jpg)

- **Os pools de front-end são emparelhados para habilitar a recuperação de desastres.** Os pools de Front-End no Site A e no Site B são emparelhados uns com os outros para oferecer suporte à recuperação de desastres. Se o pool em um site falhar, o administrador poderá fazer o fail over dos usuários desse site para o pool de Front-End emparelhado no outro site, com um mínimo de interrupção de serviço para os usuários. Cada um desses dois pools de Front End tem seis servidores, o que é suficiente para todos os 40.000 usuários em ambos os pools em caso de failover. Para obter mais informações, [consulte Plano para alta disponibilidade e recuperação de desastre no Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)

- **Servidores back-end são espelhados** Para fornecer mais alta disponibilidade para recursos básicos do usuário, a organização implantou um par espelhado de Servidores back-end para cada pool de Front-End. Essa é uma topologia opcional e, em vez disso, você pode optar por implantar um único Servidor back-end. Grupos de cluster SQL e Disponibilidade AlwaysOn também são suportados. Para obter mais informações, consulte [Back End Server high availability in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

- **Usando o servidor Standard Edition em um site de filial.** Essa organização considera o Site C como um site de filial porque tem apenas 600 funcionários. No entanto, os usuários de lá têm muitas conferências A/V entre si. Se ele foi implantado no Skype for Business Server como um site de filial, a mídia dessas conferências seria executado em toda a wan (rede de área ampla) para e de um site central que tenha um Servidor front-end implantado. Para evitar essa carga de largura de banda potencial, eles instalaram um par de servidores Standard Edition neste site, que hospedará essas conferências. E como os servidores Standard Edition estão instalados lá, o Skype for Business Server por definição o considera um site central e é tratado como tal no Construtor de Topologias e na Ferramenta de Planejamento.

    Apenas um servidor Standard Edition seria suficiente para o desempenho aqui, mas a organização implantou dois e os emparelhou para fornecer alta disponibilidade caso um servidor pare.

    Embora o Site C seja considerado um site central, você não precisa implantar Servidores de Borda lá. Neste exemplo, o Site C usará os Servidores de Borda implantados no Site A.

- **Monitoramento e arquivamento** Essa organização implantou o monitoramento e o arquivamento. Quando você implanta o Monitoramento ou Arquivamento, ele é executado em todos os Servidores Front-End. Os bancos de dados desses recursos podem ser alocados com o banco de dados back-end ou localizados em um servidor separado. Essa organização localizou esses bancos de dados em um servidor separado dos Servidores back-end, no Site Central B. Os bancos de dados aqui recebem dados de Monitoramento e Arquivamento dos Servidores Front-End em todos os sites.

- **Opções de implantação de site de filiais.** Na verdade, essa organização tem mais de 50 sites de filial, apenas dois deles são mostrados nos diagramas detalhados. O Site de Filial 1 não tem um link WAN resiliente para o site central, portanto, eles têm Aparelhos de Filial Persistente implantados para fornecer serviço telefônico caso o link WAN para o site central cai. No entanto, o Site de Filial 2 tem um link WAN resiliente, portanto, ele precisa apenas de um gateway PSTN (rede telefônica pública comutado). O gateway PSTN implantado tem suporte para bypass de mídia, portanto, nenhum Servidor de Mediação é necessário na Filial 2. Para obter detalhes sobre como decidir o que instalar em um site de filial, consulte Plano de resiliência do [Enterprise Voice no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-resiliency.md)

- **Tronco SIP e Servidor de Mediação.** Observe que, no Local Central B, o Servidor de Mediação não está alocado com os Servidores Front-End. Isso porque o Servidor de Mediação autônomo é recomendado para sites que usam tronco SIP. Na maioria das outras instâncias, recomendamos que você collocate o Servidor de Mediação com o Servidor Front-End. Para obter detalhes sobre topologias do Servidor de Mediação, consulte [Components and Topologies for Mediation Server](https://technet.microsoft.com/library/71397168-36c3-4d21-b8ef-db6a751634ee.aspx) in the Planning documentation.

- **O Chat Persistente é Implantado.** Essa organização implantou os servidores necessários para habilitar o Chat Persistente. Ele implantou vários Servidores Front End de Chat Persistente para lidar com a carga do número de usuários no pool e para fornecer alta disponibilidade. Ele também implantou a Conformidade para Chat Persistente e localizou o Armazenamento de Chat Persistente e o Armazenamento de Conformidade de Chat Persistente em servidores separados. Esses armazenamentos podem ser alocados e até mesmo podem ser alocados com o Servidor back-end, mas essa organização optou por separá-los para oferecer melhor desempenho.

    > [!NOTE]
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

- **Balanceamento de carga do DNS.** O pool de Front End e o pool do Servidor de Borda usam o balanceamento de carga DNS. Isso elimina a necessidade de balanceadores de carga de hardware para a interface interna dos Servidores de Borda e diminui significativamente o tempo que você precisa gastar na instalação e manutenção dos balanceadores de carga de hardware para os outros pools, pois os balanceadores de carga de hardware são necessários apenas para tráfego HTTP. Para obter mais informações, consulte (.. /.. /plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing).

- **Implantação do Exchange do UM.** O Skype for Business Server funciona com implantações locais da Unificação de Mensagens (UM) do Exchange e do UM do Exchange hospedado. O Site Central A inclui um Servidor de Unificação de Mensagens (UM) do Exchange, que executa o Microsoft Exchange Server, não o Skype for Business Server. A funcionalidade de UM do Exchange para o Skype for Business Server é executado no pool de Front-End.

    O Site Central B usa o Exchange hospedado, portanto, a funcionalidade do Exchange UM Server também é hospedada.

    Para obter detalhes sobre a UM do Exchange, consulte [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Hosted Exchange Unified Messaging Integration](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx) in the Planning documentation.

- **Servidor do Office Web Apps.** Recomendamos implantar um Servidor do Office Web Apps ou um farm do Servidor do Office Web Apps em todas as organizações que usam webconferência. Você pode implantar um único farm do Servidor do Office Web Apps em um site que atende ao tráfego de todos os sites ou implantá-lo em cada site. O Servidor do Office Web Apps possibilita a apresentação de slides do PowerPoint em webconferência.

- **Os Diretores podem ser adicionados.** Se essa organização quisesse aumentar a segurança contra ataques de negação de serviço, ela também poderia implantar um pool de Diretores. Um Diretor é uma função de servidor separada e opcional no Skype for Business Server que não home contas de usuário, ou fornece serviços de presença ou conferência. Ele serve como um servidor de próximo salto interno para o qual um Servidor de Borda encaminha o tráfego SIP de entrada destinado a servidores internos. O Diretor pré-autentica solicitações de entrada e as redireciona para o pool ou servidor principal do usuário. A pré-autenticação no Diretor permite o cancelamento de solicitações de contas de usuário desconhecidas para a implantação. Um Diretor ajuda a isolar servidores front-end de tráfego mal-intencionado, como ataques de negação de serviço (DoS). Se a rede estiver inundada com tráfego externo inválido em tal ataque, o tráfego terminará no Diretor.

- **O System Center Operations Manager é recomendado.** Recomendamos que você monitore a saúde da implantação do Skype for Business Server para ajudar a garantir a disponibilidade do serviço para os usuários finais. Você pode usar o Pacote de Gerenciamento do System Center Operations Manager para Skype for Business que está disponível como download gratuito da Microsoft. Com o Pacote de Gerenciamento do Skype for Business, você pode receber alertas proativamente em tempo real quando ocorrerem problemas, executar transações sintéticas para testar a funcionalidade do Skype for Business de ponta a ponta, obter relatórios de disponibilidade do serviço e assim por diante. Isso ajuda você a responder proativamente a problemas com sua implantação antes que os usuários finais os experimentem.


