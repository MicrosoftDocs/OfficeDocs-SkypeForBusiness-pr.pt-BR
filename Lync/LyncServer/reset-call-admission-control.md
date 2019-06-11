---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a>Redefinir controle de admissão de chamada

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-11_

Se um pool de front-end do Lync Server 2010 estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover o hospedagem do CAC para um pool do Lync Server 2013 para poder remover o pool de front-ends do Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Para redefinir o CAC

1.  Abrir o construtor de topologias.

2.  Clique com o botão direito do mouse no nó do site e, em seguida, clique em **Editar propriedades**.

3.  Em **configuração de controle de admissão de chamada**, verifique se a opção **habilitar controle de admissão de chamadas** está selecionada.

4.  Em **pool de front-ends para executar o controle de admissão de chamadas (CAC)**, selecione o pool do Lync Server 2013 para hospedar o CAC e, em seguida, clique em **OK**.

5.  Publique a topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

