---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138068c73264ded3483d8d9f0902d403833a306d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC do Lync Server. Após a migração de uma implantação do Lync Server 2010 para o Lync Server 2013, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Shell de gerenciamento do Lync Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comum do Lync Server 2010 e, em seguida, moverá esses objetos para o pool do Lync Server 2013.

**Migrar telefones de área comum**

1.  No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Para verificar se todos os objetos de contato foram movidos para o pool do Lync Server 2013, no Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Verifique se todos os objetos de contato agora estão associados ao pool do Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

