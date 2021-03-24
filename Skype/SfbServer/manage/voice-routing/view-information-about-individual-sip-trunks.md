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
description: No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são um e o mesmo, e os administradores devem usar o cmdlet Get-CsTrunk para exibir informações sobre um tronco SIP individual.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102997"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre troncos SIP individuais no Skype for Business Server

No Skype for Business Server, vários troncos podem ser atribuídos a um único gateway PSTN; isso significa que gateways e troncos não são um e os mesmos, e que os administradores devem usar o cmdlet [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O Get-CsTrunk cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.

**Para exibir informações de todos os troncos SIP**

O comando a seguir retorna informações sobre todos os troncos SIP em uso em sua organização:

`Get-CsTrunk`

**Para exibir informações de um tronco SIP específico**

Este comando retorna informações apenas para o tronco SIP com Identity PstnGateway:192.168.0.240:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Exibindo informações de todos os troncos SIP atribuídos a um pool**

Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`