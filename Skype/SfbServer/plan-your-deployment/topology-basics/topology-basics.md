---
title: Noções básicas de topologia para Skype para Business Server
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumo: Escolha sua topologia para Skype para Business Server. Saiba mais sobre a colocação do servidor para Skype para Business Server.'
ms.openlocfilehash: 566d044defd69dd9ae79bc964c9a587332649b42
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205969"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Noções básicas de topologia para Skype para Business Server

**Resumo:** Escolha sua topologia para o Skype para Business Server. Saiba mais sobre a colocação do servidor para Skype para Business Server.

Antes de preparar qualquer outra coisa, você vai querer saber que você estiver planejando para a topologia adequada para sua implantação do Skype para Business Server. A primeira coisa que você precisará decidir é se você vai ter uma implantação local do Skype para Business Server, ou se você vai combinar isso com um Skype para implantação Business Server Online em uma implantação híbrida. De qualquer forma, você vai desejamos ler Além disso, como podemos vai detalham as topologias de local aqui, mas os detalhes de híbrido documentados em sua própria seção.

Você também pode ver alguns exemplos de topologias em [topologias de referência para Skype para Business Server](reference-topologies.md).

## <a name="sites"></a>Sites

Skype para Business Server, você define sites em sua rede que contêm Skype para componentes de servidor de negócios. Um site é um conjunto de computadores conectados por meio de uma rede de alta velocidade e baixa latência, como uma rede local (LAN), ou de duas redes conectadas por uma rede de fibra ótica de alta velocidade. Observe que o Skype para sites de Business Server são um conceito separado em sites do Microsoft Exchange Server e sites do Active Directory Domain Services. Não é necessário que sua Skype para sites de Business Server correspondem aos seus sites do Active Directory.

Skype para Business Server oferece suporte a implantação de local de um ou mais sites que podem ser dimensionados de acordo com suas necessidades de local e a alta disponibilidade.

Sua implantação terá pelo menos um site central (também chamado de um datacenter, isso é um datacenter para todos os servidores localizados nela), e cada site central em sua implantação terá um servidor Standard Edition ou pelo menos um pool de Front End do Enterprise Edition. Veja abaixo as diferenças em cada opção:

- Servidor Standard Edition inclui um banco de dados colocado do SQL Server Express.

- Pool de Front End do Enterprise Edition inclui:

  - Um ou mais servidores Front-End (idealmente pelo menos três, para escalabilidade), com um máximo de doze. O balanceamento de carga seria necessário para mais de um servidor.

  - Um separado servidor Back-End.

Você aprenderá mais sobre as diversas funções de servidor mais adiante nesta seção.

Além dos seus locais centrais, você também pode acabar tendo um ou mais sites de filiais associados ao seu site central. Eles dependem o site central para quase todas as suas funcionalidades, portanto quais são eles formada, exatamente?

- Aparelho de filial persistente, que combina um gateway PSTN (rede) telefônica pública comutada, com algumas Skype para a funcionalidade do servidor de negócios.

- Servidor de filial persistente, é um servidor executando o Windows Server que tenha Skype para negócios servidor registrador e o software de servidor de mediação instalado.

- Gateway PSTN autônomo (que não fazem parte do aparelho de filial persistente).

- Servidor de mediação autônomo ou pool do servidor de mediação autônomo (se você não deseja colocar essa função com o aparelho de filial persistente).

## <a name="whats-in-a-skype-for-business-server-site"></a>O que há em um Skype para site de Business Server?

Para obter mais detalhes, um site central também pode ter:

- Vários pools Front-End no mesmo domínio ou em domínios diferentes (Lembre-se no planejamento de que todos os servidores Front-End em um pool de Front-End, juntamente com os servidores Back-End para o pool, é preciso estar no mesmo domínio).

- Vários servidores Standard Edition.

- Office Web Apps Server, que é usado com o Office Web Apps no Skype para Business Server para compartilhamento e de renderização de apresentações do PowerPoint.

- Pool do servidor de borda ou de borda (em uma rede de perímetro). Necessário se você desejar que a sua implantação ofereça suporte para parceiros federados, conectividade a redes públicas de mensagens instantâneas, gateway XMPP e acesso de usuários remotos. Mais detalhes podem ser encontrados na documentação de planejamento do servidor de borda.

