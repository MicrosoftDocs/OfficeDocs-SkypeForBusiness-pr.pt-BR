---
title: 'Lync Server 2013: recursos de resiliência de site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5f477bcb5620112789a338339b6ca00bf9c3c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Recursos de resiliência de site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-10_

Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial com um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:

<div>


  - Chamadas de rede telefônica pública comutada (PSTN) de entrada e saída

  - Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

  - Manipulação de chamada básica, incluindo chamada em espera, recuperação e transferência

  - Mensagens instantâneas de dois participantes

  - Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamada e serviços de chamada de equipe, mas somente se o delegante e o representante (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estiverem configurados no mesmo site

  - Registros de detalhes da chamada (CDRs)

  - Conferência de discagem PSTN com Atendedor Automático de Conferência

  - Recursos de caixa postal, se você definir configurações de reencaminhamento de caixa postal. (Para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Autenticação e autorização de usuário

Os recursos a seguir estarão disponíveis somente se sua solução de resiliência for uma implantação do Lync Server em escala total no site de filial:

  - Conferência de IM, Web e A/V

  - Presence e não incomodar (DND)-roteamento baseado (onde as chamadas são impedidas de tocar em extensões com o DND ativado)

  - Atualização de configurações de encaminhamento de chamadas

  - Aplicativo de grupo de resposta e aplicativo de estacionamento de chamada

  - Provisionamento de novos telefones e clientes, mas somente se o serviços de domínio do Active Directory estiver presente no site de filial.

  - Enhanced 9-1-1 (E9-1-1)
    
    Se o E9-1-1 for implantado e o tronco SIP no site central não estiver disponível porque o link WAN está inoperante, o aparelho de filial persistente encaminhará chamadas E9-1-1 para o gateway de filial local. Para habilitar esse recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local em caso de falha de WAN.

<div>


> [!NOTE]  
> SBA (filial persistente) não tem suporte para o XMPP. Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens instantâneas ou ver presença com contatos do XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

