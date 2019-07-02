---
title: Noções básicas de topologia para o Skype for Business Server
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: 'Resumo: escolha sua topologia para o Skype for Business Server. Saiba mais sobre a colocação do servidor no Skype for Business Server.'
ms.openlocfilehash: 064dc9d4f7f5d2a5ac722b3cfae928501b217822
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418008"
---
# <a name="topology-basics-for-skype-for-business-server"></a>Noções básicas de topologia para o Skype for Business Server

**Resumo:** Escolha sua topologia para o Skype for Business Server. Saiba mais sobre a colocação do servidor no Skype for Business Server.

Antes de preparar qualquer coisa, você desejará saber que está planejando a topologia certa para sua implantação do Skype for Business Server. A primeira coisa que você precisa decidir é se você tiver uma implantação local do Skype for Business Server, ou se for combinar isso com uma implantação do Skype for Business Server online em uma implantação híbrida. De qualquer forma, você vai querer ler mais, como detalharemos as topologias locais aqui, mas os detalhes híbridos estão documentados na sua própria seção.

Você também pode ver alguns exemplos de topologias em [topologias de referência para o Skype for Business Server](reference-topologies.md).

## <a name="sites"></a>Sites

No Skype for Business Server, você define sites em sua rede que contenham componentes do Skype for Business Server. Um site é um conjunto de computadores conectados por meio de uma rede de alta velocidade e baixa latência, como uma rede local (LAN), ou de duas redes conectadas por uma rede de fibra ótica de alta velocidade. Observe que os sites do Skype for Business Server são um conceito separado dos sites dos serviços de domínio Active Directory e dos sites do Microsoft Exchange Server. Seus sites do Skype for Business Server não precisam corresponder a seus sites do Active Directory.

O Skype for Business Server permite a implantação local de um ou mais sites que podem ser dimensionados de acordo com os requisitos de alta disponibilidade e local.

Sua implantação terá pelo menos um site central (também chamado de datacenter, que é um datacenter para todos os servidores localizados), e cada site central na sua implantação terá um servidor Standard Edition ou, pelo menos, um pool de front-end Enterprise Edition. Veja abaixo as diferenças em cada opção:

- O servidor Standard Edition inclui um banco de dados do SQL Server Express posicionado.

- O pool de front-end do Enterprise Edition inclui:

  - Um ou mais servidores front-end (ideal no mínimo três, para escalabilidade), com um máximo de doze. O balanceamento de carga seria necessário para mais de um servidor.

  - Um servidor back-end separado.

Você aprenderá mais sobre as diversas funções de servidor mais adiante nesta seção.

Além dos sites centrais, você também pode acabar tendo um ou mais sites de filiais associados ao seu site central. Elas dependem do site central para praticamente todas as suas funcionalidades, portanto, quais são as que são feitas de maneira exata?

- Aparelho de ramificação sobreviventes, que combina um gateway PSTN (rede telefônica pública comutada), com uma funcionalidade do Skype for Business Server.

- Servidor de ramificação sobreviventes, é um servidor que executa o Windows Server que tem o software do servidor de mediador e mediação do Skype for Business Server instalado.

- Gateway PSTN autônomo (que não faz parte do aparelho de ramificação sobreviventes).

- Servidor de mediação autônomo ou pool autônomo do servidor de mediação (se você não quiser posicionar essa função com o aparelho de ramificação sobreviventes).

## <a name="whats-in-a-skype-for-business-server-site"></a>O que há em um site do Skype for Business Server?

Para obter mais detalhes, um site central também pode ter:

- Vários pools de front-end, no mesmo domínio ou domínios diferentes (Lembre-se de planejar que todos os servidores front-ends em um pool Front-end, juntamente com os servidores de back-end para o pool, devem estar no mesmo domínio).

- Vários servidores Standard Edition.

- Office Web Apps Server, que é usado com o Office Web Apps no Skype for Business Server para compartilhamento e renderização de apresentações do PowerPoint.

- Servidor de borda ou o pool de bordas (em uma rede de perímetro). Necessário se você desejar que a sua implantação ofereça suporte para parceiros federados, conectividade a redes públicas de mensagens instantâneas, gateway XMPP e acesso de usuários remotos. Mais detalhes podem ser encontrados na documentação de planejamento do servidor de borda.

