---
title: Migrando vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97bd53e884d4b66b8197ef2672d6ffdca39d4cea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrando vários sites e pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-26_

O Lync Server 2013 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools do Office Communications Server 2007 R2 para o Lync Server 2013 requer as seguintes considerações:

1.  Depois de implantar um pool piloto do Lync Server 2013, você precisa definir um subconjunto de usuários piloto que serão movidos para o pool do Lync Server 2013 e uma metodologia para validar a funcionalidade dos usuários.

2.  Após implantar um servidor de borda no pool piloto, você precisará validar que os usuários externos podem se comunicar com o pool do Lync Server 2013.

3.  Após a transição das rotas federadas dos servidores de borda do Office Communications Server 2007 R2 para os servidores de borda do Lync Server 2013 piloto, você precisará validar que os usuários federados podem se comunicar com o pool 2013 do Lync Server.

4.  Depois de mover todos os objetos de contato usuários e não usuários, é necessário validar que o pool do Office Communications Server 2007 R2 está vazio.

5.  Depois de verificar se o pool do Office Communications Server 2007 R2 está vazio, você pode desativar o pool.
    
    Para obter detalhes sobre como desativar o pool e servidores herdados do Office Communications Server 2007 R2, consulte [fase 10: encerrar o site herdado](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

