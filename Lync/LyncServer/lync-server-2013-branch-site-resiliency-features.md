---
title: 'Lync Server 2013: Recursos de resiliência do site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Recursos de resiliência do site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-10_

Se você fornecer resiliência de site de filial, se a conexão WAN de um site de filial com um site central falhar ou se o site central estiver inacessível, os seguintes recursos de voz deverão continuar disponíveis:

<div>


  - Chamadas de rede de telefonia pública comutada (PSTN) de entrada e saída

  - Chamadas corporativas entre usuários no mesmo site e entre dois sites diferentes

  - Administração básica de chamadas, incluindo espera, recuperação e transferência de chamadas

  - Mensagens instantâneas de dois participantes

  - Encaminhamento de chamadas, toque simultâneo de pontos de extremidade, delegação de chamadas e serviços de chamada de equipe, mas somente se o delegante e o delegado (por exemplo, um gerente e o administrador do gerente) ou todos os membros da equipe estiverem configurados no mesmo site

  - Registros de detalhes de chamadas (CDRs)

  - Conferência de discagem PSTN com Atendedor Automático de Conferência

  - Recursos de caixa postal, se forem configuradas definições de reroteamento de caixa postal. (Para obter detalhes, consulte [requisitos de resiliência de site de filial para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)

  - Autenticação e autorização de usuário

Os recursos a seguir estarão disponíveis somente se a sua solução de resiliência for uma implantação do Lync Server em escala total no site da filial:

  - Conferências de IM, webconferências e conferências de A/V

  - Presença e roteamento baseado em Não Incomodar (DND), onde as chamadas não tocam em extensões com o DND ativado

  - Atualização de configurações de encaminhamento de chamadas

  - Aplicativo grupo de resposta e aplicativo de estacionamento de chamada

  - Provisionar novos telefones e clientes, mas somente se os serviços de domínio Active Directory estiverem presentes no site de filial.

  - 9-1-1 Avançado (E9-1-1)
    
    Se o E9-1-1 estiver implantado e o tronco SIP no site central não estiver disponível porque o link de WAN está indisponível, então o aparelho de ramificação sobreviventes roteará chamadas E9-1-1 para o gateway de filial local. Para habilitar este recurso, as políticas de voz dos usuários do site de filial devem rotear chamadas para o gateway local, em caso da falha da WAN.

<div>


> [!NOTE]  
> O SBA (aparelho de filial persistente) não tem suporte no XMPP. Os usuários hospedados em uma configuração do SBA não poderão enviar mensagens de chat nem ver a presença com os contatos do XMPP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

