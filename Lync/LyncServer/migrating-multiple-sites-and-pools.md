---
title: Migrar vários sites e pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7759c52051dfe4ca4a46e105e6a33f3284f334e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Migrar vários sites e pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

O Lync Server 2013 oferece suporte a implantações de vários locais e vários pools. O processo de migração de vários pools do Lync Server 2010 para o Lync Server 2013 requer as seguintes considerações:

1.  Depois de implantar um pool piloto do Lync Server 2013, você precisa definir um subconjunto de usuários pilotos que serão movidos para o pool do Lync Server 2013 e uma metodologia para validar a funcionalidade dos usuários. Por exemplo, depois de mover um usuário para o pool piloto, verifique se a política de conferência do usuário foi movida para o Lync Server 2013.

2.  Depois de implantar um servidor de borda no pool piloto, você precisa validar que os usuários externos podem se comunicar com o pool do Lync Server 2013.

3.  Após a transição de rotas federadas dos servidores de borda do Lync Server 2010 para os servidores piloto do Lync Server 2013 Edge, você precisa validar que os usuários federados podem se comunicar com o pool do Lync Server 2013.

4.  Depois de mover todos os usuários e objetos de contato que não sejam usuários, você precisa validar que o pool do Lync Server 2010 está vazio.

5.  Depois de verificar se o pool do Lync Server 2010 está vazio, você pode desativar o pool.
    
    Para obter detalhes sobre como desativar o pool e os servidores herdados do Lync Server 2010, consulte [fase 8:](phase-8-decommission-legacy-pools.md)descomissionar pools herdados.

</div>

<span> </span>

</div>

</div>

</div>

