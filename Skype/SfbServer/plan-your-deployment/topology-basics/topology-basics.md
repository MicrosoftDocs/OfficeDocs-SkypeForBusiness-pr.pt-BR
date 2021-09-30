---
title: Noções básicas de topologia para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumo: escolha sua topologia para o Skype for Business Server. Saiba mais sobre a localização do servidor para o Skype for Business Server.'
ms.openlocfilehash: 3fae86501dfc0952bfb3fcf43347a1f0c9641536
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012525"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Noções básicas de topologia para o Skype for Business Server

**Resumo:** Escolha sua topologia para o Skype for Business Server. Saiba mais sobre a localização do servidor para o Skype for Business Server.

Antes de preparar qualquer outra coisa, você vai querer saber que está planejando a topologia certa para sua implantação do Skype for Business Server. A primeira coisa que você precisa decidir é se você vai ter uma implantação local do Skype for Business Server ou se você vai combinar isso com uma implantação do Skype for Business Server Online em uma implantação híbrida. De qualquer forma, você vai querer ler mais, pois detalhamos as topologias locais aqui, mas os detalhes híbridos são documentados em sua própria seção.

Você também pode ver algumas topologias de exemplo em [Topologias de referência para o Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>Sites

No Skype for Business Server, você define sites em sua rede que contêm componentes do Skype for Business Server. Um site é um conjunto de computadores bem conectados por uma rede de alta velocidade e baixa latência, como uma única rede local (LAN) ou duas redes conectadas por uma rede de fibra ótica de alta velocidade. Observe que os sites do Skype for Business Server são um conceito separado dos sites de Serviços de Domínio do Active Directory e Microsoft Exchange Server sites. Seus sites do Skype for Business Server não precisam corresponder aos sites do Active Directory.

O Skype for Business Server oferece suporte à implantação local de um ou mais sites que podem ser dimensionados de acordo com seus requisitos de alta disponibilidade e localização.

Sua implantação terá pelo menos um site central (também chamado de datacenter, este é um datacenter para todos os servidores localizados nele) e cada site central em sua implantação terá um servidor Standard Edition ou pelo menos um pool de Front-End enterprise Edition. Você pode ver as diferenças em cada opção abaixo:

- O servidor Standard Edition inclui um banco de dados SQL Server Express.

- O pool de Front-End do Enterprise Edition inclui:

  - Um ou mais Servidores Front-End (Idealmente, pelo menos três, para escalabilidade), com um máximo de doze. O balanceamento de carga seria necessário para mais de um servidor.

  - Um servidor back-end separado.

Você pode saber mais sobre as várias funções de servidor um pouco mais adiante nesta seção.

Além de seus sites centrais, você também pode acabar tendo um ou mais sites de filial associados ao seu site central. Eles dependem do site central para quase todas as funcionalidades, portanto, do que eles são feitos, exatamente?

- Aparelho de Filial Suportável, que combina um gateway PSTN (rede telefônica pública comutado), com algumas funcionalidades do Skype for Business Server.

- Servidor de Filial Suportável, é um servidor que executa o Windows Server que tem o Software do Registrador do Skype for Business Server e o Servidor de Mediação instalados.

- Gateway PSTN autônomo (que não faz parte do Aparelho de Filial Suportável).

- Servidor de Mediação autônomo ou pool de Servidor de Mediação autônomo (se você não quiser reajustar essa função com o Aparelho de Filial Desavivável).

## <a name="whats-in-a-skype-for-business-server-site"></a>O que há em um site do Skype for Business Server?

Para entrar em mais detalhes, um site central também pode ter:

- Vários pools de Front-End, no mesmo domínio ou domínios diferentes (lembre-se de planejar que todos os Servidores Front-End em um pool de Front-End, juntamente com os Servidores Back-End para o pool, devem estar no mesmo domínio).

- Diversos Servidores Standard Edition.

- Servidor do Office Web Apps, que é usado com o Office Web Apps no Skype for Business Server para compartilhamento e renderização de apresentações do PowerPoint.

- Servidor de Borda ou Pool de Borda (em uma rede de perímetro). Necessário se você quiser que sua implantação suporte parceiros federados, conectividade de IM pública, gateway XMPP (extensible messaging and presence protocol) e acesso de usuário remoto. Mais detalhes podem ser encontrados na documentação planejamento do Servidor de Borda.

- Servidor de Chat Persistente. Útil se você quiser que os usuários sejam capazes de participar de conversas baseadas em vários tópicos que persistem ao longo do tempo. Há mais informações no tópico Planejamento do Servidor de Chat Persistente.

- Monitoramento. Usado para dar suporte à coleta de dados para qoE (qualidade de experiência de áudio/vídeo) e cdr (gravação de detalhes de chamada) para conferências de Enterprise Voice e A/V em sua implantação. Discutimos isso em detalhes no tópico Planejamento para Monitoramento.

- Pool de diretores ou diretores. Não obrigatório, mas útil se você quiser melhorar a resiliência e habilitar o redirecionamento de solicitações de usuário do Skype for Business para o pool 1 do usuário. Se você quiser implantar Diretores, há suporte para no máximo 10 por pool. Se isso for algo de que você precisa, definitivamente continue lendo no tópico Planejamento para Diretores.

- Proxy Reverso. Este não é um componente do Skype for Business Server, mas se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados, se você pretende dar suporte ao tráfego mobility, se os usuários remotos quiserem usar o livro de endereços, participar de reuniões e assim por diante, isso é algo que você deseja ter em seu ambiente. Há um tópico Configurando o servidor proxy reverso que você pode verificar para obter mais detalhes, quando estiver pronto.

Informações adicionais sobre a localização desses servidores podem ser encontradas abaixo.

Todos os pools de Front-End e servidores Standard Edition implantados em seu site central compartilham o seguinte, supondo que você os tenha implantado:

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|Pool de diretores ou diretores   |Servidor de Mediação Autônomo ou Pool de Servidores de Mediação   |Servidor do Office Web Apps   |
|Servidor de Borda ou Pool de Borda   |Servidor de Chat Persistente ou Pool de Servidor de Chat Persistente   |Monitoramento   |

Onde está o Servidor de Unificação de Mensagens (UM) do Exchange nesta lista? Bem, você certamente pode usá-lo com o Skype for Business Server se quiser integrar-se à UM do Exchange, mas não é um componente do site do Skype for Business Server, portanto, não estamos mencionando isso aqui.

Você pode estar planejando ter vários sites centrais e, se for esse o caso, eles poderão compartilhar os seguintes servidores e funções, se eles são implantados em seu site central:

|&nbsp;|&nbsp;|
|:-----|:-----|
|Servidor de Mediação Autônomo ou Pool de Servidores de Mediação   |Servidor de Borda ou Pool de Borda   |
|Servidor de Chat Persistente ou Pool de Servidor de Chat Persistente   |Monitoramento   |

Assim como a última lista, não estamos incluindo o Servidor de UM do Exchange aqui porque ele não faz parte da implantação do Skype for Business Server, mas também se enquadra na mesma categoria aqui.

Há alguns outros componentes e opções que vão para implantações, é claro.

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|Firewalls   |Gateways PSTN (se você implantar Enterprise Voice   |Exchange UM Server (se você deseja integrar-se à UM do Exchange)   |Balanceamento de carga DNS   |
|Balanceadores de carga de hardware   |SQL Server bancos de dados   |Compartilhamentos de arquivo   ||

## <a name="server-roles"></a>Funções de servidor

Cada servidor que executa o Skype for Business Server executa uma ou mais funções de servidor. Uma função de servidor é um conjunto definido de funcionalidades do Skype for Business Server fornecidas por esse servidor. Você não precisa implantar todas as funções de servidor disponíveis em sua rede. Instale somente as funções com a funcionalidade desejada.

Na maioria das funções de servidor, para escalabilidade e alta disponibilidade você pode implantar pools de vários servidores, todos executando a mesma função de servidor. Cada servidor em um pool deve executar uma função ou funções do servidor idênticas. Para a maioria dos tipos de pools no Skype for Business Server, você deve implantar um balanceador de carga para propagar o tráfego entre os vários servidores no pool. O Skype for Business Server oferece suporte ao balanceamento de carga dns e balanceadores de carga de hardware.

### <a name="front-end-server-and-back-end-server"></a>Servidor de front-end e Servidor de back-end

No Skype for Business Server Enterprise Edition, o Servidor front-end é a função de servidor principal e executa muitas funções básicas do Skype for Business Server. O Servidor Front-End, juntamente com os Servidores Back-End, são as únicas funções de servidor necessárias para estar em qualquer implantação do Skype for Business Server Enterprise Edition.

Um pool de Front-Ends é um conjunto de servidores Front-End, configurados de forma idêntica, que trabalham juntos para fornecer serviços a um grupo de usuários comuns. Um pool de vários servidores executando a mesma função fornece a capacidade de escalabilidade e failover.

O servidor Front-End inclui:

- Autenticação e registro do usuário.

- Informações de presença e troca de cartão de visita.

- Serviços de lista de endereços e expansão de lista de distribuição.

- Funcionalidade de IM, incluindo conferências de IM de várias partes.

- Webconferência, conferência discada PSTN e conferência A/V (se implantado).

- Hospedagem de aplicativos, para ambos os aplicativos incluídos no Skype for Business Server (por exemplo, o assistente de conferência e o aplicativo grupo de resposta) e aplicativos de terceiros.

- Opcionalmente, Monitoramento para coletar informações de uso na forma de CDRs (registros de detalhes de chamada) e CERs (registros de erros de chamada). Essas informações fornece métricas sobre a qualidade da mídia (áudio e vídeo) percorrendo sua rede para chamadas Enterprise Voice e conferências A/V.

- Componentes da Web para tarefas compatíveis com base na Web, como agendador da Web e iniciador de ingresso.

- Opcionalmente, Arquivamento para arquivar comunicações de mensagens instantâneas e conteúdo de reunião por motivos de conformidade. Para obter detalhes, consulte [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving) na documentação de planejamento.

    No Lync Server 2010 e nas versões anteriores, Monitoramento e Arquivamento eram funções de servidor separadas, não alocadas no Servidor Front-End.

- Opcionalmente, e o chat persistente estiver habilitado, serviços Web de chat persistente para gerenciamento de salas de chat e serviços Web de chat persistente para upload/download de arquivos.

Os pools front-end também são o repositórios principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três servidores front-end no pool, e o backup delas é realizado nos servidores back-end.

Além disso, um Servidor front-end na implantação também executa o Servidor de Gerenciamento Central, que gerencia e implanta dados básicos de configuração para todos os servidores que executam o Skype for Business Server. O Servidor de Gerenciamento Central também fornece recursos de Shell de Gerenciamento do Lync Server e transferência de arquivos.

Os Servidores Back-End são servidores de banco de dados que executam Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de Front-End. Os Servidores Back-End servem como armazenamentos de backup para os dados de usuário e conferência do pool e são os principais armazenamentos para outros bancos de dados, como o banco de dados do Grupo de Resposta. Você pode ter um único Servidor Back-End, mas a alta disponibilidade do [Servidor Back-End](../high-availability-and-disaster-recovery/back-end-server.md) no Skype for Business Server é recomendada para failover. Os Servidores Back-End não são executados em nenhum software do Skype for Business Server.

> [!IMPORTANT]
> Não recomendamos a localização de bancos de dados do Skype for Business Server com outros bancos de dados. Caso contrário, a disponibilidade e o desempenho poderão ser afetados.

> [!NOTE]
> SQL espelhamento está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, Instâncias de Cluster de Failover AlwaysOn (FCI) e SQL de cluster de failover são preferenciais com o Skype for Business Server 2019.

As informações armazenadas nos bancos de dados do servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferência, incluindo os dados persistentes sobre o estado de todas as conferências atuais e dados de agendamento de conferência.

### <a name="edge-server"></a>Servidor de Borda

O Servidor de Borda permite que seus usuários se comuniquem e colaborem com usuários fora dos firewalls da organização. Esses usuários externos podem incluir os próprios usuários da organização que estão trabalhando fora do local, usuários de organizações parceiras federadas e usuários externos que foram convidados a participar de conferências hospedadas em sua implantação do Skype for Business Server.

A implantação do servidor de borda também habilita serviços de mobilidade, com suporte à funcionalidade do Lync em dispositivos móveis. Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades como enviar e receber mensagens instantâneas, exibir contatos e exibir presença. Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas. O recurso de mobilidade também oferece suporte a notificações por push para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.

Os servidores de borda também incluem um proxy XMPP completamente integrado, com um gateway XMPP incluído nos servidores front-end. Você pode configurar esses componentes XMPP para permitir que seus usuários do Skype for Business Server adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas e presença.

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não são mais suportados no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

### <a name="mediation-server"></a>Servidor de Mediação

O Servidor de Mediação é um componente necessário para implementar Enterprise Voice, chamada via trabalho e conferência discda. O Servidor de Mediação converte a sinalização e, em algumas configurações, a mídia entre sua infraestrutura interna do Skype for Business Server e um gateway PSTN (rede telefônica pública comutado), IP-PBX ou um tronco SIP (Session Initiation Protocol). Você pode executar o Servidor de Mediação colocado no mesmo servidor do servidor front-end ou separado em um pool de Servidor de Mediação independente.

Para obter detalhes, consulte [Componente do Servidor de Mediação no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de Interoperabilidade de Vídeo

O Servidor de Interop de Vídeo é uma nova função do Skype for Business Server 2015. Ele permite integrar sua implantação do Skype for Business Server a determinadas soluções de VTC (Video Teleconferencing System) de terceiros. Um VIS atua como um intermediário entre um sistema de teleconferência de terceiros e uma implantação do Skype for Business Server. Para essa versão, o VIS está focado na interoperabilidade com sistemas de vídeo cisco/Tandberg.

Para obter detalhes, [consulte Plan for Video Interop Server in Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Diretor

Os diretores podem autenticar solicitações de usuário do Skype for Business Server, mas eles não têm contas de usuário em casa ou fornecem serviços de presença ou conferência. Os diretores são mais úteis para aprimorar a segurança em implantações que permitam o acesso de usuários externos. O diretor pode autenticar solicitações antes de enviá-las a servidores internos. No caso de ataque de negação de serviço, o ataque termina no diretor e não atinge os servidores front-end.

### <a name="persistent-chat-server-roles"></a>Funções do servidor de chat persistente

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Como começar com a atualização do Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

O chat persistente permite que os usuários participem de conversações baseadas em tópicos com várias pessoas. Essas conversas persistem ao longo do tempo. O servidor front-end de chat persistente executa o serviço de chat persistente. O servidor back-end de chat persistente armazena os dados de histórico e as informações sobre categorias e salas de chat. O servidor back-end de conformidade de chat persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.

Os servidores que executam o Skype for Business Server Standard Edition também podem executar chat persistente alocado no mesmo servidor. Não é possível colocar o Servidor Front-End de Chat Persistente com o Servidor De Front-End enterprise Edition.

Para obter detalhes, [consulte Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Suporte a alta disponibilidade e recuperação de desastres

O Skype for Business Server fornece alta disponibilidade por redundância de servidor por meio do pool. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor. Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.

O Skype for Business Server também fornece medidas de recuperação de desastres habilitando o emparelhamento de pool. Sr você implantar tal topologia, pode designar pares para pools de Front End, com cada pool em um par localizado em um datacenter separado, e em uma área geográfica separada. Se um pool ou site sair do ar, você pode redirecionar os usuários deste pool para outro pool no par, com o mínimo de interrupção de serviço.

O Skype for Business Server também oferece suporte a várias opções para alta disponibilidade do Servidor Back-End. Elas incluem o seguinte:

- Espelhamento do banco de dados

- Grupos de disponibilidade AlwaysOn

- Instâncias de Cluster de Failover AlwaysOn (FCI)

- SQL clustering de failover

Para obter detalhes sobre emparelhamento de pool e alta disponibilidade do Servidor Back-End, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Localização de servidor no Skype for Business Server

Já utilizamos o termo collocate, mas o que isso significa? O Skype for Business Server permite que você localize algumas funções de servidor e recursos no mesmo servidor, que é a colocação ou em servidores diferentes, mas pode ser confuso quando você está começando e se você está fazendo uma implantação de servidor Standard Edition ou Enterprise Edition (cada uma delas vem com suas próprias regras). Para ajudar no planejamento, incluímos a colocação de servidor em implantações de servidor Standard Edition e implantações de pool de Front-End enterprise edition (na maioria dos casos, essas informações são idênticas e onde são diferentes, são chamadas especificamente).

### <a name="collocation-of-server-roles"></a>Collocação de funções de servidor

O servidor Standard Edition tem a seguinte função alocada (a configuração adicional é necessária no entanto), enquanto no pool de Front-End enterprise Edition, essa função pode ser locada ou implantada em um servidor separado:

- Mediação

Essas funções de servidor devem ser implantadas em um servidor separado:

- Diretor

- Borda

- Servidor de Interoperabilidade de Vídeo

- Office Web Apps

### <a name="databases"></a>Bancos de dados

Esta é a área com diferenças reais entre implantações de servidor Standard Edition e implantações de pool de servidores Enterprise Edition, portanto, teremos duas seções abaixo, seguidas de algumas regras adicionais para ambos.

#### <a name="standard"></a>Padrão

Como SQL Server Express é alocado no servidor Standard Edition e não pode ser movido, isso é bastante simples. Além disso, se você implantar o Servidor de Chat Persistente em um servidor Standard Edition, também poderá colocar o Chat Persistente e o banco de dados de conformidade de Chat Persistente no servidor Standard Edition também, mas não é preciso.

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Como começar com a atualização do Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

Eles não podem ser alocados no servidor Standard Edition, mas podem ir para um único servidor de banco de dados por conta própria:

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Qualquer banco de dados back-end para um pool de front-end do Enterprise Edition

#### <a name="enterprise"></a>Corporativo

Os bancos de dados a seguir podem ser alocados no mesmo back-end SQL Server:

- Banco de dados back-end

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de Chat Persistente

- Banco de dados de conformidade de Chat Persistente

#### <a name="both"></a>Ambos

Agora, há algumas regras adicionais a seguir ao localizar bancos de dados do Skype for Business Server em uma única instância SQL ou em várias instâncias SQL no mesmo banco de dados SQL Server:

- Cada SQL pode conter apenas um único banco de dados de back-end para um pool de Front-End enterprise edition, um único banco de dados de Monitoramento, um único banco de dados de Arquivamento, um único banco de dados de Chat Persistente e um único banco de dados de conformidade de Chat Persistente.

- O servidor de banco de dados não pode suportar mais de um pool de Front-End enterprise Edition, um servidor executando Arquivamento, um servidor executando Monitoramento, um único banco de dados de Chat Persistente e um único banco de dados de conformidade de Chat Persistente, mas pode dar suporte a um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.

    > [!NOTE]
    > O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Como começar com a atualização do Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

### <a name="file-shares"></a>Compartilhamentos de arquivo

O compartilhamento de arquivos pode estar em um servidor separado ou você pode coloá-lo no mesmo servidor que qualquer um dos seguintes:

- Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de Chat Persistente

- Banco de dados de conformidade de Chat Persistente

> [!CAUTION]
> Observe que, embora você possa colocar o compartilhamento de arquivos nesses servidores, é fundamental observar que não o recomendamos. Se você estiver localizando o compartilhamento de arquivos com qualquer outra função de servidor, verifique se está monitorando os problemas de espaço em disco e desempenho regularmente.

### <a name="keep-in-mind"></a>Tenha em mente

- Você não pode colocar um servidor proxy reverso, que não é um componente Skype for Business Server e pode nem estar em sua topologia. Você precisará de um proxy reverso se quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados, entre muitas outras coisas. Se precisar, vá em frente e implemente o suporte a proxy reverso para Skype for Business Server configurando um servidor proxy reverso existente que já está em sua organização que está sendo usado por outros aplicativos.

- Não é possível reajustar nenhum componente Exchange um ou SharePoint Server com qualquer função Skype for Business Server.

## <a name="see-also"></a>Confira também

[Topologias de referência para Skype for Business Server](reference-topologies.md)