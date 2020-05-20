---
title: Instalar a versão de pré-lançamento do módulo do teams PowerShell
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Siga estas etapas para instalar a versão de pré-lançamento do módulo do teams PowerShell da Galeria de teste do PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321764"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="d91db-103">Instalar a versão de pré-lançamento do módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="d91db-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="d91db-104">Este artigo descreve como instalar a versão de pré-lançamento mais recente do módulo do teams PowerShell da [Galeria de teste do PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="d91db-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="d91db-105">Você precisará da versão de pré-lançamento do módulo do teams PowerShell nos cenários em que cmdlets para gerenciar um recurso do Teams não são compatíveis com a versão geralmente disponível do módulo e estão disponíveis apenas na versão de pré-lançamento.</span><span class="sxs-lookup"><span data-stu-id="d91db-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="d91db-106">Use estas etapas para instalar a versão de pré-lançamento mais recente do módulo do teams PowerShell a partir da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="d91db-107">Não instale o módulo Teams PowerShell da Galeria de teste do PowerShell lado a lado com uma versão do módulo da [Galeria pública do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="d91db-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="d91db-108">Siga estas etapas para desinstalar primeiro o módulo do teams PowerShell da galeria do PowerShell público e instalar a versão mais recente do módulo da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="d91db-109">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="d91db-110">Inicie uma nova instância do módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="d91db-111">Execute o seguinte para desinstalar o módulo do teams PowerShell da galeria do PowerShell público:</span><span class="sxs-lookup"><span data-stu-id="d91db-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="d91db-112">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="d91db-113">Inicie o módulo do Windows PowerShell novamente e, em seguida, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável:</span><span class="sxs-lookup"><span data-stu-id="d91db-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="d91db-114">Execute o seguinte para instalar o módulo do PowerShell mais recente do teams a partir da Galeria de teste do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d91db-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="d91db-115">Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:</span><span class="sxs-lookup"><span data-stu-id="d91db-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="d91db-116">Atualize para a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d91db-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="d91db-117">Se você já tiver instalado o módulo do teams PowerShell da Galeria de teste do PowerShell, use as etapas a seguir para atualizar para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="d91db-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="d91db-118">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="d91db-119">Inicie uma nova instância do módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d91db-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="d91db-120">Execute o seguinte para atualizar a versão atualmente instalada do módulo do teams PowerShell a partir da Galeria de teste do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d91db-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="d91db-121">Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:</span><span class="sxs-lookup"><span data-stu-id="d91db-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="d91db-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d91db-122">Related topics</span></span>

- [<span data-ttu-id="d91db-123">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="d91db-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
