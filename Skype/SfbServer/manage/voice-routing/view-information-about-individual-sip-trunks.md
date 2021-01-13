---
title: Exibir informações sobre troncos SIP individuais no Skype for Business Server
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
description: No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são os mesmos, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826171"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre troncos SIP individuais no Skype for Business Server

No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são iguais e devem usar o cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O Get-CsTrunk cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.

**Para exibir informações de todos os troncos SIP**

O comando a seguir retorna informações sobre todos os troncos SIP em uso na organização:

`Get-CsTrunk`

**Para exibir informações de um tronco SIP específico**

Este comando retorna informações apenas para o tronco SIP com a Identidade PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Exibindo informações de todos os troncos SIP atribuídos a um pool**

Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
