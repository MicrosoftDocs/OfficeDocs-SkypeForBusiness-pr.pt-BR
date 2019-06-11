---
title: 'Lync Server 2013: Novos recursos para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Novos recursos para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-17_

O Lync Server 2013 introduz novos recursos que ampliam os recursos e métodos de comunicação para seus usuários. Além disso, o Lync Server 2013 introduz alterações em serviços existentes para integrar melhor e estender os serviços que estão disponíveis para sua organização. Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação de serviços do servidor de borda do Lync Server 2013.

  - **Suporte para endereçamento**   IPv6 o Lync Server 2013 suporta endereçamento IPv6 para todos os serviços de servidor de borda. Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda por meio da configuração do endereço IP no construtor de topologias.
    
    <div>
    

    > [!IMPORTANT]  
    > O uso de endereços IPv6 no Lync Server 2013 depende do suporte do IPv6 em roteadores e firewalls implantados por sua organização, bem como suporte para o seu provedor de serviços de Internet.

    
    </div>

  - ****   O Lync Server 2013 (XMPP) do Lync Server introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP implantado em seus servidores front-ends. Você pode implantar a Federação do XMPP como um componente opcional. Adicionar e configurar o XMPP proxy e XMPP gateway permitirá que seus usuários do Microsoft Lync 2013 adicionem contatos de parceiros baseados no XMPP para mensagens instantâneas (IM) e presença.
    
    <div>
    

    > [!NOTE]  
    > Atualmente, os serviços do XMPP no Lync Server 2013 fornecem apenas mensagens instantâneas e presença entre os clientes do Lync e os contatos baseados no XMPP.

    
    </div>

  - **Serviços de mobilidade para clientes móveis**   introduzidos em uma atualização do cliente para o Lync Server 2010, os serviços de mobilidade no Lync Server 2013 permitem que os clientes móveis do Microsoft Lync em celulares e dispositivos tablets com suporte para Apple Ios, Android, Windows Telefone ou dispositivos móveis Nokia para executar tais atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas por meio de trabalho, de alcance de número único, caixa postal e notificação de chamada perdida.
    
    <div>
    

    > [!NOTE]  
    > Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end. Nenhuma alteração é necessária para servidores Edge.

    
    </div>

  - **Os diretores são uma função**   opcional a função do servidor Diretor na topologia do Lync Server 2013 não mudou. Ele ainda hospeda serviços Web, autentica previamente as solicitações do usuário e direciona os usuários externos para o pool inicial. Alterar o diretor de uma função recomendada para uma função opcional não diminui o valor do diretor, mas enfatiza a redução da contagem do servidor e outros requisitos de hardware (por exemplo, saldos de carga de hardware para o diretor) requisitos sem recursos e funcionalidades de comprometimento. Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode, opcionalmente, implantar diretores se optar por fazê-lo. Você pode excluir com segurança o diretor com certeza de que os servidores de front-end fornecerão os mesmos serviços em seu lugar.

<div>

## <a name="see-also"></a>Confira também


[Planejando e Configurando o IPv6 no Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Como planejar a Federação do protocolo de presença e de mensagens extensíveis (XMPP) no Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

