---
title: Redefinir o controle de admissão de chamada
description: Redefina o controle de admissão de chamadas.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551237"
---
# <a name="reset-call-admission-control"></a>Redefinir o controle de admissão de chamada

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-11_

Se um pool de front-ends do Lync Server 2010 estiver hospedando o CAC (controle de admissão de chamadas), você deve mover a hospedagem de CAC para um pool do Lync Server 2013 antes de poder remover o pool de front-ends do Lync Server 2010.

<div>

## <a name="to-reset-cac"></a>Para redefinir o CAC

1.  Abra o Construtor de Topologia.

2.  Clique com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.

3.  Em **Configuração de Controle de Admissão de Chamadas**, certifique-se de que a opção ** Habilitar controle de admissão de chamadas** está selecionada.

4.  Em **pool de front-ends para executar o CAC (controle de admissão de chamadas)**, selecione o pool do Lync Server 2013 que deve hospedar o CAC e clique em **OK**.

5.  Publique a topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

