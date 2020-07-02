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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944076"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar o Microsoft Teams PowerShell

Este artigo explica como instalar o módulo do Microsoft Teams PowerShell usando o [PowerShellGet](/powershell/scripting/gallery/installing-psget). Estas instruções funcionam nas plataformas [do Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e Windows.

## <a name="requirements"></a>Requisitos

O Teams PowerShell funciona com o PowerShell 6.2.4 e posterior em todas as plataformas. Também é compatível com o PowerShell 5,1 no Windows. Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para o seu sistema operacional. O Teams PowerShell não tem requisitos adicionais quando executados no PowerShell 6.2.4 e posteriores.

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

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda `Yes` ou `Yes to All` para continuar com a instalação.


## <a name="install-teams-powershell-public-preview"></a>Instale a visualização pública do teams PowerShell

> [!NOTE]
> Se você estiver usando a versão de visualização pública do teams PowerShell, recomendamos que primeiro desinstale o Skype for Business online Connector.

Instalar o módulo de visualização pública do teams para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux.

Se você estiver usando o PowerShell 5,1, será necessário atualizar o módulo **PowerShellGet** antecipadamente. Após atualizar o **PowerShellGet**, feche e reabra uma sessão do PowerShell com privilégios para garantir que o **PowerShellGet** mais recente seja carregado.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar a visualização pública do teams PowerShell, execute o comando do PowerShell abaixo.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>Instalar o conector do Skype for Business Online

> [!WARNING]
> O conector Skype for Business online atualmente faz parte da visualização pública do teams PowerShell. Depois de lançarmos esse recurso no lançamento de GA do teams PowerShell, o conector do Skype for Business online não estará mais disponível.

Baixe e instale o [módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366)e execute o seguinte no PowerShell.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Entrar

Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.

> [!NOTE]
> Se você estiver usando a versão mais recente do [PowerShell Public Preview do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), não será necessário instalar o conector do Skype for Business online.

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
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
