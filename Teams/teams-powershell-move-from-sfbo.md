---
title: Mover do Skype for Business Online Connector para o módulo do PowerShell do Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como mover do Skype for Business Online Connector para o módulo do Teams PowerShell para gerenciar o Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469659"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="84e63-103">Mover do Skype for Business Online Connector para o módulo do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="84e63-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="84e63-104">Para mudar do uso do Skype for Business Online Connector para o módulo do PowerShell do Teams para gerenciar o Teams, você precisará atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84e63-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="84e63-105">Este artigo explica como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="84e63-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="84e63-106">Instale o módulo mais recente do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84e63-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="84e63-107">Para ver as etapas, [consulte Instalar o Microsoft Teams Powershell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="84e63-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="84e63-108">Desinstale o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="84e63-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="84e63-109">Para fazer isso, no Painel de Controle, acesse Programas e **Recursos,** selecione **Skype for Business Online, Módulo do Windows PowerShell** e, em seguida, selecione **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="84e63-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="84e63-110">Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` ```MicrosoftTeams``` para.</span><span class="sxs-lookup"><span data-stu-id="84e63-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="84e63-111">Por exemplo, altere ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="84e63-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="84e63-112">Os administradores devem continuar a usar [o New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar a sessão antes de usar cmdlets do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="84e63-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="84e63-113">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="84e63-113">Related topics</span></span>

[<span data-ttu-id="84e63-114">Instalar o Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="84e63-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="84e63-115">Gerenciar equipes com o Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="84e63-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="84e63-116">Notas de versão do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="84e63-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="84e63-117">Referência de cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84e63-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="84e63-118">Referência de cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="84e63-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
