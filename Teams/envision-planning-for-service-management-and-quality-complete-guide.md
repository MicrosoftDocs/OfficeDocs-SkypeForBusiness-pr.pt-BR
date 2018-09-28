---
title: Guia de planejamento do gerenciamento do serviço do Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Ofereça aos usuários do Microsoft Teams uma experiência de qualidade com o gerenciamento da integridade do serviço, da rede e dos pontos de extremidade e a definição de funções operacionais e defensor da qualidade.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29b17157178f8e7565fd6f484d6d95262c76ce05
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015577"
---
# <a name="plan-for-service-management-and-quality"></a>Planejar o gerenciamento e a qualidade do serviço

Este documento trata da fase de Concepção do Microsoft Teams.
 
## <a name="introduction"></a>Introdução

Este conteúdo fornecerá uma visão geral dos requisitos necessários para fornecer e manter uma implantação do Microsoft Teams de alta qualidade. Você pode ajudar a garantir uma implantação bem-sucedida com o planejamento do gerenciamento e da qualidade do serviço durante a fase de Concepção, antes de fazer o primeiro piloto ou da primeira implantação em produção.

As orientações estão organizadas nas seguintes seções:

-   Primeiro, uma visão geral da experiência do usuário e dos principais componentes que sustentam a qualidade. São destacadas as áreas que devem ser focadas antes da integração do Microsoft Teams.

-   Segundo, são fornecidas orientações para planejar um modelo de suporte para gerenciar o Microsoft Teams antes do primeiro piloto com usuários ou da primeira implantação em produção. Esta seção descreve as tarefas que precisam ser realizadas regularmente para manter uma implantação do Microsoft Teams de alta qualidade. Além disso, esta seção apresenta mais orientações, que você pode usar para começar a entender e operacionalizar essas tarefas.

-   Terceiro, orientações específicas ajudam no planejamento da rede e dos pontos de extremidade em sua organização para dar suporte ao Microsoft Teams.

-   Por fim, as etapas seguintes são resumidas com referências ao conteúdo relacionado.

## <a name="key-components-that-affect-user-experience"></a>Principais componentes que afetam a experiência do usuário

Os principais componentes que afetam a experiência do usuário serão examinados nesta seção. Antes de analisar os principais componentes, é essencial que você entenda a experiência do usuário e sua importância para alcançar as metas de negócios da organização. Primeiro, vamos examinar como definimos a experiência do usuário.

### <a name="user-experience-defined"></a>Definição de experiência do usuário

As metas de negócios podem ser alcançadas quando você implanta o Microsoft Teams e incorpora as comunicações em seus processos empresariais para melhorar seu fluxo de trabalho. A qualidade promove a adoção e o uso: se a sua organização fornece um serviço de alta qualidade que satisfaz os usuários, então indivíduos e equipes podem ganhar confiança e descobrir maneiras novas e inovadoras de usar o serviço para obter benefícios para os negócios.

No centro disso tudo está a experiência do usuário com o Microsoft Teams; os sentimentos e as posturas da pessoa em relação ao serviço. Então, o que contribui para a experiência do usuário? Isso varia desde os usuários saberem como usar o Microsoft Teams e incorporá-lo em seu fluxo de trabalho diários até a experiência de uma qualidade excepcional nas chamadas e a capacidade de se conectar de modo confiável, independentemente do lugar onde se encontram. Por natureza, a experiência do usuário é muito ampla; este documento foca apenas os elementos que podem ser controlados pela organização.

Há requisitos específicos à implantação que são fundamentais para oferecer uma experiência do usuário fantástica, especialmente ao usar os recursos de voz em nuvem no Microsoft Teams. É essencial tratar o Microsoft Teams como um cidadão de primeira linha com outros investimentos em comunicação e colaboração, priorizando o tráfego em tempo real de maneira correspondente. A próxima seção fornece uma visão geral dos principais componentes que afetam a experiência do usuário. Nas outras seções, forneceremos orientações para você começar o planejamento para implantar e manter os principais componentes que compreendem a qualidade.

### <a name="key-components-of-quality"></a>Principais componentes da qualidade

Uma organização ou um parceiro de apoio deve começar a planejar três componentes principais durante a fase de Concepção de uma implantação do Microsoft Teams: gerenciamento do serviço, rede e pontos de extremidade. A combinação dessas três áreas é fundamental para a qualidade da experiência do usuário.

![Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes.](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes.")

#### <a name="service-management"></a>Gerenciamento do serviço

O gerenciamento do serviço pode ser dividido em duas categorias de responsabilidade diferentes:

-   **Responsabilidades da Microsoft**. A Microsoft é responsável pelos componentes de infraestrutura que o serviço do Office 365 compreende. A Microsoft se responsabiliza frente aos clientes por garantir que todos os usuários que se conectam ao Microsoft Teams recebam uma experiência confiável e de alta qualidade.

-   **Responsabilidade do cliente**. Você e sua organização são responsáveis pelo gerenciamento dos vários aspectos do serviço do Office 365, da rede local e dos pontos de extremidade dos usuários. Por exemplo, conforme novos endereços IP são adicionados ao Office 365, você deve atualizar os firewalls apropriados para permitir a comunicação com os novos pontos de extremidade a fim e evitar transtornos para os usuários.

Para obter orientações detalhadas sobre o planejamento do gerenciamento do serviço, consulte [Planejar o gerenciamento do serviço](#plan-for-service-management).

#### <a name="network"></a>Rede 

Na maioria das organizações, as redes foram projetadas inicialmente para dar acesso a dados e aplicativos que residiam em seus data centers. Os aplicativos baseados em nuvem, como o Office 365, exigem alterações nessas redes para dar suporte aos novos fluxos de acesso e dados requeridos pelo Microsoft Teams. Para poder habilitar os usuários para o Microsoft Teams em sua organização, é necessário avaliar e otimizar sua rede atual. Isso é fundamental ao aproveitar funcionalidades de voz em nuvem.

Em redes tradicionais, os usuários precisam cruzar as redes de perímetro de uma organização para acessar o Microsoft Teams. Muitas organizações terão dispositivos de segurança, como servidores proxy, firewalls e VPNs, capazes de bloquear, impedir ou fornecer um caminho não otimizado para o tráfego de rede.

Além disso, as redes internas centrais precisam ser otimizadas e ter o tamanho certo para fornecer capacidade e qualidade suficientes para dar suporte às cargas de trabalho do Microsoft Teams, inclusive de mídia em tempo real. Você pode usar o planejamento, a correção e a otimização da largura de banda para ajudar a garantir que sua rede forneça um caminho eficiente e de alta qualidade para o Office 365.

Para obter orientações detalhadas sobre o planejamento da rede, consulte [Planejar a qualidade da rede](#plan-for-network-quality).

#### <a name="endpoints"></a>Pontos de extremidade

O Microsoft Teams dá suporte a diversos pontos de extremidade. De computadores a tablets e celulares, você pode acessar o Microsoft Teams de qualquer lugar, em praticamente qualquer dispositivo.

Para que seus usuários tenham a melhor experiência possível, você precisa considerar estes aspectos importantes durante a fase de Concepção: seus pontos de extremidade atendem aos requisitos de hardware e software do Microsoft Teams? Você configurou e otimizou os pontos de extremidade para que deem suporte a redes Wi-Fi? Quais dispositivos você vai usar para fazer e receber chamadas de voz? Esses dispositivos estão otimizados para o Microsoft Teams?

Para obter orientações detalhadas sobre o planejamento de pontos de extremidade, consulte [Planejar a qualidade dos pontos de extremidade](#plan-for-endpoint-quality).

## <a name="plan-for-service-management"></a>Planejar o gerenciamento do serviço

O gerenciamento do serviço é um tema amplo, que abrange as operações do serviço Microsoft Teams no dia a dia depois que ele é implantado e habilitado para os usuários. O serviço Microsoft Teams abrange o Microsoft Office 365 e os componentes de infraestrutura implantados localmente (por exemplo, a rede).

É provável que a noção de gerenciamento do serviço não seja um conceito novo para a maioria das organizações. Você provavelmente já implementou processos e tarefas que estão associados a serviços existentes. Considerando isso, é possível que você possa expandir o que já está funcionando ao planejar o gerenciamento do serviço atual para dar suporte ao Microsoft Teams no futuro.

O gerenciamento do serviço compreende todas as atividades e processos envolvidos no gerenciamento do Microsoft Teams de ponta a ponta. Conforme descrito anteriormente, alguns componentes do gerenciamento do serviço — os componentes de infraestrutura que o próprio serviço do Office 365 engloba — são de responsabilidade da Microsoft, enquanto o clientes é responsável por gerenciar os diversos aspectos do Microsoft Teams, da rede e dos pontos de extremidade que fornecem a seus clientes. Esta seção do documento foca a responsabilidade do cliente segundo a perspectiva do gerenciamento do serviço.

![Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre o gerenciamento do serviço.](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre o gerenciamento do serviço.")

### <a name="introduction-to-the-operations-guide"></a>Introdução ao Guia de Operações 

**O que**, **quem** e **como** são três perguntas importantes que precisam ser respondidas ao lidar com o gerenciamento do serviço.

O [Guia de Operações](1-drive-value-operate-my-service.md) pode ajudar a responder a essas três perguntas. O guia fornece uma lista de atividades que devem ser realizadas diariamente, semanalmente, mensalmente e conforme a necessidade. Essas atividades e tarefas são essenciais para a manutenção de uma implantação do Microsoft Teams de alta qualidade. A determinação de quem será responsável pela realização de atividades específicas de gerenciamento do serviço é um aspecto crítico do planejamento que você precisa fazer logo no início da fase de Concepção para garantir o sucesso da implantação. Depois que você identificar essas tarefas e atividades, os grupos ou as pessoas aos quais elas serão atribuídas deverão entendê-las e acompanhá-las. O Guia de Operações apresenta informações e orientações para a realização de cada uma das tarefas e/ou referências de conteúdo externo.

### <a name="operational-role-mapping"></a>Mapeamento de funções operacionais

O planejamento inicial do gerenciamento do serviço é uma etapa crítica, pois a fase de operações começa quando os primeiros usuários piloto são habilitados. A equipe do projeto deve revisar e concordar com as tarefas e atividades necessárias, identificar a equipe que será responsável por cada tarefa operacional e então obter o comprometimento e a aprovação de cada equipe envolvida.

Após a conclusão da aprovação, a equipe responsável deve iniciar a operacionalização das funções e responsabilidades. Isso pode incluir um processo de treinamento e preparação, a atualização do modelo de alocamento de pessoal ou a verificação de que os parceiros externos estão prontos para o fornecimento.

O mapeamento das funções operacionais logo no início da fase de Concepção permite que todas as equipes comecem suas tarefas operacionais durante o piloto e reforcem as operações e garantam que tudo está pronto logo após o início da implantação.

O Guia de Operações apresenta uma lista de tarefas comuns mapeadas para as funções típicas que devem ser válidas na maioria dos cenários. Você precisa personalizar essas responsabilidades de maneira adequada para a sua organização.

### <a name="the-quality-champion-role"></a>Função de defensor da qualidade

Todos os grupos ou indivíduos precisam se responsabilizar pela qualidade em todas as organizações. Essa é a função mais importante do gerenciamento do serviço. O defensor da qualidade é uma função do cliente atribuída a uma pessoa ou um grupo apaixonado pela experiência de seus usuários. Essa função requer a habilidade de identificar tendências no ambiente e a capacidade de trabalhar com outras equipes para possibilitar correções. Normalmente, o melhor candidato a defensor da qualidade é o proprietário do serviço. Dependendo do tamanho e da complexidade da organização, pode ser qualquer pessoa ou grupo que tenha paixão pela experiência do usuário.

O defensor da qualidade utiliza as ferramentas existentes e os processos documentados, como o Painel de Qualidade de Chamadas (PQC) e o Guia de Revisão da Experiência de Qualidade, para monitorar a experiência do usuário, identificar tendências da qualidade e conduzir correções, quando necessário. O defensor da qualidade trabalha com as respectivas equipes para conduzir ações de correção, reportando-se a uma comissão de coordenação sobre seu andamento e os problemas não solucionados.

As tarefas e atividades associadas à função estão documentadas no Guia de Operações. Essa função deve ser atribuída logo no início da fase de Concepção. Um etapa importante da operacionalização da função de defensor da qualidade é a obtenção do conhecimento necessário para a função e a garantia de que os pré-requisitos para a execução das tarefas foram cumpridos. Uma tarefa importante dessa função é a realização periódica de uma revisão da experiência de qualidade.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introdução ao Guia de Revisão da Experiência de Qualidade

O Guia de Revisão da Experiência de Qualidade apresenta uma série de atividades que avalia e fornece orientações de correção nas principais áreas que têm mais impacto sobre o aprimoramento da experiência do usuário, conforme mostrado na figura a seguir.

![Diagrama que ilustra as principais áreas examinadas durante a revisão da experiência de qualidade.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "Diagrama que ilustra as principais áreas examinadas durante a revisão da experiência de qualidade.")

Por meio da avaliação e correção contínuas das áreas descritas neste documento, você pode reduzir seu potencial de afetar negativamente a experiência do usuário. A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:

-   Configuração incompleta do firewall ou proxy

-   Cobertura insatisfatória da rede Wi-Fi

-   Largura de banda insuficiente

-   VPN

-   Uso de dispositivos de áudio internos ou não otimizados

-   Dispositivos de rede ou sub-redes com problemas

As orientações fornecidas no Guia de Revisão da Experiência de Qualidade concentram-se no uso do Painel de Qualidade de Chamadas (PQC) Online como ferramenta principal para relatar e investigar cada área descrita, com foco sobre o áudio para maximizar a adoção e o impacto. Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.

Recomendamos enfaticamente que você nomeie o defensor da qualidade logo no início do processo. Após a nomeação, ele deve começar a se familiarizar com o conteúdo do Guia de Revisão da Experiência de Qualidade.

O Guia de Revisão da Experiência de Qualidade está disponível [aqui](https://aka.ms/qerguide).

## <a name="plan-for-network-quality"></a>Planejar a qualidade da rede 

O planejamento da qualidade da rede será o foco desta seção.

![Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre a rede.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre a rede.")

Conforme mencionado anteriormente, é fundamental planejar a qualidade da rede antes da integração do Microsoft Teams. Para obter mais orientações sobre a preparação da rede, consulte [Preparo da rede da sua organização para o Microsoft Teams](prepare-network.md).

Na maioria das organizações, as redes compreendem redes gerenciadas e não gerenciadas.

As redes gerenciadas são componentes da infraestrutura de rede sobre os quais a organização tem controle direto. Como resultado, as redes gerenciadas têm influência direta sobre a qualidade que pode ser fornecida para as cargas de trabalho de tráfego em tempo real.

Por outro lado, as redes não gerenciadas são segmentos da rede sobre os quais o cliente tem controle limitado ou nenhum controle.

As conexões de Internet entre a organização e o Office 365 compreendem redes nas quais o cliente tem controle limitado. Elas são gerenciadas por um ISP, mas as organizações devem ser capazes de afetar a qualidade da rede por meio da atualização da largura de banda, da garantia de otimizações de rotas ou, em último caso, da troca do ISP.

As redes domésticas ou de hotéis e cafés são exemplos de redes em que o cliente não tem qualquer controle.

Nas seções a seguir, vamos focar os requisitos de qualidade das redes gerenciadas.

### <a name="key-network-planning-areas"></a>Principais áreas do planejamento de redes

As próximas seções focam as áreas importantes para fornecer uma rede de alta qualidade.

> [!NOTE]
> Muitas redes evoluem ao longo do tempo devido a atualizações, expansões ou outros requisitos empresariais. Verifique se você tem processos operacionais em vigor para manter essas áreas como parte do planejamento do gerenciamento do serviço.

#### <a name="bandwidth"></a>Largura de banda

O planejamento da largura de banda é um aspecto crítico da atividade de preparação da rede. É fundamental garantir que haja largura de banda suficiente para as cargas de trabalho do Microsoft Teams. Para conseguir dimensionar corretamente uma rede existente, você precisa entender o que é provisionado no momento, a utilização atual e, por fim, a largura de banda disponível restante.

Para medir a utilização atual, você precisa monitorar a rede. Essa medida poderá então ser usada como ponto inicial para o planejamento da largura de banda. Além disso, a rede deve ser monitorada continuamente durante e após a implantação para garantir que a rede seja provisionada de maneira suficiente.

> [!NOTE]
> Ao monitorar a utilização da rede, é importante evitar o uso de médias ao longo do dia. Essas médias podem incluir horários atípicos que distorcem o resultado. As médias podem ocultar períodos de pico e mascarar algum problema subjacente.

O [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) ajuda a determinar e organizar os requisitos de rede de sua implantação em algumas etapas simples. Ao usar a ferramenta para coletar os detalhes da rede de sua organização e de uso do Cloud Voice, você poderá obter um cálculo aproximado dos requisitos de rede que serão necessários para a implantação do Cloud Voice, gerenciar e exportar esses detalhes para a geração de relatórios e ver as áreas que deverão ser melhor investigadas, além das próximas etapas.

#### <a name="quality-of-service-qos"></a>Qualidade de serviço (QoS)

A QoS deve ser implementada em todos os segmentos da rede gerenciada, até nas redes com uma largura de banda adequada provisionada. Nesse caso, a QoS atua como uma mitigação de risco, caso ocorra uma carga de rede não prevista. Ao implementar a QoS, o tráfego de voz será priorizado de modo que esses eventos não previstos não afetem a qualidade.

A implementação da QoS deve incluir áreas da rede desde o ponto de extremidade até os pontos de saída e dos pontos de saída de volta até o ponto de extremidade. Isso garantirá que o tráfego de voz seja priorizado nas duas direções. A QoS deve ser implementada em redes com fio e Wi-Fi.

Para a implementação da QoS em sua rede, as orientações contidas em [Qualidade de Serviço no Microsoft Teams](qos-in-teams.md) podem ser úteis

#### <a name="proxy-servers"></a>Servidores proxy

Muitas organizações consideram o tráfego destinado à Internet como um risco de segurança e fazem a mitigação desse risco monitorando e avaliando o tráfego nos pontos de saída da rede. Os servidores proxy são uma classe de dispositivos que pode ser implantada para atender a esse requisito.

O servidor proxy pode introduzir problemas ao realizar a inspeção de pacotes ou modificar a carga. Isso pode levar a falhas na configuração, interrupções e baixa qualidade das chamadas. Se a mídia em tempo real for forçada a percorrer um servidor proxy, a pilha de mídia no Microsoft Teams será forçada a fazer failback para o TCP, o que pode reduzir ainda mais a qualidade. O UDP sempre tem preferência em relação ao TCP.

Além disso, um servidor proxy pode não ser projetado para lidar com a carga adicional do Office 365 e, especificamente, as cargas de trabalho do Microsoft Teams, incluindo mídia em tempo real.

Por causa dos problemas em potencial que um servidor proxy pode introduzir e dessas questões adicionais de capacidade, a Microsoft recomenda desviar do servidor proxy e estabelecer uma conexão direta com o Office 365.

A configuração necessária para contornar o servidor proxy varia de um fornecedor para outro, mas a abordagem mais comum normalmente envolve a atualização do arquivo de configuração automática do proxy (PAC). O arquivo PAC é um arquivo de configuração que descreve qual tráfego passa pelo proxy e qual tráfego é desviado.

Alguns fornecedores de servidores proxy oferecem um processo automatizado para garantir que a configuração esteja atualizada. Se o seu fornecedor não oferece esse processo automático, você pode baixar um arquivo PAC atualizado em <https://aka.ms/o365proxies>.

[Servidores proxy para o Skype for Business Online e o Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>Firewalls

É necessário garantir que as portas e os protocolos certos estejam abertos para todos os IPs e URLs do Office 365 para poder acessar o Microsoft Teams. Isso também é crítico para conseguir uma implantação de alta qualidade. O fato de fazer uma chamada ou ingressar em uma chamada em conferência não é suficiente para garantir que o firewall esteja configurado corretamente.

Se apenas o TCP estiver aberto no firewall, a sessão será estabelecida, mas o transporte preferencial (UDP) não será negociado. É necessário que os protocolos TCP e UDP estejam abertos no firewall para oferecer a melhor experiência do usuário.

Devido a sua natureza com estado, o TCP não é preferencial para mídia em tempo real, sendo fornecido apenas para o transporte de rede de failback do Microsoft Teams. Com o TCP, se houver um atraso ou uma perda do pacote, esse pacote deverá ser retransmitido até que seja confirmado. Isso pode fazer com que pacotes de mídia que não são mais relevantes concorram com a entrega em tempo hábil de pacotes de mídia atuais. O cliente do Microsoft Teams do usuário tenta alongar o áudio e pode produzir artefatos audíveis, dependendo das condições da rede. Com a sobrecarga adicional do TCP, uma experiência em geral aceitável pode se transformar em uma experiência do usuário medíocre. Por isso, o transporte de rede sem estado do UDP é necessário.

Todas as orientações para abrir o firewall para o Microsoft Teams estão disponíveis no artigo [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips).

Depois que o firewall for aberto, você poderá usar a [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) para confirmar a conectividade para funcionalidades de voz em nuvem.

> [!IMPORTANT]
> Os IPs e as URLs do Microsoft Office 365 serão alterados ao longo do tempo. Como parte do planejamento do gerenciamento do serviço, é importante garantir que um processo operacional esteja funcionando e que um grupo seja responsável pelo monitoramento de [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips) e por fazer as atualizações necessárias.

#### <a name="local-internet-egress"></a>Saída para a Internet local

Muitas redes foram projetadas para usar uma topologia hub-spoke. Nessa topologia, normalmente o tráfego da Internet percorre a WAN até um data center central antes de exteriorizar-se (sair) na Internet. Muitas vezes, isso é feito para centralizar os dispositivos de segurança de rede a fim de reduzir o custo total.

O tráfego de retorno pela WAN aumenta a latência e tem um impacto negativo sobre a qualidade e a experiência do usuário. Como o Microsoft Teams é executado na ampla rede global da Microsoft, frequentemente há um local de emparelhamento de rede perto do usuário. O usuário provavelmente terá melhor desempenho ao sair de um ponto de Internet local próximo de sua localização e entrar em nossa rede com otimização de voz assim que possível. Para algumas cargas de trabalho, solicitações DNS são usadas para enviar o tráfego para o servidor front-end mais próximo. Nesses casos, é importante que, ao usar um ponto de saída local, ele esteja emparelhado com a resolução de DNS local.

A otimização do caminho de rede para a rede global da Microsoft melhorará o desempenho e, em última instância, oferecerá a melhor experiência para os usuários. Para obter mais detalhes, consulte a postagem no blog [Como obter a melhor conectividade e desempenho no Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

#### <a name="vpn"></a>VPN

As VPNs fornecem um serviço valioso para muitas organizações. Infelizmente, em geral elas não são projetadas ou configuradas para dar suporte a mídia em tempo real. Algumas VPNs também podem não dar suporte ao UDP. As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia já criptografado. Além disso, a conectividade com o serviço Microsoft Teams pode não ser eficiente por causa do hairpinning do tráfego através de um dispositivo de VPN. E eles não são necessariamente projetados considerando a capacidade para acomodar as cargas previstas que o Microsoft Teams exigirá.

A recomendação é fornecer um caminho alternativo que contorne a VPN para o tráfego do Microsoft Teams. Geralmente, isso é conhecido como VPN de túnel dividido. O túnel dividido significa que o tráfego do Office 365 não percorrerá a VPN, mas passará diretamente para o Office 365. Essa alteração tem um impacto positivo sobre a qualidade, mas também apresenta um benefício secundário de reduzir a carga dos dispositivos de VPN e da rede da organização.

Para implementar um túnel dividido, consulte o fornecedor da VPN para obter os detalhes de configuração.

#### <a name="wi-fi"></a>Wi-Fi

Como a VPN, as redes Wi-Fi não são necessariamente projetadas ou configuradas para dar suporte a mídia em tempo real. O planejamento e/ou a otimização da rede Wi-Fi para dar suporte ao Microsoft Teams é um fator importante para a implantação de qualidade.

Há vários fatores que devem ser considerados ao otimizar uma rede Wi-Fi.

-   Implementar a QoS ou o Multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia seja priorizado corretamente pelas redes Wi-Fi.

-   Planejar e otimizar as bandas de Wi-Fi e o posicionamento dos pontos de acesso. O intervalo de 2,4 GHz pode fornecer uma experiência adequada, dependendo do posicionamento do ponto de acesso, mas muitas vezes os pontos de acesso são afetados por outros dispositivos do consumidor que funcionam naquele intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real porque é mais denso, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.

-   Ser foram implantadas redes Wi-Fi de banda dupla, considere a implementação do direcionamento de banda. O direcionamento de banda é uma técnica implementada pelos fornecedores de Wi-Fi para afetar clientes de banda dupla que usam o intervalo de 5 GHz.

-   Sobreposição de canais – quando os pontos de acesso do mesmo canal estão muito próximos, podem causar a sobreposição do sinal e uma concorrência involuntária, resultando em uma experiência ruim para o usuário. Os pontos de acesso que estão próximos devem estar em canais não sobrepostos.

Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Recomendamos que você consulte as orientações específicas do fornecedor.

### <a name="network-readiness-assessment"></a>Avaliação da preparação da rede

Parte das atividades de preparação da rede inclui uma avaliação da rede. Depois de concluir o planejamento e a configuração, a avaliação proporciona uma compreensão de referência da qualidade da sua rede antes da integração dos usuários no Microsoft Teams. Os resultados da avaliação também ajudarão a identificar e priorizar iniciativas de correção antes de habilitar os usuários para o Microsoft Teams.

A avaliação da rede deve ser realizada para redes com fio e Wi-Fi de todos os edifícios que terão funcionalidades de voz em nuvem habilitadas no Microsoft Teams.

A avaliação da rede pode ser conduzida por um parceiro da Microsoft, ferramentas de terceiros ou a [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885). Também fornecemos outras orientações sobre como executar a avaliação usando a Microsoft Network Assessment Tool como parte de nossas orientações de preparação [aqui](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11)..

## <a name="plan-for-endpoint-quality"></a>Planejar a qualidade dos pontos de extremidade

Como é possível ver no diagrama a seguir, os pontos de extremidade são um bloco de construção importante para fornecer uma experiência de alta qualidade para os usuários.

![Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre os pontos de extremidade.](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "Diagrama que ilustra os três componentes da qualidade e como o gerenciamento do serviço se sobrepõe a todos os três componentes. Com foco sobre os pontos de extremidade.")

Os pontos de extremidade do Microsoft Teams podem ser executados em vários dispositivos, como PCs, Macs, tablets e dispositivos móveis. Parte da experiência engloba não apenas o dispositivo, mas o modo como o usuário se conecta a ele. Por exemplo, usando o microfone/viva-voz interno do dispositivo, fones de ouvido ou um fone de ouvido com microfone otimizado. O uso de um fone de ouvido com microfone otimizado pode melhorar a experiência geral do usuário.

As orientações de planejamento de pontos de extremidade a seguir ajudarão a garantir que sua organização tenha uma experiência de integração com o Microsoft Teams positiva.

### <a name="endpoint-capability"></a>Funcionalidades dos pontos de extremidade

A primeira parte do planejamento consiste em garantir que todos os computadores e outros dispositivos da organização possam executar o Microsoft Teams. Além de examinar os requisitos de hardware, isso também envolve a compreensão das outras atividades do computador em segundo plano. Muitas organizações executam outros softwares, incluindo sistemas de detecção de intrusões e software antimalware, o que pode afetar o desempenho básico de um dispositivo.

O Microsoft Teams tem clientes disponíveis para Web, desktops (Windows e Mac) e dispositivos móveis (Android, iOS e Windows Phone). Para obter informações sobre os requisitos de software de cada plataforma, consulte [Obter clientes para o Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Firewalls de ponto de extremidade

Os firewalls do lado do cliente podem ter um impacto significativo sobre a experiência do usuário. Os firewalls do lado do cliente podem afetar a qualidade das chamadas, além de impedir o estabelecimento da chamada. Configure as exclusões apropriadas no firewall do cliente de acordo com as informações contidas em [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365ips). O fornecedor terceirizado deve ter orientações específicas sobre como criar exclusões.

> [!NOTE]
> O Microsoft Teams atualizará automaticamente o Firewall do Windows com uma configuração de firewall apropriada.

### <a name="wi-fi-recommendations-for-endpoints"></a>Recomendações de Wi-Fi para pontos de extremidade

O planejamento e a implantação de uma rede Wi-Fi otimizada para dar suporte a cargas de trabalho em tempo real no Microsoft Teams exigirão um planejamento significativo. As seções a seguir fornecem algumas orientações gerais que podem ajudar a evitar alguns problemas comuns ao fazer o planejamento de pontos de extremidade.

#### <a name="wi-fi-drivers"></a>Drivers de Wi-Fi

Alguns drivers de Wi-Fi podem ser problemáticos. Como exemplo, um driver pode ter comportamentos de roaming muito agressivos entre os pontos de acesso, resultando na baixa qualidade das chamadas. Isso não é comum, mas é importante garantir que os drivers de Wi-Fi do computador tenham sido atualizados e testados antes da implantação.

#### <a name="wi-fi-bands"></a>Bandas de Wi-Fi

Existem dois tipos de bandas principais usadas atualmente nos equipamentos de Wi-Fi: 2,4 GHz e 5,0 GHz. Se a sua organização oferece as duas bandas, você deve configurar o driver para preferir a banda de 5,0 GHz. Essa banda é muito mais densa em termos de taxa de transferência, sendo menos afetada pela interferência observada na banda de 2,4 GHz. Essa recomendação presume que você tenha otimizado a banda de 5,0 GHz corretamente.

#### <a name="wi-fi-radio-type"></a>Tipo de rádio de Wi-Fi

Planeje usar dispositivos que dão suporte aos tipos de rádio de Wi-Fi mais novos. Você poderá obter excelente desempenho do Wi-Fi se utilizar o tipo 802.11ac ou mais recente nos dispositivos provisionados.

#### <a name="wireless-avoidance"></a>Rejeição de redes sem fio

Algumas organizações preferem evitar totalmente as redes Wi-Fi. Às vezes, essas orientação é fornecida por meio de uma recomendação de que os usuários se conectem diretamente a uma rede com fio. Em alguns casos, a ordem de associação de redes pode ter a conexão sem fio como preferencial e continuar usando essa conexão, mesmo que o computador esteja conectado à rede com fio. Para evitar esse comportamento indesejado, configure a ordem de associação de modo a evitar esse cenário.

#### <a name="80211-power-save-protocol"></a>Protocolo de economia de energia 802.11

Se a sua organização usa pontos de acesso ou roteadores sem fio que não dão suporte ao protocolo de economia de energia 802.11, as chamadas podem ser interrompidas ou ter baixa qualidade no Microsoft Teams em execução em dispositivos Windows. Se não for possível atualizar seus pontos de acesso ou roteadores sem fio, atualize as configurações do Plano de Energia do Windows dos dispositivos que funcionam com energia da bateria. Outros detalhes e orientações de configuração estão disponíveis neste [artigo de suporte](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

### <a name="devices-for-teams"></a>Dispositivos para o Microsoft Teams

O Microsoft Teams pode ser usado para reuniões ou como um sistema de telefonia. Ao usar esses recursos, o dispositivo de interface que é usado para o Microsoft Teams tem um papel importante na experiência do usuário.

O uso do viva-voz e do microfone internos do computador pode ser aceitável para os usuários que têm essa configuração. Porém, normalmente esses dispositivos não são otimizados para cancelamento de ruído, e qualquer tipo de ruído do ambiente pode afetar também os outros participantes da chamada. A utilização de dispositivos otimizados para esses cenários ajuda a garantira uma experiência de alta qualidade.

Cada dispositivo precisa atender às necessidades de seus usuários. Você precisará adaptar os dispositivos, como fones de ouvido com microfone, para as diferentes personas e os diferentes casos de uso em sua organização. Um exercício de mapeamento entre personas e dispositivos deve ser realizado como parte do processo de planejamento.

Depois de selecionar os dispositivos, inclua-os no plano de testes do piloto para a validação final. Faça pesquisas durante o piloto para obter comentários e assim garantir que sua estratégia de dispositivos seja a ideal.

No momento, recomendamos usar dispositivos de áudio certificados pelo Programa de Certificação do Skype for Business. Para saber quais dispositivos foram certificados por esse programa, consulte o catálogo de soluções [Dispositivos USB certificados para o Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Para obter mais detalhes, consulte [Cliente e dispositivos - workshop de preparação](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>Atualizações de cliente

Um dos principais benefícios do Microsoft Teams é que o cliente é atualizado automaticamente. Os clientes no PC e no Mac são atualizados por meio de um processo em segundo plano que verifica novos builds e baixa o novo cliente assim que o aplicativo fica ocioso. O tamanho do download do cliente é de aproximadamente 100 MB.

A organização não tem nenhum controle ou acesso à configuração da política para gerenciar o processo de atualização. Para mitigar o risco de um problema que possa ser descoberto em um build mais novo, a última versão íntegra conhecida é mantida no ponto de extremidade. Se houver algum problema com um novo build, o serviço Microsoft Teams poderá reverter automaticamente o ponto de extremidade para a versão anterior.

## <a name="next-steps-and-references"></a>Próximas etapas e referências

Esta tabela inclui um resumo das atividades de planejamento com links para o conteúdo relacionado.

| Área | Detalhes | Referências |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Planejar o gerenciamento do serviço | Realizar um exercício de mapeamento de funções operacionais <br/> Aprovação das equipes responsáveis <br/> Preparação de funções | [Guia de Operações](1-drive-value-operate-my-service.md) |
| | Nomear defensor(es) da qualidade <br/> Preparação do defensor da qualidade| [Learn CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [Guia de Revisão da Experiência de Qualidade](https://aka.ms/qerguide) |
| | Instalar os modelos de Revisão de Experiência da Qualidade <br/> Carregar um arquivo de construção | [Modelos QERLite](https://aka.ms/qertemplates) <br/> [Carregar informações de construção](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)|
| Planejar a qualidade da rede | Executar o Network Planner | [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | Implementar a QoS | [Qualidade de Serviço no Microsoft Teams](qos-in-teams.md) |
| | Contornar servidores proxy | [Orientações de proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | Implementar a VPN de túnel dividido | [Orientações de túnel dividido de VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Otimizar redes Wi-Fi para mídia em tempo real  | Consultar fornecedores terceirizados |
| | Implementar a saída para a Internet local | [Saída para a Internet local](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | Implementar a conectividade de rede <br/> Validar a conectividade de rede | [URLs e endereços IP do Office 365](https://aka.ms/o365ips) |
| | | [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) |
| | Realizar a avaliação da rede | [Avaliação da preparação da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| Planejar a qualidade dos pontos de extremidade | Atualizar os firewalls de ponto de extremidade | [URLs e endereços IP do Office 365](https://aka.ms/o365ips) |
| | Validar os requisitos de software | [Obter clientes do Microsoft Teams](get-clients.md) |
| | Implementar as recomendações de Wi-Fi para pontos de extremidade | Consultar fornecedores terceirizados |
| | Realizar o mapeamento entre personas e dispositivos <br/> Provisionar dispositivos e realizar o piloto com eles | [Cliente e dispositivos - workshop de preparação](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [Catálogo de dispositivos](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |