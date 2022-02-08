---
title: Exemplo de script do PowerShell - Criar & de mensagens de atribuição
author: serdars
ms.author: serdars
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
ms.openlocfilehash: c6c1faaff2ce252b1363fab149c7d168c5e042e5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390833"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Exemplo de script do PowerShell, criar e atribuir uma política de mensagens

Use este script do PowerShell para criar uma política de mensagens no Microsoft Teams e atribuí-la aos usuários. 

Para obter mais informações sobre como usar esse script do PowerShell, consulte [Início rápido - Teams para Educação](../teams-quick-start-edu.yml).

Este script usa o cmdlet [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) que está no módulo Skype for Business PowerShell Online. Consulte [Teams visão geral do PowerShell](../teams-powershell-overview.md) para saber mais sobre como gerenciar Teams usando o PowerShell.


## <a name="before-you-start"></a>Antes de começar

Baixe e instale o [módulo Skype for Business PowerShell Online](https://www.microsoft.com/download/details.aspx?id=39366) e reinicie o computador, se solicitado.

Para se inclinar mais, consulte [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> Você também pode atribuir uma política de mensagens diretamente aos usuários em escala por meio de uma atribuição de política em lote ou a um grupo de que os usuários são membros. Para obter mais informações, [consulte Atribuir políticas a grandes conjuntos](../batch-group-policy-assignment-edu.md) de usuários em sua escola e [Atribuir políticas aos usuários em Teams](../policy-assignment-overview.md).