---
title: 'Lync Server 2013: preparando seu ambiente para VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bf8480a0905184d7259a9f0c3aa79725453f59d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506798"
---
# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a>Preparando seu ambiente do Lync Server 2013 para VDI

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Para preparar o ambiente para o plug-in do Lync VDI, o administrador deve executar as seguintes etapas.

1.  No Lync Server 2013, verifique se EnableMediaRedirection está definido como TRUE para todos os usuários do VDI. Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

2.  No computador do Data Center, instale o cliente do Lync 2013 em todas as máquinas virtuais.

3.  Nos computadores locais, instale o plug-in do Lync VDI.

</div>

<span> </span>

</div>

</div>

</div>

