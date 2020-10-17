---
title: 'Lync Server 2013: concedendo permissões'
description: 'Lync Server 2013: concedendo permissões.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bdb2b1ef39b85caa89c7597f455e6e4fc08e44e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554497"
---
# <a name="granting-permissions-in-lync-server-2013"></a>Concedendo permissões no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-15_

Para a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio especificado. Ao conceder permissões para um OU, as seguintes permissões são concedidas:

  - Ler

  - Gravação

  - ReadSPN

  - WriteSPN

Para administração, você pode adicionar permissões a UOs especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem precisar ser membros do grupo de administradores de domínio. As permissões adicionadas à UO especificada são as mesmas permissões que o cmdlet **Enable-CsAdDomain** adiciona aos contêineres de UO computadores e usuários.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Concedendo permissões de configuração no Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Concedendo permissões de unidade organizacional no Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