- Servidor de chat persistente. Útil se você desejar que os usuários possam participar de conversas baseadas em tópico persistentes com vários participantes. Há mais informações no tópico planejando para servidor de chat persistente.

- Monitoramento. Usado para dar suporte à coleta de dados para A coleta de qualidade de áudio/vídeo (A/V) e A CDR (gravação de detalhes de chamadas) para conferências do Enterprise Voice e de A/V na sua implantação. Esse assunto será abordado em mais detalhes no tópico Planejamento do Monitoramento.

- Grupo Diretor ou diretor. Não é necessário, mas útil se você quiser melhorar a resiliência e habilitar o redirecionamento de solicitações de usuário do Skype for Business para o pool inicial do usuário. Se você quiser implantar diretores, há suporte para um máximo de 10 por pool. Se isso for algo de que você precisa, definitivamente Continue lendo no tópico Planning for directors.

- Proxy reverso. Este não é um componente do Skype for Business Server, mas se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados, se pretende dar suporte ao tráfego de mobilidade, se os usuários remotos desejam usar o catálogo de endereços, ingressar em reuniões e assim por diante, isso é algo que você vai Quer ter em seu ambiente. Há um tópico Configurando o servidor proxy inverso no qual você pode fazer check-out para obter mais detalhes quando estiver pronto.

Mais Informações sobre a colocação desses servidores podem ser encontradas a seguir.

Todos os pools de front-end e servidores Standard Edition implantados em seu site central compartilham o seguinte, pressupondo que você os tenha implantado:

||||
|:-----|:-----|:-----|
|Pool de directors ou diretor  <br/> |Servidor autônomo de mediação ou pool do servidor de mediação  <br/> |Servidor Office Web Apps  <br/> |
|Servidor de borda ou o pool de bordas  <br/> |Servidor de chat persistente ou pool de servidor de chat persistente  <br/> |Monitoramento  <br/> |

Onde é o servidor de UM (Unificação de mensagens) do Exchange nesta lista? Bem, você certamente pode usá-lo com o Skype for Business Server se quiser integrá-lo com o Exchange UM, mas não é um componente do site do Skype for Business Server, por isso não estamos mencionando aqui.

Você pode estar planejando ter vários sites centrais e, se for esse o caso, poderá compartilhar os seguintes servidores e funções se eles estiverem implantados em seu site central:

|||
|:-----|:-----|
|Servidor autônomo de mediação ou pool do servidor de mediação  <br/> |Servidor de borda ou o pool de bordas  <br/> |
|Servidor de chat persistente ou pool de servidor de chat persistente  <br/> |Monitoramento  <br/> |

Da mesma forma que a última lista, não incluímos o servidor do Exchange UM aqui porque ele não faz parte da implantação do Skype for Business Server, mas também na mesma categoria.

Também há outros componentes e opções incluídos nas implantações.

|||||
|:-----|:-----|:-----|:-----|
|Firewalls  <br/> |Gateways PSTN (se você implantar o Enterprise Voice)  <br/> |Servidor Exchange UM (se quiser integrar com UM Exchange UM)  <br/> |Balanceamento de carga DNS  <br/> |
|Balanceadores de carga de hardware  <br/> |Bancos de dados do SQL Server  <br/> |Compartilhamentos de arquivo  <br/> ||

## <a name="server-roles"></a>Funções de servidor

Cada servidor que executa o Skype for Business Server executa uma ou mais funções de servidor. Uma função de servidor é um conjunto definido de funcionalidades do Skype for Business Server fornecidas pelo servidor. Você não precisa implantar todas as funções de servidor disponíveis na sua rede. Instale somente as funções que contêm a funcionalidade desejada.

Na maioria das funções de servidor, para fins de escalabilidade e alta disponibilidade, você pode implantar pools de vários servidores, todos executando a mesma função. Cada servidor de um pool deve executar funções idênticas de servidor. Para a maioria dos tipos de pools no Skype for Business Server, você deve implantar um balanceador de carga para espalhar o tráfego entre os vários servidores do pool. O Skype for Business Server dá suporte a balanceamento de carga de DNS (Domain Name System) e a balanceamento de carga de hardware.

### <a name="front-end-server-and-back-end-server"></a>Servidor Front-End e Servidor Back-End

