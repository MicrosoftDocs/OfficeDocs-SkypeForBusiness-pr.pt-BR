---
title: Exemplo de script do PowerShell - Teams de implantação
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script do PowerShell para desinstalar Teams e remover a pasta Teams para usuários.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4853cf99bc6d600f8673df065c3dee3e0068207b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767149"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Exemplo de script do PowerShell - Teams implantação limpa

Use este script para remover Teams. Esse script desinstala Teams e remove a pasta Teams para um usuário. Execute esse script para cada perfil de usuário no qual Teams foi instalado em um computador.


## <a name="sample-script"></a>Script de exemplo

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Implantar Teams com Microsoft 365 Apps](/deployoffice/teams-install)
