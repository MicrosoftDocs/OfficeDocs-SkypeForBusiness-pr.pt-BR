---
title: Redefinir o controle de admissão de chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se um pool de Front End herdado estiver hospedando o cac (controle de admissão de chamadas), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de remover o pool de Front-End herdado.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753293"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="da13c-103">Redefinir o controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="da13c-103">Reset call admission control</span></span>

<span data-ttu-id="da13c-104">Se um pool de Front End herdado estiver hospedando o cac (controle de admissão de chamadas), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de remover o pool de Front-End herdado.</span><span class="sxs-lookup"><span data-stu-id="da13c-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="da13c-105">Para redefinir o CAC</span><span class="sxs-lookup"><span data-stu-id="da13c-105">To reset CAC</span></span>

1. <span data-ttu-id="da13c-106">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="da13c-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="da13c-107">Clique com o botão direito no nó do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="da13c-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="da13c-108">Em **Configuração de Controle de Admissão de Chamadas**, certifique-se de que a opção **Habilitar controle de admissão de chamadas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="da13c-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="da13c-109">Em **Pool de Front-End** para executar o CAC (controle de admissão de chamadas), selecione o pool do Skype for Business Server 2019 que hospedará o CAC e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="da13c-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="da13c-110">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="da13c-110">Publish the topology.</span></span>
    

