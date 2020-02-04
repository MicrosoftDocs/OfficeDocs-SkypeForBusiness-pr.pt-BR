---
title: 'Lync Server 2013: Recursos de mobilidade'
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
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Recursos de mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro suporta a funcionalidade do Lync 2010 Mobile e do Lync 2013 para clientes móveis. Ao implantar o serviço de mobilidade do Lync Server 2013, os usuários podem usar dispositivos móveis Apple iOS, Android e Windows Phone, ou dispositivos móveis Nokia Symbian para executar atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença. Além disso, os dispositivos móveis dão suporte a alguns recursos de voz empresarial, como o clique para ingressar em uma conferência, fazer chamadas pelo trabalho, por um único número, por correio de voz e chamadas perdidas. Novos recursos apresentados nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 incluem recurso de voz sobre IP (VoIP) e vídeo (H. 264) para participantes da reunião.

O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro suporta a funcionalidade de cliente móvel do Lync 2013. As atualizações cumulativas do Lync Server 2013: fevereiro de 2013 instale a API da Web de comunicação unificada ou UCWA. UCWA é o componente usado para clientes móveis do Lync 2013. No Lync Server 2013, MCX é usado para clientes móveis do Lync 2010. Atualizações cumulativas do Lync Server 2013:2013 de fevereiro introduz UCWA como o novo ponto de entrada para serviços de mobilidade. O Lync Server 2013 implementa simultaneamente o serviço de mobilidade (MCX), introduzido nas atualizações cumulativas do Lync Server 2010: de novembro de 2011 e fornece suporte para o Lync 2010 Mobile. Ao implantar as atualizações cumulativas do Lync Server 2013:2013 de fevereiro, os usuários podem usar dispositivos móveis do Windows Phone, Android e Windows Phone compatíveis para executar tais atividades como:

<div>


> [!IMPORTANT]  
> Recursos compatíveis com o serviço de mobilidade nas atualizações cumulativas do Lync Server 2010: novembro de 2011 são observados com (MCX). Todos os recursos listados são compatíveis com o UCWA, introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

  - Envie e receba mensagens instantâneas (MCX)

  - Exibir presença (MCX)

  - Exibir Contatos (MCX)

  - Clique para ingressar em uma conferência (MCX)

  - Ligar por trabalho (MCX)

  - Alcance de número único (MCX)

  - Caixa postal (MCX)

  - Notificação de chamada perdida (MCX)

  - Voz sobre IP  (VoIP)

  - Vídeo de participante (H.264)

<div>


> [!NOTE]  
> O Lync 2010 Mobile forneceu um cliente para dispositivos Nokia Symbian. O Lync 2013 Mobile não terá um cliente para dispositivos baseados em Nokia Symbian.



</div>

Os usuários do iPad da Apple terão acesso às funcionalidades aprimoradas. Depois de ingressar em uma reunião usando o recurso de retorno de chamada de áudio, um usuário do iPad poderá ver as apresentações do Microsoft PowerPoint carregadas em uma reunião, compartilhar aplicativos e áreas de trabalho, exibir a lista de participantes da reunião e receber notificações de outros tipos de conteúdo que estão sendo compartilhados na reunião.

<div>


> [!TIP]  
> Com o alcance de um único número, um usuário recebe chamadas em um celular que foram discadas para o número do trabalho. Com a chamada por meio do trabalho, o usuário insere uma chamada de saída do cliente móvel Lync usando um número de telefone comercial em vez do número de telefone celular. Com o dial-out, o cliente envia uma solicitação para MCX ou UCWA (com base na versão do Lync Mobile) para fazer a chamada para ele. O servidor inicia a chamada e, em seguida, chama o usuário de volta no celular. Quando o usuário atende, o servidor conclui a chamada discando a outra pessoa. Ao usar a chamada por meio do trabalho, os usuários podem manter a identidade do trabalho durante uma chamada, o que significa que o destinatário da chamada não vê o número do celular do chamador, e o chamador evita cobranças de chamadas de saída.



</div>

<div>


> [!NOTE]  
> Nem todos os recursos funcionam exatamente da mesma forma em todos os dispositivos móveis. Para obter detalhes sobre os recursos com suporte em dispositivos móveis, consulte as tabelas de <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>comparação de clientes móveis em. Para obter detalhes sobre dispositivos e sistemas operacionais com suporte, consulte os tópicos de requisitos em <A href="lync-server-2013-planning-for-mobile-clients.md">planejando para clientes móveis no Lync Server 2013</A>.



</div>

Quando você usa o recurso de descoberta automática do Lync Server 2013, os aplicativos móveis podem localizar automaticamente os serviços Web do Lync Server 2013 sem exigir que os usuários insiram manualmente as URLs nas configurações do dispositivo. A inserção manual de URLs nas configurações do dispositivo móvel também é suportada, principalmente para fins de solução de problemas.

<div>


> [!IMPORTANT]  
> Os MCX e UCWA são serviços complementares e ambos são implantados para dar suporte aos clientes móveis do Lync 2010 e Lync 2013. O Lync 2013 Mobile não poderá entrar nas implantações do Lync Server 2010. O Lync 2010 móvel e o Lync 2013 Mobile poderão usar uma implantação do Lync Server 2013 com as atualizações cumulativas do Lync Server 2013:2013 de fevereiro aplicado.



</div>

O recurso de mobilidade também oferece suporte a *notificações por push* em dispositivos móveis que não aceitam aplicativos executados em segundo plano. Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo. Por exemplo, um convite perdido de mensagens instantâneas (IM) pode resultar em uma notificação por push.

O MCX, o UCWA, o serviço de descoberta automática e o suporte para notificações por push são fornecidos no Lync Server 2013. Recursos de cliente atualizados, recursos e o uso de UCWA como o ponto de entrada da mobilidade são introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.

</div>

<span> </span>

</div>

</div>

</div>

