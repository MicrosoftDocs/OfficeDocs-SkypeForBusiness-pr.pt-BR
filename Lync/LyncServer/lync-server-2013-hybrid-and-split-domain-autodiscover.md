---
title: 'Lync Server 2013: híbrido e dividido-Domain-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0340e1226d3fb7abc475769892f0cd675c838c89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528158"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Descoberta automática de domínio e híbrido no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-14_

Um espaço de endereçamento SIP compartilhado, também conhecido como implantação de *domínio dividido* , ou uma implantação *híbrida* , é uma configuração em que os usuários são implantados em uma implantação local e em um ambiente online. O resultado desejado é ter um usuário, independentemente de onde o servidor local está localizado (local ou online), fazer logon na implantação e ser redirecionado para o local do servidor de origem. Para fazer isso, o recurso de descoberta automática do Lync Server 2013 é usado para redirecionar o usuário online para a topologia online. Você pode fazer isso Configurando o localizador de recursos uniforme (URL) de descoberta automática usando o Shell de gerenciamento do Lync Server, o cmdlet **Get-CsHostingProvider** e o cmdlet **set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilidade para a Implantação de domínio dividido

Será necessário coletar e registrar os seguintes atributos implantados:

  - No Shell de gerenciamento do Lync Server, digite
    
        Get-CsHostingProvider

  - Nos resultados, encontre o provedor online com o atributo **ProxyFQDN**. Por exemplo, sipfed.online.lync.com.

  - Registre o valor de ProxyFQDN.

  - Habilite a Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online.

  - Habilite a federação para o provedor online. Por padrão, todos os usuários online estão habilitados para Federação de domínio e podem se comunicar com todos os domínios.

  - Se você definir domínios bloqueados e permitidos, determine os domínios que você irá explicitamente permitir ou bloquear explicitamente.

  - Para Federação online, você deve planejar exceções de firewall, certificados e host DNS (A ou AAAA, se estiver usando IPv6). Além disso, é necessário configurar as políticas de federação. Para obter detalhes, consulte [Planning for Lync server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

