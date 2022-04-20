---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976009"
---
1. Instale o PowerShell versão 7 ou posterior. Para obter diretrizes passo a passo, consulte [Instalar o PowerShell no Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Execute o PowerShell no modo de administrador.
1. Instale o módulo microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Verifique se ela é a versão 1.6.1 ou posterior.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Instale o módulo Teams Versão Prévia do PowerShell.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Verifique se ela é pelo menos a versão 4.1.0 e se contém os cmdlets do conector shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Defina o PowerShell para sair se ocorrer um erro ao executar o script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Habilitar scripts a serem executados Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```