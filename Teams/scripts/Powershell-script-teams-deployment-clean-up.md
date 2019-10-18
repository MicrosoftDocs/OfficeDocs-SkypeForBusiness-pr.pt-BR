---
title: Exemplo de script do PowerShell - Ajuda na limpeza de implantação do Microsoft Teams
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
audience: admin
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Use este script do PowerShell para limpar o Microsoft Teams nas máquinas de destino ou para usuários específicos.
localization_priority: Normal
ms.openlocfilehash: 6e543e31dd926075d83ad0ccf7187ac602ba8065
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568082"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="c851d-103">Exemplo de script do PowerShell - Limpeza de implantação do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c851d-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="c851d-104">Esse script do PowerShell pode ser aproveitado para a limpeza do Microsoft Teams de máquinas ou usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="c851d-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="c851d-105">Ele deve ser executado para todos os usuários em uma máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="c851d-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="c851d-106">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="c851d-106">Sample script</span></span>

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
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