- Servidor de Chat persistente. Útil se você desejar que os usuários possam participar de conversas baseadas em tópico persistentes com vários participantes. Não há mais informações em Planning for tópico Persistent Chat Server.

- Monitoramento. Usado para oferecer suporte a coleta de dados para áudio/vídeo (A / V) Quality of Experience (QoE) e chamada detalham recording (CDR) para o Enterprise Voice e uma / conferências de V em sua implantação. Esse assunto será abordado em mais detalhes no tópico Planejamento do Monitoramento.

- Diretor ou pool de diretores. Não é necessária, mas útil se você deseja melhorar a resiliência e habilitar o redirecionamento do Skype para solicitações de usuário de negócios para o pool base do usuário. Se você deseja implantar os diretores, há suporte para um máximo de 10 por pool. Caso se trate algo que você precisa, definitivamente continue lendo em Planning for tópico diretores.

- Proxy reverso. Isso não é um Skype para o componente do servidor de negócios, mas se você quiser suportar o compartilhamento de conteúdo da web para usuários federados, se você pretende suportar o tráfego de mobilidade, se quiserem que os usuários remotos usar o catálogo de endereços, reuniões de ingresso e assim por diante, isso é algo que você vai deseja que tenham em seu ambiente. Não há uma configuração de tópico de servidor de proxy reverso, que Confira para obter mais detalhes, quando você estiver pronto para cima.

Mais Informações sobre a colocação desses servidores podem ser encontradas a seguir.

Todos os pools de Front-End e servidores Standard Edition implantados no seu site central compartilham a seguir, supondo que você implantou-las:

||||
|:-----|:-----|:-----|
|Diretor ou pool de diretores  <br/> |Servidor de mediação autônomo ou pool de servidor de mediação  <br/> |Servidor Office Web Apps  <br/> |
|Pool de servidor de borda ou de borda  <br/> |Pool de servidor de Chat persistente ou de servidor de Chat persistente  <br/> |Monitoramento  <br/> |

Onde está o servidor do Exchange Unified Messaging (UM) nesta lista? Bem, você pode certamente usá-lo com Skype para Business Server se você deseja integrar com UM do Exchange, mas não é um componente do Skype para site de Business Server, portanto, podemos não estiver mencioná-lo aqui.

Você pode estar planejando ter vários sites centrais e se for assim, eles podem compartilhar os seguintes servidores e funções, se eles são implantados em seu site central:

|||
|:-----|:-----|
|Servidor de mediação autônomo ou pool de servidor de mediação  <br/> |Pool de servidor de borda ou de borda  <br/> |
|Pool de servidor de Chat persistente ou de servidor de Chat persistente  <br/> |Monitoramento  <br/> |

Assim como última lista, podemos não incluindo UM servidor Exchange aqui porque ele não faz parte do Skype a implantação de servidor de negócios, mas ele enquadra aqui, a mesma categoria muito.

Também há outros componentes e opções incluídos nas implantações.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Gateways PSTN (se você implantar o Enterprise Voice)  <br/> |UM servidor Exchange (se você deseja integrar com UM do Exchange)  <br/> |Balanceamento de carga DNS  <br/> |
|Balanceadores de carga de hardware  <br/> |Bancos de dados do SQL Server  <br/> |Compartilhamentos de arquivo  <br/> ||

## <a name="server-roles"></a>Funções de servidor

Cada servidor que executa o Skype para Business Server executa uma ou mais funções de servidor. Uma função de servidor é um conjunto definido de Skype para funcionalidades Business Server fornecido por esse servidor. Você não precisa implantar todas as funções de servidor disponíveis na sua rede. Instale somente as funções que contêm a funcionalidade desejada.

Na maioria das funções de servidor, para fins de escalabilidade e alta disponibilidade, você pode implantar pools de vários servidores, todos executando a mesma função. Cada servidor de um pool deve executar funções idênticas de servidor. Para a maioria dos tipos de pools em Skype para Business Server, você deve implantar um balanceador de carga para difundir o tráfego entre os vários servidores no pool. Skype para Business Server suporta o balanceamento de carga de sistema de nome de domínio (DNS) e balanceadores de carga de hardware.

### <a name="front-end-server-and-back-end-server"></a>Servidor Front-End e Servidor Back-End

No Skype para Business Server Enterprise Edition, servidor Front-End é a função de servidor de núcleo e executa muitos Skype básico para funções de servidor de negócios. Servidor Front-End, juntamente com os servidores Back-End, são as funções de servidor único necessárias para estar em qualquer Skype para implantação Business Server Enterprise Edition.

