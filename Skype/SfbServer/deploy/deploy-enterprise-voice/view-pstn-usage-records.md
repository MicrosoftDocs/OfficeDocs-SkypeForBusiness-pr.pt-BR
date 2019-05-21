---
title: Exibir registros de uso de PSTN no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Resumo: saiba como exibir registros de uso de PSTN usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300920"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="4b3e3-103">Exibir registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4b3e3-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="4b3e3-104">**Resumo:** Saiba como exibir registros de uso de PSTN usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="4b3e3-p101">Um registro de uso de Rede Telefônica Pública Comutada (PSTN) especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4b3e3-107">Para exibir um registro de uso PSTN usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b3e3-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4b3e3-108">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="4b3e3-109">Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Uso do PSTN**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="4b3e3-110">Na página **Uso do PSTN**, destaque o registro de uso PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b3e3-111">Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.</span><span class="sxs-lookup"><span data-stu-id="4b3e3-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="4b3e3-112">Para exibir informações de uso de PSTN usando cmdlets do Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b3e3-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="4b3e3-113">Para ver informações sobre todos os usos de PSTN, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4b3e3-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="4b3e3-114">Este comando retorna informações semelhantes para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4b3e3-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="4b3e3-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="4b3e3-115">See also</span></span>

[<span data-ttu-id="4b3e3-116">Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4b3e3-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

