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
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943984"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="9e856-103">Visão geral do Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e856-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="9e856-104">O Microsoft Teams PowerShell é um conjunto de cmdlets para o gerenciamento de equipes diretamente da linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e856-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="9e856-105">Escrito em .NET Standard, o PowerShell do teams funciona no PowerShell 5,1 no Windows, PowerShell 6. x e superior em todas as plataformas, incluindo o Shell do Azure.</span><span class="sxs-lookup"><span data-stu-id="9e856-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="9e856-106">Antes de começar a usar o PowerShell, você precisará [instalá-lo](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="9e856-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="9e856-107">Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e856-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="9e856-108">Recomendamos usar o PowerShell 5,1 até que os problemas sejam resolvidos.</span><span class="sxs-lookup"><span data-stu-id="9e856-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="9e856-109">Imprensa</span><span class="sxs-lookup"><span data-stu-id="9e856-109">Releases</span></span>


<span data-ttu-id="9e856-110">O Microsoft Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.</span><span class="sxs-lookup"><span data-stu-id="9e856-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="9e856-111">**Disponibilidade geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.</span><span class="sxs-lookup"><span data-stu-id="9e856-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="9e856-112">**Visualização pública**: acesso antecipado aos recursos.</span><span class="sxs-lookup"><span data-stu-id="9e856-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="9e856-113">Pode ser atualizado com mais frequência do que o GA.</span><span class="sxs-lookup"><span data-stu-id="9e856-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="9e856-114">Para obter informações detalhadas sobre adições de recursos e melhorias para ambos os lançamentos, leia as [notas de versão do teams PowerShell](teams-powershell-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="9e856-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="9e856-115">Gerenciar equipes com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e856-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="9e856-116">Você usará ambos os módulos do PowerShell para gerenciar totalmente as equipes:</span><span class="sxs-lookup"><span data-stu-id="9e856-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="9e856-117">[Módulo do PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): o módulo do PowerShell do teams contém cmdlets para gerenciar equipes, chats e canais.</span><span class="sxs-lookup"><span data-stu-id="9e856-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="9e856-118">[Módulo do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366): o módulo do PowerShell do Skype for Business contém os cmdlets para gerenciar reuniões, sistemas de telefonia e recursos de políticas.</span><span class="sxs-lookup"><span data-stu-id="9e856-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="9e856-119">Para obter um guia completo sobre o gerenciamento de equipes usando esses módulos, consulte [gerenciar equipes com o PowerShell do teams](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9e856-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9e856-120">A versão mais recente do [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada ao conector do Skype for Business Online, fornecendo um único módulo para gerenciamento do teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e856-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e856-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e856-121">Related topics</span></span>

[<span data-ttu-id="9e856-122">Instalando o Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e856-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="9e856-123">Gerenciando equipes com o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="9e856-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="9e856-124">Notas de versão do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e856-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="9e856-125">Referência do cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e856-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="9e856-126">Referência do cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9e856-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="9e856-127">Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e856-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