No Skype for Business Server Enterprise Edition, o servidor front-end é a função básica do servidor e executa muitas funções básicas do Skype for Business Server. O servidor front-end, juntamente com os servidores back-end, são as únicas funções de servidor necessárias para estar em qualquer implantação do Skype for Business Server Enterprise Edition.

Um pool de front-ends é um conjunto de servidores front-end configurados de maneira idêntica, que funcionam em conjunto para fornecer serviços para um grupo comum de usuários. Um pool de vários servidores que executa a mesma função fornece escalabilidade e o recurso de failover.

O servidor front-end inclui o seguinte:

- Autenticação e registro de usuários.

- Informações de presença e troca de cartões de visita.

- Serviços de catálogo de endereços e expansão da lista de distribuição.

- Funcionalidade de IM, incluindo conferências de IM com vários participantes.

- Webconferência, conferência discada PSTN e conferência de áudio/vídeo (se implantada).

- Hospedagem de aplicativos, para os dois aplicativos incluídos no Skype for Business Server (por exemplo, o atendedor de conferência e o aplicativo de grupo de resposta) e aplicativos de terceiros.

- Opcionalmente, Monitoramento, para coleta de informações de uso na forma de registros de detalhes das chamadas (CDRs) e registros de erros das chamadas (CERs). Essas informações fornecem métricas sobre a qualidade da mídia (áudio e vídeo) que atravessa a sua rede para chamadas de voz corporativa e conferências A/V.

- Componentes da Web para tarefas com suporte baseadas na Web, como agendador da Web e iniciador de ingresso.

