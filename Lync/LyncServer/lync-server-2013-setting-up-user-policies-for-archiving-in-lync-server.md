---
title: 'Lync Server 2013: Configurando políticas de usuário para arquivamento no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee2074aa9608dad4adcfe85845e7b2e045276f59
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497508"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configurando políticas de usuário para arquivamento no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

Habilitar ou desabilitar o arquivamento para usuários específicos hospedados no Lync Server 2013 requer a criação e configuração de uma ou mais políticas de usuário e, em seguida, a aplicação da política apropriada a usuários ou grupos de usuários específicos. As políticas de usuário substituem as políticas globais e do site, mas somente para os usuários hospedados no Lync Server 2013.

Os usuários sempre estão hospedados no Lync Server. Se a integração com o Microsoft Exchange estiver habilitada, os usuários cujas caixas de correio estão no Microsoft Exchange Server 2013 não precisam ter suas políticas de arquivamento no Lync Server gerenciadas. Esses usuários com arquivamento serão gerenciados pelo Exchange In-Place isenção.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlam se o arquivamento está habilitado para os usuários hospedados no Exchange 2013. O arquivamento desses usuários exige que eles tenham suas caixas de correio colocadas em In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criando e Configurando políticas de usuário para arquivamento no Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Aplicando uma política de arquivamento do Lync Server a um usuário no Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

