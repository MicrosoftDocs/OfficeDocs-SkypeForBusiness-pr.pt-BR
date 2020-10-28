---
title: Exemplo de script do PowerShell – limpeza de implantação de equipes
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Use este script do PowerShell para desinstalar o Microsoft Teams e remover a pasta Teams para usuários.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7245e3cfee88beb51389f20bc99bbcc312f55b0
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778904"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="a3a7a-103">Exemplo de script do PowerShell – limpeza de implantação de equipes</span><span class="sxs-lookup"><span data-stu-id="a3a7a-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="a3a7a-104">Use esse script para remover o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-104">Use this script to remove Teams.</span></span> <span data-ttu-id="a3a7a-105">Esse script desinstala o Teams e remove a pasta Teams para um usuário.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="a3a7a-106">Execute este script para cada perfil de usuário em que as equipes foram instaladas em um computador.</span><span class="sxs-lookup"><span data-stu-id="a3a7a-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="a3a7a-107">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="a3a7a-107">Sample script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="a3a7a-108">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a3a7a-108">Related topics</span></span>

- [<span data-ttu-id="a3a7a-109">Instalar o Microsoft Teams usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a3a7a-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="a3a7a-110">Implantar equipes com os aplicativos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3a7a-110">Deploy Teams with Microsoft 365 Apps</span></span>](https://docs.microsoft.com/deployoffice/teams-install)
