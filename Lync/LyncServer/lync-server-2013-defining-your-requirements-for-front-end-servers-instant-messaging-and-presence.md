---
title: 'Lync Server 2013: definindo seus requisitos para servidores front-end, mensagens instantâneas e presença'
description: 'Lync Server 2013: definindo seus requisitos para servidores front-end, sistema de mensagens instantâneas e presença.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545367"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definindo seus requisitos para servidores front-end, mensagens instantâneas e presença no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

A principal tarefa de planejamento de mensagens instantâneas (IM) e presença é garantir que você tenha servidores front-end suficientes para os usuários.

<div>

## <a name="enabling-communication-with-external-users"></a>Habilitando a comunicação com usuários externos

Você pode aumentar significativamente os benefícios de seu investimento no Lync Server, permitindo que os usuários se comuniquem com usuários externos. Os usuários externos podem incluir:

  - **Usuários**     remotos Os próprios usuários da sua organização, quando estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros dispositivos do Lync Server.

  - **Usuários federados**     Usuários de empresas com as quais você trabalha e que também executam o Lync Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.

  - **Usuários públicos**     Usuários de serviços públicos de IM, como serviços de IM fornecidos pela rede do Windows Live de serviços de Internet, Yahoo e \! AOL, e usuários de provedores e servidores que usam o protocolo XMPP (Extensible Messaging and Presence Protocol), como o Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Observe que uma licença separada pode ser necessária para a conectividade de mensagens instantâneas públicas com Windows Live, AOL e Yahoo!.

    
    </div>
    
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

Para habilitar qualquer um ou todos esses cenários, você precisa implantar um servidor de borda para ajudar a habilitar comunicações seguras entre sua implantação do Lync Server e usuários externos. Os usuários e usuários remotos da sua organização em organizações federadas poderão ver a presença de cada um e se comunicar usando mensagens instantâneas. Para obter detalhes sobre como habilitar a comunicação com usuários externos, consulte [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.

</div>

<div>

## <a name="archiving-im-content"></a>Arquivamento de conteúdo de IM

O Lync Server fornece recursos que você pode usar se sua organização deve seguir as regulamentações de conformidade. Você pode usar o arquivamento para arquivar o conteúdo de mensagens INSTANTÂNEAs para todos os usuários em sua organização ou apenas para determinados usuários que você especificar. Para obter detalhes, consulte [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.

Se você também tiver o Microsoft Exchange Server 2013 implantado, você pode integrar o arquivamento de dados do Exchange com o arquivamento de dados do Lync Server e usar uma única ferramenta para pesquisar ambos os tipos de dados arquivados. Para obter mais informações, consulte [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange server 2013 Archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

