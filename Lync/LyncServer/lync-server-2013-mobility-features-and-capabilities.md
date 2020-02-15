---
title: 'Lync Server 2013: recursos e recursos de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac62cb2fe222a2a36c0fc0aeb79a4aaa37e9964
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Recursos e recursos de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 oferece suporte à funcionalidade de clientes móveis do Lync 2010 Mobile e Lync 2013. Quando você implanta o serviço de mobilidade do Lync Server 2013, os usuários podem usar os dispositivos móveis Apple iOS, Android e Windows Phone compatíveis, ou dispositivos móveis Nokia Symbian para realizar atividades, como enviar e receber mensagens instantâneas, exibir contatos e ver a presença. Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas. Novos recursos introduzidos nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 incluem recursos de voz sobre IP (VoIP) e vídeo (H. 264) para o participante da reunião.

O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 oferece suporte à funcionalidade de cliente móvel do Lync 2013. As atualizações cumulativas do Lync Server 2013: fevereiro de 2013 instalar a API da Web de comunicações unificadas ou UCWA. UCWA é o componente usado para clientes móveis do Lync 2013. No Lync Server 2013, MCX é usado para clientes móveis do Lync 2010. Atualizações cumulativas do Lync Server 2013: fevereiro de 2013 Introduza UCWA como o novo ponto de entrada para serviços de mobilidade. Lync Server 2013 implementa o serviço de mobilidade (MCX) simultaneamente, introduzido nas atualizações cumulativas do Lync Server 2010: de novembro de 2011 e fornece suporte para o Lync 2010 Mobile. Ao implantar as atualizações cumulativas do Lync Server 2013:2013 de fevereiro, os usuários podem usar os dispositivos móveis Apple iOS, Android e Windows Phone compatíveis para executar essas atividades como:

<div>


> [!IMPORTANT]  
> Recursos com suporte do serviço de mobilidade das atualizações cumulativas para Lync Server 2010: novembro de 2011 são observados com (MCX). Todos os recursos listados têm suporte no UCWA, introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

  - Enviar e receber mensagens instantâneas (MCX)

  - Exibir presença (MCX)

  - Exibir Contatos (MCX)

  - Clique para ingressar em uma conferência (MCX)

  - Chamada via trabalho (MCX)

  - Alcance de número único (MCX)

  - Caixa postal (MCX)

  - Notificação de chamada não atendida (MCX)

  - Voice over IP (VoIP)

  - Vídeo de participante (H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile fornecia um cliente para dispositivos Nokia Symbian. O Lync 2013 Mobile não terá um cliente para dispositivos baseados em Nokia Symbian.



</div>

Usuários do Apple iPad terão acesso a recursos avançados. Após ingressar em uma reunião usando o retorno de chamada de áudio, um usuário do iPad poderá exibir apresentações carregadas do Microsoft PowerPoint em uma reunião, compartilhar aplicativos e áreas de trabalho, exibir a lista de participantes da reunião e receber notificações de outros tipos de conteúdo que estão sendo compartilhados dentro da reunião.

<div>


> [!TIP]  
> Com o acesso a único número, um usuário recebe chamadas feitas para o número do trabalho em um celular. Com a chamada via trabalho, o usuário faz uma chamada de saída do cliente móvel do Lync usando um número de telefone comercial em vez do número de telefone celular. Com a discagem, o cliente envia uma solicitação para o MCX ou o UCWA (com base na versão do Lync Mobile) para fazer a chamada para eles. O servidor inicia a chamada e depois retorna a chamada no celular do usuário. Quando o usuário atende, o servidor completa a chamada discando para a outra parte. Usando o Chamada via Trabalho, os usuários podem manter sua identidade de trabalho durante uma chamada, o que significa que o destinatário da chamada não visualiza o número de celular do chamador, e este evita incorrer em tarifas da chamada de saída.



</div>

<div>


> [!NOTE]  
> Nem todos os recursos funcionam exatamente da mesma forma em dispositivos móveis. Para obter detalhes sobre os recursos suportados em dispositivos móveis, consulte as tabelas de comparação <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>de clientes móveis em. Para obter detalhes sobre dispositivos e sistemas operacionais com suporte, consulte os tópicos requirements em <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile clients in Lync Server 2013</A>.



</div>

Quando você usa o recurso de descoberta automática do Lync Server 2013, os aplicativos móveis podem localizar automaticamente os serviços Web do Lync Server 2013, sem exigir que os usuários insiram manualmente as URLs em suas configurações de dispositivo. A inserção manual de URLs nas configurações do dispositivo móvel também é suportada, principalmente para fins de solução de problemas.

<div>


> [!IMPORTANT]  
> O MCX e o UCWA são serviços complementares e ambos são implantados para oferecer suporte aos clientes móveis do Lync 2010 Mobile e Lync 2013. Lync 2013 Mobile não poderá entrar no Lync Server 2010 implantações. Lync 2010 Mobile e Lync 2013 Mobile poderão usar uma implantação do Lync Server 2013 com as atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

O recurso de mobilidade também oferece suporte a *notificações por push* para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo. Por exemplo, um convite perdido de mensagens instantâneas (IM) pode resultar em uma notificação por push.

O MCX, o UCWA, o serviço de descoberta automática e o suporte para notificações por push são fornecidos no Lync Server 2013. Recursos de cliente atualizados, recursos e o uso do UCWA como o ponto de entrada de mobilidade são introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.

</div>

<span> </span>

</div>

</div>

</div>

