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
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569077"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Mover do Skype for Business Online Connector para o módulo do Teams PowerShell

Para mudar do uso do Conector do Skype for Business Online para o módulo do Teams PowerShell para gerenciar o Teams, você precisará atualizar os scripts existentes do PowerShell. Este artigo explica como fazer isso.

1. Instale o módulo mais recente do Teams PowerShell. Para ver as etapas, [consulte Install Microsoft Teams Powershell](teams-powershell-install.md).
2. Desinstale o Conector do Skype for Business Online. Para fazer isso, no Painel de Controle, **vá** Programas e Recursos, selecione Skype for **Business Online, Windows PowerShell Módulo** e selecione **Desinstalar**. 
3. Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de ```SkypeOnlineConnector``` ou para ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Por exemplo, altere ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .
4. Ao usar o Módulo 2.0 ou posterior do Teams PowerShell, altere New-csOnlineSession para Connect-MicrosoftTeams. 

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

## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Microsoft Teams Powershell](teams-powershell-install.md)

[Gerenciar equipes com o PowerShell do Teams](teams-powershell-managing-teams.md)

[Notas de versão do Teams PowerShell](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
