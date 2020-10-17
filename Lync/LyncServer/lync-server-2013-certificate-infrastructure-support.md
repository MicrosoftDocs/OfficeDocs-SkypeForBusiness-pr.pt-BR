---
title: Suporte à infraestrutura de certificado do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b17c6f53130d5f0cca96ce3b719001029398d91c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507998"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Suporte à infraestrutura de certificado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

O Lync Server 2013 requer uma infraestrutura de chave pública (PKI) para suportar conexões de TLS e TLS mútuo (MTLS). Por padrão, o Lync Server 2013 é configurado para usar o TLS para conexões de cliente para servidor. O MTLS é usado para conexões entre servidores.

Os certificados MTLS devem ser emitidos por autoridades de certificação confiáveis (CAs) para o Lync Server 2013. O Lync Server oferece suporte a certificados emitidos por meio das seguintes autoridades de certificação:

  - Certificados emitidos por uma autoridade de certificação interna
    
      - A autoridade de certificação do sistema operacional Windows Server 2003
    
      - A autoridade de certificação do sistema operacional Windows Server 2008
    
      - A CA do sistema operacional Windows Server 2008 R2
    
      - A autoridade de certificação do sistema operacional Windows Server 2012
    
      - A CA do sistema operacional Windows Server 2012 R2

  - Certificados emitidos por uma autoridade de certificação pública

A comunicação com outros aplicativos e servidores, como o Exchange 2013, requer um certificado que seja compatível com outros aplicativos e produtos. Para a versão 2013, Lync Server 2013 e outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o SharePoint Server, dão suporte ao protocolo de autorização aberta (OAuth) para autenticação e autorização de servidor para servidor. Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou a documentação de operações.

Para conexões de clientes que executam o sistema operacional Windows 7, o sistema operacional Windows Server 2008 R2 e o Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclui suporte para (mas não exige) certificados assinados usando a função de hash de criptografia SHA-256. Para suportar acesso externo usando SHA-256, o certificado externo é emitido por um AC público usando SHA-256.

Para obter detalhes sobre os requisitos de certificado, consulte [Certificate Infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) na documentação de planejamento. Para obter detalhes sobre o uso de caracteres curinga com certificados, confira [suporte a certificados curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) na documentação de suporte.

</div>

<span> </span>

</div>

</div>

</div>

