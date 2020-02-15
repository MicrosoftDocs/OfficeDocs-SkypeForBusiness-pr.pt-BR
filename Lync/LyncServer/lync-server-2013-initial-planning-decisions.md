---
title: Decisões de planejamento inicial do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4d9d90c56f44b14c19d7f4cc387f4e0aaf58f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisões de planejamento inicial para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A primeira parte do processo de planejamento é decidir quais cargas de trabalho do Lync Server e recursos principais você deseja para sua organização.

1.  **Você deseja uma implantação local ou online?**    O Lync Server suporta os dois cenários de implantação. Para obter mais informações sobre como tomar essa decisão, consulte [decidindo como implantar o Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), anteriormente nesta seção

2.  **Você deseja uma topologia física ou virtualizada?**    O Lync Server oferece suporte a todas as cargas de trabalho e funções de servidor em topologias físicas e virtualizadas. A capacidade de usuário e escalabilidade podem diferir entre topologias virtuais e físicas. Para obter mais informações, consulte [executando o Lync Server 2013 em servidores virtuais](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **Mensagens instantâneas *(IM)* e *presença* estão sempre habilitadas.**    Em qualquer implantação do Lync Server, as mensagens instantâneas (IM) e a carga de trabalho de presença são instaladas e habilitadas por padrão. IM permite que seus usuários se comuniquem com mensagens de texto em tempo real e a presença permite que eles vejam o status de outros usuários na rede. O status de presença de um usuário fornece informações para ajudar os outros a decidir se devem tentar entrar em contato com o usuário e por qual meio. Para obter detalhes, consulte [planejamento de servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) na documentação de planejamento.

4.  **Você deseja implantar qualquer modo de conferência?**    A conferência é outro recurso principal do Lync Server. Há suporte para diversos modos de conferência. Você pode escolher implantar todos os tipos suportados de conferência ou apenas alguns deles. *Webconferência* permite que os usuários vejam um arquivo, como um conjunto de slides criado com o programa de gráficos de apresentação Microsoft PowerPoint, que está sendo apresentado. *Compartilhamento de aplicativo* permite que os usuários compartilhem toda ou parte de suas áreas de trabalho com outros usuários em tempo real. Com a *Conferência de A/V*, os usuários podem adicionar áudio (e possivelmente vídeo) às suas conferências e comunicações ponto a ponto. *Conferência discada* permite que os usuários usem telefones PSTN padrão para participar da parte de áudio das conferências realizadas em sua organização. Para obter detalhes, consulte [Planning for Conferencing in Lync Server 2013](lync-server-2013-planning-for-conferencing.md) na documentação de planejamento.
    
    No Lync Server 2013, se você implantar a Webconferência, também deverá planejar a integração com o servidor do Office Web Apps para habilitar o compartilhamento e a exibição do PowerPoint em reuniões. Para obter mais informações, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Se você implantar uma conferência A/V, também deverá monitorar a qualidade de áudio dessas conferências.**    Muitos fatores afetam a qualidade de áudio e vídeo das conferências a/V do Lync Server. Usando o Monitoramento, é possível monitorar a qualidade A/V das suas chamadas e conferências. É possível detectar problemas que afetam a qualidade de mídia e garantir que seus usuários tenham a melhor experiência de mídia possível. Para obter mais informações, consulte [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Você deseja alta disponibilidade para seus servidores de IM, presença e conferência?**    Se você tiver apenas um servidor em um site que forneça recursos de IM, presença e conferência, a produtividade dos usuários será muito afetada se o servidor ficar inativo. Ao implantar um *pool* Enterprise Edition de pelo menos três servidores para essas funções, você permite que o Lync Server continue funcionando com todos esses recursos intactos, mesmo que um servidor não esteja disponível.
    
    Outra opção para organizações com 5000 ou menos usuários que desejam alta disponibilidade é implantar dois servidores que executam o Lync Server Standard Edition e emparelhar esses servidores juntos. Para obter mais informações, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Você quer as opções de recuperação de desastres?**    Se você tiver dois data centers e quiser opções de recuperação de desastres para permitir que os usuários continuem a trabalhar se todos ou vários servidores em um datacenter estiverem para baixo, você poderá implantar seus servidores com a recuperação de desastres em mente. Para esta implantação, você emparelha um pool de servidores em um centro de dados com um pool correspondente em outro centro de dados. Se um centro de dados cair, o outro pool no par pode realizar serviços dos usuários em ambos os pools com a mínima interrupção dos serviços. Para obter mais informações, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Você deseja permitir que os usuários se comuniquem e colaborem com usuários externos?**    Habilitar a comunicação e colaboração com usuários externos pode aumentar o retorno sobre o investimento no Lync Server. Isso permite que os próprios usuários da sua organização se beneficiem dos recursos do Lync Server, mesmo quando estão trabalhando fora dos firewalls da sua organização. Você também pode federar suas organizações de parceiros ou clientes que executam o Lync Server. Ao fazer isso, seus usuários e parceiros federados podem facilmente enviar e receber mensagens de IM, convidar uns aos outros para reuniões e ver a presença uns dos outros. Além disso, seus usuários podem utilizar uma mensagem de email para convidar usuários externos específicos às conferências que realizam. Para obter mais informações, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Você deseja implantar o Enterprise Voice?** O     *Enterprise Voice* é a solução de voz sobre IP (VoIP) fornecida pelo Lync Server. Ele fornece uma alternativa atraente para a telefonia tradicional baseada em PBX. O Enterprise Voice permite que os usuários façam chamadas de seus computadores ou telefones VoIP clicando em um contato no Outlook ou no Lync Server. Eles podem fazer chamadas sobre a rede IP de computador para computador, computador para telefone ou telefone para computador. Os usuários se beneficiam em ter todas suas opções de comunicação, voz, email, IM e conferência, disponíveis e integradas em seus computadores. Para obter detalhes, consulte [Planning for Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) na documentação de planejamento.

10. **Se você implantar o Enterprise Voice, também deverá monitorar a qualidade de áudio dessas chamadas.**    Recomendamos que você use o monitoramento para garantir a qualidade de áudio de suas chamadas do Enterprise Voice, se você implantar o Enterprise Voice. Para obter mais informações, consulte [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **Você precisa arquivar conteúdo de IM ou conteúdo de reunião para fins de conformidade?**    Se sua organização tiver que arquivar conteúdo de IM ou conteúdo de reunião para fins de conformidade, você poderá implantar o arquivamento. Para obter mais informações, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Você deseja implantar o chat persistente?**    Se você deseja permitir que seus usuários tenham conversas em tempo real que podem persistir ao longo do tempo, você pode implantar o chat persistente. Para obter mais informações, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Você tem o Microsoft Exchange implantado?**    Se sua organização usa o Microsoft Exchange Server para seus serviços de email, você pode habilitar vários recursos que melhoram a utilidade do Lync Server e do Microsoft Exchange Server. Alguns desses recursos, chamados de Unificação de mensagens (UM), incluem permitir que os usuários recebam avisos de caixa postal e escutem a caixa postal do Outlook ou Outlook Web Access para acessar suas caixas de correio do Microsoft Exchange usando um telefone e receber faxes no suas caixas de correio do Microsoft Exchange. Além disso, se você tiver o Exchange 2013 implantado, poderá integrar os repositórios de contatos para usuários entre os dois sistemas, usar o Exchange para armazenar fotos de contato de maior resolução e integrar o arquivamento de emails e mensagens instantâneas. Para obter mais informações, consulte [Planning for Exchange Server Integration with Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Você tem filiais em sua organização?**    Se sua organização tiver filiais, o Lync Server oferece suporte a várias maneiras de dar suporte a elas e garantir a resiliência de voz e outros recursos. Em particular, em uma filial que não tem um link de WAN resistente a um Data Center, você pode instalar um aparelho de filial persistente ou servidor de filial persistente para manter o suporte do Enterprise Voice, caso o link de rede de longa distância (WAN) vá para baixo. Para obter mais informações, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

