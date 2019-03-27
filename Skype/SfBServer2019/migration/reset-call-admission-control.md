---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um pool de Front-End herdado está hospedando o controle de admissão de chamadas (CAC), você deve mover a hospedagem de CAC para um Skype para Business Server 2019 pool antes de poder remover o pool de Front-End herdado.
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895772"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="e33af-103">Redefinir controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="e33af-103">Reset call admission control</span></span>

<span data-ttu-id="e33af-104">Se um pool de Front-End herdado está hospedando o controle de admissão de chamadas (CAC), você deve mover a hospedagem de CAC para um Skype para Business Server 2019 pool antes de poder remover o pool de Front-End herdado.</span><span class="sxs-lookup"><span data-stu-id="e33af-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="e33af-105">Para redefinir o CAC</span><span class="sxs-lookup"><span data-stu-id="e33af-105">To reset CAC</span></span>

1. <span data-ttu-id="e33af-106">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="e33af-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="e33af-107">Com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e33af-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e33af-108">Em **configuração de controle de admissão de chamada**, certifique-se de **Que Enable Call Admission Control** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="e33af-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="e33af-109">Em **pool de Front-End para executar o controle de admissão de chamadas (CAC)**, selecione o Skype para pool de negócios 2019 de servidor hospedar o CAC e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="e33af-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e33af-110">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="e33af-110">Publish the topology.</span></span>
    

