---
title: Exemplo de script do PowerShell - Criar uma equipe englobando toda a empresa no Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: Use este script do PowerShell para criar uma equipe pública englobando toda a empresa no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 6c4c1acf659e391320f1fa713be0e8d6c9e09853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884092"
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>Exemplo de script do PowerShell - Criar uma equipe englobando toda a empresa no Microsoft Teams
-------------------------------------------------------------------------

Este script do PowerShell cria uma equipe pública englobando toda a empresa no Microsoft Teams. O script usa o módulo do MicrosoftTeams do PowerShell (atualmente na fase beta) para criar uma equipe pública englobando toda a empresa. Ele também usa o módulo do AzureAD do PowerShell para buscar a lista de usuários em seu locatário. 

Para obter instruções completas de uso desse script do PowerShell, confira nosso tutorial, [Criar uma equipe englobando toda a empresa no Microsoft Teams usando o PowerShell](../Company-wide-team-creation-powershell.yml).

Se você é novato no PowerShell e precisa de ajuda para começar, consulte [Visão geral do Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Script de exemplo

> [!TIP]
> Um arquivo de script do PowerShell é um arquivo de texto com a extensão .PS1. Para usar esse script, clique em **Copiar** e cole o código em um arquivo de texto. Salve-o com o nome de arquivo CreateCompanyWideTeam.ps1e você terá um script do PowerShell.

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>Explicação do script


Para obter instruções completas de uso desse script do PowerShell, confira nosso tutorial, [Criar uma equipe englobando toda a empresa no Microsoft Teams usando o PowerShell](../Company-wide-team-creation-powershell.yml)

Há cinco seções para esse script (listadas na ordem de cima para baixo):
1. **Documentação e definições de variáveis**
2. **Função Create-Team**: se necessário, cria uma equipe. Se você não especificar GroupID, essa seção criará a equipe com TeamName e TeamDescription especificados.
3. **Função Add-Channels**: se você especificou canais, a descrição do canal é solicitada aqui. Em seguida, o canal é criado. 
4. **Função Add-Members**: faz todo o gerenciamento de membros. Essa seção se conecta ao AzureAD, busca um conjunto de usuários e os adiciona à equipe, caso você não forneça uma lista de membros. Ela trata da lógica de adição de proprietários e membros, e não de adição de membros que já pertencem à equipe. 
5. **Programa principal**: essa é a ordem na qual as funções são executadas. 


