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
description: Aprenda a usar os controles do PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6ba8545159f8b18ebe39e49356f64378f946b29
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874801"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="db2a5-103">Instalar o Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="db2a5-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="db2a5-104">Este artigo explica como instalar o módulo do Microsoft Teams PowerShell usando [o PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="db2a5-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="db2a5-105">Essas instruções funcionam em plataformas [do Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="db2a5-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="db2a5-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db2a5-106">Requirements</span></span>

<span data-ttu-id="db2a5-107">O PowerShell do Teams exige o PowerShell 5.1 ou superior em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="db2a5-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="db2a5-108">Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="db2a5-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="db2a5-109">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="db2a5-110">Para a melhor experiência, recomendamos que você use o PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="db2a5-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="db2a5-111">Instalar o módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="db2a5-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="db2a5-112">Para a melhor experiência, use os módulos Disponibilidade Geral (GA) ou Visualização Pública - não ambos.</span><span class="sxs-lookup"><span data-stu-id="db2a5-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="db2a5-113">Eles não se destinam a trabalhar juntos.</span><span class="sxs-lookup"><span data-stu-id="db2a5-113">They're not intended to work together.</span></span>


<span data-ttu-id="db2a5-114">Use os cmdlets **PowerShellGet** para instalar o módulo do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="db2a5-115">Instalar o módulo para todos os usuários em um sistema requer privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="db2a5-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="db2a5-116">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o comando em `sudo` macOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="db2a5-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="db2a5-117">Por padrão, a Galeria do PowerShell (PSGallery) não é configurada como um repositório confiável para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="db2a5-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="db2a5-118">Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="db2a5-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="db2a5-119">Responda **Sim** ou **Sim a Todos** para continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="db2a5-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="db2a5-120">Instalar a visualização pública do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="db2a5-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="db2a5-121">Se você estiver usando a versão de Visualização Pública do Teams PowerShell, é recomendável desinstalar primeiro o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="db2a5-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="db2a5-122">Instalar o módulo de visualização pública do Teams PowerShell para todos os usuários em um sistema requer privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="db2a5-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="db2a5-123">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o comando em `sudo` macOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="db2a5-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="db2a5-124">Se você estiver usando o PowerShell 5.1, deverá atualizar o **módulo PowerShellGet** antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="db2a5-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="db2a5-125">Depois de atualizar **o PowerShellGet,** feche e reabra uma sessão elevada do PowerShell para garantir que o **PowerShellGet** mais recente seja carregado.</span><span class="sxs-lookup"><span data-stu-id="db2a5-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="db2a5-126">Para instalar a visualização pública do Teams PowerShell, execute o comando do PowerShell abaixo.</span><span class="sxs-lookup"><span data-stu-id="db2a5-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="db2a5-127">Você pode encontrar a versão de visualização mais recente na Galeria do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) ou no PowerShell executando "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span><span class="sxs-lookup"><span data-stu-id="db2a5-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="db2a5-128">Instalar o Conector do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="db2a5-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="db2a5-129">O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="db2a5-130">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="db2a5-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a><span data-ttu-id="db2a5-131">Entrar</span><span class="sxs-lookup"><span data-stu-id="db2a5-131">Sign in</span></span>

<span data-ttu-id="db2a5-132">Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="db2a5-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="db2a5-133">Se você estiver usando a versão de visualização pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="db2a5-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="db2a5-134">Entrar usando a MFA e a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="db2a5-134">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="db2a5-135">Se sua conta usa autenticação multifacional, use as etapas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="db2a5-135">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="db2a5-136">Atualizar o PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="db2a5-136">Update Teams PowerShell</span></span>

<span data-ttu-id="db2a5-137">Para atualizar o PowerShell do Teams, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="db2a5-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="db2a5-138">Se o PowerShell do Teams já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="db2a5-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="db2a5-139">Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="db2a5-140">Desinstalar o Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="db2a5-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="db2a5-141">Para desinstalar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="db2a5-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="db2a5-142">Se o PowerShell do Teams já tiver sido importado para sua sessão do PowerShell, a desinstalação do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="db2a5-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="db2a5-143">Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="db2a5-144">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="db2a5-144">Next Steps</span></span>

<span data-ttu-id="db2a5-145">Agora você está pronto para gerenciar o Teams usando o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db2a5-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="db2a5-146">Consulte [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span><span class="sxs-lookup"><span data-stu-id="db2a5-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db2a5-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="db2a5-147">Related topics</span></span>

[<span data-ttu-id="db2a5-148">Gerenciando o Teams com o Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="db2a5-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="db2a5-149">Notas de versão do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="db2a5-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="db2a5-150">Referência de cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db2a5-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="db2a5-151">Referência de cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="db2a5-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
