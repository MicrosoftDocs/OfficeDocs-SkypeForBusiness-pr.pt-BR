---
title: 'Lync Server 2013: Funções do servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Funções do servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

Cada servidor que executa o Lync Server executa uma ou mais *funções de servidor*. Uma função de servidor é um conjunto definido de funcionalidades do Lync Server fornecidas pelo servidor. Você não precisa implantar todas as funções de servidor disponíveis em sua rede. Instale somente as funções que contêm a funcionalidade desejada.

Mesmo que você não esteja familiarizado com funções de servidor no Lync Server, a ferramenta de planejamento pode orientá-lo na melhor solução para os servidores que você precisa implantar, com base nos recursos desejados. Esta seção fornece uma breve visão geral das funções de servidor e os recursos gerais que elas fornecem:

  - Servidor Standard Edition

  - Servidor Front-End e Servidor Back-End

  - Servidor de Borda

  - Servidor de Mediação

  - Diretor

  - Servidor de front-end de bate-papo persistente

  - Repositório de chat persistente (servidor persistente de back-end de chat)

  - Repositório de conformidade de chat persistente (servidor back-end de conformidade de chat persistente)

Na maioria das funções de servidor, para fins de escalabilidade e alta disponibilidade, você pode implantar *pools* de vários servidores, todos executando a mesma função. Cada servidor de um pool deve executar funções idênticas de servidor. Para a maioria dos tipos de pools no Lync Server, você deve implantar um balanceador de carga para espalhar o tráfego entre os vários servidores do pool. O Lync Server dá suporte ao balanceamento de carga do sistema de nomes de domínio (DNS) e ao equilíbrio de carga de hardware.

<div>

## <a name="standard-edition-server"></a>Servidor Standard Edition

O servidor Standard Edition foi projetado para pequenas organizações e para projetos pilotos de organizações de grande porte. Ele permite que muitos dos recursos do Lync Server, incluindo os bancos de dados necessários, sejam executados em um único servidor. Isso permite que você tenha a funcionalidade do Lync Server por um custo menor, mas não oferece uma solução de alta disponibilidade real.

O servidor Standard Edition permite que você use mensagens instantâneas (IM), presença, conferência e Enterprise Voice, tudo em execução em um servidor.

Para uma solução de alta disponibilidade, use o Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Servidor Front-End e Servidor Back-End

No Lync Server Enterprise Edition, o servidor front-end é a função básica do servidor e executa muitas funções básicas do Lync Server. O servidor front-end, juntamente com os servidores de back-end, são as únicas funções de servidor necessárias para a implantação do Lync Server Enterprise Edition.

Um *pool de front-ends* é um conjunto de servidores front-end configurados de maneira idêntica, que funcionam em conjunto para fornecer serviços para um grupo comum de usuários. Um pool de vários servidores que executa a mesma função fornece escalabilidade e o recurso de failover.

