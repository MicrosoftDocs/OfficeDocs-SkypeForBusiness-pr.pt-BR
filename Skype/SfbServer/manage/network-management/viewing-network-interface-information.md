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
description: Você pode exibir informações da interface de rede usando o Windows PowerShell e o Get-CsNetworkInterface cmdlet. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815131"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="15ae0-104">Exibindo informações da interface de rede no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="15ae0-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="15ae0-105">Você pode exibir informações da interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="15ae0-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="15ae0-106">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15ae0-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="15ae0-107">Para exibir informações da interface de rede</span><span class="sxs-lookup"><span data-stu-id="15ae0-107">To view network interface information</span></span>

  - <span data-ttu-id="15ae0-108">Para exibir as informações da interface de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="15ae0-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="15ae0-109">Este comando retorna informações semelhantes às seguintes para cada interface de rede:</span><span class="sxs-lookup"><span data-stu-id="15ae0-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="15ae0-110">Para obter detalhes, [consulte Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="15ae0-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


