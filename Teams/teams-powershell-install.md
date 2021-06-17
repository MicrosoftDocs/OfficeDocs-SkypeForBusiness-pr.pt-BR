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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947562"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="b8270-103">Instalar Microsoft Teams Módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8270-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="b8270-104">Este artigo explica como instalar o módulo Microsoft Teams PowerShell usando a Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="b8270-105">O Microsoft Teams do PowerShell é suportado em todas as Windows plataformas.</span><span class="sxs-lookup"><span data-stu-id="b8270-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="b8270-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8270-106">Requirements</span></span>

<span data-ttu-id="b8270-107">Microsoft Teams O módulo do PowerShell exige o PowerShell 5.1 ou superior em todas as plataformas.</span><span class="sxs-lookup"><span data-stu-id="b8270-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="b8270-108">Instale a [versão mais recente do PowerShell](/powershell/scripting/install/installing-powershell)disponível para seu sistema   operacional.</span><span class="sxs-lookup"><span data-stu-id="b8270-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="b8270-109">Para verificar sua versão do PowerShell, execute o seguinte comando de dentro de uma sessão do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b8270-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="b8270-110">Recomendamos que você use o cmdlet Install-Module para instalar o módulo Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="b8270-111">Se a Galeria do PowerShell (PSGallery) não estiver configurada como um repositório confiável para **PowerShellGet**, na primeira vez que você usar o PSGallery, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="b8270-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="b8270-112">Responda **Sim** ou **Sim a Todos** para continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="b8270-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="b8270-113">Instalar usando o PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="b8270-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="b8270-114">Microsoft Teams No momento, o módulo do PowerShell tem suporte para uso com o PowerShell 5.1 no Windows.</span><span class="sxs-lookup"><span data-stu-id="b8270-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="b8270-115">Siga estas etapas para instalar o módulo:</span><span class="sxs-lookup"><span data-stu-id="b8270-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="b8270-116">Atualizar para [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b8270-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="b8270-117">Se você estiver no Windows 10 versão 1607 ou superior, já tem o PowerShell 5.1 instalado.</span><span class="sxs-lookup"><span data-stu-id="b8270-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="b8270-118">Instale [.NET Framework 4.7.2](/dotnet/framework/install) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b8270-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="b8270-119">Execute o seguinte comando para instalar o PowerShellGet mais recente:</span><span class="sxs-lookup"><span data-stu-id="b8270-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="b8270-120">Instale o módulo Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="b8270-121">Instalação offline</span><span class="sxs-lookup"><span data-stu-id="b8270-121">Offline Installation</span></span> 

<span data-ttu-id="b8270-122">Em alguns ambientes, não é possível se conectar à Galeria do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="b8270-123">Nessas situações, siga estas etapas [manuais de instalação](https://aka.ms/psgallery-manualdownload).</span><span class="sxs-lookup"><span data-stu-id="b8270-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="b8270-124">Entrar</span><span class="sxs-lookup"><span data-stu-id="b8270-124">Sign in</span></span>

<span data-ttu-id="b8270-125">Para começar a trabalhar com Microsoft Teams módulo do PowerShell, entre com suas credenciais do Azure.</span><span class="sxs-lookup"><span data-stu-id="b8270-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="b8270-126">Atualizar Teams Módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8270-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="b8270-127">Para atualizar qualquer módulo do PowerShell, você deve usar o mesmo método usado para instalar o módulo.</span><span class="sxs-lookup"><span data-stu-id="b8270-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="b8270-128">Por exemplo, se você usou o Install-Module originalmente, deve usar [o Update-Module](/powershell/module/powershellget/update-module) para obter a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="b8270-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="b8270-129">Se Teams PowerShell já tiver sido importado para sua sessão do PowerShell, a atualização do módulo falhará.</span><span class="sxs-lookup"><span data-stu-id="b8270-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="b8270-130">Feche o PowerShell e reaberto uma nova sessão elevada do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="b8270-131">Desinstalar Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8270-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="b8270-132">Para desinstalar Microsoft Teams PowerShell, abra um novo prompt de comando do PowerShell e execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8270-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="b8270-133">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="b8270-133">Next Steps</span></span> 

<span data-ttu-id="b8270-134">Agora você está pronto para gerenciar o Microsoft Teams usando Microsoft Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8270-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="b8270-135">Consulte [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span><span class="sxs-lookup"><span data-stu-id="b8270-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b8270-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8270-136">Related topics</span></span>

[<span data-ttu-id="b8270-137">Gerenciando Teams com Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8270-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="b8270-138">Teams Notas de versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8270-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="b8270-139">Microsoft Teams de cmdlet</span><span class="sxs-lookup"><span data-stu-id="b8270-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="b8270-140">Skype for Business de cmdlet</span><span class="sxs-lookup"><span data-stu-id="b8270-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
