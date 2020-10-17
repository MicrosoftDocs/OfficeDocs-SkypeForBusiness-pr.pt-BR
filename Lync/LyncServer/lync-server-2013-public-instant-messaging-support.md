---
title: 'Lync Server 2013: suporte a mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026ceb24ef3e046d6d800db4ba82381c8905b99d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512398"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a>Suporte a mensagens instantâneas públicas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

O Lync Server 2013 suporta o uso de provedores de conectividade de mensagens instantâneas públicas licenciados, bem como o uso de protocolo XMPP (eXtensible Messaging and Presence Protocol) para implementar um tipo especial de Federação que permite a um Lync Server acessar parceiros de domínio do XMPP configurados usando o cliente Lync 2013.

<div>

## <a name="public-im-connectivity-provider-support"></a>Suporte do provedor de conectividade de IM público

Os parceiros de conectividade de mensagem instantânea pública suportados atualmente são:

  - America Online

  - Windows Live

  - Instant\!

Para comunicações com usuários do Windows Live, o Lync Server 2013 suporta mensagens instantâneas ponto a ponto e chamadas de áudio e vídeo. Para comunicações com AOL e Yahoo \! , o Lync Server 2013 oferece suporte a mensagens instantâneas ponto a ponto. Uma licença separada pode ser necessária.

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

</div>

<div>

## <a name="xmpp-federation-support"></a>Suporte de Federação XMPP

A federação XMPP suporta a comunicação de usuários do Lync com usuários de domínio XMPP configurado que usam um provedor público, como GTalk. As comunicações com estes usuários podem incluir o seguinte:

  - IM ponto a ponto e presença

  - Criação de contatos federados XMPP no cliente Lync

</div>

</div>

<span> </span>

</div>

</div>

</div>

