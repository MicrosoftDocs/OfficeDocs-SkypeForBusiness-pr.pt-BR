---
title: Microsoft Teams Visão geral do PowerShell
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
description: Aprenda a usar os controles do PowerShell para gerenciar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768350"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="ead59-103">Microsoft Teams Visão geral do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ead59-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="ead59-104">Microsoft Teams O PowerShell é um conjunto de cmdlets para gerenciar Teams diretamente da linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ead59-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="ead59-105">Escrito no .NET Standard, o Teams PowerShell funciona no PowerShell 5.1 em Windows, PowerShell 6.x e superior em todas as plataformas, incluindo o Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="ead59-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="ead59-106">Antes de começar a usar o PowerShell, você precisará [instalá-lo](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="ead59-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="ead59-107">Há problemas conhecidos com o PowerShell 7 e Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ead59-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="ead59-108">Recomendamos usar o PowerShell 5.1 até que os problemas sejam resolvidos.</span><span class="sxs-lookup"><span data-stu-id="ead59-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="ead59-109">Versões</span><span class="sxs-lookup"><span data-stu-id="ead59-109">Releases</span></span>


<span data-ttu-id="ead59-110">Teams O PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.</span><span class="sxs-lookup"><span data-stu-id="ead59-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="ead59-111">**Disponibilidade Geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.</span><span class="sxs-lookup"><span data-stu-id="ead59-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="ead59-112">**Visualização Pública**: Acesso antecipado aos recursos.</span><span class="sxs-lookup"><span data-stu-id="ead59-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="ead59-113">Pode ser atualizado com mais frequência do que GA.</span><span class="sxs-lookup"><span data-stu-id="ead59-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="ead59-114">Para obter informações detalhadas sobre adições de recursos e melhorias para ambas as versões, leia as notas de versão [Teams do PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="ead59-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="ead59-115">Gerenciar Teams com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ead59-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="ead59-116">Você usará os módulos Teams PowerShell para gerenciar Teams:</span><span class="sxs-lookup"><span data-stu-id="ead59-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="ead59-117">[Microsoft Teams módulo do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): o módulo Teams PowerShell contém cmdlets para gerenciar equipes, chat e canais.</span><span class="sxs-lookup"><span data-stu-id="ead59-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="ead59-118">O Teams versão pública do [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) versão 2.0 ou superior inclui todos os cmdlets do Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ead59-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="ead59-119">[Skype for Business Conector do PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): o conector Skype for Business PowerShell agora faz parte do módulo Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ead59-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="ead59-120">Para ver um guia completo para gerenciar Teams usando esses módulos, consulte [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ead59-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="ead59-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ead59-121">Related topics</span></span>

[<span data-ttu-id="ead59-122">Instalando Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ead59-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="ead59-123">Gerenciando Teams com Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ead59-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ead59-124">Teams Notas de versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ead59-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ead59-125">Microsoft Teams de cmdlet</span><span class="sxs-lookup"><span data-stu-id="ead59-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ead59-126">Skype for Business de cmdlet</span><span class="sxs-lookup"><span data-stu-id="ead59-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="ead59-127">Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ead59-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
