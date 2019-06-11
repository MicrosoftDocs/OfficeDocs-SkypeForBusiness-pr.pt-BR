---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-16_

As versões anteriores do Office Communications Server forneciam um gateway Extensible Messaging and Presence Protocol (XMPP) que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. No Lync Server 2013, a funcionalidade XMPP pode ser implantada como um recurso. A funcionalidade XMPP é instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda do Lync Server 2013 e o Gateway XMPP executado no servidor front-end do Lync Server 2013.

De uma perspectiva de migração, uma conta de usuário do Office Communications Server 2007 R2 pode ser movida para um pool do Lync Server 2013 e continuar a usar o gateway do Office Communications Server 2007 R2 XMPP. Isso só é possível quando o parceiro federado XMPP não está configurado no Lync Server 2013.

Em resumo, se o Office Communications Server tiver sido implantado com o gateway do Office Communications Server 2007 R2 e a Federação do XMPP tiver sido habilitada para usuários herdados do Office Communications Server 2007 R2, para migrar a Federação do XMPP para o Lync Server 2013:

1.  Implantar um pool do Lync Server 2013.

2.  Implantar um servidor de borda do Lync Server 2013.

3.  Mover todos os usuários para o pool do Lync Server 2013.

4.  Criar políticas e certificados de acesso XMPP para o servidor de borda.

5.  Habilite a Federação do XMPP no Lync Server 2013. 

6.  Atualize as entradas de DNS para apontar para o gateway do Lync Server 2013 XMPP.

</div>

<span> </span>

</div>

</div>

</div>

