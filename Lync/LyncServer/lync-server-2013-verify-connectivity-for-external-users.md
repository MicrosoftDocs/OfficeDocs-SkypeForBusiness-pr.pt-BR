---
title: 'Lync Server 2013: verificar conectividade para usuários externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14d3dbc74119ff4f5669776dafce8a7cc2dee21a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Verificar a conectividade para usuários externos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Para validar a conectividade de usuários externos, é necessário garantir a conectividade dos usuários com o servidor e a porta do Serviço de Borda de Acesso.

Um recurso valioso para confirmar sua configuração e a capacidade de se conectar, enviar e receber as mensagens corretas para os cenários que o acesso de usuário externo requer é o site do analisador de conectividade remota (<http://www.testocsconnectivity.com>). O site é gerenciado e mantido pelo suporte da Microsoft. Para acessar o Analisador de Conectividade Remota, abra o site da Web em um navegador e siga as instruções para selecionar o cenário.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Teste a conectividade de usuários externos e do acesso externo

Os testes de acesso de usuários externos devem incluir todos os tipos de usuário externo aceitos pela sua organização, incluindo um ou todos os seguintes:

  - Os usuários de pelo menos um domínio federado e o teste de IM, presença, A/V e compartilhamento de área de trabalho.

  - Os usuários de cada provedor de serviços públicos de IM que tem suporte em sua empresa (e para o qual o provisionamento foi concluído).

  - Usuários anônimos.

  - Usuários em sua organização que fizeram logon no Lync remotamente, mas sem usar VPN.

Esses testes determinam se o Servidor de Borda:

  - Escuta as portas necessárias usando um cliente telnet de fora da rede.
    
      - Exemplo: telnet sip.contoso.com 443
    
      - Executa o teste anterior nas portas que você está usando no Servidor de Borda ou no pool do Servidor de Borda dependendo da sua implantação.

  - Executa a resolução DNS externa precisa.
    
      - De fora da sua rede, execute ping em cada FQDN externo da Borda ou do pool de Borda. Mesmo se o ping falhar, você verá os endereços IP, que poderá comparar com aqueles que você atribuiu.

</div>

</div>

<span> </span>

</div>

</div>

</div>

