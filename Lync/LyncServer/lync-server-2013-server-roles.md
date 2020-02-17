---
title: Funções de servidor do Lync Server 2013
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
ms.openlocfilehash: 093161cec5a13ac12840776dec731773782966c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Funções de servidor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

Cada servidor que executa o Lync Server executa uma ou mais *funções de servidor*. Uma função de servidor é um conjunto definido de funcionalidades do Lync Server fornecidas por esse servidor. Você não precisa implantar todas as funções de servidor disponíveis na sua rede. Instale somente as funções com a funcionalidade desejada.

Mesmo que você não esteja familiarizado com as funções de servidor no Lync Server, a ferramenta de planejamento poderá orientá-lo na melhor solução para os servidores que você precisa implantar, com base nos recursos desejados. Esta seção fornece uma visão geral sobre as funções de servidor e os recursos gerais que eles fornecem:

  - Standard Edition Server

  - Servidor Front-End e Servidor Back-End

  - Servidor de Borda

  - Servidor de Mediação

  - Be

  - Servidor front-end de chats persistentes

  - Repositório de chats persistentes (servidor back-end de chats persistentes)

  - Repositório de conformidade de chats persistentes (servidor back-end de conformidade de chats persistentes)

Na maioria das funções de servidor, para escalabilidade e alta disponibilidade você pode implantar *pools* de vários servidores, todos executando a mesma função de servidor. Cada servidor em um pool deve executar uma função ou funções de servidor. Para a maioria dos tipos de pools no Lync Server, você deve implantar um balanceador de carga para espalhar o tráfego entre os vários servidores no pool. O Lync Server suporta o balanceamento de carga do DNS (sistema de nomes de domínio) e balanceadores de carga de hardware.

<div>

## <a name="standard-edition-server"></a>Servidor Standard Edition

O servidor Standard Edition foi projetado para pequenas empresas e para projetos piloto de grandes organizações. Ele permite que muitos dos recursos do Lync Server, incluindo os bancos de dados necessários, sejam executados em um único servidor. Isso permite que você tenha a funcionalidade do Lync Server para um custo menor, mas não fornece uma solução real de alta disponibilidade.

Servidor Standard Edition permite que você use mensagens instantâneas (IM), presença, conferência e Enterprise Voice, tudo em execução em um servidor.

Para uma solução de alta disponibilidade, use o Lync Server Enterprise Edition.

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>Servidor de front-end e Servidor de back-end

No Lync Server Enterprise Edition, o servidor front-end é a função de servidor principal e executa muitas funções básicas do Lync Server. O servidor front-end, junto com os servidores back-end, são as únicas funções de servidor necessárias para estar em qualquer implantação do Lync Server Enterprise Edition.

Um *pool de Front-Ends* é um conjunto de servidores Front-End, configurados de forma idêntica, que trabalham juntos para fornecer serviços a um grupo de usuários comuns. Um pool de vários servidores executando a mesma função fornece a capacidade de escalabilidade e failover.

O servidor Front-End inclui:

  - Registro e autenticação de usuário

  - Informações de presença e troca do cartão contato

  - Serviços de catálogo de endereço e expansão de lista de distribuição

  - Funcionalidade de mensagens instantâneas, incluindo conferências de mensagens instantâneas com vários participantes

  - Webconferências, conferências de discagem PSTN e conferências A/V (se implantadas)

  - Hospedagem de aplicativos, para os dois aplicativos incluídos no Lync Server (por exemplo, o atendedor de conferência e o aplicativo de grupo de resposta) e aplicativos de terceiros

  - Opcionalmente, Monitoramento para coletar informações de uso na forma de CDRs (registros de detalhes de chamada) e CERs (registros de erros de chamada). Essas informações fornecem métricas sobre a qualidade da mídia (áudio e vídeo) que atravessam sua rede para chamadas do Enterprise Voice e conferências A/V.

  - Componentes da Web para tarefas compatíveis com base na Web, como agendador da Web e iniciador de ingresso.

  - Opcionalmente, Arquivamento para arquivar comunicações de mensagens instantâneas e conteúdo de reunião por motivos de conformidade. Para obter detalhes, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.
    
    No Lync Server 2010 e versões anteriores, o monitoramento e o arquivamento eram funções de servidor separadas, não posicionadas no servidor front-end.

  - Opcionalmente, e o chat persistente estiver habilitado, serviços Web de chat persistente para gerenciamento de salas de chat e serviços Web de chat persistente para upload/download de arquivos.

Os pools front-end também são o repositórios principal de dados de usuários e conferências. As informações sobre cada usuário são replicadas em três servidores front-end no pool, e o backup delas é realizado nos servidores back-end.

