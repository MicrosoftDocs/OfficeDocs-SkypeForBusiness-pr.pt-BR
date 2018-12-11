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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Exibindo informações de interface de rede no Skype para Business Server

Você pode visualizar informações de interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Para exibir informações de interface de rede

  - Para exibir informações de interface de rede, digite o seguinte comando no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:
    
        Get-CsNetworkInterface
    
    Esse comando retorna informações semelhantes às seguintes para cada interface de rede:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Para obter detalhes, consulte [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


