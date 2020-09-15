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
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="2f123-103">Instalar o Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f123-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="2f123-104">Este artigo explica como instalar o módulo do Microsoft Teams PowerShell usando o [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="2f123-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="2f123-105">Estas instruções funcionam nas plataformas [do Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="2f123-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="2f123-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f123-106">Requirements</span></span>

<span data-ttu-id="2f123-107">O Teams PowerShell requer o PowerShell 5,1 ou superior em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="2f123-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="2f123-108">Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para o seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2f123-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="2f123-109">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f123-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="2f123-110">Para obter a melhor experiência, recomendamos que você use o PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="2f123-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="2f123-111">Instalar o módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f123-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="2f123-112">Para obter a melhor experiência, use módulos de disponibilidade geral (GA) ou Public Preview, não ambos.</span><span class="sxs-lookup"><span data-stu-id="2f123-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="2f123-113">Eles não têm a intenção de trabalhar juntos.</span><span class="sxs-lookup"><span data-stu-id="2f123-113">They're not intended to work together.</span></span>


<span data-ttu-id="2f123-114">Use os cmdlets **PowerShellGet** para instalar o módulo do PowerShell do teams.</span><span class="sxs-lookup"><span data-stu-id="2f123-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="2f123-115">A instalação do módulo para todos os usuários em um sistema exige privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="2f123-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2f123-116">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="2f123-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="2f123-117">Por padrão, a galeria do PowerShell (PSGallery) não está configurada como um repositório confiável para o **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="2f123-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="2f123-118">Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="2f123-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="2f123-119">Responda **Sim** ou **Sim para tudo** para continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="2f123-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="2f123-120">Instale a visualização pública do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f123-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="2f123-121">Se você estiver usando a versão de visualização pública do teams PowerShell, recomendamos que primeiro desinstale o Skype for Business online Connector.</span><span class="sxs-lookup"><span data-stu-id="2f123-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="2f123-122">Instalar o módulo de visualização pública do teams para todos os usuários em um sistema requer privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="2f123-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="2f123-123">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="2f123-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="2f123-124">Se você estiver usando o PowerShell 5,1, será necessário atualizar o módulo **PowerShellGet** antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="2f123-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="2f123-125">Após atualizar o **PowerShellGet**, feche e reabra uma sessão do PowerShell com privilégios para garantir que o **PowerShellGet** mais recente seja carregado.</span><span class="sxs-lookup"><span data-stu-id="2f123-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="2f123-126">Para instalar a visualização pública do teams PowerShell, execute o comando do PowerShell abaixo.</span><span class="sxs-lookup"><span data-stu-id="2f123-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="2f123-127">Você pode encontrar a versão de visualização mais recente na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou no PowerShell executando "Find-Module MicrosoftTeams-AllowPrerelease"</span><span class="sxs-lookup"><span data-stu-id="2f123-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="2f123-128">Instalar o conector do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f123-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="2f123-129">O conector do Skype for Business online atualmente faz parte do módulo do PowerShell mais recente do teams.</span><span class="sxs-lookup"><span data-stu-id="2f123-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="2f123-130">Se você estiver usando a [versão pública do teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)mais recente, não será necessário instalar o conector do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2f123-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="2f123-131">Entrar</span><span class="sxs-lookup"><span data-stu-id="2f123-131">Sign in</span></span>

<span data-ttu-id="2f123-132">Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="2f123-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="2f123-133">Se você estiver usando a versão mais recente do [PowerShell Public Preview do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), não será necessário instalar o conector do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2f123-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="2f123-134">Atualizar o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="2f123-134">Update Teams PowerShell</span></span>

<span data-ttu-id="2f123-135">Para atualizar o PowerShell do Teams, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f123-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="2f123-136">Se o Microsoft Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="2f123-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="2f123-137">Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="2f123-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="2f123-138">Desinstalar o PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f123-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="2f123-139">Para desinstalar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2f123-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="2f123-140">Se o Microsoft Teams PowerShell já tiver sido importado para a sua sessão do PowerShell, a desinstalação do módulo irá falhar.</span><span class="sxs-lookup"><span data-stu-id="2f123-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="2f123-141">Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="2f123-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2f123-142">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="2f123-142">Next Steps</span></span>

<span data-ttu-id="2f123-143">Agora você está pronto para gerenciar o Microsoft Teams usando o PowerShell do teams.</span><span class="sxs-lookup"><span data-stu-id="2f123-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="2f123-144">Consulte [gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="2f123-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f123-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f123-145">Related topics</span></span>

[<span data-ttu-id="2f123-146">Gerenciando equipes com o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="2f123-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="2f123-147">Notas de versão do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f123-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="2f123-148">Referência do cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f123-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="2f123-149">Referência do cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2f123-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
