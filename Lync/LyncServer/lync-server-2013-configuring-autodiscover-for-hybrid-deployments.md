---
title: 'Lync Server 2013: Configurando a descoberta automática para implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8924194d89eafb75c06ff78ed3b765699e36b196
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Configurando a descoberta automática no Lync Server 2013 para implantações híbridas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-12_

Implantações híbridas são configurações que usam o serviço de nuvem do Microsoft Lync Online e a implantação local. Nesse tipo de configuração, o serviço de descoberta automática deve ser capaz de localizar onde o usuário está realmente localizado. Isso é dizer, o recurso de descoberta automática ajuda a localizar a conta de usuário e onde o servidor que hospeda a conta do usuário é, independentemente de estar na implantação local ou na implantação do Lync Online.

Por exemplo, se a conta de um usuário estiver hospedada em um servidor no Lync Online, a tentativa de localizar o usuário acontecerá da seguinte maneira, em um processo conhecido como *descoberta*:

  - O usuário inicia uma tentativa de conexão com a implantação local, **contoso.com**.

  - A tentativa é enviada para lyncdiscover.contoso.com, o nome DNS associado ao serviço de descoberta automática.

  - A descoberta automática se refere ao pool de registradores presumidos na implantação do contoso.com local e recebe informações sobre o servidor primário real do usuário hospedado no Lync Online. A descoberta automática envia ao usuário uma referência para o serviço de descoberta automática do **Lync.com** online.

  - O usuário inicia uma tentativa de conexão com o serviço de descoberta automática do lync.com Online e consegue localizar a conta do usuário e o servidor primário do usuário.

Para permitir que os clientes descubram a implantação em que o servidor primário do usuário está localizado, você deve configurar o serviço de descoberta automática com um novo Uniform Resource Locator (URL). Siga este procedimento para configurar o serviço de descoberta automática.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configurando a descoberta automática para implantações híbridas

1.  No tópico [requisitos de serviço de descoberta automática para o Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), use Get-CsHostingProvider para recuperar o valor do atributo ProxyFQDN.

2.  No Shell de gerenciamento do Lync Server, digite
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Onde \[a\] identidade é substituída pelo nome de domínio do espaço de endereço SIP compartilhado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

