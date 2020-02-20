---
title: Redefinir controle de admissão de chamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8f4a0b222d39b32eb22d2c96f5944f18c094da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="7a4ea-102">Redefinir controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="7a4ea-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a4ea-103">_**Última modificação do tópico:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="7a4ea-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="7a4ea-104">Se um pool de front-ends do Lync Server 2010 estiver hospedando o CAC (controle de admissão de chamadas), você deve mover a hospedagem de CAC para um pool do Lync Server 2013 antes de poder remover o pool de front-ends do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="7a4ea-105">Para redefinir o CAC</span><span class="sxs-lookup"><span data-stu-id="7a4ea-105">To reset CAC</span></span>

1.  <span data-ttu-id="7a4ea-106">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="7a4ea-107">Clique com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="7a4ea-108">Em **Configuração de Controle de Admissão de Chamadas**, certifique-se de que a opção \*\* Habilitar controle de admissão de chamadas\*\* está selecionada.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="7a4ea-109">Em **pool de front-ends para executar o CAC (controle de admissão de chamadas)**, selecione o pool do Lync Server 2013 que deve hospedar o CAC e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="7a4ea-110">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="7a4ea-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

