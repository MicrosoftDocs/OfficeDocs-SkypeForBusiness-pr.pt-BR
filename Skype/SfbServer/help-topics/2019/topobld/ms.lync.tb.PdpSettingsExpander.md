---
title: Expansor de Configurações do Serviço de Controle de Admissão de Chamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.
ms.openlocfilehash: 62d77de88a6bf0f0195e1c54eef4e5cac6d2a409
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701766"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="f93fb-104">Expansor de Configurações do Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f93fb-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="f93fb-p102">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="f93fb-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f93fb-107">Você também pode usar o painel de controle ou cmdlets de shell de gerenciamento para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="f93fb-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="f93fb-108">Na seção **Configuração de Controle de Admissão de Chamadas** da caixa de diálogo **Editar Propriedades** de seu site, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f93fb-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="f93fb-109">**Habilitar controle de admissão de chamadas** Selecione esta configuração para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="f93fb-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="f93fb-110">Desmarque essa configuração para desabilitar o CAC para toda sua rede.</span><span class="sxs-lookup"><span data-stu-id="f93fb-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="f93fb-111">Para habilitar o CAC, você deve ter configurado sua rede para CAC.</span><span class="sxs-lookup"><span data-stu-id="f93fb-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="f93fb-112">Para obter detalhes, consulte [implantar controle de admissão de chamadas no Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f93fb-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="f93fb-113">**Pool de front-end para executar o controle de admissão de chamadas** Se você ativou o CAC, poderá alterar o pool que o executa.</span><span class="sxs-lookup"><span data-stu-id="f93fb-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="f93fb-114">Selecione o pool na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f93fb-114">Select the pool from the drop-down list.</span></span>
    

