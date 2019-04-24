---
title: Exibir informações sobre individuais troncos SIP no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No Skype para Business Server, os vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que não são da mesma gateways e troncos, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214614"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre individuais troncos SIP no Skype para Business Server

No Skype para Business Server, os vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são da mesma e que os administradores devem usar o cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O cmdlet Get-CsTrunk pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.

**Para visualizar as informações de todos os seus troncos SIP**

O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:

`Get-CsTrunk`

**Para visualizar as informações de um tronco SIP específico**

Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Exibindo informações para todos os troncos SIP atribuídos a um Pool**

Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
