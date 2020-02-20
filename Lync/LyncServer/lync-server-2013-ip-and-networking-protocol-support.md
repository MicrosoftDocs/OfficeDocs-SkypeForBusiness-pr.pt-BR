---
title: 'Lync Server 2013: suporte a protocolo IP e de rede'
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
ms.openlocfilehash: ea7312cff97b6c339d960c14902e912f6e2e7bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a>Suporte a protocolo IP e de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O Lync Server 2013 oferece suporte aos seguintes protocolos de rede e IP:

  - **Protocolos IP.**    O Lync Server 2013 oferece suporte a IP versão 4 (IPv4) ou IP versão 6 (IPv6) para a rede do servidor.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server 2013 pode funcionar em uma rede com uma pilha de IP Dual habilitada.

    
    </div>

  - **Protocolos de transporte SIP.**    Genericamente, o SIP pode usar pelo menos três tipos de transporte: UDP (protocolo de datagrama de usuário), TCP (protocolo de controle de transmissão) e TLS (Transport Layer Security). Na configuração de transporte de SIP padrão, TLS é executado sobre TCP. O TLS é usado na rede do Lync Server 2013. Na borda da rede, o Lync Server 2013 pode interoperar sobre TCP. O Lync Server 2013 não é compatível com UDP para transporte SIP porque não atende aos padrões mínimos para segurança, confiabilidade e escalabilidade de comunicações corporativas. Para obter detalhes, consulte o artigo de blog NextHop, "para UDP, ou não para UDP, que é a pergunta" [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369)em.
    
    <div>
    

    > [!NOTE]  
    > O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

