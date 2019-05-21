---
title: Redefinir controle de admissão de chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307095"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="0e9ee-103">Redefinir controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="0e9ee-103">Reset call admission control</span></span>

<span data-ttu-id="0e9ee-104">Se um pool de front-end herdado estiver hospedando o controle de admissão de chamadas (CAC), você deverá mover a hospedagem do CAC para um pool do Skype for Business Server 2019 antes de poder remover o pool de front-end herdado.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="0e9ee-105">Para redefinir o CAC</span><span class="sxs-lookup"><span data-stu-id="0e9ee-105">To reset CAC</span></span>

1. <span data-ttu-id="0e9ee-106">Abrir o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0e9ee-107">Clique com o botão direito do mouse no nó do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0e9ee-108">Em **configuração de controle de admissão de chamada**, verifique se a opção **habilitar controle de admissão de chamadas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="0e9ee-109">Em **pool de front-ends para executar o controle de admissão de chamadas (CAC)**, selecione o pool do Skype for Business Server 2019 para hospedar o CAC e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="0e9ee-110">Publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="0e9ee-110">Publish the topology.</span></span>
    

