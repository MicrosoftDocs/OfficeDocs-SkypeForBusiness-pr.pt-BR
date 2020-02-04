---
title: 'Lync Server 2013: Definindo seus requisitos para Servidores Front-End Servers, sistema de mensagens instantâneas e presença'
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
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definindo seus requisitos para Servidores Front-End Servers, sistema de mensagens instantâneas e presença no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

A principal tarefa de planejar mensagens instantâneas (IM) e presença é garantir que você tenha servidores front-end suficientes para os usuários.

<div>

## <a name="enabling-communication-with-external-users"></a>Habilitar a comunicação com usuários externos

Você pode aumentar bastante as vantagens do seu investimento no Lync Server ao permitir que seus usuários se comuniquem com usuários externos. Entre os usuários externos podem estar:

  - **Usuários remotos**   os próprios usuários da organização, quando estiverem trabalhando fora dos firewalls e estiverem usando laptops ou outros dispositivos do Lync Server.

  - **Usuários federados usuários**   de empresas que você trabalha com quem também executa o Lync Server. Para habilitar que seus usuários entrem em contato facilmente com esses usuários, crie relacionamentos federados com essas empresas.

  - **Usuários públicos usuários**   de serviços públicos de mensagens de chat, como serviços de mensagens instantâneas fornecidos pela rede do Windows Live\!dos serviços de Internet, Yahoo e AOL, e usuários de provedores e servidores que usam o XMPP (mensagens extensíveis e o protocolo de presença), como o Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Observe que uma licença separada pode ser necessária para conectividade de IM pública com Windows Live, AOL e Yahoo!

    
    </div>
    
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

Para habilitar qualquer um desses cenários, você precisa implantar um servidor de borda para ajudar a habilitar comunicações seguras entre a implantação do Lync Server e os usuários externos. Os usuários remotos de sua organização e os usuários em organizações federadas poderão ver a presença uns dos outros e se comunicar usando mensagens instantâneas. Para obter detalhes sobre como habilitar a comunicação com usuários externos, consulte [planejando o acesso de usuários externos no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) na documentação de planejamento.

</div>

<div>

## <a name="archiving-im-content"></a>Arquivar conteúdo de IM

O Lync Server fornece recursos que você pode usar se a sua organização deve seguir as normas de conformidade. É possível usar a função Arquivamento para arquivar o conteúdo de mensagens instantâneas de todos os usuários de sua organização ou apenas de usuários específicos. Para obter detalhes, consulte [planejando o arquivamento no Lync Server 2013](lync-server-2013-planning-for-archiving.md) na documentação de planejamento.

Se você também tiver o Microsoft Exchange Server 2013 implantado, poderá integrar o arquivamento dos dados do Exchange com o arquivamento dos dados do Lync Server e usar uma única ferramenta para pesquisar os dois tipos de dados arquivados. Para obter mais informações, consulte [Configurando o Microsoft Lync server 2013 para usar o Microsoft Exchange server 2013 Archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

