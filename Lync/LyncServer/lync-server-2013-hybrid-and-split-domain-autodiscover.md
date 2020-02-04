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
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Descoberta automática de domínio híbrido e dividido no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-14_

Um espaço de endereço SIP compartilhado, também conhecido como uma implantação de *domínio dividido* , ou uma implantação *híbrida* , é uma configuração na qual os usuários são implantados em uma implantação local e em um ambiente online. O resultado desejado é ter um usuário, independentemente de onde o servidor local está localizado (local ou online), fazer logon na implantação e ser redirecionado para o local do servidor de casa. Para fazer isso, o recurso descoberta automática do Lync Server 2013 é usado para redirecionar o usuário online para a topologia online. Você pode fazer isso Configurando o localizador de recursos uniforme (URL) da descoberta automática usando o Shell de gerenciamento do Lync Server, o cmdlet **Get-CsHostingProvider** e o cmdlet **set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilidade para a implantação de domínio dividido

Será preciso coletar e gravar os seguintes atributos implantados:

  - No Shell de gerenciamento do Lync Server, digite
    
        Get-CsHostingProvider

  - Nos resultados, localize o provedor online com o atributo **ProxyFQDN**. Por exemplo, sipfed.online.lync.com.

  - Grave o valor do ProxyFQDN.

  - Habilite a Federação no painel de controle do Lync Server local, permitindo Federação com o provedor online.

  - Habilite a Federação para o provedor online. Por padrão, todos os usuários online estão habilitados para Federação de domínio e podem se comunicar com todos os domínios.

  - Se você definirá domínios bloqueados e permitidos, determine os domínios que você permitirá explicitamente ou bloqueará explicitamente.

  - Para a Federação online, você deve planejar exceções de firewall, certificados e host DNS (A ou AAAA, se estiver usando IPv6) registros. Além disso, você deve configurar políticas de Federação. Para obter detalhes, consulte [planejando a Federação para o Lync server 2013 e o Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