Um pool de Front-End é um conjunto de servidores Front-End, configurados de forma idêntica, que trabalham juntos para fornecer serviços para um grupo de usuários comuns. Um pool de vários servidores que executa a mesma função fornece escalabilidade e o recurso de failover.

Servidor Front-End inclui o seguinte:

- Autenticação e registro de usuários.

- Informações de presença e troca de cartões de visita.

- Serviços de catálogo de endereços e expansão da lista de distribuição.

- Funcionalidade de IM, incluindo conferências de IM com vários participantes.

- Webconferência, conferência discada PSTN e conferência de áudio/vídeo (se implantada).

- Hospedagem de aplicativos, para aplicativos incluídos com Skype para Business Server (por exemplo, aplicativo Atendedor de conferência e o grupo de resposta) e aplicativos de terceiros.

- Opcionalmente, Monitoramento, para coleta de informações de uso na forma de registros de detalhes das chamadas (CDRs) e registros de erros das chamadas (CERs). Essas informações fornecem métricas sobre a qualidade da mídia (áudio e vídeo) atravessando a sua rede para chamadas do Enterprise Voice e uma / conferências V.

- Componentes da Web para tarefas com suporte baseadas na Web, como agendador da Web e iniciador de ingresso.

- Opcionalmente, Arquivamento, para arquivar o conteúdo de reuniões e comunicações de IM por motivos de conformidade. Para obter detalhes, consulte [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) na documentação de Planejamento.

    No Lync Server 2010 e versões anteriores, monitoramento e arquivamento eram funções de servidor separadas, não alocadas no servidor Front-End.

- Opcionalmente, se o chat Persistente estiver habilitado, Serviços Web de Chat Persistente para Gerenciamento de Salas de Chat e Serviços Web de Chat Persistente para Upload/Download de Arquivos.

Os Pools de Front-Ends também são o repositório principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três Servidores Front-End do pool, e o seu backup é realizado nos Servidores Back-End.

Além disso, um servidor Front-End na implantação também executa o servidor de gerenciamento Central, que gerencia e instala os dados de configuração básica para todos os servidores que executam o Skype para Business Server. O servidor de gerenciamento Central também fornece o Shell de gerenciamento do Lync Server e os recursos de transferência de arquivos.

Os servidores Back-End são os servidores de banco de dados executando o Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de Front-End. Os servidores Back-End servir como repositórios de backup para o usuário e os dados de conferência do pool e são os armazenamentos principais para outros bancos de dados, como o banco de dados do grupo de resposta. Você pode ter um único servidor Back-End, mas o [servidor Back-End de alta disponibilidade em Skype para Business Server](../high-availability-and-disaster-recovery/back-end-server.md) é recomendado para failover. Servidores back-End não execute qualquer Skype para o software do servidor de negócios.

> [!IMPORTANT]
> Não é recomendável colocar Skype para bancos de dados de Business Server com outros bancos de dados. Se você fizer isso, disponibilidade e desempenho podem ser afetados.

> [!NOTE]
> Espelhamento do SQL está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. Os métodos de cluster de failover de grupos de disponibilidade AlwaysOn, instâncias de Cluster de Failover AlwaysOn (FCI) e SQL terão preferência com Skype para Business Server 2019.

As informações armazenadas nos bancos de dados do Servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferências, como dados persistentes sobre o estado de todas as conferências atuais, e dados de agendamento de conferências.

### <a name="edge-server"></a>Servidor de Borda

Servidor de borda permite que os usuários se comuniquem e colaborem com os usuários fora dos firewalls da organização. Esses usuários externos podem incluir os usuários da organização que estão atualmente trabalhando fora do local, os usuários de organizações de parceiros federados e usuários externos que foram convidados para ingressar em conferências hospedadas no seu Skype para implantação de servidor de negócios.

Implantando o servidor de borda também permite que os serviços de mobilidade, que oferece suporte à funcionalidade do Lync em dispositivos móveis. Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades, como enviar e receber mensagens instantâneas, e exibir contatos e presença. Além disso, os dispositivos móveis oferece suporte a alguns recursos do Enterprise Voice, como Clique para ingressar em uma conferência, chamada via trabalho, acesso a único número, caixa postal e chamadas perdidas. O recurso de mobilidade também oferece suporte a notificações por push em dispositivos móveis que não aceitam aplicativos executados em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.

