---
title: Exibir registros de uso de PSTN no Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: Saiba como exibir registros de uso PSTN usando-se o Skype para painel de controle do Business Server ou o Skype para Business Server Management Shell.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a><span data-ttu-id="71117-103">Exibir registros de uso de PSTN no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="71117-103">View PSTN usage records in Skype for Business 2015</span></span>
 
<span data-ttu-id="71117-104">**Resumo:** Saiba como exibir registros de uso do PSTN, usando o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="71117-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="71117-105">Um registro de uso de Rede Telefônica Pública Comutada (PSTN) especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização.</span><span class="sxs-lookup"><span data-stu-id="71117-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="71117-106">Para obter detalhes, consulte [Os registros de uso do PSTN](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="71117-106">For details, see [PSTN Usage Records](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="71117-107">Para exibir um registro de uso PSTN usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="71117-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="71117-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="71117-108">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="71117-109">Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Uso do PSTN**.</span><span class="sxs-lookup"><span data-stu-id="71117-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>
    
3. <span data-ttu-id="71117-110">Na página **Uso do PSTN**, destaque o registro de uso PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="71117-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="71117-111">Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.</span><span class="sxs-lookup"><span data-stu-id="71117-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span> 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="71117-112">Para exibir informações de uso do PSTN, usando Skype para cmdlets do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="71117-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="71117-113">Para exibir informações sobre todos os usos de PSTN, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="71117-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="71117-114">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71117-114">This command returns information similar to the following:</span></span>
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a><span data-ttu-id="71117-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="71117-115">See also</span></span>

#### 

[<span data-ttu-id="71117-116">Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="71117-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

