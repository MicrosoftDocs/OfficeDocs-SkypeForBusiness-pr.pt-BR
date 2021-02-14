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
description: Saiba como usar os controles do PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852152"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="9e6a8-103">Visão geral do Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6a8-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="9e6a8-104">O Microsoft Teams PowerShell é um conjunto de cmdlets para gerenciar o Teams diretamente da linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="9e6a8-105">Escrito no .NET Standard, o PowerShell do Teams funciona no PowerShell 5.1 no Windows, PowerShell 6.x e superior em todas as plataformas, incluindo o Shell de Nuvem do Azure.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="9e6a8-106">Antes de começar a usar o PowerShell, você precisará [instalá-lo.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="9e6a8-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="9e6a8-107">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="9e6a8-108">Recomendamos usar o PowerShell 5.1 até que os problemas sejam resolvidos.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="9e6a8-109">Libera</span><span class="sxs-lookup"><span data-stu-id="9e6a8-109">Releases</span></span>


<span data-ttu-id="9e6a8-110">O Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="9e6a8-111">**Disponibilidade Geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="9e6a8-112">**Visualização Pública:** acesso antecipado aos recursos.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="9e6a8-113">Pode ser atualizado com mais frequência do que GA.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="9e6a8-114">Para obter informações detalhadas sobre adições de recursos e melhorias para ambas as versões, leia as notas de versão [do PowerShell do Teams.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="9e6a8-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="9e6a8-115">Gerenciar equipes com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6a8-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="9e6a8-116">Você usará módulos do Teams PowerShell para gerenciar completamente o Teams:</span><span class="sxs-lookup"><span data-stu-id="9e6a8-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="9e6a8-117">[Módulo do Microsoft Teams PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)o módulo do Teams PowerShell contém cmdlets para gerenciar equipes, chats e canais.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="9e6a8-118">A versão [pública mais recente do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="9e6a8-119">[Skype for Business PowerShell Connector:](https://www.microsoft.com/download/details.aspx?id=39366)o conector do PowerShell do Skype for Business agora faz parte do módulo do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="9e6a8-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="9e6a8-120">Para ver um guia completo sobre como gerenciar o Teams usando esses módulos, consulte [Gerenciar Equipes com o Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9e6a8-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="9e6a8-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e6a8-121">Related topics</span></span>

[<span data-ttu-id="9e6a8-122">Instalando o PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9e6a8-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="9e6a8-123">Gerenciando equipes com o Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e6a8-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="9e6a8-124">Notas de versão do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9e6a8-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="9e6a8-125">Referência de cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e6a8-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="9e6a8-126">Referência de cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9e6a8-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="9e6a8-127">Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e6a8-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
