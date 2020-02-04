---
title: 'Lync Server 2013: Suporte a protocolo IP e de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285ed0d383b09276979ad6e29c390e2fc22a1caf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Suporte a protocolo IP e de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O Lync Server 2013 dá suporte aos seguintes protocolos de IP e de rede:

  - **Protocolos IP.**    O Lync Server 2013 oferece suporte ao IP versão 4 (IPv4) ou IP versão 6 (IPv6) para a rede do servidor.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server 2013 pode funcionar em uma rede com a pilha de IP duplo habilitada.

    
    </div>

  - **Protocolos de transporte SIP.**    Em geral, o SIP pode usar pelo menos três tipos de transporte: protocolo UDP, protocolo de controle de transmissão (TCP) e Transport Layer Security (TLS). Na configuração de transporte SIP padrão, o TLS é executado sobre TCP. O TLS é usado na rede do Lync Server 2013. Na borda da rede, o Lync Server 2013 pode interoperar via TCP. O Lync Server 2013 não é compatível com o UDP para transporte SIP porque ele não atende aos padrões mínimos de segurança, confiabilidade e escalabilidade de comunicação corporativa. Para obter detalhes, consulte o artigo sobre o blog NextHop, "para UDP ou não para UDP, que é a pergunta" [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)em.
    
    <div>
    

    > [!NOTE]  
    > O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

