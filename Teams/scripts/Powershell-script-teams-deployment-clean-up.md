---
title: Amostra de Script do PowerShell - contribuem para implantação de equipes da Microsoft que elimine
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Use esse script do PowerShell para limpar o Teams da Microsoft em máquinas direcionadas ou usuários específicos.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9b95ca42e1f110b72d092ada65b2d672627fac4f
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887278"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="f0e93-103">Exemplo de Script do PowerShell - implantação do Microsoft Teams limpar</span><span class="sxs-lookup"><span data-stu-id="f0e93-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="f0e93-104">Esse script do PowerShell pode ser utilizado para a limpeza do Microsoft Teams de máquinas de destino ou usuários.</span><span class="sxs-lookup"><span data-stu-id="f0e93-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="f0e93-105">Ele deve ser executado para cada usuário em uma máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="f0e93-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="f0e93-106">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="f0e93-106">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}

````


