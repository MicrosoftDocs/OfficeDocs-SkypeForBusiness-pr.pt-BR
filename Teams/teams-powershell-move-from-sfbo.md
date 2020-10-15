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
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Mover do conector do Skype for Business online para o módulo do teams PowerShell

Para mover-se usando o conector do Skype for Business online para o módulo do teams PowerShell para gerenciar o Teams, você precisará atualizar seus scripts existentes do PowerShell. Este artigo explica como fazer isso.

1. Instale o módulo do PowerShell das Teams mais recente. Para ver as etapas, confira [instalar o Microsoft Teams PowerShell](teams-powershell-install.md).
2. Desinstalar o conector do Skype for Business online. Para fazer isso, no painel de controle, acesse **programas e recursos**, selecione **Skype for Business Online, módulo do Windows PowerShell**e, em seguida, selecione **desinstalar**. 
3. Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` em ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` para ```MicrosoftTeams``` .

    Por exemplo, alterar ```Import-Module -Name SkypeOnlineConnector``` para ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Os administradores devem continuar a usar o [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar a sessão antes de usar cmdlets do Skype for Business online. 

## <a name="related-topics"></a>Tópicos relacionados

[Instalar o Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciar equipes com o PowerShell do teams](teams-powershell-managing-teams.md)

[Notas de versão do teams PowerShell](teams-powershell-release-notes.md)

[Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
