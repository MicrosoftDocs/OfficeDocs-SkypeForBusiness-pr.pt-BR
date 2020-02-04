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
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Configurar números de telefone não atribuídos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O Lync Server permite configurar o que acontece com as chamadas recebidas para números de telefone que sejam válidos para a sua organização, mas não são atribuídos a um usuário ou a um telefone. Para configurar o tratamento dessas chamadas, configure uma tabela de número não atribuído. Você pode usar a tabela para direcionar as chamadas para um aplicativo de anúncio ou para um servidor de UM Exchange.

Como configurar a tabela de números não atribuídos dependerá de como você deseja usá-la. Você pode configurar a tabela com todas as extensões válidas para a sua organização, somente com extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuídos pode incluir ambos, números atribuídos e não atribuídos, mas será invocada somente quando um chamador discar um número que não esteja atribuído atualmente. Se você incluir todas as extensões válidas na tabela de números não atribuídos, pode especificar a ação que ocorre sempre que alguém sair da sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, pode ajustar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao cliente, poderá incluir o número do atendimento ao cliente antigo na tabela e atribuí-lo a um comunicado que fornece o novo número.

<div>


> [!IMPORTANT]  
> Antes de configurar a tabela número não atribuído, você já deve ter um ou mais comunicados definidos ou um atendedor automático de UM do Exchange. Para obter detalhes sobre como criar comunicados, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>. Para ver se você configurou as configurações de UM do Exchange UM, execute o cmdlet <STRONG>Get-CsExUmContact</STRONG> . Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Excluir um intervalo de números não atribuído no Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

