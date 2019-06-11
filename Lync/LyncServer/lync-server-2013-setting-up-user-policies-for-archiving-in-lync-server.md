---
title: 'Lync Server 2013: Configurando as políticas de usuário para arquivamento no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configurando políticas de usuário para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

Habilitar ou desabilitar o arquivamento para usuários específicos hospedados no Lync Server 2013 requer a criação e a configuração de uma ou mais políticas de usuário e, em seguida, a aplicação da política apropriada a usuários específicos ou grupos de usuários. Políticas de usuário substituem políticas globais e do site, mas somente para usuários hospedados no Lync Server 2013.

Os usuários sempre são hospedados no Lync Server. Se a integração com o Microsoft Exchange estiver habilitada, os usuários cujas caixas de correio estiverem no Microsoft Exchange Server 2013 não precisarão ter suas políticas de arquivamento no Lync Server gerenciadas. Esses usuários com arquivamento serão gerenciados pelo bloqueio in-loco do Exchange.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.

<div>


> [!NOTE]  
> Se você tiver habilitado a integração do Microsoft Exchange para a sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários que são hospedados no Exchange 2013. O arquivamento para estes usuários requer que eles tenham suas caixas de correio colocadas no bloqueio in-loco. Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte Configurando <A href="lync-server-2013-configuring-archiving-options.md">Opções de arquivamento no Lync Server 2013</A> na documentação de implantação.



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

