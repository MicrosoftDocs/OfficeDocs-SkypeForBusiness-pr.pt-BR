---
title: Migrando a Federação XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61a48c579ed9afa3f1a09ed1c3a7129e9e24924d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrando a Federação XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Versões anteriores do Lync Server e Office Communications Server forneciam um Gateway XMPP (Extensible Messaging and Presence Protocol) que pode ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. No Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso. A funcionalidade do XMPP está instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda do Lync Server 2013 e no Gateway XMPP que é executado no servidor front-end do Lync Server 2013.

De uma perspectiva de migração, uma conta de usuário do Lync Server pode ser movida para um pool do Lync Server 2013 e continuar a usar o Gateway XMPP herdado. Isso só é possível quando o parceiro federado XMPP não está configurado no Lync Server 2013.

Em resumo, se o Lync Server 2010 tiver sido implantado com o gateway do Office Communications Server 2007 R2 XMPP e a Federação XMPP tiver sido habilitada para usuários herdados do Lync Server 2010, para migrar a Federação do XMPP para o Lync Server 2013:

1.  Implantar um pool do Lync Server 2013.

2.  Implantar um servidor de borda do Lync Server 2013.

3.  Mover todos os usuários para o pool do Lync Server 2013

4.  Crie políticas de acesso XMPP e certificados para o servidor de borda.

5.  Habilite a Federação XMPP no Lync Server 2013. 

6.  Atualize as entradas de DNS para apontar para o gateway do Lync Server 2013 XMPP.

</div>

<span> </span>

</div>

</div>

</div>