O servidor front-end inclui o seguinte:

  - Autenticação e registro de usuários

  - Informações de presença e troca de cartão de contato

  - Expansão de serviços de catálogo de endereços e lista de distribuição

  - Funcionalidade de mensagens instantâneas, incluindo conferências de mensagens instantâneas com vários participantes

  - Conferência via Web, conferência discada de PSTN e conferência A/V (se implantada)

  - Hospedagem de aplicativos, para os dois aplicativos incluídos no Lync Server (por exemplo, o atendedor de conferência e o aplicativo de grupo de resposta) e aplicativos de terceiros

  - Opcionalmente, Monitoramento, para coleta de informações de uso na forma de registros de detalhes das chamadas (CDRs) e registros de erros das chamadas (CERs). Essas informações fornecem métricas sobre a qualidade da mídia (áudio e vídeo) que atravessa a sua rede para chamadas de voz corporativa e conferências A/V.

  - Componentes da Web para tarefas com suporte baseadas na Web, como agendador da Web e iniciador de ingresso.

  - Opcionalmente, Arquivamento, para arquivar o conteúdo de reuniões e comunicações de IM por motivos de conformidade. Para obter detalhes, consulte [planejando o arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.
    
    No Lync Server 2010 e em versões anteriores, o monitoramento e o arquivamento eram funções de servidor separadas, não posicionadas no servidor front-end.

  - Opcionalmente, se o chat Persistente estiver habilitado, Serviços Web de Chat Persistente para Gerenciamento de Salas de Chat e Serviços Web de Chat Persistente para Upload/Download de Arquivos.

Os Pools de Front-Ends também são o repositório principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três Servidores Front-End do pool, e o seu backup é realizado nos Servidores Back-End.

Além disso, um pool de front-end na implantação também executa o *servidor central de gerenciamento*, que gerencia e implanta dados de configuração básica em todos os servidores que executam o Lync Server. O servidor central de gerenciamento também oferece recursos de shell e transferência de arquivos do Lync Server Management.

Os servidores de back-end são servidores de banco de dados executando o Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de front-ends. Eles servem como repositórios de backup para os dados de conferências e de usuários do pool; além disso, eles são os repositórios principais para outros bancos de dados, como o banco de dados de Grupo de Resposta. Você pode ter um único servidor back-end, mas uma solução que usa o espelhamento do SQL Server é recomendada para failover. Os servidores back-end não executam qualquer software do Lync Server.

<div>


> [!IMPORTANT]  
> Não recomendamos a colocação de bancos de dados do Lync Server com outros bancos de dados. Se isso for feito, a disponibilidade e o desempenho poderão ser afetados.



</div>

As informações armazenadas nos bancos de dados do Servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferências, como dados persistentes sobre o estado de todas as conferências atuais, e dados de agendamento de conferências.

</div>

<div>

## <a name="edge-server"></a>Servidor de Borda

O servidor de borda permite que os usuários se comuniquem e colaborem com usuários de fora dos firewalls da organização. Esses usuários externos podem incluir os próprios usuários da organização que estão trabalhando externamente, usuários de organizações parceiras federadas e usuários externos que foram convidados a participar de conferências hospedadas na sua implantação do Lync Server. O Edge Server também permite a conectividade com serviços públicos de conectividade de IM, incluindo Windows Live\!, AOL, Yahoo e Google Talk.

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

Implantar o Edge Server também permite serviços de mobilidade, que aceitam a funcionalidade do Lync em dispositivos móveis. Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades, como enviar e receber mensagens instantâneas, e exibir contatos e presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas pelo trabalho, por um único número, por correio de voz e chamadas perdidas. O recurso de mobilidade também oferece suporte a *notificações por push* em dispositivos móveis que não aceitam aplicativos executados em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.

Os Servidores de Borda também incluem um proxy XMPP (Extensible Messaging and Presence Protocol) totalmente integrado, com um gateway XMPP nos Servidores Front-End. Você pode configurar esses componentes do XMPP para permitir que os usuários do Lync Server 2013 adicionem contatos de parceiros baseados no XMPP (como Google Talk) para mensagens instantâneas e presença.

Para obter detalhes, consulte [planejando o acesso de usuários externos no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.

</div>

<div>

## <a name="mediation-server"></a>Servidor de Mediação

O servidor de mediação é um componente necessário para a implementação de conferência de voz e discada da empresa. O servidor de mediação traduz a sinalização e, em algumas configurações, mídia entre a infraestrutura interna do Lync Server e um gateway PSTN (rede telefônica pública comutada), IP-PBX ou um tronco SIP (Session Initiation Protocol). Você pode executar o servidor de mediação posicionado no mesmo servidor do front-end Server ou separado em um pool autônomo do servidor de mediação.

Para obter detalhes, consulte [componente do servidor de mediação no Lync server 2013](lync-server-2013-mediation-server-component.md) na documentação de planejamento.

</div>

<div>

## <a name="director"></a>Diretor

Os diretores podem autenticar solicitações de usuário do Lync Server, mas não podem usar contas de usuário em casa nem fornecer serviços de presença ou de conferência. Eles são úteis principalmente para aumentar a segurança em implantações que permitem o acesso de usuários externos. O Diretor pode autenticar as solicitações antes de enviá-las aos servidores internos. Em caso de um ataque de negação de serviço, o ataque termina no Diretor e não atinge os servidores Front-End. Para obter detalhes, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Funções de servidor de chat persistente

O chat persistente permite que os usuários participem de conversas baseadas em tópicos com vários participantes e que persistem ao longo do tempo. O Servidor Front-End de Chat Persistente executa o serviço de chat persistente. O Servidor Back-End de Chat Persistente armazena os dados de histórico de chat, bem como as informações sobre categorias e salas de chat. O Servidor Back-End de Conformidade de Chat Persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.

Os servidores que executam o Lync Server Standard Edition também podem executar o chat persistente posicionado no mesmo servidor. Você não pode colocar o servidor front-end do chat persistente com o servidor front-end do Enterprise Edition.

Para obter detalhes, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Componente servidor de mediação no Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planejando Arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Cenários para o Diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planejando o Servidor de Chat Persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

