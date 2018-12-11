---
title: Exibir informações sobre individuais troncos SIP no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No Skype para Business Server, os vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que não são da mesma gateways e troncos, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: c8463fb23ea09167d760a1b9068235da871792c2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222790"
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