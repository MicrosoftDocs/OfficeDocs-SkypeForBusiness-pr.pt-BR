---
title: 'Lync Server 2013: requisitos de infraestrutura de certificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestrutura de certificado para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-06-23_

O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para dar suporte a conexões TLS e TLS mútua (MTLS).

O Lync Server usa certificados para as seguintes finalidades:

  - Conexões de TLS entre cliente e servidor

  - Conexões MTLS entre servidores

  - Federação usando descoberta automática de DNS de parceiros

  - Acesso de usuários remotos a IM (mensagens instantâneas)

  - Acesso de usuário externo a sessões de áudio/vídeo (A/V), compartilhamento de aplicativos e conferência

  - Solicitações móveis usando a descoberta automática de serviços Web

Para o Lync Server, os seguintes requisitos comuns se aplicam:

  - Todos os certificados de servidor devem oferecer suporte à autorização de servidor (EKU de servidor).

  - Todos os certificados de servidor devem conter um CDP (Ponto de Distribuição de CRL).

  - Todos os certificados devem ser assinados usando um algoritmo de assinatura que seja compatível com o sistema operacional. O Lync Server 2013 é compatível com o pacote de Resumo de SHA-1 e SHA-2 (224, 256, 384 e 512) e atende ou supera os requisitos do sistema operacional. Para obter suporte para o sistema [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)operacional, consulte.
    
    <div>
    

    > [!NOTE]  
    > O uso do algoritmo de assinatura RSASSA-PSS não é permitido e pode levar a erros no login e a problemas de encaminhamento de chamadas, entre outros. 

    
    </div>

  - O registro automático tem suporte para servidores internos que executam o Lync Server.

  - Não há suporte para a inscrição automática nos servidores do Lync Server Edge.

  - Ao enviar uma solicitação de certificado baseada na Web para uma autoridade de certificação do Windows Server 2003, você deve enviá-la a partir de um computador que esteja executando o Windows Server 2003 com SP2 ou Windows XP.
    
    Observe que, embora o KB922706 forneça suporte para resolver problemas com a inscrição de certificados da Web em relação a um registro na Web de serviços de certificado do Windows Server 2003, ele não permite usar o Windows Server 2008, o Windows Vista ou o Windows 7 para solicitar um certificado de uma autoridade de certificação do Windows Server 2003.

  - Os comprimentos de chave de criptografia de 1024, 2048 e 4096 são suportados. Comprimentos de pelo menos 2048 são recomendados.

  - O algoritmo de hash de assinatura ou sumário padrão é RSA. Os algoritmos ECDH\_P256\_, ECDH P384 e\_ECDH P521 também têm suporte. 

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisitos de certificado para acesso do usuário externo no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisitos de certificado para o servidor de Chat Persistente no Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisitos de certificado para mobilidade no Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

