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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Exibir informações da interface de rede no Skype for Business Server

Você pode exibir as informações da interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Para exibir as informações da interface de rede

  - Para exibir as informações da interface de rede, digite o seguinte comando no Shell de gerenciamento do Skype for Business Server e pressione ENTER:
    
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


