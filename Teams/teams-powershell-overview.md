---
title: Visão geral do Microsoft Teams PowerShell
ms.reviewer: ''
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
ms.openlocfilehash: 3ec9c9062a26442ae03a332f7cdd6f1e9b56cee5
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756148"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="74ddd-103">Visão geral do Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ddd-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="74ddd-104">O Microsoft Teams PowerShell é um conjunto de cmdlets para gerenciar o Teams diretamente da linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ddd-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="74ddd-105">Escrito no .NET Standard, o PowerShell do Teams funciona no PowerShell 5.1 no Windows, PowerShell 6.x e superior em todas as plataformas, incluindo o Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="74ddd-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="74ddd-106">Antes de começar a usar o PowerShell, você precisará [instalá-lo](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="74ddd-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="74ddd-107">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ddd-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="74ddd-108">Recomendamos usar o PowerShell 5.1 até que os problemas sejam resolvidos.</span><span class="sxs-lookup"><span data-stu-id="74ddd-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="74ddd-109">Versões</span><span class="sxs-lookup"><span data-stu-id="74ddd-109">Releases</span></span>


<span data-ttu-id="74ddd-110">O Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.</span><span class="sxs-lookup"><span data-stu-id="74ddd-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="74ddd-111">**Disponibilidade Geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.</span><span class="sxs-lookup"><span data-stu-id="74ddd-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="74ddd-112">**Visualização Pública**: Acesso antecipado aos recursos.</span><span class="sxs-lookup"><span data-stu-id="74ddd-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="74ddd-113">Pode ser atualizado com mais frequência do que GA.</span><span class="sxs-lookup"><span data-stu-id="74ddd-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="74ddd-114">Para obter informações detalhadas sobre adições de recursos e melhorias para ambas as versões, leia as notas de versão [do Teams PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="74ddd-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="74ddd-115">Gerenciar o Teams com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ddd-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="74ddd-116">Você usará módulos do Teams PowerShell para gerenciar totalmente o Teams:</span><span class="sxs-lookup"><span data-stu-id="74ddd-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="74ddd-117">[Módulo do PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): o módulo do Teams PowerShell contém cmdlets para gerenciar equipes, chat e canais.</span><span class="sxs-lookup"><span data-stu-id="74ddd-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="74ddd-118">A [versão pública do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) versão 1.1.6 ou posterior é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ddd-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="74ddd-119">[Conector do PowerShell do Skype for Business](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): O conector do PowerShell do Skype for Business agora faz parte do módulo do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74ddd-119">[Skype for Business PowerShell Connector](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="74ddd-120">Para ver um guia completo sobre como gerenciar o Teams usando esses módulos, consulte [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="74ddd-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="74ddd-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="74ddd-121">Related topics</span></span>

[<span data-ttu-id="74ddd-122">Instalando o PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="74ddd-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="74ddd-123">Gerenciando o Teams com o Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="74ddd-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="74ddd-124">Notas de versão do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="74ddd-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="74ddd-125">Referência de cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74ddd-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="74ddd-126">Referência de cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="74ddd-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="74ddd-127">Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74ddd-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