- Opcionalmente, Arquivamento, para arquivar o conteúdo de reuniões e comunicações de IM por motivos de conformidade. Para obter detalhes, consulte [Planning for Archiving](https://technet.microsoft.com/library/898b83c1-007b-43be-9484-08fe49c10951.aspx) na documentação de Planejamento.

    No Lync Server 2010 e em versões anteriores, o monitoramento e o arquivamento eram funções de servidor separadas, não posicionadas no servidor front-end.

- Opcionalmente, se o chat Persistente estiver habilitado, Serviços Web de Chat Persistente para Gerenciamento de Salas de Chat e Serviços Web de Chat Persistente para Upload/Download de Arquivos.

Os Pools de Front-Ends também são o repositório principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três Servidores Front-End do pool, e o seu backup é realizado nos Servidores Back-End.

Além disso, um servidor front-end na implantação também executa o servidor central de gerenciamento, que gerencia e implanta dados de configuração básica em todos os servidores que executam o Skype for Business Server. O servidor central de gerenciamento também oferece recursos de shell e transferência de arquivos do Lync Server Management.

Os servidores de back-end são servidores de banco de dados executando o Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de front-ends. Os servidores de back-end servem como armazenamentos de backup para os dados de usuário e conferência do pool e são as lojas primárias para outros bancos de dados, como o banco de dados do grupo de resposta. Você pode ter um único servidor back-end, mas o [back-end Server High Availability no Skype for Business Server](../high-availability-and-disaster-recovery/back-end-server.md) é recomendado para failover. Os servidores back-end não executam qualquer software do Skype for Business Server.

> [!IMPORTANT]
> Não recomendamos posicionar os bancos de dados do Skype for Business Server com outros bancos de dados. Se isso for feito, a disponibilidade e o desempenho poderão ser afetados.

> [!NOTE]
> O espelhamento do SQL está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. Os grupos de disponibilidade AlwaysOn, as instâncias de cluster de failover AlwaysOn (FCI) e os métodos de cluster de failover do SQL são preferidos com o Skype for Business Server 2019.

As informações armazenadas nos bancos de dados do Servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferências, como dados persistentes sobre o estado de todas as conferências atuais, e dados de agendamento de conferências.

### <a name="edge-server"></a>Servidor de Borda

O servidor de borda permite que os usuários se comuniquem e colaborem com usuários de fora dos firewalls da organização. Esses usuários externos podem incluir os próprios usuários da organização que estão trabalhando externamente, usuários de organizações parceiras federadas e usuários externos que foram convidados a participar de conferências hospedadas na implantação do Skype for Business Server.

Implantar o Edge Server também permite serviços de mobilidade, que aceitam a funcionalidade do Lync em dispositivos móveis. Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades, como enviar e receber mensagens instantâneas, e exibir contatos e presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas pelo trabalho, por um único número, por correio de voz e chamadas perdidas. O recurso de mobilidade também oferece suporte a notificações por push em dispositivos móveis que não aceitam aplicativos executados em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.

Os Servidores de Borda também incluem um proxy XMPP (Extensible Messaging and Presence Protocol) totalmente integrado, com um gateway XMPP nos Servidores Front-End. Você pode configurar esses componentes do XMPP para permitir que seus usuários do Skype for Business Server adicionem contatos de parceiros baseados no XMPP para mensagens instantâneas e presença.

> [!NOTE]
> Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.

### <a name="mediation-server"></a>Servidor de Mediação

O servidor de mediação é um componente necessário para a implementação do Enterprise Voice, chamada por meio de trabalho e conferência discada. O servidor de mediação traduz a sinalização e, em algumas configurações, mídia entre sua infraestrutura interna do Skype for Business Server e um gateway de rede telefônica pública comutada (PSTN), IP-PBX ou um tronco de protocolo de iniciação de sessão (SIP). Você pode executar o servidor de mediação posicionado no mesmo servidor do front-end Server ou separado em um pool autônomo do servidor de mediação.

Para obter detalhes, consulte [componente do servidor de mediação no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>Servidor de Interoperabilidade de Vídeo

O servidor de interoperabilidade de vídeo é uma nova função do Skype for Business Server 2015. Ele permite que você integre a implantação do Skype for Business Server a determinadas soluções VTC (sistema de videoconferências) de terceiros. Um VIS age como um intermediário entre um sistema de teleconferência de terceiros e uma implantação do Skype for Business Server. Nesta versão, o enfoque do VIS está na interoperabilidade com sistemas de vídeo da Cisco e da Tandberg.

Para obter detalhes, consulte [planejar o servidor de interoperabilidade de vídeo no Skype for Business Server](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>Diretor

Os diretores podem autenticar solicitações de usuário do Skype for Business Server, mas não podem usar contas de usuário ou serviços de presença ou de conferência. Eles são úteis principalmente para aumentar a segurança em implantações que permitem o acesso de usuários externos. O Diretor pode autenticar as solicitações antes de enviá-las aos servidores internos. Em caso de um ataque de negação de serviço, o ataque termina no Diretor e não atinge os servidores Front-End.

### <a name="persistent-chat-server-roles"></a>Funções de servidor de chat persistente

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.

O chat persistente permite que os usuários participem de conversas baseadas em tópicos com vários participantes e que persistem ao longo do tempo. O Servidor Front-End de Chat Persistente executa o serviço de chat persistente. O Servidor Back-End de Chat Persistente armazena os dados de histórico de chat, bem como as informações sobre categorias e salas de chat. O Servidor Back-End de Conformidade de Chat Persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.

Os servidores que executam o Skype for Business Server Standard Edition também podem executar o chat persistente posicionado no mesmo servidor. Você não pode colocar o servidor front-end do chat persistente com o servidor front-end do Enterprise Edition.

Para obter detalhes, consulte [plano para servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>Suporte para alta disponibilidade e recuperação de desastre

O Skype for Business Server fornece alta disponibilidade por redundância de servidor via pool. Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor. Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.

O Skype for Business Server também fornece medidas de recuperação de desastres habilitando o emparelhamento de pool. Se implantar essa topologia, você designará pares de pools de Front-Ends, com cada pool de um par localizado em um datacenter e em uma área geográfica distinta. Se um pool ou site ficar inativo, você poderá redirecionar os usuários desse pool para outro pool do par, com o mínimo de interrupção de serviço.

O Skype for Business Server também oferece suporte a várias opções para a alta disponibilidade do servidor back-end. Isso inclui o seguinte:

- Espelhamento de banco de dados

- Grupos de Disponibilidade Sempre Visíveis

- Instâncias de cluster de failover do AlwaysOn (FCI)

- Clustering de failover do SQL

Para obter detalhes sobre o emparelhamento de pool e a alta disponibilidade do servidor back-end, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>Colocação do servidor no Skype for Business Server

Já usamos o termo posicionar-se, mas o que isso significa? O Skype for Business Server permite localizar algumas funções e recursos de servidor no mesmo servidor, que é a colocação ou em servidores diferentes, mas pode ser confuso quando você está iniciando e se estiver fazendo uma edição Standard ou Enterprise Edition Server implantação (cada um vem com suas próprias regras). Para ajudar com seu planejamento, estamos incluindo a colocação do servidor nas implantações do servidor Standard Edition e nas implantações do pool de front-end do Enterprise Edition (na maioria dos casos, essas informações são idênticas e, em que é diferente, ela é chamada especificamente).

### <a name="collocation-of-server-roles"></a>Colocação de funções de servidor

O servidor Standard Edition tem a seguinte função posicionada (Entretanto, é necessária configuração adicional) enquanto estiver no pool Front-end da edição Enterprise, essa função pode ser posicionada ou implantada em um servidor separado:

- Mediação

As seguintes funções de servidor devem ser implantadas em um servidor separado:

- Diretor

- Borda

- Servidor de Interoperabilidade de Vídeo

- Office Web Apps

### <a name="databases"></a>Bancos de dados

Esta é a área com diferenças reais entre implantações de servidor da edição padrão e implantações do pool do servidor Enterprise Edition, portanto, teremos duas seções abaixo, seguidas por algumas regras adicionais para ambos.

#### <a name="standard"></a>Standard

Como o SQL Server Express é posicionado no servidor Standard Edition e não pode ser movido, isso é bem simples. Além disso, se você implantar o servidor de chat persistente em um servidor Standard Edition, também será possível colocar o chat persistente e o banco de dados de conformidade de chat persistente no servidor Standard Edition, mas você não precisa.

    > [!NOTE]
    > Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019. The same functionality is available in Teams. For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.

Elas não podem ser posicionadas no servidor Standard Edition, mas podem ficar em um único servidor de banco de dados próprio:

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Qualquer banco de dados back-end para um pool de front-end da edição Enterprise

#### <a name="enterprise"></a>Enterprise

Os seguintes bancos de dados podem ser posicionados no mesmo SQL Server de back-end:

- Banco de dados back end

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de chat persistente

- Banco de dados de conformidade de chat persistente

#### <a name="both"></a>Ambos

Agora, há algumas regras adicionais a serem seguidas ao posicionar bancos de dados do Skype for Business Server em uma única instância SQL ou em várias instâncias SQL no mesmo banco de dados SQL Server:

- Cada instância do SQL pode conter apenas um único banco de dados back-end para um pool Front-end Enterprise Edition, um único banco de dados de monitoramento, um único banco de dados de arquivamento persistente, um único banco de dados persistente de conformidade de chat.

- O servidor de banco de dados não pode dar suporte a mais de um pool de front-end da Enterprise Edition, um servidor executando o arquivamento, um servidor com monitoramento, um único banco de dados persistente de chat e um único banco de dados de conformidade de chat persistente, mas ele pode dar suporte a um de cada, Não importa se os bancos de dados usam a mesma instância do SQL Server ou instâncias separadas do SQL Server.

    > [!NOTE]
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.

### <a name="file-shares"></a>Compartilhamentos de arquivo

O compartilhamento de arquivo pode estar em um servidor separado ou você pode colocá-lo no mesmo servidor que qualquer um destes componentes:

- Servidor de banco de dados, incluindo o servidor back-end de um pool Front-end da Enterprise Edition

- Banco de dados de monitoramento

- Banco de dados de arquivamento

- Banco de dados de chat persistente

- Banco de dados de conformidade de chat persistente

> [!CAUTION]
> Observe que, embora seja possível colocar o compartilhamento de arquivos nesses servidores, é importante observar que não isso não é recomendado. Se você quiser colocar o compartilhamento de arquivo com qualquer outra função de servidor, certifique-se de monitorar o espaço em disco e problemas de desempenho regularmente.

### <a name="keep-in-mind"></a>Lembre-se do seguinte:

- Você não pode colocar um servidor proxy reverso, que não seja um componente do Skype for Business Server, e pode nem mesmo estar na sua topologia. Você precisará de um proxy inverso se quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados, entre muitas outras coisas. Se precisar, vá em frente e implemente o suporte de proxy reverso para o Skype for Business Server Configurando um servidor proxy reverso existente que já está em sua organização que está sendo usado por outros aplicativos.

- Você não pode colocar nenhum componente de UM do Exchange ou componente do SharePoint Server com qualquer função do Skype for Business Server.

## <a name="see-also"></a>Confira também

[Topologias de referência para o Skype for Business Server](reference-topologies.md)