Além disso, um pool de front-ends na implantação também executa o *servidor de gerenciamento central*, que gerencia e implanta dados básicos de configuração para todos os servidores que executam o Lync Server. O servidor de gerenciamento central também fornece o Shell de gerenciamento do Lync Server e os recursos de transferência de arquivos.

Os servidores de back-end são servidores de banco de dados executando o Microsoft SQL Server que fornecem os serviços de banco de dados para o pool de front-ends. Os servidores de back-end servem como repositórios de backup para os dados de usuário e conferência do pool e são os principais repositórios de outros bancos de dados, como o banco de dados do grupo de resposta. Você pode ter um único servidor back-end, mas uma solução que usa o espelhamento do SQL Server é recomendada para failover. Os servidores de back-end não executam qualquer software do Lync Server.

<div>


> [!IMPORTANT]  
> Não recomendamos colocar os bancos de dados do Lync Server com outros bancos de dados. Caso contrário, a disponibilidade e o desempenho poderão ser afetados.



</div>

As informações armazenadas nos bancos de dados do servidor Back-End incluem informações de presença, listas de contatos dos usuários, dados de conferência, incluindo os dados persistentes sobre o estado de todas as conferências atuais e dados de agendamento de conferência.

</div>

<div>

## <a name="edge-server"></a>Servidor de Borda

O Servidor de Borda permite que os usuários se comuniquem e colaborem com usuários fora dos firewalls da organização. Esses usuários externos podem incluir os próprios usuários da organização que estão trabalhando fora do local, usuários de organizações de parceiros federados e usuários externos que tenham sido convidados a participar de conferências hospedadas na sua implantação do Lync Server. O servidor de borda também permite a conectividade para serviços públicos de conectividade de IM, incluindo Windows\!Live, AOL, Yahoo e Google Talk.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>



</div>

A implantação do servidor de borda também habilita serviços de mobilidade, com suporte à funcionalidade do Lync em dispositivos móveis. Os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades como enviar e receber mensagens instantâneas, exibir contatos e exibir presença. Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas. O recurso de mobilidade também oferece suporte a *notificações por push* para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.

Os servidores de borda também incluem um proxy XMPP completamente integrado, com um gateway XMPP incluído nos servidores front-end. Você pode configurar esses componentes do XMPP para permitir que seus usuários do Lync Server 2013 adicionem contatos de parceiros baseados no XMPP (como Google Talk) para mensagens instantâneas e presença.

Para obter detalhes, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.

</div>

<div>

## <a name="mediation-server"></a>Servidor de Mediação

O servidor de mediação é um componente necessário para a implementação da conferência de discagem e voz da empresa. O servidor de mediação converte a sinalização e, em algumas configurações, mídia entre sua infraestrutura interna do Lync Server e um gateway PSTN (rede telefônica pública comutada), IP-PBX ou um tronco SIP (protocolo de iniciação de sessão). Você pode executar o Servidor de Mediação colocado no mesmo servidor do servidor front-end ou separado em um pool de Servidor de Mediação independente.

Para obter detalhes, consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) na documentação de planejamento.

</div>

<div>

## <a name="director"></a>Be

Os diretores podem autenticar solicitações de usuário do Lync Server, mas não hospedam contas de usuário nem fornecem serviços de presença ou conferência. Os diretores são mais úteis para aprimorar a segurança em implantações que permitam o acesso de usuários externos. O diretor pode autenticar solicitações antes de enviá-las a servidores internos. No caso de ataque de negação de serviço, o ataque termina no diretor e não atinge os servidores front-end. Para obter detalhes, consulte [cenários para o diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.

</div>

<div>

## <a name="persistent-chat-server-roles"></a>Funções de servidor de chat persistente

O chat persistente permite que os usuários participem de conversações baseadas em tópicos com várias pessoas. Essas conversas persistem ao longo do tempo. O servidor front-end de chat persistente executa o serviço de chat persistente. O servidor back-end de chat persistente armazena os dados de histórico e as informações sobre categorias e salas de chat. O servidor back-end de conformidade de chat persistente (opcional) pode armazenar o conteúdo de chats e eventos de conformidade para fins de conformidade.

Os servidores que executam o Lync Server Standard Edition também podem executar o chat persistente colocado no mesmo servidor. Não é possível colocar o servidor front-end de chat persistente com o servidor front-end Enterprise Edition.

Para obter detalhes, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Componente do servidor de mediação no Lync Server 2013](lync-server-2013-mediation-server-component.md)  


[Planejamento para arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Cenários para o diretor no Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

