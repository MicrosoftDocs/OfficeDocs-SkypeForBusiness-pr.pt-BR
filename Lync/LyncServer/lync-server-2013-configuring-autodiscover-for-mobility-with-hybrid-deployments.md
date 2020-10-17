---
title: Configurando a descoberta automática para mobilidade com implantações híbridas
description: Configurando a descoberta automática para mobilidade com implantações híbridas.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66f0045ec1fce65b8e21b6a6f4494b96c93912
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562457"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configurando a descoberta automática no Lync Server 2013 para mobilidade com implantações híbridas

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-18_

As implantações híbridas são configurações que usam o serviço de nuvem do Microsoft Lync Online e a implantação no local. Nesse tipo de configuração, o serviço de descoberta automática deve ser capaz de localizar onde o usuário está realmente localizado. Isso é dizer, a descoberta automática ajuda a localizar a conta de usuário e onde o servidor que hospeda a conta do usuário é, independentemente de se ele estiver na implantação local ou na implantação do Lync Online.

Por exemplo, se a conta de um usuário estiver hospedada em um servidor no Lync Online, a tentativa de localizar o usuário acontecerá da seguinte maneira, em um processo conhecido como *descoberta*:

  - O usuário inicia uma tentativa de conexão com a implantação local, **contoso.com**.

  - A tentativa é enviada a lyncdiscover.contoso.com, o nome de DNS associado ao serviço de descoberta automática.

  - A descoberta automática se refere ao pool de registradores assumido na implantação local do contoso.com e recebe informações sobre o servidor local real do usuário hospedado no Lync Online. A descoberta automática envia ao usuário uma referência do serviço online de descoberta automática do **lync.com**.

  - O usuário inicia uma tentativa de conexão com o serviço online de descoberta automática do lync.com e pode localizar a conta do usuário e o servidor que o está hospedando.

Para permitir que os clientes móveis descubram a implantação em que o servidor que hospeda o usuário está localizado, é necessário configurar o serviço de descoberta automática com uma nova URL. Para configurar o serviço de descoberta automática, faça o seguinte:

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configurando a descoberta automática em implantações híbridas

1.  Você usa Get-CsHostingProvider para recuperar o valor do atributo ProxyFQDN.

2.  No Shell de gerenciamento do Lync Server, digite
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Onde \[ Identity \] é substituído pelo nome de domínio do espaço de endereçamento SIP compartilhado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

