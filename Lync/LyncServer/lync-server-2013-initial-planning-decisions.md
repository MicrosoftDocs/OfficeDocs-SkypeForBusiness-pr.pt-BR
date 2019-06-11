---
title: 'Lync Server 2013: Decisões de planejamento inicial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Initial planning decisions
ms:assetid: cbaa5cb3-2b00-4b9f-952d-986a0c9f160b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398855(v=OCS.15)
ms:contentKeyID: 48185651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd1359e27f6869dab1ead38da3716135a2468ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="initial-planning-decisions-for-lync-server-2013"></a>Decisões de planejamento inicial para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

A primeira parte do processo de planejamento é decidir quais cargas de trabalho e recursos principais do Lync Server você deseja para a sua organização.

1.  **Você quer uma implantação local ou online?**    O Lync Server oferece suporte a ambos os cenários de implantação. Para obter mais informações sobre como tomar essa decisão, consulte [decidindo como implantar o Lync Server 2013](lync-server-2013-deciding-how-to-deploy-microsoft-lync.md), anteriormente nesta seção

2.  **Você quer uma topologia física ou virtualizada?**    O Lync Server oferece suporte a todas as cargas de trabalho e funções de servidor em topologias físicas e virtualizadas. A capacidade e a escalabilidade do usuário podem ser diferentes entre topologias físicas e virtuais. Para obter mais informações, consulte [executando o Lync Server 2013 em servidores virtuais](lync-server-2013-running-lync-server-on-virtual-servers.md).

3.  **O recurso de mensagens instantâneas *(IM)* e a *presença* sempre estão habilitados.**    Em qualquer implantação do Lync Server, o sistema de mensagens instantâneas (IM) e a carga de trabalho de presença são instalados e habilitados por padrão. A mensagem instantânea permite que os usuários se comuniquem com mensagens de texto em tempo real, e a presença permite que eles vejam o status de outros usuários na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a decidirem se devem tentar contatar o usuário e, por isso, o que significa. Para obter detalhes, consulte [planejando servidores front-end, mensagens instantâneas e presença no Lync Server 2013](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md) na documentação de planejamento.

