---
title: Instalar Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a usar os controles do PowerShell para gerenciar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039969"
---
# <a name="install-microsoft-teams-powershell-module"></a>Instalar Microsoft Teams Módulo do PowerShell

Este artigo explica como instalar o módulo Microsoft Teams PowerShell usando a Galeria do PowerShell. O Microsoft Teams do PowerShell é suportado em todas as Windows plataformas. Não há suporte para Mac e Linux.

## <a name="requirements"></a>Requisitos

Microsoft Teams módulo do PowerShell exige o PowerShell 5.1 ou superior em todas as plataformas. Instale  [a versão mais recente do PowerShellavailable](/powershell/scripting/install/installing-powershell)  para seu sistema operacional. 

Para verificar sua versão do PowerShell, execute o seguinte comando de dentro de uma sessão do PowerShell: 

```powershell
$PSVersionTable.PSVersion 
```
Recomendamos que você use o cmdlet Install-Module para instalar o módulo Microsoft Teams PowerShell. 
 
Se a Galeria do PowerShell (PSGallery) não estiver configurada como um repositório confiável para **o PowerShellGet**, na primeira vez que você usar o PSGallery, você verá a seguinte mensagem:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sim** ou **Sim a Todos** para continuar com a instalação.

## <a name="installing-using-the-powershellgallery"></a>Instalar usando o PowerShellGallery

Microsoft Teams módulo do PowerShell atualmente tem suporte para uso com o PowerShell 5.1 no Windows. Siga estas etapas para instalar o módulo: 

- Atualize para [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Se você estiver no Windows 10 versão 1607 ou superior, já tem o PowerShell 5.1 instalado. 
- Instale [.NET Framework 4.7.2](/dotnet/framework/install) ou posterior. 
- Execute o seguinte comando para instalar o PowerShellGet mais recente:
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Instale o Teams PowerShell.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Instalação offline 

Em alguns ambientes, não é possível se conectar à Galeria do PowerShell. Nessas situações, siga estas etapas [de instalação manuais](https://aka.ms/psgallery-manualdownload).  

## <a name="sign-in"></a>Entrar

Para começar a trabalhar com Microsoft Teams módulo do PowerShell, entre com suas credenciais do Azure.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Atualizar Teams Módulo do PowerShell

Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo. Por exemplo, se você usou o Install-Module originalmente, deve usar [o Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará. Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.


## <a name="uninstall-teams-powershell"></a>Desinstalar Teams PowerShell

Para desinstalar Microsoft Teams PowerShell, abra um novo prompt de comando do PowerShell e execute o seguinte: 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>Próximos passos 

Agora você está pronto para gerenciar o Microsoft Teams usando Microsoft Teams PowerShell. Consulte [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started. 

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciando Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Teams notas de versão do PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams de cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)
