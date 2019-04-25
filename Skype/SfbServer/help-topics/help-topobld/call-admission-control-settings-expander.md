---
title: Expansor de Configurações do Serviço de Controle de Admissão de Chamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.
ms.openlocfilehash: 7152596fa8db00ed4bbc31d196c96da8ab7d3942
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226904"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="2b632-104">Expansor de Configurações do Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="2b632-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="2b632-p102">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="2b632-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2b632-107">Você também pode usar o painel de controle ou cmdlets de shell de gerenciamento para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="2b632-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="2b632-108">Na seção **Configuração de Controle de Admissão de Chamadas** da caixa de diálogo **Editar Propriedades** de seu site, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2b632-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="2b632-109">**Habilitar o controle de admissão de chamada** Selecione esta configuração para habilitar CAC.</span><span class="sxs-lookup"><span data-stu-id="2b632-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="2b632-110">Desmarque essa configuração para desabilitar o CAC para toda sua rede.</span><span class="sxs-lookup"><span data-stu-id="2b632-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="2b632-111">Para habilitar o CAC, você deve ter configurado sua rede para CAC.</span><span class="sxs-lookup"><span data-stu-id="2b632-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="2b632-112">Para obter detalhes, consulte [Deploy no Skype para Business Server 2015 o controle de admissão de chamada](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2b632-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="2b632-113">**Pool de Front-End para executar o controle de admissão de chamada** Se você habilitou o CAC, você pode alterar o pool que executa a ele.</span><span class="sxs-lookup"><span data-stu-id="2b632-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="2b632-114">Selecione o pool na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="2b632-114">Select the pool from the drop-down list.</span></span>
    

