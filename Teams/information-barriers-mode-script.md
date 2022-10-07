---
title: Alterar modos de barreiras de informações com um script do PowerShell
description: Use esse script do PowerShell depois de implantar barreiras de informações para atualizar o modo de aberto para implícito para todos os grupos em seu locatário.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047121"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Alterar modos de barreiras de informações com um script do PowerShell

Use esse script do PowerShell para atualizar o modo de IB (barreiras de informações) para todos os grupos conectados ao Teams em seu locatário. Você precisará atualizar o modo para esses grupos depois de implantar barreiras de informações. Os grupos provisionados antes de habilitar o IB recebem o *modo* Abrir. No *modo* Aberto, não há nenhuma política de IB aplicável. Depois de habilitar o IB, *Implícito* se tornará o modo padrão para todos os novos grupos que você criar. No entanto, os grupos existentes ainda mantêm a *configuração do modo* Aberto. Execute esse script para alterar esses grupos existentes para o *modo Implícito* .

Nesse script, você usará o cmdlet [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup), que está no módulo Exchange Online PowerShell para atualizar o modo. Para saber mais sobre como gerenciar o Teams usando o PowerShell, confira [a visão geral do PowerShell do Teams](./teams-powershell-overview.md).

## <a name="sample-script"></a>Script de exemplo

Você precisará usar uma conta corporativa ou de estudante que tenha sido atribuída a função de administrador global para seu locatário executar esse script.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```