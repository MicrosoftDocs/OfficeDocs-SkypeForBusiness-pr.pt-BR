---
title: 'Lync Server 2013: Configurar a tabela de número não atribuído'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configurar a tabela de número não atribuído no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

No Lync Server 2013, você pode especificar o que acontece com as chamadas recebidas para números de telefone válidos para a sua organização, mas que não estão atribuídas a um usuário ou telefone. Os chamadores podem ouvir uma mensagem ou podem ser roteados para outro destino, ou ambos.

O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribuí-lo a um anúncio que fornece o novo número.

<div>


> [!IMPORTANT]  
> Antes de configurar a tabela numérica não atribuída, seu sistema já deve ter comunicados definidos ou uma configuração de atendedor automático de Unificação de mensagens do Exchange (um).



</div>

<div>


> [!TIP]  
> Quando alguém chama um número não atribuído, o Lync Server procura a tabela número não atribuído da parte superior para a inferior e usa o primeiro intervalo correspondente. Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

[Criar ou modificar um intervalo de números não atribuídos no Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [criar um anúncio no Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

