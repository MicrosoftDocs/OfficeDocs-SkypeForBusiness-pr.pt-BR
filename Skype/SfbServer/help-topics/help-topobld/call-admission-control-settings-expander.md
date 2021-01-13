---
title: Expansor de Configurações do Serviço de Controle de Admissão de Chamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833111"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="8243e-104">Expansor de Configurações do Serviço de Controle de Admissão de Chamadas</span><span class="sxs-lookup"><span data-stu-id="8243e-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="8243e-p102">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível. Após configurar a rede para o CAC, habilite-o para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="8243e-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8243e-107">Você também pode usar o painel de controle ou os cmdlets do shell de gerenciamento para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="8243e-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="8243e-108">Na seção **Configuração de Controle de Admissão de Chamadas** da caixa de diálogo **Editar Propriedades** de seu site, você pode alterar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8243e-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="8243e-109">**Habilitar o Controle de Admissão de Chamada** Selecione essa configuração para habilitar o CAC.</span><span class="sxs-lookup"><span data-stu-id="8243e-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="8243e-110">Limpe esta configuração para desabilitar CAC para toda sua rede.</span><span class="sxs-lookup"><span data-stu-id="8243e-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="8243e-111">Para habilitar CAC, você deve ter configurado sua rede para CAC.</span><span class="sxs-lookup"><span data-stu-id="8243e-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="8243e-112">Para obter detalhes, [consulte Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="8243e-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="8243e-113">**Pool de front-end para executar o Controle de Admissão de Chamada** Se você habilitar o CAC, poderá alterar o pool que o executa.</span><span class="sxs-lookup"><span data-stu-id="8243e-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="8243e-114">Selecione o pool a partir da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8243e-114">Select the pool from the drop-down list.</span></span>
    

