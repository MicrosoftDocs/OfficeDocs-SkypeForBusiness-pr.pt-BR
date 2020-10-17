---
title: 'Lync Server 2013: configurar números de telefone não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd933ac87addf4a2094009e9f437c29437d882a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520228"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Configurar números de telefone não atribuídos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Lync Server permite que você configure o que acontece com as chamadas de entrada para números de telefone que são válidos para a sua organização, mas não estão atribuídos a um usuário ou telefone. Para configurar a manipulação dessas chamadas, configure uma tabela de números não atribuídos. Você pode usar a tabela para encaminhar as chamadas para um aplicativo de comunicado ou para um servidor de UM do Exchange.

O modo como você configura a tabela de números não atribuídos depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação dos dois tipos de números. A tabela de números não atribuídos pode incluir números atribuídos e não atribuídos, mas é invocada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuídos, será possível especificar a ação que ocorre quando alguém deixa sua organização, sem precisar reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao consumidor, poderá incluir o número antigo do serviço de atendimento ao consumidor na tabela e atribuí-lo a um anúncio que fornece o novo número.

<div>


> [!IMPORTANT]  
> Antes de configurar a tabela de números não atribuídos, você já deve ter um ou mais comunicados definidos ou um atendedor automático de UM do Exchange configurado. Para obter detalhes sobre como criar comunicados, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>. Para ver se você definiu as configurações do UM do Exchange, execute o cmdlet <STRONG>Get-CsExUmContact</STRONG> . Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Excluir um intervalo de números não atribuídos no Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

