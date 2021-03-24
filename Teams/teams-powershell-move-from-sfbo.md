---
title: Mover do Skype for Business Online Connector para o módulo do Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como mover do Conector do Skype for Business Online para o módulo do Teams PowerShell para gerenciar o Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094122"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="488bf-103">Mover do Skype for Business Online Connector para o módulo do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="488bf-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="488bf-104">Para mudar do uso do Conector do Skype for Business Online para o módulo do Teams PowerShell para gerenciar o Teams, você precisará atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="488bf-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="488bf-105">Este artigo explica como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="488bf-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="488bf-106">Instale o módulo mais recente do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="488bf-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="488bf-107">Para ver as etapas, [consulte Install Microsoft Teams Powershell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="488bf-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="488bf-108">Desinstale o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="488bf-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="488bf-109">Para fazer isso, no Painel de Controle, **vá** Programas e Recursos, selecione Skype for **Business Online, Windows PowerShell Módulo** e selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="488bf-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="488bf-110">Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de ```SkypeOnlineConnector``` ou para ```LyncOnlineConnector``` ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="488bf-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="488bf-111">Por exemplo, altere ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="488bf-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="488bf-112">Ao usar o Módulo 2.0 ou posterior do Teams PowerShell, altere New-csOnlineSession para Connect-MicrosoftTeams.</span><span class="sxs-lookup"><span data-stu-id="488bf-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="488bf-113">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="488bf-113">Related topics</span></span>

[<span data-ttu-id="488bf-114">Instalar o Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="488bf-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="488bf-115">Gerenciar equipes com o PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="488bf-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="488bf-116">Notas de versão do Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="488bf-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="488bf-117">Referência de cmdlet do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="488bf-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="488bf-118">Referência de cmdlet do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="488bf-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)