---
title: 'Lync Server 2013: novos recursos para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Novos recursos para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-17_

O Lync Server 2013 introduz novos recursos que estendem os recursos e os métodos de comunicação para seus usuários. Além disso, o Lync Server 2013 introduz alterações nos serviços existentes para integrar e estender melhor os serviços que estão disponíveis para sua organização. Veja a seguir um resumo das alterações que podem afetar o planejamento e a implantação dos serviços do servidor de borda do Lync Server 2013.

  - **O suporte para IPv6 Addressing**   Lync Server 2013 oferece suporte ao endereçamento IPv6 para todos os serviços do servidor de borda. Se você tiver fornecido endereços IPv6 para as interfaces por meio da configuração no Windows Server, poderá usar endereços IPv6 na configuração do servidor de borda através da configuração de endereço IP no construtor de topologias.
    
    <div>
    

    > [!IMPORTANT]  
    > O uso de endereços IPv6 no Lync Server 2013 depende do suporte do IPv6 em roteadores e firewalls que sua organização implanta, bem como suporte por meio de seu provedor de serviços de Internet.

    
    </div>

  - **O XMPP (Extensible Messaging and Presence Protocol)**   Lync Server 2013 introduz um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP implantado em seus servidores front-end. Você pode implantar a Federação do XMPP como um componente opcional. Adicionar e configurar o XMPP proxy e o Gateway XMPP permitirão que seus usuários do Microsoft Lync 2013 adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.
    
    <div>
    

    > [!NOTE]  
    > Atualmente, os serviços do XMPP no Lync Server 2013 só fornecem mensagens instantâneas e presença entre os clientes do Lync e os contatos baseados no XMPP.

    
    </div>

  - **Serviços de mobilidade para clientes móveis**   introduzidos em uma atualização de cliente para o Lync Server 2010, os serviços de mobilidade no Lync Server 2013 permitem que clientes móveis do Microsoft Lync em telefones celulares e dispositivos tablets usando dispositivos móveis Apple Ios, Android, Windows Phone ou Nokia com suporte para executar tais atividades, como enviar e receber mensagens instantâneas, exibir contatos e ver a presença. Além disso, os dispositivos móveis são compatíveis com alguns recursos do Enterprise Voice, como clique para ingressar em uma conferência, ligar via trabalho, alcance de um único número, caixa postal e notificação de chamada perdida.
    
    <div>
    

    > [!NOTE]  
    > Os serviços de mobilidade usam o proxy reverso e os serviços publicados que são implantados em seus servidores front-end. Nenhuma alteração é necessária para os servidores de borda.

    
    </div>

  - **Os diretores são uma função**   opcional a função do servidor Diretor na topologia do Lync Server 2013 não foi alterada. Ele ainda hospeda serviços Web, autentica previamente as solicitações do usuário e direciona os usuários externos para o pool inicial. Alterar o diretor de uma função recomendada para uma função opcional não diminui o valor do diretor, mas enfatiza a redução da contagem de servidores e outros requisitos de hardware (por exemplo, balanceadores de carga de hardware para os requisitos de diretor) sem recursos de comprometimento e funcionalidade. Como os servidores de front-end podem fazer o mesmo trabalho que o diretor sem impacto nos serviços fornecidos, você pode, opcionalmente, implantar diretores, se você escolher. Você pode excluir com segurança o diretor com confiança de que os servidores front-end fornecerão os mesmos serviços em seu lugar.

<div>

## <a name="see-also"></a>Confira Também


[Planejando e Configurando o IPv6 no Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Planejamento para acesso de usuário externo no Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

