---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593630"
---
1. Instale o PowerShell versão 7 ou posterior. Para obter orientações passo a passo, consulte [Installing PowerShell on Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Execute o PowerShell no modo de administrador.
1. Instale o módulo do Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Verifique se é a versão 1.6.1 ou posterior.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Instale o Teams do PowerShell de visualização.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Verifique se é pelo menos a versão 4.1.0 e contém os cmdlets do conector Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Instale o módulo do MSAL PowerShell.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. De definir o PowerShell para sair se ocorrer um erro ao executar o script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Habilitar scripts para executar em Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```