Os Servidores de Borda também incluem um proxy XMPP (Extensible Messaging and Presence Protocol) totalmente integrado, com um gateway XMPP nos Servidores Front-End. Você pode configurar esses componentes XMPP para permitir que seu Skype para usuários corporativos Server adicionar contatos de parceiros XMPP para mensagens instantâneas e presença.

> [!NOTE]
> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019. Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

### <a name="mediation-server"></a>Servidor de Mediação

Servidor de mediação é um componente necessário para implementar o Enterprise Voice, chamadas Via trabalho e conferência discada. Servidor de mediação converte a sinalização e, em algumas configurações, mídia entre seu Skype interno para a infra-estrutura de servidor de negócios e uma pública comutada telefônica gateway PSTN (rede), IP-PBX ou um tronco de protocolo de iniciação de sessão (SIP). Você pode executar o servidor de mediação colocado no mesmo servidor como um servidor Front-End, ou separado em um pool do servidor de mediação autônomo.

Para obter detalhes, consulte o [componente de servidor de mediação em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de Interoperabilidade de Vídeo

Servidor de interoperabilidade de vídeo é uma nova função a partir do Skype para Business Server 2015. Ele permite que você integre sua Skype para implantação de servidor de negócios determinadas soluções VTC (Video Teleconferencing System) de terceiros. Um VIS atua como um intermediário entre um sistema de teleconferência de terceiros 3º e um Skype para implantação de servidor de negócios. Nesta versão, o enfoque do VIS está na interoperabilidade com sistemas de vídeo da Cisco e da Tandberg.

Para obter detalhes, consulte [Planejar para o servidor de interoperabilidade de vídeo no Skype para Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Diretor

Diretores podem autenticar Skype para solicitações de usuário de servidor de negócios, mas não hospedar contas de usuário ou fornecer presença ou serviços de conferência. Eles são úteis principalmente para aumentar a segurança em implantações que permitem o acesso de usuários externos. O Diretor pode autenticar as solicitações antes de enviá-las aos servidores internos. Em caso de um ataque de negação de serviço, o ataque termina no Diretor e não atinge os servidores Front-End.

### <a name="persistent-chat-server-roles"></a>Funções de servidor de bate-papo persistente

> [!NOTE]
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.

O chat persistente permite que os usuários participem de conversas baseadas em tópicos com vários participantes e que persistem ao longo do tempo. O Servidor Front-End de Chat Persistente executa o serviço de chat persistente. O Servidor Back-End de Chat Persistente armazena os dados de histórico de chat, bem como as informações sobre categorias e salas de chat. O Servidor Back-End de Conformidade de Chat Persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.

Servidores que executam o Skype para Business Server Standard Edition também pode executar o bate-papo persistente colocado no mesmo servidor. Você não pode ser colocada Persistent Chat servidor Front-End com servidor de Front End Enterprise Edition.

Para obter detalhes, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Suporte para alta disponibilidade e recuperação de desastre

Skype para Business Server oferece alta disponibilidade por redundância de servidor por meio do pool. Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor. Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.

Skype para Business Server também fornece desastres medidas de recuperação, permitindo pareamento de pool. Se implantar essa topologia, você designará pares de pools de Front-Ends, com cada pool de um par localizado em um datacenter e em uma área geográfica distinta. Se um pool ou site ficar inativo, você poderá redirecionar os usuários desse pool para outro pool do par, com o mínimo de interrupção de serviço.

Skype para Business Server também oferece suporte a várias opções de alta disponibilidade do servidor Back-End. Isso inclui o seguinte:

- Espelhamento de banco de dados

- Grupos de Disponibilidade Sempre Visíveis

- Instâncias de Cluster de Failover AlwaysOn (FCI)

- Clustering de failover do SQL

Para obter detalhes sobre o pareamento de pool e alta disponibilidade do servidor Back-End, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Posicionamento do servidor em Skype para Business Server

Usamos o termo colocar já, mas o que isso significa? Skype para Business Server permite que você localize alguns recursos e funções de servidor no mesmo servidor, que é de colocação, ou em servidores diferentes, mas pode ser confusa quando você está iniciando check-out e se você estiver fazendo um servidor Standard Edition ou Enterprise Edition implantação (cada um deles vêm com seus próprios regras). Para ajudar no seu planejamento, estamos incluindo colocação do servidor em implantações de servidor do Standard Edition e implantações de pool de Front End do Enterprise Edition (na maioria dos casos, essa informação é idêntica e onde ele está diferente, ele é chamado check-out especificamente).

### <a name="collocation-of-server-roles"></a>Colocação de funções de servidor

O servidor Standard Edition tem as seguintes role colocado (configuração adicional é necessária entanto), enquanto estiver no pool de Front End do Enterprise Edition, essa função pode ser colocada ou implantada em um servidor separado:

- Mediação

As seguintes funções de servidor devem ser implantadas em um servidor separado:

- Diretor

- Borda

- Servidor de Interoperabilidade de Vídeo

- Office Web Apps

### <a name="databases"></a>Bancos de dados

Essa é a área com reais diferenças entre as implantações de servidor do Standard Edition e implantações de pool do servidor Enterprise Edition, então teremos que duas seções a seguir, seguido por algumas regras adicionais para ambos.

#### <a name="standard"></a>Standard

Como o SQL Server Express é colocado no servidor do Standard Edition e não podem ser movido, isso é muito simples. Além disso, se você implantar o servidor de Chat persistente em um servidor Standard Edition, você também é capaz de colocar o Chat persistente e o Chat persistente conformidade banco de dados no servidor do Standard Edition muito, mas não é necessário.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Esses não podem ser colocadas no servidor Standard Edition, mas podem passar em um servidor de banco de dados único de suas próprias:

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Qualquer banco de dados de back-end para um pool de Front End do Enterprise Edition

#### <a name="enterprise"></a>Enterprise

Os seguintes bancos de dados podem ser colocados no mesmo back-end do SQL Server:

- Banco de dados back end

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de bate-papo persistente

- Banco de dados de conformidade de bate-papo persistente

#### <a name="both"></a>Ambos

Agora, há algumas regras adicionais a seguir ao colocando Skype para bancos de dados do servidor de negócios em uma única instância SQL ou em várias instâncias do SQL no mesmo banco de dados do SQL Server:

- Cada instância SQL pode conter somente um banco de dados de back-end único para um pool de Front End do Enterprise Edition, um único banco de dados de monitoramento, um único banco de dados de arquivamento, um único banco de dados de Chat persistente e um único Chat persistente conformidade banco de dados.

- O servidor de banco de dados não oferece suporte a mais de um pool de Front End do Enterprise Edition, um servidor executando o arquivamento, um servidor executando o monitoramento, um único banco de dados de Chat persistente e um único Chat persistente conformidade banco de dados, mas ele pode oferecer suporte a um de cada, independentemente do tipo os bancos de dados que usar a mesma instância do SQL Server ou instâncias separadas do SQL Server.

    > [!NOTE]
    > Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.

### <a name="file-shares"></a>Compartilhamentos de arquivo

O compartilhamento de arquivo pode estar em um servidor separado ou você pode colocá-lo no mesmo servidor que qualquer um destes componentes:

- Servidor de banco de dados, incluindo o servidor Back-End de um pool de Front End do Enterprise Edition

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de bate-papo persistente

- Banco de dados de conformidade de bate-papo persistente

> [!CAUTION]
> Observe que, embora seja possível colocar o compartilhamento de arquivos nesses servidores, é importante observar que não isso não é recomendado. Se você quiser colocar o compartilhamento de arquivo com qualquer outra função de servidor, certifique-se de monitorar o espaço em disco e problemas de desempenho regularmente.

### <a name="keep-in-mind"></a>Lembre-se do seguinte:

- Você não é possível colocar um servidor de proxy reverso, que não é um Skype para o componente do servidor de negócios e não pode até ser em sua topologia. Se você quiser dar suporte ao compartilhamento de conteúdo da web para que os usuários federados, entre muitas outras coisas, você precisará um proxy reverso. Se for necessário, vá em frente e implementar o suporte de proxy reverso para Skype para Business Server configurando um servidor de proxy reverso existente que já esteja em sua organização que está sendo usada por outros aplicativos.

- Você não é possível colocar nenhum componente de UM do Exchange ou o componente de servidor do SharePoint com qualquer Skype para a função de servidor de negócios.

## <a name="see-also"></a>Confira também

[Topologias de referência do Skype para Business Server](reference-topologies.md)
