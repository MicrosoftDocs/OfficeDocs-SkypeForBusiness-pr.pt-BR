---
title: Exibindo informações da interface de rede
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode exibir informações da interface de rede usando Windows PowerShell e o cmdlet Get-CsNetworkInterface de rede. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.
ms.openlocfilehash: 0e72b2550413004038b110292b693dda25affaf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122415"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="e132a-104">Exibindo informações da interface de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e132a-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="e132a-105">Você pode exibir informações da interface de rede usando Windows PowerShell e o cmdlet **Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="e132a-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="e132a-106">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e132a-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="e132a-107">Para exibir informações da interface de rede</span><span class="sxs-lookup"><span data-stu-id="e132a-107">To view network interface information</span></span>

  - <span data-ttu-id="e132a-108">Para exibir informações da interface de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e132a-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="e132a-109">Este comando retorna informações semelhantes às seguintes para cada interface de rede:</span><span class="sxs-lookup"><span data-stu-id="e132a-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="e132a-110">Para obter detalhes, [consulte Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="e132a-110">For details, see [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).</span></span>