---
title: 'Lync Server 2013: planejando a conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

A conectividade de mensagens instantâneas públicas é uma classe de Federação e está configurada para permitir que os usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:

  - Contatos do Messenger

  - Instant\! contatos

  - Contatos do America Online (AOL)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de desligamento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário e por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. O recurso da Microsoft para fornecer esse serviço tem o apoio acordado do Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de mensagens instantâneas e de voz.</P></LI></UL>



</div>

Essa classe de Federação requer as seguintes considerações de planejamento:

  - Os usuários do Windows Live Messenger podem ter áudio/comunicação visual ponto a ponto com usuários do Lync Server 2013, além de mensagens instantâneas. Seus servidores de borda devem atender a requisitos específicos de portabilidade e protocolo. Para obter detalhes, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles geralmente usados no planejamento e na implantação do servidor de borda típico que está fornecendo a Federação.

  - O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um uso avançado de chave (EKU) do cliente.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo do certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Resumo de portabilidade-conectividade de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Resumo de DNS-conectividade de mensagens instantâneas públicas no Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

