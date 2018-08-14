---
title: Planejar o gerenciamento de serviço e qualidade - Teams da Microsoft
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Use estas diretrizes para saber mais sobre os requisitos necessários para entregar e manter uma implantação do Microsoft Teams de alta qualidade.
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0050834f55568a6a747d84e8efdffb3e898d226
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "20398025"
---
![Estágios da atualização jornada, com ênfase na etapa de preparação técnica] (media/upgrade-banner-tech-readiness.png "Estágios da atualização jornada, com ênfase na etapa de preparação técnica")

Este artigo faz parte do estágio de prontidão técnica de sua atualização jornada, uma atividade que você concluir em paralelo com o estágio de preparação do usuário. Antes de continuar, confirme que você tiver concluído essas atividades desde estágios anteriores:

-   [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolhido sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->
# <a name="plan-for-quality"></a>Planejar a qualidade

Se você estiver implantando o áudio, vídeo ou reuniões, você pode executar algumas etapas adicionais para aperfeiçoar seu ambiente para essa funcionalidade. Esse conteúdo fornecerá uma visão geral dos requisitos necessários entregar e manter uma implantação do Microsoft Teams de alta qualidade. Você pode ajudar a garantir uma implantação bem-sucedida pelo planejamento de gerenciamento de serviço e a qualidade, antes da sua implantação piloto ou de produção primeira.

A orientação é organizada nas seguintes seções:

-   Primeiro, é uma visão geral da experiência do usuário e os principais componentes que são a base de qualidade. Isso realça as áreas para focalizar em antes da inclusão a Microsoft Teams.

-   Em segundo lugar, orientação é fornecida para o planejamento de um modelo de suporte para gerenciar o Microsoft Teams antes da implantação de produção ou piloto de usuário primeira. Esta seção descreve as tarefas que precisam ser executadas regularmente para manter uma implantação de equipes de alta qualidade. Além disso, esta seção apresenta orientação adicional que você pode usar para iniciar a compreensão e operacionalização essas tarefas.

-   Orientação de terceira, específica ajuda a planejar sua rede e pontos de extremidade em sua organização para oferecer suporte a Teams da Microsoft.

-   Por fim, próximas etapas estão resumidas com referências aos conteúdo relacionado.

## <a name="key-technical-components-that-affect-user-experience"></a>Os principais componentes técnicos que afetam a experiência do usuário

Os principais componentes técnicos que afetam a experiência do usuário serão revisados nesta seção. Antes de examinar os principais componentes, é importante que você compreenda a experiência do usuário e sua importância na percebendo metas de negócios da sua organização. Vamos analisar como podemos definem a experiência do usuário pela primeira vez.

### <a name="user-experience-defined"></a>Experiência do usuário definida

Metas de negócios podem ser obtidas quando você implanta o Microsoft Teams e quando os usuários adotarem equipes como sua solução de colaboração e comunicação de núcleo. Qualidade pode ajudar a garantir uma experiência de usuário positivo, um atributo-chave no orientando a adoção e uso. Por fornecer um serviço de alta qualidade que delights pessoas, indivíduos e equipes podem ganhar confiança e encontre novas e inovadores maneiras de usar o serviço que benefícios comerciais de unidade.

No Centro de esta é a experiência do usuário com equipes — emoções e posturas em direção o serviço da pessoa. Portanto, o que contribui para a experiência do usuário? Ele varia dos usuários saber como e por que usar equipes e incorporá-lo em seu fluxo de trabalho diário experimentando uma qualidade de chamada excepcionais e poder conectar confiável, independentemente de onde estejam. Experiência do usuário é muito ampla de natureza temporária; Este artigo foca somente aqueles elementos técnicos que podem ser controlados pela sua organização. Informações adicionais sobre a preparação do usuário podem ser encontradas em [Prepare sua organização para equipes](https://aka.ms/SkypeToTeams-UserReadiness).

Há requisitos específicos à implantação que são extremamente importantes para proporcionar uma experiência de usuário fantástico — especialmente quando usando a voz nuvem recursos no aplicativo de equipes. É essencial para tratar Teams Microsoft como um cidadãos de primeira classe com outros investimentos de comunicação e colaboração, priorização de tráfego em tempo real adequadamente. A seção a seguir oferece uma visão geral dos principais componentes que afetam a experiência do usuário. Ainda mais seções, podemos fornecerá orientações sobre como começar a planejar, implantar e manter os principais componentes que compõem a qualidade.

### <a name="key-components-of-quality"></a>Principais componentes de qualidade

Uma organização ou um parceiro de suporte deve começar a planejar três componentes principais durante a fase de preparação técnica de uma implantação de equipes: gerenciamento, rede e pontos de extremidade de serviço. A combinação de todos os três áreas é fundamental para a qualidade da experiência do usuário.

![Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes.] (media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes.")

#### <a name="service-management"></a>Gerenciamento de serviço

Gerenciamento de serviço pode ser dividido em duas categorias distintas de responsabilidade:

-   **Responsabilidade da Microsoft**. Microsoft é responsável pelos componentes de infraestrutura que compõe o serviço Office 365. Microsoft é responsável aos clientes para assegurar que qualquer um dos seus usuários conectando-se às equipes é fornecido com uma experiência confiável e de alta qualidade.

-   **Responsabilidade do cliente**. Você e sua organização são responsáveis pelo gerenciamento dos vários aspectos do serviço do Office 365, rede local e pontos de extremidade do usuário. Por exemplo, como novos endereços IP são adicionados ao Office 365, você deve atualizar os firewalls apropriados para permitir a comunicação com os novos pontos de extremidade para evitar interrupções do usuário.

Para obter orientações detalhadas para o planejamento de gerenciamento de serviço, consulte [Planejar o gerenciamento de serviço](#plan-for-service-management).

#### <a name="network"></a>Rede 

Na maioria das organizações, redes inicialmente foram projetados para fornecer acesso aos dados e aplicativos que estava instalado em seus centros de dados. Aplicativos baseados em nuvem, como o Office 365 exigem alterações nessas redes para dar suporte os novos fluxos de dados e de acesso requer equipes. Para poder habilitar usuários para equipes em sua organização, você deve avaliar e otimizar sua rede atual. Isso é extremamente importante quando aproveitando os recursos de voz de nuvem.

Em redes tradicionais, os usuários precisarão percorrer as redes de perímetro de uma organização para acessar as equipes. Muitas organizações terão a dispositivos baseados no segurança como VPNs que podem bloquear, impedem ou fornecer um caminho não otimizado para tráfego de rede, firewalls e servidores proxy.

Além disso, as redes internas de núcleo precisam ser otimizada e adequados para fornecer qualidade e capacidade suficiente para dar suporte as cargas de trabalho de equipes, incluindo mídia em tempo real. Você pode usar o planejamento, correção, de largura de banda e otimização para ajudar a garantir a sua rede fornece um caminho de alta qualidade e eficiente para o Office 365.

Para obter orientações detalhadas sobre o planejamento de rede, consulte [Planejar a qualidade da rede](#plan-for-network-quality).

#### <a name="endpoints"></a>Pontos de extremidade

Microsoft Teams suporta uma variedade de pontos de extremidade. De PCs para tablets aos telefones, você pode acessar as equipes em qualquer lugar de praticamente qualquer dispositivo.

Para oferecer a melhor experiência de seus usuários possíveis, você precisa considerar estes aspectos importantes: faça seus pontos de extremidade atendem aos requisitos de hardware e software de equipes? Você configurada e otimizada de pontos de extremidade para oferecer suporte a redes Wi-Fi? Os dispositivos que você usará para fazer e receber chamadas de voz? Esses dispositivos otimizados para equipes?

Para obter orientações detalhadas sobre o planejamento de ponto de extremidade, consulte [Planejar a qualidade do ponto de extremidade](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Planejar o gerenciamento de serviço

Gerenciamento de serviço é um tópico amplo que cobre as operações diárias do serviço Microsoft Teams depois que ele tenha sido implantado e habilitado para usuários. O serviço de equipes engloba Microsoft Office 365 e os componentes de infraestrutura que são implantados no local (por exemplo, de rede).

A noção do gerenciamento de serviços não mais provável é um novo conceito na maioria das organizações. Você provavelmente já implementou processos e as tarefas associadas com serviços existentes. Além disso, você provavelmente pode aumentar o que você tenha em mãos quando você planejar gerenciamento de serviço de hoje a suporte Teams da Microsoft no futuro.

Gerenciamento de serviço abrange todas as atividades e processos envolvidos no gerenciamento Teams de ponta a ponta da Microsoft. Conforme descrito anteriormente, alguns componentes do gerenciamento de serviços — os componentes de infraestrutura que compõe o próprio serviço Office 365 — são responsabilidade da Microsoft, enquanto o cliente é responsável a seus usuários para gerenciar os vários aspectos de equipes, o rede e pontos de extremidade que eles oferecem. Esta seção do documento abordará responsabilidade do cliente de uma perspectiva de gerenciamento de serviço.

![Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco no gerenciamento de serviço.] (media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco no gerenciamento de serviço.")

### <a name="introduction-to-the-operations-guide"></a>Introdução ao guia de operações 

**Quais**, **que**e **como** são três perguntas importantes que precisam ser respondidas quando se trata de gerenciamento de serviço.

Você pode usar o [Guia de operações](1-drive-value-operate-my-service.md) para ajudá-lo a resolver todos os três dessas perguntas. O guia fornece uma lista de atividades a serem realizadas em uma base diária, semanal, mensal e conforme necessário. Essas tarefas e atividades são essenciais para manter uma implantação de equipes de alta qualidade. Determinar quem será responsável pela execução de atividades específicas no gerenciamento de serviço é um aspecto crítico do seu planejamento que você precisa fazer logo no início do [estágio de planejamento](upgrade-enlist-stakeholders.md) para garantir uma implantação bem-sucedida. Depois que você calculou as tarefas e atividades, elas precisam ser compreendidos e seguido de grupos ou indivíduos que podem ser atribuídos a eles. Guia de operações fornece conhecimento e orientação sobre como executar cada uma das tarefas, e/ou as referências para conteúdo externo.

### <a name="operational-role-mapping"></a>Mapeamento de função operacionais

No início de planejamento para gerenciamento de serviço é uma etapa crítico, porque a fase de operações começa quando os usuários piloto primeiro estão habilitados. A equipe de projeto deve revisar e concordam com as tarefas e atividades necessárias, identificar a equipe responsável por cada tarefa operacional, e, em seguida, obtenha um compromisso e aprovação de cada equipe respectivo.

Após a aprovação estiver concluída, a equipe responsável deve iniciar, em seguida, operacionalização essas funções e responsabilidades. Isso pode incluir o treinamento e preparação, atualizando o modelo de equipe ou garantir que os parceiros externos sejam prontos para entregar.

Mapeamento funções operacionais conforme você coletou sua [equipe de projeto](upgrade-enlist-stakeholders.md) habilita todas as equipes iniciar suas tarefas operacionais durante o piloto e conheça as operações e certifique-se de que tudo esteja pronto após a implantação é iniciado.

Guia de operações fornece uma lista de tarefas comuns mapeada para funções típicas que deveriam estar válidas na maioria dos cenários. Você precisa personalizar essas responsabilidades para trabalhar em sua organização.

### <a name="the-quality-champion-role"></a>A função campeão de qualidade

Um grupo ou individual precisa ser responsável qualidade em todas as organizações. Essa é a função mais importante no gerenciamento de serviço. O campeão de qualidade é uma função de cliente que é atribuída a uma pessoa ou grupo que esteja entusiasmados pela sobre a experiência dos seus usuários. Essa função requer habilidades a identificar tendências no ambiente e o patrocínio para trabalhar com outras equipes para conduzir a correção. O melhor candidato para o campeão de qualidade é geralmente o proprietário do serviço de cliente, que — dependendo do tamanho e a complexidade da organização — poderia ser qualquer pessoa ou grupo que é entusiasmados pela sobre a experiência do usuário.

O campeão de qualidade aproveita as ferramentas existentes e processos documentados, como o painel de qualidade de chamada (CQD) e o guia de revisão qualidade de experiência, para monitorar a experiência do usuário, identificam tendências de qualidade e remediação de unidade onde for necessário. Os campeões qualidade trabalha com as respectivas equipes para ações de remediação de unidade, relatórios para um comitê de orientação sobre seus progressos e os problemas em aberto.

As tarefas e atividades associadas à função foram documentadas no guia de operações. Essa função deve ser atribuída durante a [fase de planejamento](https://aka.ms/SkypeToTeams-Plan). Uma etapa importante operacionalização a função do campeão de qualidade está ganhando o conhecimento necessário para a função e garantir que os pré-requisitos estejam em vigor para entregar nas tarefas. Uma tarefa de chave para essa função está executando uma revisão de experiência de qualidade regular.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introdução ao guia de revisão de experiência de qualidade

A qualidade de experiência Revise o guia tem um conjunto de atividades que avaliar e oferecem orientação de remediação em áreas principais que têm um impacto maior para melhorar a experiência do usuário, conforme mostrado na figura a seguir.

![Um diagrama que ilustra as principais áreas que são examinadas durante uma revisão da experiência de qualidade.] (media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Um diagrama que ilustra as principais áreas que são examinadas durante uma revisão da experiência de qualidade.")

Continuamente avaliando e correção as áreas descritas neste documento, você pode reduzir seu potencial para afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:

-   Configuração de firewall ou proxy incompleta

-   Baixa cobertura de Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio não otimizados ou internos

-   Sub-redes problemáticos ou dispositivos de rede

As diretrizes fornecidas no guia de revisão de experiência de qualidade enfoca usando Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área descrita, com foco para maximizar a adoção e o impacto de áudio. Otimizações de feitas à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.

É altamente recomendável que você designar desde o início do campeão de qualidade. Depois que está sendo indicado, eles devem iniciar podem se familiarizar com o conteúdo no guia de revisão de experiência de qualidade.

O guia de revisão de experiência de qualidade podem ser encontrado [aqui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="plan-for-network-quality"></a>Planejar a qualidade da rede 

Planejamento de qualidade da rede será o foco para a seção a seguir.

![Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco na rede.] (media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco na rede.")

Conforme mencionado anteriormente, planejamento de qualidade da rede antes da inclusão a Microsoft Teams é crítica. Para obter mais orientações para a preparação da rede, consulte [preparar a rede da sua organização para equipes da Microsoft](prepare-network.md).

Na maioria das organizações, redes podem abranger gerenciadas e redes.

Redes gerenciadas são componentes da infraestrutura de rede que uma organização tem controle direto sobre. Como resultado, redes gerenciadas tem uma influência direta sobre a qualidade que pode ser fornecida aos cargas de trabalho de tráfego em tempo real.

Por outro lado, redes não gerenciadas são segmentos da rede que um cliente tem limitado controle ou nenhum controle, acima.

Conexões com a Internet entre a organização e o Office 365 são redes onde um cliente tem controle limitado. As redes são gerenciadas por um ISP, mas as organizações devem ser capazes de influenciar a qualidade da rede ao atualizar sua largura de banda, defendendo para otimizações de rota, ou — se tudo mais falhar — os provedores de alternância.

Redes residencial ou em hotéis ou lanchonetes são exemplos de redes onde um cliente tiver sem controle.

As seções a seguir, iremos nos concentrar nos requisitos de qualidade de redes gerenciadas.

### <a name="key-network-planning-areas"></a>Rede principais áreas de planejamento

As seções a seguir focalizar as áreas importantes proporciona uma rede de alta qualidade.

> [!NOTE]
> Muitas redes evoluem ao longo do tempo devido às atualizações, expansão ou outros requisitos de negócios. Certifique-se de que você tenha processos operacionais in-loco para manter nessas áreas como parte do seu planejamento de gerenciamento de serviço.

#### <a name="bandwidth"></a>Largura de banda

O planejamento de largura de banda é um aspecto crítico da atividade de preparação da rede. Garantindo que haja largura de banda suficiente para as cargas de trabalho do Microsoft Teams é imperativo. Para poder tamanho certo uma rede existente, você deve compreender o que tem provisionados no momento, a utilização atual, e — basicamente — a largura de banda disponível restante.

Para medir a utilização atual, você precisa monitorar a rede. Essa medida, em seguida, pode ser usada como o ponto de partida para o planejamento de largura de banda. Além disso, a rede deve ser monitorada continuamente durante a implantação e depois da implantação para garantir que a rede suficientemente está provisionada.

> [!NOTE]
> Ao monitorar o uso da rede, é importante evitar o uso de médias por dia. Esses médias podem incluir horários não essenciais distorção o resultado. Médias oculte os períodos de pico e mascarar um problema subjacente.

[Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) ajuda a determinar e os requisitos de rede para sua implantação no apenas algumas etapas simples. Usando a ferramenta para coletar detalhes de redes da sua organização e o uso de voz de nuvem, você pode obter um cálculo aproximado dos requisitos de rede, você precisa para sua implantação de voz de nuvem, gerenciar e exportar esses detalhes para geração de relatórios e exibir áreas para uma investigação adicional e próximas etapas.

#### <a name="quality-of-service-qos"></a>Qualidade de serviço (QoS)

QoS deve ser implementada em todos os segmentos da rede gerenciada, até mesmo redes que tenham sido configurados adequadamente para a largura de banda. Neste caso, a QoS atua como uma mitigação de riscos em caso de carga de rede inesperadas. Quando a QoS é implementado, o tráfego de voz será priorizado para que esses eventos inesperados não afetam a qualidade.

Uma implementação de QoS deve incluir as áreas da rede, do ponto de extremidade até os pontos de saída e de volta para o ponto de extremidade, os pontos de saída. Isso garantirá que o tráfego de voz está sendo priorizado em ambas as direções. QoS deve ser implementada em ambos com fio e redes Wi-Fi.

Para implementar o QoS em sua rede, as orientações a seguir podem ajudar a [Qualidade de serviço em equipes da Microsoft](qos-in-teams.md)

#### <a name="proxy-servers"></a>Servidores proxy

Muitas organizações exibir o tráfego destinado à internet como um risco de segurança e eles atenuar esse risco, monitoramento e avaliar o tráfego nos pontos de saída na rede. Servidores proxy são uma classe de dispositivos que podem ser implantados para atender a esse requisito.

Um servidor proxy pode introduzir problemas durante a execução de inspeção de pacotes ou modificação de carga. Isso pode causar falhas de instalação, capitular chamadas e chamada de baixa qualidade de chamada. Se a mídia em tempo real é forçada a atravessar um servidor proxy, a pilha de mídia em equipes será forçada para realizar failback para TCP, que pode reduzir ainda mais a qualidade. UDP é sempre preferido sobre TCP.

Além disso, um servidor proxy não pode ser designado para lidar com a carga adicional do Office 365 e cargas de trabalho especificamente Teams Microsoft — incluindo mídia em tempo real.

Devido aos potenciais problemas de que um servidor proxy pode introduzir e essas preocupações de capacidade adicional, a Microsoft recomenda ignorando o servidor proxy e o estabelecimento de uma conexão direta para o Office 365.

A configuração necessária para ignorar o servidor proxy varia entre os fornecedores, mas a abordagem comum geralmente envolve atualizar o arquivo de configuração automática (PAC) do proxy. O arquivo PAC é um arquivo de configuração que descreve qual tráfego passar pelo proxy e o tráfego que ignora a ele.

Alguns fornecedores de servidores proxy fornecem um processo automatizado para garantir a configuração está atualizado. Se o seu fornecedor não fornecer esse processo automático, você pode baixar um arquivo PAC atualizado do <https://aka.ms/o365proxies>.

[Servidores proxy para Skype para negócios on-line e equipes](/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Firewalls

Garantir que as portas direita e protocolos sejam abertos para todas as URLs e IPs do Office 365 é necessária para acessar os Teams da Microsoft. Também é essencial para uma implantação de alta qualidade. Basta fazer uma chamada ou ingressar em uma chamada em conferência não é suficiente para garantir que seu firewall está configurado corretamente.

Se apenas TCP é aberto no firewall, a sessão será estabelecida, mas o transporte preferido (UDP) não é negociado. TCP e UDP devem ser abertas no firewall para oferecer a melhor experiência de usuário.

Devido à natureza com informações de estado, o TCP não é preferencial para a mídia em tempo real e é fornecido apenas como um transporte de rede failback for Microsoft Teams. Com o TCP, se não houver atraso do pacote ou perda, nesses pacotes devem ser retransmitidos até que eles estiver confirmados. Isso pode resultar em pacotes de mídia que não são mais relevantes concorrentes em tempo hábil entrega de pacotes de mídia atual. O cliente do usuário equipes tenta Alongar áudio e pode produzir audíveis artefatos, dependendo das condições de rede. Com a sobrecarga adicional do TCP, uma experiência aceitável geralmente pode deslocar para uma experiência de usuário ruim. Por esse motivo, o transporte de rede sem estado UDP é necessário.

Orientação completa para abertura do firewall for Microsoft Teams é fornecida no artigo [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips) .

Depois que a firewall for aberto, você pode usar a [Ferramenta de avaliação de rede Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) para validar a conectividade para os recursos de voz de nuvem.

> [!IMPORTANT]
> O Microsoft Office 365 IPs e URLs serão alterados ao longo do tempo. Como parte do planejamento de gerenciamento de serviço, é importante garantir um processo operacional esteja in-loco e um grupo é responsável para monitorar os [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips) e atualizá-las adequadamente.

#### <a name="local-internet-egress"></a>Saída local de internet

Muitas redes foram projetados para usar um hub e spoke de topologia. Nessa topologia, o tráfego da internet geralmente percorre WAN com um datacenter central antes de ele surge (egresses) para a internet. Normalmente, isso é feito para centralizar dispositivos de segurança de rede com o objetivo de reduzir o custo total.

Tráfego de back-puxar pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como Teams Microsoft opera em uma rede grande de global da Microsoft, geralmente há um local de rede aos e está perto do usuário. Um usuário provavelmente receberá um melhor desempenho por egressing sem um ponto de internet local e está perto do seu local e em nossa rede de voz-otimizado assim que possível. Para algumas cargas de trabalho, as solicitações de DNS são usadas para enviar o tráfego para o mais próximo do servidor front-end. Nesses casos, é importante que, ao usar um ponto de saída local, ele é emparelhado com resolução DNS local.

Otimizar o caminho de rede para a rede global da Microsoft, melhorar o desempenho e basicamente oferecer a melhor experiência para usuários. Para obter mais detalhes, consulte o blog postar [Obtendo o melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, geralmente não estiverem projetados ou configuradas para oferecer suporte a mídia em tempo real. Alguns VPNs também podem não suportar UDP. VPNs também apresentam uma camada adicional de criptografia, na parte superior de tráfego de mídia já criptografados. Além disso, a conectividade com o serviço Microsoft Teams talvez não seja eficiente devido ao tráfego de fixação de forma por meio de um dispositivo VPN. Além disso, eles não são necessariamente projetados de uma perspectiva de capacidade para acomodar as cargas antecipadas que precisarão de equipes.

A recomendação é fornecer um caminho alternativo que ignora a VPN para tráfego de equipes. Isso normalmente é conhecido como divisão de túnel VPN. Divisão encapsulamento significa que o tráfego para o Office 365 não atravessa VPN, mas será levado diretamente para o Office 365. Essa alteração terá um impacto positivo na qualidade, mas também proporciona a vantagem secundária de reduzir a carga de dispositivos VPN e da rede da organização.

Para implementar uma divisão de túnel, consulte o fornecedor VPN para ver os detalhes de configuração.

#### <a name="wi-fi"></a>Wi-Fi

Como o VPN, redes Wi-Fi não necessariamente são projetados ou configuradas para oferecer suporte a mídia de tempo real. Planejando e/ou otimizando, uma rede Wi-Fi para equipes de suporte é uma consideração importante para uma implantação de qualidade.

Há vários fatores que entram em cena para otimizar uma rede Wi-Fi.

-   Implementação de QoS ou Wi-Fi WMM (multimídia) para garantir que o tráfego de mídia é obtendo priorizado adequadamente através das redes Wi-Fi.

-   Posicionamento de ponto de planejamento e otimizando as faixas de W-Fi e o access. O intervalo de 2,4 GHz pode fornecer uma experiência adequada dependendo de posicionamento de ponto de acesso, mas os pontos de acesso geralmente são afetados por outros dispositivos de consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado à mídia em tempo real devido ao seu intervalo densidade, mas exige mais pontos de acesso para obter cobertura suficiente. Pontos de extremidade também precisam oferecer suporte a esse intervalo e ser configurado para aproveitar nessas faixas de acordo.

-   Se forem implantados redes Wi-Fi de banda dupla, considere a implementação de direcionamento de banda. O direcionamento de banda é uma técnica implementada por fornecedores de Wi-Fi para influenciar a banda dupla aos clientes utilizarem o intervalo de 5Ghz.

-   Sobreposição de canal – quando os pontos de acesso no mesmo canal estiverem muito juntos podem causar sobreposição de sinal e competem acidentalmente, resultando em uma experiência ruim para o usuário. Certifique-se de que o ponto de acesso que estão próximas umas das outras estão no canais que não se sobreponham.

Fornecedor de cada sem fio tem seus próprio recomendações para a implantação de sua solução sem fio. Recomendamos que você consulte seu fornecedor para obter orientações específicas.

### <a name="network-readiness-assessment"></a>Avaliação da prontidão da rede

Parte das atividades de preparação de rede inclui uma avaliação da rede. Depois de concluir a configuração e planejamento, a avaliação pode fornecer uma compreensão de linha de base da qualidade da sua rede antes de usuários onboard a Microsoft Teams. Os resultados da avaliação também ajudará você identificar e priorizar os esforços de remediação antes de habilitar usuários para equipes.

A avaliação de rede deve ser executada em ambos com fio e redes Wi-Fi para todos os prédios que estão sendo habilitados para recursos de voz em equipes em nuvem.

A avaliação de rede poderá ser realizada por meio de um parceiro da Microsoft, ferramentas de terceiros ou a [ferramenta de avaliação de rede da Microsoft](https://www.microsoft.com/download/details.aspx?id=53885). Fornecemos também ainda mais diretrizes sobre como executar a avaliação usando a ferramenta de avaliação de rede da Microsoft como parte de nossa orientação de preparação [aqui](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>Planejar a qualidade do ponto de extremidade

Como você pode ver do diagrama a seguir, os pontos de extremidade são um bloco de construção importante no fornecimento de uma experiência de alta qualidade para usuários.

![Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.] (media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagrama que ilustra os três componentes de qualidade e como o gerenciamento de serviço se sobrepõe a todos os três componentes. Com foco nos pontos de extremidade.")

Pontos de extremidade do Microsoft Teams podem ser executado em vários dispositivos, incluindo PCs, Macs, tablets e dispositivos móveis. Parte da experiência abrange não apenas o dispositivo, mas como um usuário se conecta ao dispositivo — por exemplo, usando um fone de ouvido otimizada, fones de ouvido com ou microfone/alto-falante interno do dispositivo. Usar um fone de ouvido otimizada pode enriquecer a experiência geral do usuário.

A orientação sobre o planejamento de ponto de extremidade a seguir ajudarão você a Certifique-se de que sua organização tem uma inclusão bem-sucedida de experiência com equipes.

### <a name="endpoint-capability"></a>Recurso de ponto de extremidade

A primeira parte do planejamento é garantir que todos os PCs e outros dispositivos em sua organização podem executar Teams da Microsoft. Isso envolve não só olhando os requisitos de hardware, mas também Noções básicas sobre o que mais PC está fazendo em segundo plano. Muitas organizações executarem outros softwares, incluindo os sistemas de detecção de invasão e software de antimalware, que pode afetar o desempenho de base de um dispositivo.

Microsoft Teams tem clientes disponíveis para a área de trabalho, web (Windows e Mac) e mobile (Android, iOS e Windows Mobile). Para obter informações sobre os requisitos de software para cada plataforma, consulte [obter clientes para equipes da Microsoft](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls do ponto de extremidade

Firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário. Firewalls do lado do cliente podem afetar a qualidade da chamada além impedindo uma chamada de sendo estabelecida. Configure as exclusões apropriadas no firewall cliente com base nas informações em [URLs do Office 365 e intervalos de endereços IP](https://aka.ms/o365ips). O fornecedor terceirizado terão orientações específicas sobre como criar as exclusões.

> [!NOTE]
> Microsoft Teams atualizará automaticamente o Firewall do Windows com uma configuração de firewall apropriada.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recomendações de Wi-Fi para pontos de extremidade

Planejando e implantando uma rede Wi-Fi otimizada para suportar cargas de trabalho em tempo real no Microsoft Teams exigirá significante planejamento. As seções a seguir fornecem algumas diretrizes gerais que podem ajudá-lo a evitar algumas armadilhas comuns durante o planejamento para os pontos de extremidade.

#### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Alguns drivers Wi-Fi podem ser problemáticos. Por exemplo, um driver pode ter muito agressivos comportamentos roaming entre os pontos de acesso, causando a qualidade de chamadas ruins. Isso não é uma coisa comum, mas é importante garantir que os drivers de Wi-Fi no PC foram atualizados e testados antes da implantação.

#### <a name="wi-fi-bands"></a>Faixas Wi-Fi

Existem basicamente dois tipos de faixas usados em equipamento hoje Wi-Fi, 2,4 GHz e GHz 5.0. Se sua organização fornece as duas faixas, você deve configurar as configurações do driver para preferir faixa de GHz 5.0. Este banda é muito mais densos em termos de taxa de transferência e menor afetado por essa interferência Vista na faixa de 2,4 GHz. Essa recomendação pressupõe que você tiver otimizado adequadamente banda de rede de GHz 5.0.

#### <a name="wi-fi-radio-type"></a>Tipo de rádio Wi-Fi

Plano para dispositivos que oferecem suporte os tipos de rádio Wi-Fi mais recentes. Você pode obter um desempenho muito bom Wi-Fi, se você aproveitar a 802.11ac ou mais recente nos dispositivos de provisionar.

#### <a name="wireless-avoidance"></a>Contenção de sem fio

Algumas organizações preferem evitar Wi-Fi totalmente. Em alguns casos, este guia é fornecido por meio de uma recomendação para os usuários se conectarem diretamente a uma rede com fio. Em alguns casos, a ordem de ligação de rede pode ter a conexão sem fio preferencial e continuar a usar essa conexão, mesmo que o PC esteja conectado para a conexão com fio. Para evitar esse comportamento acidentais, configure a ordem de ligação para evitar esse cenário.

#### <a name="80211-power-save-protocol"></a>protocolo de economia de energia 802.11

Se sua organização usa pontos de acesso sem fio ou roteadores que não oferecem suporte a potência 802.11 Salvar protocolo, você pode sofrer capitular chamadas ou a qualidade de chamadas ruins em Teams da Microsoft em execução em dispositivos do Windows. Se não for possível atualizar o ponto de acesso sem fio ou roteadores, você deverá atualizar as configurações de plano de energia do Windows em dispositivos que executam com bateria. Diretrizes de configuração e os detalhes mais são fornecidas no seguinte [artigo de suporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Dispositivos para equipes

Microsoft Teams pode ser usadas para reuniões ou como um sistema telefônico. Ao usar esses recursos, o dispositivo de interface que é usado para equipes desempenha um papel importante na experiência do usuário.

Usando um alto-falante e microfone de internas pode parecer aceitável ao usuário que tem essa configuração. Mas geralmente esses dispositivos não otimizados para o cancelamento de ruído e qualquer tipo de ruído ambiental pode ter um impacto downstream em outros na chamada. Aproveitando a dispositivos otimizados para esses cenários ajudará a garantir uma experiência de alta qualidade.

Cada dispositivo deve atender às necessidades dos seus usuários. Você precisará ajustar os dispositivos como fones de ouvido para os diferentes personagens e casos de uso em sua organização. Um exercício de mapeamento de pessoa para dispositivo deve ser concluído como parte do processo de planejamento.

Depois que você selecionou os dispositivos, incluí-los no plano de teste piloto para validação final. Pesquisas de alavancar durante o piloto para coletar comentários para garantir que sua estratégia de dispositivo é ideal.

Neste momento, recomendamos o uso de dispositivos de áudio que foram certificados por meio do Skype para o programa de certificação de negócios. Para localizar dispositivos certificados sob este programa, consulte o catálogo de soluções [USB dispositivos Certified para Skype para negócios](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

Para obter mais detalhes, consulte [Client and Devices - Workshop de preparação](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Atualizações do cliente

Um dos principais benefícios do Microsoft Teams é que o cliente sejam mantido atualizado automaticamente. Os clientes no PC e Mac são atualizados usando um processo de plano de fundo que verifica se há novas compilações e baixa o novo cliente quando o aplicativo estiver ocioso. O tamanho de download do cliente é de aproximadamente 100 MB.

Uma organização não tem qualquer controle ou o acesso a uma configuração de diretiva para gerenciar o processo de atualização. Para reduzir o risco de um problema que pode ser descoberto em uma compilação mais recente, a última versão boa conhecida é mantida no ponto de extremidade. Se houver um problema com uma nova compilação, o serviço Microsoft Teams pode reverter automaticamente o ponto de extremidade para a versão anterior.

## <a name="next-steps-and-references"></a>Próximas etapas e referências

Esta tabela inclui um resumo das atividades de planejamento com links para conteúdo relacionado.

| Área | Detalhes | Referências |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Planejar o gerenciamento de serviço | Conduzir um exercício de mapeamento de função operacionais <br/> Aprovação de equipes responsáveis <br/> Preparação de função | [Guia de operações](1-drive-value-operate-my-service.md) |
| | Designar Champion(s) de qualidade <br/> Preparação de campeões de qualidade| [Saiba CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Revise o guia experiência de qualidade](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | Instalar modelos de revisão de experiência de qualidade <br/> Carregar um arquivo de construção | [Modelos de QERLite](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-2-1.zip?raw=true) <br/> [Informações de construção de carregamento](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)|
| Planejar a qualidade da rede | Execute Planejador de rede | [Planejador de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implementar o QoS | [Qualidade de serviço em equipes da Microsoft](qos-in-teams.md) |
| | Ignorar servidores proxy | [Orientação de proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | Implementar a divisão de túnel VPN | [Orientação de túnel de divisão VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Otimizar redes Wi-Fi para a mídia em tempo real  | Consulte fornecedores terceirizados |
| | Implementar a saída de internet local | [Saída de Internet local](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementar a conectividade de rede <br/> Validar a conectividade de rede | [URLs do Office 365 e endereços IP](https://aka.ms/o365ips) |
| | | [Ferramenta de avaliação de rede](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Realizar uma avaliação de rede | [Avaliação de prontidão de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Planejar a qualidade do ponto de extremidade | Firewalls do ponto de extremidade de atualização | [URLs do Office 365 e endereços IP](https://aka.ms/o365ips) |
| | Validar os requisitos de software | [Obter clientes para o Microsoft Teams](get-clients.md) |
| | Implementar as recomendações de ponto de extremidade Wi-Fi | Consulte fornecedores terceirizados |
| | Conduzir a pessoa para mapeamento de dispositivos <br/> Provisionar dispositivos e testá-los | [Clientes e dispositivos - Workshop de preparação](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Catálogo de dispositivo](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

Depois que terminar de planejamento, prossiga para a próxima etapa: [preparar seu ambiente para equipes](https://aka.ms/SkypeToTeams-TechnicalReadiness).