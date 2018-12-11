---
title: Visualizando informações de interface de rede
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode visualizar informações de interface de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkInterface. Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell.
ms.openlocfilehash: b3f1217c53176ae2a67ba81893864e1fb3a4e384
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222762"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="5f5a7-104">Exibindo informações de interface de rede no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5f5a7-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="5f5a7-105">Você pode visualizar informações de interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="5f5a7-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="5f5a7-106">Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f5a7-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="5f5a7-107">Para exibir informações de interface de rede</span><span class="sxs-lookup"><span data-stu-id="5f5a7-107">To view network interface information</span></span>

  - <span data-ttu-id="5f5a7-108">Para exibir informações de interface de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="5f5a7-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="5f5a7-109">Esse comando retorna informações semelhantes às seguintes para cada interface de rede:</span><span class="sxs-lookup"><span data-stu-id="5f5a7-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="5f5a7-110">Para obter detalhes, consulte [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="5f5a7-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


