---
title: Mover do conector do Skype for Business online para o módulo do teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como migrar do Skype for Business online Connector para o módulo do teams PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469659"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="75c26-103">Mover do conector do Skype for Business online para o módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="75c26-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="75c26-104">Para mover-se usando o conector do Skype for Business online para o módulo do teams PowerShell para gerenciar o Teams, você precisará atualizar seus scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75c26-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="75c26-105">Este artigo explica como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="75c26-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="75c26-106">Instale o módulo do PowerShell das Teams mais recente.</span><span class="sxs-lookup"><span data-stu-id="75c26-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="75c26-107">Para ver as etapas, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="75c26-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="75c26-108">Desinstalar o conector do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="75c26-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="75c26-109">Para fazer isso, no painel de controle, acesse **programas e recursos**, selecione **Skype for Business Online, módulo do Windows PowerShell**e, em seguida, selecione **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="75c26-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="75c26-110">Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` em ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` para ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="75c26-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="75c26-111">Por exemplo, alterar ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="75c26-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="75c26-112">Os administradores devem continuar a usar o [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar a sessão antes de usar cmdlets do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="75c26-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="75c26-113">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="75c26-113">Related topics</span></span>

[<span data-ttu-id="75c26-114">Instalar o Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="75c26-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="75c26-115">Gerenciar equipes com o PowerShell do teams</span><span class="sxs-lookup"><span data-stu-id="75c26-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="75c26-116">Notas de versão do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="75c26-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="75c26-117">Referência do cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75c26-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="75c26-118">Referência do cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="75c26-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
