---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812799"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="f9192-103">Redefinir controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="f9192-103">Reset call admission control</span></span>

<span data-ttu-id="f9192-104">Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.</span><span class="sxs-lookup"><span data-stu-id="f9192-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="f9192-105">Para redefinir o CAC</span><span class="sxs-lookup"><span data-stu-id="f9192-105">To reset CAC</span></span>

1. <span data-ttu-id="f9192-106">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f9192-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="f9192-107">Clique com o botão direito do mouse no nó do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f9192-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="f9192-108">Em **configuração de controle de admissão de chamada**, verifique se a opção **habilitar controle de admissão de chamadas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="f9192-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="f9192-109">Em **pool de front-ends para executar o controle de admissão de chamadas (CAC)**, selecione o pool do Skype for Business Server 2019 para hospedar o CAC e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9192-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="f9192-110">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="f9192-110">Publish the topology.</span></span>
    

