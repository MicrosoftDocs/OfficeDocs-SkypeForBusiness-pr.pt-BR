---
title: 'Lync Server 2013: Planejar certificados do Servidor de Borda'
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
ms.openlocfilehash: faad6dba610df8033b75b0c87c52fbb065dc5dcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-edge-server-certificates-in-lync-server-2013"></a>Planejar certificados do Servidor de Borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-05_

A criação de certificados para o Edge é simplificada no Lync Server 2013.

**Fluxograma de certificados do servidor de borda**

![a5fc20db-7ced-4364-b577-6a709a8367cd](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "a5fc20db-7ced-4364-b577-6a709a8367cd")

Crie um único certificado público, verifique se você tem uma chave privada exportável definida para o certificado e atribui-la às seguintes interfaces externas do servidor de borda usando o assistente de certificado:

<div>


> [!IMPORTANT]  
> Não há suporte para certificados curinga no Lync Server, exceto onde usados para resumir as URLs simples por meio do proxy reverso. Você deve definir nomes alternativos de assunto distintos (SANs) para cada nome de domínio SIP, serviço de borda de webconferência, serviço de borda A/V e domínio XMPP oferecidos pela sua implantação.



</div>

<div>


> [!NOTE]  
> Apresentado no Lync Server 2013, a transferência de certificados de autenticação de áudio/vídeo antes do tempo de expiração do certificado atual requer algum planejamento adicional. Em vez de um certificado com várias finalidades para a interface de borda externa, você precisará de dois certificados, um atribuído ao serviço de borda de acesso e serviço de borda de Webconferência e um certificado para o serviço de borda A/V. Para obter mais detalhes, consulte <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate">preparando certificados do AV e do OAuth no Lync Server 2013 usando o-roll Set-CsCertificate</A>



</div>

<div>


> [!IMPORTANT]  
> No caso de um pool de servidores de borda, exporte o certificado com a chave particular para cada servidor de borda e atribua o certificado a cada serviço de servidor de borda. Faça o mesmo para o certificado interno do servidor de borda, exportando o certificado com a chave privada e atribuindo a cada interface de borda interna.



</div>

  - Verifique se você tem uma chave privada exportável atribuída para o certificado

  - Serviço de borda de acesso (chamado de **borda de acesso SIP externa** no assistente de certificado)

  - Serviço de borda de Webconferência (chamado de **borda de Webconferência externa** no assistente de certificado)

  - Serviço de autenticação a/V (chamado de **borda de a/v externa** no assistente de certificado)

Crie um único certificado interno com a chave privada exportável, copie e atribua-o a cada uma das interfaces internas do servidor de borda:

  - Servidor de borda (chamado de **borda interna** no assistente de certificado)

<div>


> [!IMPORTANT]  
> É possível usar certificados separados e distintos para cada serviço do servidor de borda. Um bom motivo para escolher certificados separados é se você quiser usar o novo recurso de certificado de reversão para o certificado de serviço de borda A/V. No caso desse recurso, é recomendável a dissociação do certificado de serviço de borda a/V do serviço de borda de acesso e do serviço de borda de conferência via Web. Se você optar por solicitar, adquirir e atribuir certificados separados para cada serviço, será necessário solicitar que a chave privada seja exportável para o serviço de borda A/V (novamente, isso está em realidade, o serviço de autenticação A/V) e atribui o mesmo certificado à interface externa de Edge a/V em cada servidor de borda.



</div>

<div>

## <a name="see-also"></a>Confira também


[Preparando certificados do AV e do OAuth no Lync Server 2013 usando-roll no set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  


[Alterações no Lync Server 2013 que afetam o planejamento do Servidor de Borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

