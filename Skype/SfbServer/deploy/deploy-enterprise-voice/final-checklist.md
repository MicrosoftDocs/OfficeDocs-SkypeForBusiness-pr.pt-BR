---
title: Processo final de implantação de controle de admissão de chamada para Skype para Business Server 2015
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 9971d59f0b9c3c2c1f9bfd5e8176122715b19d20
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="ea681-103">Lista de verificação final da implantação do serviço de controle de admissão de chamadas do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea681-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ea681-104">Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ea681-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ea681-105">Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do serviço de Controle de Admissão de Chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="ea681-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="ea681-106">Se um ou mais servidores de borda estiverem implantados, cada endereço IP de interface externa deve ser adicionado à lista de sub-rede nas definições de configuração de rede, com uma máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="ea681-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="ea681-107">Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.</span><span class="sxs-lookup"><span data-stu-id="ea681-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea681-108">Servidores de borda não são necessárias para implementar o CAC.</span><span class="sxs-lookup"><span data-stu-id="ea681-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="ea681-109">Certifique-se de que CAC está habilitado, como especificado em [Habilitar o controle de admissão de chamada no Skype para Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="ea681-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="ea681-110">Certifique-se de que o CAC está habilitado em todos os sites centrais.</span><span class="sxs-lookup"><span data-stu-id="ea681-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="ea681-111">Isso pode ser feito por meio do construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="ea681-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="ea681-112">Se um aviso será gerado quando você publica, *não* ignorá-la.</span><span class="sxs-lookup"><span data-stu-id="ea681-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="ea681-113">Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="ea681-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="ea681-114">Também é essencial que todas as sub-redes ser associadas a um site de rede, conforme explicado em [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="ea681-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="ea681-115">Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="ea681-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

