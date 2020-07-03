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
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="327f7-103">Instalar o Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="327f7-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="327f7-104">Este artigo explica como instalar o módulo do Microsoft Teams PowerShell usando o [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span><span class="sxs-lookup"><span data-stu-id="327f7-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="327f7-105">Estas instruções funcionam nas plataformas [do Azure cloud Shell](/azure/cloud-shell/overview), Linux, MacOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="327f7-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="327f7-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="327f7-106">Requirements</span></span>

<span data-ttu-id="327f7-107">O Teams PowerShell funciona com o PowerShell 6.2.4 e posterior em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="327f7-107">Teams PowerShell works with PowerShell 6.2.4 and later on all platforms.</span></span> <span data-ttu-id="327f7-108">Também é compatível com o PowerShell 5,1 no Windows.</span><span class="sxs-lookup"><span data-stu-id="327f7-108">It is also supported with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="327f7-109">Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell) disponível para o seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="327f7-109">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> <span data-ttu-id="327f7-110">O Teams PowerShell não tem requisitos adicionais quando executados no PowerShell 6.2.4 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="327f7-110">Teams PowerShell has no additional requirements when run on PowerShell 6.2.4 and later.</span></span>

> [!WARNING]
> <span data-ttu-id="327f7-111">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327f7-111">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="327f7-112">Para obter a melhor experiência, recomendamos que você use o PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="327f7-112">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="327f7-113">Instalar o módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="327f7-113">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="327f7-114">Para obter a melhor experiência, use módulos de disponibilidade geral (GA) ou Public Preview, não ambos.</span><span class="sxs-lookup"><span data-stu-id="327f7-114">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="327f7-115">Eles não têm a intenção de trabalhar juntos.</span><span class="sxs-lookup"><span data-stu-id="327f7-115">They're not intended to work together.</span></span>


<span data-ttu-id="327f7-116">Use os cmdlets **PowerShellGet** para instalar o módulo do PowerShell do teams.</span><span class="sxs-lookup"><span data-stu-id="327f7-116">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="327f7-117">A instalação do módulo para todos os usuários em um sistema exige privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="327f7-117">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="327f7-118">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux:</span><span class="sxs-lookup"><span data-stu-id="327f7-118">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="327f7-119">Por padrão, a galeria do PowerShell (PSGallery) não está configurada como um repositório confiável para o **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="327f7-119">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="327f7-120">Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="327f7-120">The first time you use the PSGallery, you'll see the following message:</span></span>

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="327f7-121">Responda `Yes` ou `Yes to All` para continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="327f7-121">Answer `Yes` or `Yes to All` to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="327f7-122">Instale a visualização pública do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="327f7-122">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="327f7-123">Se você estiver usando a versão de visualização pública do teams PowerShell, recomendamos que primeiro desinstale o Skype for Business online Connector.</span><span class="sxs-lookup"><span data-stu-id="327f7-123">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="327f7-124">Instalar o módulo de visualização pública do teams para todos os usuários em um sistema requer privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="327f7-124">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="327f7-125">Inicie a sessão do PowerShell usando **Executar como administrador** no Windows ou use o `sudo` comando no MacOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="327f7-125">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="327f7-126">Se você estiver usando o PowerShell 5,1, será necessário atualizar o módulo **PowerShellGet** antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="327f7-126">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="327f7-127">Após atualizar o **PowerShellGet**, feche e reabra uma sessão do PowerShell com privilégios para garantir que o **PowerShellGet** mais recente seja carregado.</span><span class="sxs-lookup"><span data-stu-id="327f7-127">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="327f7-128">Para instalar a visualização pública do teams PowerShell, execute o comando do PowerShell abaixo.</span><span class="sxs-lookup"><span data-stu-id="327f7-128">To install Teams Powershell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="327f7-129">Instalar o conector do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="327f7-129">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="327f7-130">O conector Skype for Business online atualmente faz parte da visualização pública do teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327f7-130">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="327f7-131">Depois de lançarmos esse recurso no lançamento de GA do teams PowerShell, o conector do Skype for Business online não estará mais disponível.</span><span class="sxs-lookup"><span data-stu-id="327f7-131">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="327f7-132">Baixe e instale o [módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366)e execute o seguinte no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="327f7-132">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="327f7-133">Entrar</span><span class="sxs-lookup"><span data-stu-id="327f7-133">Sign in</span></span>

<span data-ttu-id="327f7-134">Para começar a trabalhar com o Teams PowerShell, entre com suas credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="327f7-134">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="327f7-135">Se você estiver usando a versão mais recente do [PowerShell Public Preview do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), não será necessário instalar o conector do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="327f7-135">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="327f7-136">Atualizar o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="327f7-136">Update Teams PowerShell</span></span>

<span data-ttu-id="327f7-137">Para atualizar o PowerShell do Teams, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="327f7-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="327f7-138">Se o Microsoft Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="327f7-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="327f7-139">Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="327f7-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="327f7-140">Desinstalar o PowerShell do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="327f7-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="327f7-141">Para desinstalar o Teams PowerShell, abra um novo prompt de comando elevado do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="327f7-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="327f7-142">Se o Microsoft Teams PowerShell já tiver sido importado para a sua sessão do PowerShell, a desinstalação do módulo irá falhar.</span><span class="sxs-lookup"><span data-stu-id="327f7-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="327f7-143">Feche o PowerShell e abra novamente uma nova sessão do PowerShell com privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="327f7-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="327f7-144">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="327f7-144">Next Steps</span></span>

<span data-ttu-id="327f7-145">Agora você está pronto para gerenciar o Microsoft Teams usando o PowerShell do teams.</span><span class="sxs-lookup"><span data-stu-id="327f7-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="327f7-146">Consulte [gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="327f7-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="327f7-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="327f7-147">Related topics</span></span>

[<span data-ttu-id="327f7-148">Gerenciando equipes com o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="327f7-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="327f7-149">Notas de versão do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="327f7-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="327f7-150">Referência do cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="327f7-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="327f7-151">Referência do cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="327f7-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)