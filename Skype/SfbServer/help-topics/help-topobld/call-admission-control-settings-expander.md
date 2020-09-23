---
title: Expansor de Configurações do Serviço de Controle de Admissão de Chamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218782"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="10213-104">Expansor de Configurações do Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="10213-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="10213-p102">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="10213-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="10213-107">Você também pode usar o painel de controle ou os cmdlets do Shell de gerenciamento para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="10213-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="10213-108">Na seção **Configuração de Controle de Admissão de Chamadas** da caixa de diálogo **Editar Propriedades** de seu site, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="10213-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="10213-109">**Habilitar controle de admissão de chamadas** Selecione essa configuração para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="10213-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="10213-110">Limpe esta configuração para desabilitar CAC para toda sua rede.</span><span class="sxs-lookup"><span data-stu-id="10213-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="10213-111">Para habilitar CAC, você deve ter configurado sua rede para CAC.</span><span class="sxs-lookup"><span data-stu-id="10213-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="10213-112">Para obter detalhes, consulte [Deploy Call Admission Control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="10213-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="10213-113">**Pool de front-ends para executar controle de admissão de chamadas** Se você habilitou o CAC, pode alterar o pool que o executa.</span><span class="sxs-lookup"><span data-stu-id="10213-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="10213-114">Selecione o pool a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="10213-114">Select the pool from the drop-down list.</span></span>
    

