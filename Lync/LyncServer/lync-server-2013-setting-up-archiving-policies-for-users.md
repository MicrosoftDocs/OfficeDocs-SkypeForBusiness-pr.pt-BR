---
title: 'Lync Server 2013: Configurando políticas de arquivamento para usuários'
description: 'Lync Server 2013: Configurando políticas de arquivamento para usuários.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559517"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>Configurando políticas de arquivamento para usuários no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

É possível habilitar ou desabilitar o Arquivamento para usuários específicos criando e configurando uma política de Arquivamento para usuários e aplicando a política para usuários ou grupos de usuários específicos. As políticas de usuário substituem qualquer política global ou locais. As políticas de arquivamento só se aplicam se você não usar a integração com o Microsoft Exchange ou, se você usar a integração com o Microsoft Exchange, mas tiver alguns usuários que não estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas em In-Place.

Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.

<div>


> [!NOTE]  
> Se você habilitar a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlará se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e se suas caixas de correio serão colocadas In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções adequadas nas configurações de Arquivamento antes de habilitar o Arquivamento de comunicações internas e externas nas políticas de Arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando políticas de usuário para arquivamento no Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

