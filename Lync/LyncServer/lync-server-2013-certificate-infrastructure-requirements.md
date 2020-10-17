---
title: Requisitos de infraestrutura de certificado do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18666f33becabcbdf61370a32900ae7a4819e0cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508018"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestrutura de certificado para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-06-23_

O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para suportar conexões TLS e TLS mútuo (MTLS).

O Lync Server usa certificados para as seguintes finalidades:

  - Conexões TLS entre cliente e servidor

  - Conexões MTLS entre servidores

  - Federação usando a descoberta automática de parceiros no DNS

  - Acesso de usuários remotos a IM (mensagens instantâneas)

  - Acesso de usuário externo a sessões A/V (áudio/vídeo), compartilhamento de aplicativos e conferência

  - Solicitações móveis utilizando descoberta automática de Serviços Web

Para o Lync Server, os seguintes requisitos comuns se aplicam:

  - Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).

  - Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).

  - Todos os certificados devem ser assinados usando um algoritmo de assinatura suportado pelo sistema operacional. O Lync Server 2013 suporta o pacote de resumos SHA-1 e SHA-2 (224, 256, 384 e 512 bits) e atende ou supera os requisitos do sistema operacional. Para suporte ao sistema operacional, consulte [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .
    
    <div>
    

    > [!NOTE]  
    > O uso do algoritmo de assinatura RSASSA-PSS não é suportado e pode levar a erros em problemas de encaminhamento de chamadas e login, entre outros problemas.

    
    </div>

  - O registro automático é suportado para servidores internos que executam o Lync Server.

  - O registro automático não é suportado para servidores de borda do Lync Server.

  - Quando você envia uma solicitação de certificado baseado em web para uma AC Windows Server 2003, você deve submete-la de um computador que esteja executando Windows Server 2003 com SP2 ou Windows XP.
    
    Observe que, embora o KB922706 oferece suporte para resolver problemas com o registro de certificados de web contra registro de web de Serviços de Certificado do Windows Server 2003, ele não torna possível utilizar o Windows Server 2008, Windows Vista, ou Windows 7 para solicitar um certificado de uma AC Windows Server 2003.

  - Há suporte para os comprimentos de chave de criptografia de 1024, 2048 e 4096. São recomendados os comprimentos de chave de 2048 e superior.

  - A compilação padrão ou a assinatura de hash, algoritmo é RSA. Os \_ algoritmos ECDH P256, ECDH \_ P384 e ECDH \_ P521 também têm suporte. 

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para acesso de usuário externo no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisitos de certificado para o servidor de chat persistente no Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisitos de certificado para mobilidade no Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

