---
title: Exibindo informações da interface de rede
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você pode exibir informações da interface de rede usando Windows PowerShell e o cmdlet Get-CsNetworkInterface de rede. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.
ms.openlocfilehash: 6414dc6e032ccd01d66af666d2c3edc2d1e021c7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742097"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>Exibindo informações da interface de rede em Skype for Business Server

Você pode exibir informações da interface de rede usando Windows PowerShell e o cmdlet **Get-CsNetworkInterface.** Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.

## <a name="to-view-network-interface-information"></a>Para exibir informações da interface de rede

Para exibir informações da interface de rede, digite o seguinte comando no Shell de Gerenciamento Skype for Business Server e pressione ENTER:
    
`Get-CsNetworkInterface`

Este comando retorna informações semelhantes às seguintes para cada interface de rede:

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

Para obter detalhes, [consulte Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface).
