---
title: 'Lync Server 2013: Alterando o Pool de borda associado ao pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Alterando o Pool de borda associado ao pool Front-End no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Se um pool de bordas ficar inoperante, mas o pool de front-end no mesmo site ainda estiver em execução, será necessário definir o pool de front-ends para usar um pool de bordas em um site diferente até que o pool de bordas com falha seja restaurado.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Alterar o pool de bordas associado a um pool de front-end

1.  No construtor de topologias, navegue até o nome do pool de front-ends que você precisa alterar.

2.  Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.

3.  Na seção **associações** , em associar a um **pool de bordas (para componentes de mídia)**, use a caixa suspensa para selecionar o pool de bordas ao qual você deseja associar esse pool de front-ends.

4.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Recuperação de desastres do servidor de borda no Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

