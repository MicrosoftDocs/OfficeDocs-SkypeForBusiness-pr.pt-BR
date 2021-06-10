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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768331"
---
# <a name="install-microsoft-teams-powershell"></a>Instalar Microsoft Teams PowerShell

Este artigo explica como instalar o módulo Microsoft Teams PowerShell usando [o PowerShellGet](/powershell/scripting/gallery/installing-psget). Essas instruções funcionam no [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows plataformas.

## <a name="requirements"></a>Requisitos

Teams O PowerShell exige o PowerShell 5.1 ou superior em todas as plataformas. Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para seu sistema operacional.

> [!NOTE]
> Para a melhor experiência, recomendamos que você use o PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Instalar o módulo Teams PowerShell

> [!NOTE]
> Para a melhor experiência, use os módulos Disponibilidade Geral (GA) ou Visualização Pública - não ambos. Eles não se destinam a trabalhar juntos.


Use os cmdlets **PowerShellGet** para instalar o módulo Teams PowerShell. Instalar o módulo para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como** administrador Windows ou use o comando `sudo` em macOS ou Linux:

```powershell
Install-Module MicrosoftTeams
```

Por padrão, a Galeria do PowerShell (PSGallery) não é configurada como um repositório confiável para **PowerShellGet**. Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sim** ou **Sim a Todos** para continuar com a instalação.

## <a name="sign-in"></a>Entrar

Para começar a trabalhar com Teams PowerShell, entre com suas credenciais do Azure.

> [!NOTE]
> Se você estiver usando a versão Teams versão de visualização pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector Skype for Business Online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Entrar usando a MFA e a autenticação moderna

 Se sua conta usa autenticação multifacional, use as etapas nesta seção.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Atualizar Teams PowerShell

Para atualizar Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Se Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará. Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.


## <a name="uninstall-teams-powershell"></a>Desinstalar Teams PowerShell

Para desinstalar Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Se Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a desinstalação do módulo falhará. Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.

## <a name="install-teams-powershell-public-preview"></a>Instalar Teams visualização pública do PowerShell

> [!NOTE]
> Se você estiver usando a versão de Visualização Pública do Teams PowerShell, é recomendável desinstalar primeiro o Skype for Business Online.

Instalar o módulo Teams visualização pública do PowerShell para todos os usuários em um sistema requer privilégios elevados. Inicie a sessão do PowerShell usando **Executar como** administrador Windows ou use o comando `sudo` em macOS ou Linux.

Se você estiver usando o PowerShell 5.1, deverá atualizar o **módulo PowerShellGet** antecipadamente. Depois de atualizar **o PowerShellGet,** feche e reabra uma sessão elevada do PowerShell para garantir que o **PowerShellGet** mais recente seja carregado.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Para instalar Teams visualização pública do PowerShell, execute o comando do PowerShell abaixo.

> [!NOTE]
> Você pode encontrar a versão de visualização mais recente na Galeria do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou no PowerShell executando "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Próximos passos

Agora você está pronto para gerenciar o Teams usando Teams PowerShell. Consulte [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciando Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de versão do PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams de cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)
