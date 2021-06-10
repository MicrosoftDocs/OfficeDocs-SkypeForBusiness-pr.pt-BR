---
title: Exemplo de script do PowerShell - Teams de implantação
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script do PowerShell para desinstalar Teams e remover a pasta Teams para usuários.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95b7f12f9d7b531de2c50ba2de197f2f799916a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117289"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="fd68d-103">Exemplo de script do PowerShell - Teams implantação limpa</span><span class="sxs-lookup"><span data-stu-id="fd68d-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="fd68d-104">Use este script para remover Teams.</span><span class="sxs-lookup"><span data-stu-id="fd68d-104">Use this script to remove Teams.</span></span> <span data-ttu-id="fd68d-105">Esse script desinstala Teams e remove a pasta Teams para um usuário.</span><span class="sxs-lookup"><span data-stu-id="fd68d-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="fd68d-106">Execute esse script para cada perfil de usuário no qual Teams foi instalado em um computador.</span><span class="sxs-lookup"><span data-stu-id="fd68d-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="fd68d-107">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="fd68d-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

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

## <a name="related-topics"></a><span data-ttu-id="fd68d-108">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fd68d-108">Related topics</span></span>

- [<span data-ttu-id="fd68d-109">Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fd68d-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="fd68d-110">Implantar Teams com Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="fd68d-110">Deploy Teams with Microsoft 365 Apps</span></span>](/deployoffice/teams-install)