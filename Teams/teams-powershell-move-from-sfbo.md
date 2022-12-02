---
title: Migrando de Skype for Business Conector Online para o módulo do Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como mover do Skype for Business Conector Online para o módulo do Teams PowerShell para gerenciar o Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242285"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrando de Skype for Business Conector Online para o módulo do Teams PowerShell

O Módulo do Teams PowerShell fornece um conjunto completo de cmdlets para gerenciar o Teams diretamente da linha de comando do PowerShell. Os administradores não exigem o Conector do Skype For Business Online para sua administração do Teams.

> [!NOTE]
> O administrador do Teams foi notificado por meio da postagem do Centro de Mensagens (MC244740, datada de 16 de março de 2021; MC250940, datado de 16 de abril de 2021) sobre essa alteração.
>
> O Módulo do Teams PowerShell usa autenticação moderna, mas o cliente do WinRM (Gerenciamento Remoto do Windows) subjacente deve ser configurado para permitir a autenticação básica. Consulte [Baixar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obter instruções sobre como habilitar o WinRM para autenticação básica.

## <a name="how-to-migrate"></a>Como migrar

Migrar de usar Skype for Business conector online para o módulo do Teams PowerShell é fácil e simples. As etapas a seguir explicam como fazer isso.

1. Instale o módulo mais recente do Teams PowerShell. Para ver as etapas, consulte [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).

2. Desinstale o Conector do Skype For Business Online. Para fazer isso, em Painel de Controle, acesse Programas e Recursos, selecione **Skype for Business Online, Windows PowerShell Módulo** e **selecione Desinstalar**.

3. Em seus scripts do PowerShell, altere o nome do módulo referenciado em ```Import-Module``` de

    `SkypeOnlineConnector` ou `LyncOnlineConnector` para `MicrosoftTeams`.

    Por exemplo, altere `Import-Module -Name SkypeOnlineConnector` para `Import-Module -Name MicrosoftTeams`.

4. Ao usar o Módulo 2.0 ou posterior do Teams PowerShell, atualize seus scripts que se referem `New-CsOnlineSession` a `Connect-MicrosoftTeams`. `Import-PsSession`não é mais necessário estabelecer um Skype for Business Sessão Remota do PowerShell Online, pois isso é feito implícito ao usar `Connect-MicrosoftTeams`.

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Tópicos relacionados

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciar o Teams com o Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de versão do Teams PowerShell](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](/powershell/teams/)

[referência de cmdlet Skype for Business](/powershell/skype/intro)
