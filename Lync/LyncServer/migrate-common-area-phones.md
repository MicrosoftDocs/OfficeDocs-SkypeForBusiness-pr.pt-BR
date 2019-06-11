---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-29_

Os telefones de área comuns são telefones IP que costumam residir em um espaço de trabalho compartilhado ou em uma área comum, como um lobby, uma cozinha ou um chão de fábrica. Os telefones de área comuns não precisam estar conectados a um computador para fornecer a funcionalidade de comunicação unificada do Lync Server. Depois de migrar uma implantação do Lync Server 2010 para o Lync Server 2013, você também deve migrar os objetos de contato associados ao telefone de área comum comum. Usando o Shell de gerenciamento do Lync Server, primeiro você recuperará todos os objetos de contato associados aos telefones da área comum do Lync Server 2010 e moverá esses objetos para o pool do Lync Server 2013.

**Migrar telefones de área comum**

1.  No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.

2.  Na linha de comando, digite o seguinte:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Para verificar se todos os objetos de contato foram movidos para o pool do Lync Server 2013, no Shell de gerenciamento do Lync Server, digite o seguinte:
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Verifique se todos os objetos de contato estão agora associados ao pool do Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

