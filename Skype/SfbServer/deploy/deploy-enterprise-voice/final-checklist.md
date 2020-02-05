---
title: Lista de verificação final da implantação do controle de admissão de chamadas do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767224"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="fa563-103">Implantação de controle de admissão de chamadas: lista de verificação final do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fa563-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="fa563-104">Lista de verificação final para implantar o controle de admissão de chamadas (CAC) no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fa563-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="fa563-105">Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do serviço de Controle de Admissão de Chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="fa563-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="fa563-106">Se um ou mais servidores Edge estiverem implantados, cada endereço IP de interface externa precisará ser adicionado à lista de sub-rede nas configurações de configuração de rede, com uma máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="fa563-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="fa563-107">Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.</span><span class="sxs-lookup"><span data-stu-id="fa563-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fa563-108">Os servidores de borda não precisam implementar o CAC.</span><span class="sxs-lookup"><span data-stu-id="fa563-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="fa563-109">Verifique se o CAC está habilitado, conforme especificado em [habilitar controle de admissão de chamadas no Skype for Business Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="fa563-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="fa563-110">Certifique-se de que o CAC está habilitado em todos os sites centrais.</span><span class="sxs-lookup"><span data-stu-id="fa563-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="fa563-111">Isso pode ser feito por meio do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="fa563-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="fa563-112">Se um aviso for gerado durante a publicação, *não* o ignore.</span><span class="sxs-lookup"><span data-stu-id="fa563-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="fa563-113">Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="fa563-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="fa563-114">Também é essencial que cada sub-rede seja associada a um site de rede, conforme explicado em [implantar regiões de rede, sites e sub-redes no Skype for Business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="fa563-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="fa563-115">Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="fa563-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

