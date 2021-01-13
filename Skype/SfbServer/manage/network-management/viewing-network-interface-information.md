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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Exibindo informações da interface de rede no Skype for Business Server

Você pode exibir informações da interface de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkInterface.** Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. 

## <a name="to-view-network-interface-information"></a>Para exibir informações da interface de rede

  - Para exibir as informações da interface de rede, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:
    
        Get-CsNetworkInterface
    
    Este comando retorna informações semelhantes às seguintes para cada interface de rede:
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    Para obter detalhes, [consulte Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).


