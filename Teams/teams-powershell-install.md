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
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814460"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar o Microsoft Teams PowerShell

Este artigo explica como instalar o módulo do Microsoft Teams PowerShell usando o [PowerShellGet](/powershell/scripting/gallery/installing-psget). Estas instruções funcionam nas plataformas [do Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e Windows.

## <a name="requirements"></a>Requisitos

O Teams PowerShell requer o PowerShell 5,1 ou superior em todas as plataformas. Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para o seu sistema operacional.

> [!WARNING]
> Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell. Para obter a melhor experiência, recomendamos que você use o PowerShell 5,1.

## <a name="install-the-teams-powershell-module"></a>Instalar o módulo do teams PowerShell

> [!NOTE]
> Para obter a melhor experiência, use módulos de disponibilidade geral (GA) ou Public Preview, não ambos. Eles não têm a intenção de trabalhar juntos.


Use os cmdlets **PowerShellGet** para instalar o módulo do PowerShell do teams. A instalação do módulo para todos os usuários em um sistema exige privilégios elevados. Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux:

```powershell
Install-Module MicrosoftTeams
```

Por padrão, a galeria do PowerShell (PSGallery) não está configurada como um repositório confiável para o **PowerShellGet**. Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sim** ou **Sim para tudo** para continuar com a instalação.


## <a name="install-teams-powershell-public-preview"></a>Instale a visualização pública do teams PowerShell

> [!NOTE]
> Se você estiver usando a versão de visualização pública do teams PowerShell, recomendamos que primeiro desinstale o Skype for Business online Connector.

Instalar o módulo de visualização pública do teams para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux.

Se você estiver usando o PowerShell 5,1, será necessário atualizar o módulo **PowerShellGet** antecipadamente. Após atualizar o **PowerShellGet**, feche e reabra uma sessão do PowerShell com privilégios para garantir que o **PowerShellGet** mais recente seja carregado.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar a visualização pública do teams PowerShell, execute o comando do PowerShell abaixo.

> [!NOTE]
> Você pode encontrar a versão de visualização mais recente na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou no PowerShell executando "Find-Module MicrosoftTeams-AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar o conector do Skype for Business Online

> [!NOTE]
>
> O conector do Skype for Business online atualmente faz parte do módulo do PowerShell mais recente do teams.
> Se você estiver usando a [versão pública do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector do Skype for Business online.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Entrar

Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.

> [!NOTE]
> Se você estiver usando a versão mais recente do [PowerShell Public Preview do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), não será necessário instalar o conector do Skype for Business online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Atualizar o PowerShell do teams

Para atualizar o PowerShell do Teams, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se o Microsoft Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará. Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.


## <a name="uninstall-teams-powershell"></a>Desinstalar o PowerShell do Microsoft Teams



Para desinstalar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Se o Microsoft Teams PowerShell já tiver sido importado para a sua sessão do PowerShell, a desinstalação do módulo irá falhar. Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.

## <a name="next-steps"></a>Próximos passos

Agora você está pronto para gerenciar o Microsoft Teams usando o PowerShell do teams. Consulte [gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md) para começar.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md)

[Notas de versão do teams PowerShell](teams-powershell-release-notes.md)

[Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
