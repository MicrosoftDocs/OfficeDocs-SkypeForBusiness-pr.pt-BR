---
title: Exemplo de script do PowerShell – Criar & atribuir política de mensagens
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Use este script do PowerShell para criar uma política de mensagens no Teams e atribuí-la aos usuários em sua organização.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 764de690bbf743991536416c7fed08d0b88e7e97
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825885"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemplo de script do PowerShell, criar e atribuir uma política de mensagens

Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la aos usuários. 

Para obter mais informações sobre como usar esse script do PowerShell, consulte [Início rápido – Teams para Educação](../teams-quick-start-edu.yml).

Esse script usa o cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que está no módulo Skype for Business Online do PowerShell. Confira [a visão geral do PowerShell do Teams](../teams-powershell-overview.md) para saber mais sobre como gerenciar o Teams usando o PowerShell.


## <a name="before-you-start"></a>Antes de começar

Baixe e instale o [módulo Skype for Business Online do PowerShell](https://www.microsoft.com/download/details.aspx?id=54616) e reinicie o computador, se solicitado.

Para se inclinar mais, [consulte Gerenciar Skype for Business Online com Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="sample-script"></a>Script de exemplo

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

> [!NOTE]
> Você também pode atribuir uma política de mensagens diretamente aos usuários em escala por meio de uma atribuição de política de lote ou a um grupo do qual os usuários são membros. Para obter mais informações, [consulte Atribuir políticas a grandes conjuntos de usuários](../batch-group-policy-assignment-edu.md) em sua escola e Atribuir [políticas aos usuários no Teams](../policy-assignment-overview.md).