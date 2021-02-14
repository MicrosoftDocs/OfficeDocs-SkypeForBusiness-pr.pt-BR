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
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Mover do Skype for Business Online Connector para o módulo do PowerShell do Teams

Para mudar do uso do Skype for Business Online Connector para o módulo do PowerShell do Teams para gerenciar o Teams, você precisará atualizar os scripts existentes do PowerShell. Este artigo explica como fazer isso.

1. Instale o módulo mais recente do Teams PowerShell. Para ver as etapas, [consulte Instalar o Microsoft Teams Powershell.](teams-powershell-install.md)
2. Desinstale o Skype for Business Online Connector. Para fazer isso, no Painel de Controle, acesse Programas e **Recursos,** selecione **Skype for Business Online, Módulo do Windows PowerShell** e, em seguida, selecione **Desinstalar.** 
3. Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` ```MicrosoftTeams``` para.

    Por exemplo, altere ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Os administradores devem continuar a usar [o New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar a sessão antes de usar cmdlets do Skype for Business Online. 

## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Microsoft Teams Powershell](teams-powershell-install.md)

[Gerenciar equipes com o Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de versão do Teams PowerShell](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
