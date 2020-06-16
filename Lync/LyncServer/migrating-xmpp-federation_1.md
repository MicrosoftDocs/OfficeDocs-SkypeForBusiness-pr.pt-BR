---
title: Migrar a federação XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e446a4981a3b9b255311ff5720e2c6dc36d61e9a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>Migrar a federação XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-16_

Versões anteriores do Office Communications Server forneceram um gateway do protocolo XMPP (Extensible Messaging and Presence Protocol) que poderia ser implantado como uma função de servidor separada para permitir a Federação com implantações do XMPP. No Lync Server 2013, a funcionalidade do XMPP pode ser implantada como um recurso. A funcionalidade do XMPP está instalada em duas partes: como um proxy do XMPP que é executado no servidor de borda do Lync Server 2013 e no Gateway XMPP que é executado no servidor front-end do Lync Server 2013.

De uma perspectiva de migração, uma conta de usuário do Office Communications Server 2007 R2 pode ser movida para um pool do Lync Server 2013 e continuar a usar o Gateway XMPP do Office Communications Server 2007 R2. Isso só é possível quando o parceiro federado XMPP não está configurado no Lync Server 2013.

Em resumo, se o Office Communications Server foi implantado com o Gateway XMPP do Office Communications Server 2007 R2 e a Federação do XMPP tiver sido habilitada para usuários herdados do Office Communications Server 2007 R2, para migrar a Federação do XMPP para o Lync Server 2013:

1.  Implantar um pool do Lync Server 2013.

2.  Implantar um servidor de borda do Lync Server 2013.

3.  Mova todos os usuários para o pool do Lync Server 2013.

4.  Crie políticas de acesso XMPP e certificados para o servidor de borda.

5.  Habilite a Federação XMPP no Lync Server 2013. 

6.  Atualize as entradas de DNS para apontar para o gateway do Lync Server 2013 XMPP.

</div>

<span> </span>

</div>

</div>

</div>

