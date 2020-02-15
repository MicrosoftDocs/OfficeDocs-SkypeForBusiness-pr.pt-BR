---
title: 'Lync Server 2013: planejamento para conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b1ad49a24e1236dbea837c596beff5e9605902
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

A conectividade de mensagens instantâneas públicas é uma classe de Federação e é configurada para permitir que seus usuários internos e externos do Lync Server 2013 adicionem contatos de qualquer um dos seguintes:

  - Contatos do Messenger

  - Instant\! contacts

  - Contatos do America Online (AOL)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync (PIC USL) não está mais disponível para a compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de desligamento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário, por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual não será renovado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas por meio de IM e voz.</P></LI></UL>



</div>

Essa classe de Federação requer as seguintes considerações de planejamento:

  - Os usuários do Windows Live Messenger podem ter a comunicação de áudio/vídeo ponto a ponto com os usuários do Lync Server 2013, além de mensagens instantâneas. Os servidores de borda devem atender a requisitos específicos de porta e protocolo. Para obter detalhes, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - O Yahoo mensagens instantâneas não tem requisitos exclusivos, além daqueles normalmente usados no planejamento e implantação do servidor de borda típico que está fornecendo Federação.

  - O America Online requer que o certificado do servidor de borda atribuído ao serviço de borda de acesso tenha um cliente de uso avançado de chave (EKU).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Resumo de porta-conectividade de mensagens instantâneas públicas no Lync Server 2013](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Resumo de DNS-conectividade de mensagens instantâneas públicas no Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