4.  **Você deseja implantar qualquer modo de conferência?**    A conferência é outro recurso básico do Lync Server. Há suporte para vários modos de conferência. Você pode optar por implantar todos os tipos de conferência com suporte ou apenas alguns deles. ** A Webconferência permite que os usuários vejam um arquivo, como um conjunto de slides criado com o programa de elementos gráficos de apresentação do Microsoft PowerPoint, que está sendo apresentado. O *compartilhamento de aplicativos* permite que os usuários compartilhem toda ou parte da área de trabalho entre si em tempo real. Com *a conferência a/V*, os usuários podem adicionar áudio (e possivelmente vídeo) às suas conferências e comunicações ponto a ponto. A *conferência discada* permite que os usuários usem telefones PSTN padrão para ingressar na parte de áudio de conferências hospedadas em sua organização. Para obter detalhes, consulte [planejando a conferência no Lync Server 2013](lync-server-2013-planning-for-conferencing.md) na documentação de planejamento.
    
    No Lync Server 2013, se você implantar a Webconferência, também deverá planejar a integração com o servidor do Office Web Apps para habilitar o compartilhamento e a exibição do PowerPoint em reuniões. Para obter mais informações, consulte Configurando [a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

5.  **Se você implantar uma conferência A/V, também deverá monitorar a qualidade de áudio dessas conferências.**    Muitos fatores afetam a qualidade de áudio e vídeo das conferências do Lync Server A/V. Ao usar o monitoramento, você pode monitorar a qualidade a/V de suas chamadas e conferências. Você pode detectar problemas que afetam a qualidade da mídia e garantir que os usuários tenham a melhor experiência de mídia possível. Para obter mais informações, consulte [planejando o monitoramento do Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

6.  **Você quer uma alta disponibilidade para seus servidores de mensagens instantâneas, presença e conferência?**    Se você tiver apenas um servidor em um site que forneça recursos de chat, presença e conferência, a produtividade dos usuários será bastante afetada se o servidor ficar inativo. Ao implantar um *pool* do Enterprise Edition de pelo menos três servidores para essas funções, você permite que o Lync Server continue a funcionar com todos esses recursos intactos, mesmo se um servidor estiver indisponível.
    
    Outra opção para organizações com o 5000 ou menos usuários que desejam alta disponibilidade é implantar dois servidores que executam o Lync Server Standard Edition e emparelhar esses servidores juntos. Para obter mais informações, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

7.  **Deseja opções de recuperação de desastres?**    Se você tiver dois datacenters e quiser opções de recuperação de desastres para permitir que os usuários continuem a funcionar se todos ou muitos servidores em um datacenter estiverem inativos, você poderá implantar seus servidores com a recuperação de desastres em mente. Para essa implantação, você emparelha um pool de servidores em um datacenter com um pool correspondente em outro datacenter. Se um datacenter ficar inoperante, o outro pool pode atender os usuários em ambos os pools com a interrupção mínima dos serviços. Para obter mais informações, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

8.  **Deseja permitir que seus usuários se comuniquem e colaborem com usuários externos?**    Habilitar a comunicação e a colaboração com usuários externos pode aumentar o retorno sobre o investimento no Lync Server. Isso permite que os usuários da sua organização se beneficiem dos recursos do Lync Server mesmo quando estiverem trabalhando fora dos firewalls da sua organização. Você também pode federar-se com o parceiro ou organizações do cliente que executam o Lync Server. Ao fazer isso, os usuários e os usuários do parceiro federado podem facilmente enviar e receber mensagens de chat, convidar-se para reuniões e ver a presença das outras pessoas. Além disso, os usuários podem usar uma mensagem de email para convidar usuários específicos externos para conferências que eles organizam. Para obter mais informações, consulte [planejando o acesso de usuários externos no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

9.  **Você deseja implantar o Enterprise Voice?** O     *Enterprise Voice* é a solução de voz sobre IP (VoIP) fornecida pelo Lync Server. Ele fornece uma alternativa atraente para a telefonia tradicional com base em PBX. O Enterprise Voice permite que os usuários façam chamadas de seus computadores ou telefones VoIP clicando em um contato no Outlook ou Lync Server. Elas podem fazer chamadas pela rede IP de computador para computador, computador para telefone ou telefone para computador. Os usuários se beneficiam de ter todas as suas opções de comunicação-voz, e-mail, mensagens instantâneas e conferência-disponível e integrada em seus computadores. Para obter detalhes, consulte [planejamento para Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) na documentação de planejamento.

10. **Se você implantar o Enterprise Voice, também deverá monitorar a qualidade de áudio dessas chamadas.**    Recomendamos que você use o monitoramento para garantir a qualidade de áudio de suas chamadas corporativas de voz, se você implantar o Enterprise Voice. Para obter mais informações, consulte [planejando o monitoramento do Lync Server 2013](lync-server-2013-planning-for-monitoring.md).

11. **Você precisa arquivar conteúdo de mensagens de chat ou conteúdo de reunião para fins de conformidade?**    Se a sua organização tiver que arquivar o conteúdo de mensagens instantâneas ou o conteúdo da reunião para fins de conformidade, você poderá implantar o arquivamento. Para obter mais informações, consulte [planejando o arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md).

12. **Você deseja implantar chats persistentes?**    Se você deseja permitir que os usuários tenham conversas em tempo real que podem persistir ao longo do tempo, você pode implantar chats persistentes. Para obter mais informações, consulte [planejando o servidor de chat persistente no Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

13. **Você tem o Microsoft Exchange implantado?**    Se a sua organização usa o Microsoft Exchange Server para seus serviços de email, você pode habilitar vários recursos que melhoram a utilidade do Lync Server e do Microsoft Exchange Server. Alguns desses recursos, chamados de Unificação de mensagens do Exchange, incluem permitir que os usuários recebam avisos de correio de voz e escutem a caixa postal do Outlook ou do Outlook Web Access, acessem suas caixas de correio do Microsoft Exchange usando um telefone e para receber faxes em suas caixas de correio do Microsoft Exchange. Além disso, se você tiver o Exchange 2013 implantado, poderá integrar os repositórios de contatos para usuários entre os dois sistemas, usar o Exchange para armazenar fotos de contatos de alta resolução e integrar o arquivamento de emails e mensagens instantâneas. Para obter mais informações, consulte [planejando a integração do Exchange Server com o Lync server 2013](lync-server-2013-planning-for-exchange-server-integration.md).

14. **Você tem filiais em sua organização?**    Se a sua organização tiver filiais, o Lync Server será compatível com diversas maneiras de dar suporte a elas e garantir a resiliência para voz e outros recursos. Em particular, em uma filial que não tem um link de WAN resistente a um Data Center, você pode instalar um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes para manter o suporte do Enterprise Voice, caso o link de rede de longa distância (WAN) fique abaixo. Para obter mais informações, consulte [planejando a resiliência de voz no site de filial no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

</div>

<span> </span>

</div>

</div>

</div>

