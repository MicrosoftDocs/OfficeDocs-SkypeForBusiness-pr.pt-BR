---
title: Skype for Business Server - Exibir informações sobre troncos SIP individuais
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
description: No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN. Gateways e troncos não são um e os mesmos, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: f78aad8aa55202cdd59107be8f5e66dc2f83e1d336dc2f66c4982b7f534c88cc
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848386"
---
# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>Skype for Business Server - Exibir informações sobre troncos SIP individuais

No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; isso significa que gateways e troncos não são um e os mesmos, e que os administradores devem usar o cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O Get-CsTrunk cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell.

**Para exibir informações de todos os troncos SIP**

O comando a seguir retorna informações sobre todos os troncos SIP em uso em sua organização:

`Get-CsTrunk`

**Para exibir informações de um tronco SIP específico**

Este comando retorna informações apenas para o tronco SIP com Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Exibindo informações de todos os troncos SIP atribuídos a um pool**

Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
