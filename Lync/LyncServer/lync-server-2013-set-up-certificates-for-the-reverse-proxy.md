---
title: 'Lync Server 2013: configurar certificados para o proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d03cec1dd2397b8471788f5c4661305e7ea93e42
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configurar certificados para o proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Cada servidor proxy reverso requer um certificado de servidor Web para ser usado pelo serviço de escuta. O certificado de servidor Web deve ser emitido por uma autoridade de certificação pública.

Para obter detalhes sobre esse e outros requisitos de certificado, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Para configurar um certificado de Serviços Web para o proxy reverso

  - Você já deve ter configurado seu proxy reverso, incluindo a configuração do certificado de Serviços Web. Se você não fez isso antes de iniciar a implantação dos servidores de borda, use os procedimentos para [Configurar servidores de proxy reverso para o Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) para criar uma solicitação e instalar o certificado de serviços Web e, em seguida, criar cada regra de publicação da Web e configurá-la para usar o certificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

