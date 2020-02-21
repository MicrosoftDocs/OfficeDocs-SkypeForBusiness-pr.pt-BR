---
title: 'Lync Server 2013: planejar certificados do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Edge Server certificates
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413010(v=OCS.15)
ms:contentKeyID: 48185798
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ac330914a0d748c366d2a6e40ac0ad9f03543d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planejar certificados de servidor de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-05_

A criação de certificado para borda é simplificada no Lync Server 2013.

**Fluxograma de certificados do Servidor de Borda**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Criar um certificado público único, certificar-se de ter uma chave privada de exportação definida para o certificado e atribui-lo às seguintes interfaces externas do Servidor de Borda usando o assistente de certificado:

<div>


> [!IMPORTANT]  
> Não há suporte para certificados curinga no Lync Server, exceto onde usados para resumir as URLs simples através do proxy reverso. Você deve definir nomes alternativos de entidades distintos (SANs) para cada nome de domínio SIP, serviço de borda de webconferência, serviço de borda A/V e domínio XMPP oferecidos por sua implantação.



</div>

<div>


> [!NOTE]  
> Introduzido no Lync Server 2013, a preparação de certificados de autenticação de áudio/vídeo com antecedência do tempo de expiração do certificado atual requer alguns planejamentos adicionais. Em vez de um certificado com várias finalidades para a interface de borda externa, você precisará de dois certificados, um atribuído ao serviço de borda de acesso e serviço de borda de Webconferência e um certificado para o serviço de borda A/V. Para obter detalhes adicionais, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">preparando o AV e certificados OAuth no Lync Server 2013 using-rolo in Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> No caso de um pool de servidores de borda, exporte o certificado com a chave privada para cada servidor de borda e atribua o certificado a cada serviço do servidor de borda. Faça o mesmo para o certificado de servidor de borda interno, exportando o certificado com a chave privada e atribuindo a cada interface de borda interna.



</div>

  - Certificar-se de ter uma chave privada de exportação atribuída ao certificado

  - Serviço de borda de acesso (chamado de **borda de acesso SIP externa** no assistente de certificado)

  - Serviço de borda de Webconferência (referido como **borda de Webconferência externa** no assistente de certificado)

  - Serviço de Autenticação A/V (referido como **Borda A/V externa** no assistente de certificado)

Criar um certificado interno único com chave privada de exportação, copiá-lo e atribui-lo a cada uma das interfaces internas do Servidor de Borda:

  - Servidor de Borda (referido como **Borda interna** no assistente de certificado)

<div>


> [!IMPORTANT]  
> É possível usar certificados separados e distintos para cada serviço de servidor de borda. Um bom motivo para escolher certificados separados é se você deseja usar o novo recurso de certificado de reversão para o certificado de serviço de borda A/V. No caso desse recurso, é recomendável desacoplar o certificado de serviço de borda a/V do serviço de borda de acesso e do serviço de borda de Webconferência. Se você optar por solicitar, adquirir e atribuir certificados separados para cada serviço, deverá solicitar que a chave privada seja exportável para o serviço de borda A/V (novamente, isso estará na realidade o serviço de autenticação A/V) e atribuir o mesmo certificado à interface externa de borda A/V em cada servidor de borda.



</div>

<div>

## <a name="see-also"></a>Confira também


[Preparando certificados AV e OAuth no Lync Server 2013 usando-o-rolo no set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Alterações no Lync Server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

