---
title: 'Lync Server 2013: Verificar conectividade para usuários externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Verificar conectividade para usuários externos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Validar a conectividade para usuários externos requer a garantia de conectividade de usuários para o servidor e porta para o serviço de borda de acesso.

Um recurso valioso para confirmar a configuração e a capacidade de se conectar, enviar e receber as mensagens corretas para os cenários que o acesso de usuários externos requer é o site do analisador de conectividade remota (<http://www.testocsconnectivity.com>). O site é gerenciado e mantido pelo suporte da Microsoft. Para acessar o analisador de conectividade remota, abra o site em um navegador e siga as instruções para selecionar o cenário.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e acesso externo

Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um dos itens a seguir ou todos eles:

  - Usuários de pelo menos um domínio federado e testem mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.

  - Usuários de cada provedor de serviços de mensagens de chat público compatível com a sua organização (e para a qual a configuração foi completada).

  - Usuários anônimos.

  - Os usuários dentro da sua organização que estão conectados ao Lync remotamente, mas não ao uso da VPN.

Estes testes determinam se o servidor de borda é:

  - Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
      - Exemplo: Telnet sip.contoso.com 443
    
      - Execute o teste anterior em portas que você está usando no servidor de borda ou no pool do servidor de borda, dependendo da sua implantação.

  - Executa a resolução DNS externa precisa.
    
      - De fora da rede, execute ping em cada um dos FQDNS externos do seu pool de bordas ou bordas. Mesmo que o ping falhe, você verá os endereços IP, que podem ser comparados àqueles que você atribuiu.

</div>

</div>

<span> </span>

</div>

</div>

</div>

