---
title: Exibir informações da interface de rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode exibir as informações da interface de rede usando o Windows PowerShell e o cmdlet Get-CsNetworkInterface. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279386"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="7203a-104">Exibir informações da interface de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7203a-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="7203a-105">Você pode exibir as informações da interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="7203a-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="7203a-106">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7203a-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="7203a-107">Para exibir as informações da interface de rede</span><span class="sxs-lookup"><span data-stu-id="7203a-107">To view network interface information</span></span>

  - <span data-ttu-id="7203a-108">Para exibir as informações da interface de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="7203a-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="7203a-109">Esse comando retorna informações semelhantes às seguintes para cada interface de rede:</span><span class="sxs-lookup"><span data-stu-id="7203a-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="7203a-110">Para obter detalhes, consulte [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="7203a-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


