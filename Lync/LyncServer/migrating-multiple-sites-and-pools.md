---
title: Migrando vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e14cccb9856534ea9b7229fd020edc2ec21dba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrando vários sites e pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

O Lync Server 2013 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools do Lync Server 2010 para o Lync Server 2013 requer as seguintes considerações:

1.  Depois de implantar um pool piloto do Lync Server 2013, você precisa definir um subconjunto de usuários piloto que serão movidos para o pool do Lync Server 2013 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Lync Server 2013.

2.  Após implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o pool do Lync Server 2013.

3.  Após a transição das rotas federadas dos servidores de borda do Lync Server 2010 para os servidores de borda do Lync Server 2013 piloto, você precisará validar que os usuários federados podem se comunicar com o pool 2013 do Lync Server.

4.  Depois de mover todos os objetos de contato usuários e não usuários, é necessário validar que o pool do Lync Server 2010 está vazio.

5.  Depois de verificar se o pool do Lync Server 2010 está vazio, você pode desativar o pool.
    
    Para obter detalhes sobre como desativar o pool e servidores herdados do Lync Server 2010, consulte [fase 8: encerrar pools herdados](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

