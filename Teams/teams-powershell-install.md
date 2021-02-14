---
title: Instalar o Microsoft Teams PowerShell
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
description: Saiba como usar os controles do PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662016"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar o Microsoft Teams PowerShell

Este artigo explica como instalar o módulo do PowerShell do Microsoft Teams usando [o PowerShellGet.](/powershell/scripting/gallery/installing-psget) Estas instruções funcionam nas plataformas [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows.

## <a name="requirements"></a>Requisitos

O PowerShell do Teams requer o PowerShell 5.1 ou superior em todas as plataformas. Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para seu sistema operacional.

> [!WARNING]
> Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell. Para ter a melhor experiência, recomendamos que você use o PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Instalar o módulo do PowerShell do Teams

> [!NOTE]
> Para ter a melhor experiência, use os módulos Disponibilidade Geral (GA) ou Visualização Pública, não ambos. Eles não devem trabalhar juntos.


Use os cmdlets do **PowerShellGet** para instalar o módulo do Teams PowerShell. Instalar o módulo para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o comando no `sudo` macOS ou Linux:

```powershell
Install-Module MicrosoftTeams
```

Por padrão, a Galeria do PowerShell (PSGallery) não está configurada como um repositório confiável para **o PowerShellGet.** Na primeira vez que usar a PSGallery, você verá a seguinte mensagem:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sim** ou **Sim a Todos** para continuar com a instalação.


## <a name="install-teams-powershell-public-preview"></a>Instalar a visualização pública do Teams PowerShell

> [!NOTE]
> Se você estiver usando a versão Visualização Pública do Teams PowerShell, é recomendável primeiro desinstalar o Skype for Business Online Connector.

Instalar o módulo de visualização pública do PowerShell do Teams para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o comando no `sudo` macOS ou No Linux.

Se você estiver usando o PowerShell 5.1, deverá atualizar o módulo **PowerShellGet** antecipadamente. Depois de atualizar **o PowerShellGet,** feche e reabra uma sessão elevada do PowerShell para garantir que o **PowerShellGet** mais recente seja carregado.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar a visualização pública do Teams PowerShell, execute o comando do PowerShell abaixo.

> [!NOTE]
> Você pode encontrar a versão de visualização mais recente na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou no PowerShell executando "MicrosoftTeams do Módulo De Pesquisa -AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar o Conector do Skype for Business Online

> [!NOTE]
>
> No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.
> Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Entrar

Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.

> [!NOTE]
> Se você estiver usando a versão prévia pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Atualizar o PowerShell do Teams

Para atualizar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se o PowerShell do Teams já tiver sido importado para a sessão do PowerShell, a atualização do módulo falhará. Feche o PowerShell e rea abra uma nova sessão elevada do PowerShell.


## <a name="uninstall-teams-powershell"></a>Desinstalar o Teams PowerShell



Para desinstalar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Se o PowerShell do Teams já tiver sido importado para a sessão do PowerShell, a desinstalação do módulo falhará. Feche o PowerShell e rea abra uma nova sessão elevada do PowerShell.

## <a name="next-steps"></a>Próximas Etapas

Agora você está pronto para gerenciar o Teams usando o Teams PowerShell. Consulte [Gerenciar Equipes com o Teams PowerShell](teams-powershell-managing-teams.md) para começar.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciando equipes com o Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
