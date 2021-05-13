---
title: Migrando do Skype for Business Online para o módulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como mover do conector Skype for Business Online para o módulo Teams PowerShell para gerenciar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469713"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migrando do Skype for Business Online para o módulo Teams PowerShell

Teams O Módulo do PowerShell fornece um conjunto completo de cmdlets para gerenciar Teams diretamente da linha de comando do PowerShell. Os administradores não exigem Skype conector para Empresas Online para sua Teams administração.

> [!NOTE]
> Teams administrador foi notificado por meio da postagem da Central de Mensagens (MC244740, datada de 16 de março de 2021; MC250940, datado de 16 de abril de 2021) sobre essa alteração.
>
> Teams O Módulo do PowerShell usa autenticação moderna, mas o cliente Windows Gerenciamento Remoto (WinRM) subjacente deve ser configurado para permitir a autenticação básica. Consulte [Baixar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obter instruções sobre como habilitar o WinRM para autenticação básica.

> [!WARNING]
> Skype for Business As conexões do Conector Online serão rejeitadas a partir de 17 de maio de 2021. Entre em contato com o Suporte da Microsoft para ter ajuda e suporte para migrar para Teams Módulo do PowerShell.

## <a name="how-to-migrate"></a>Como migrar

Migrar do uso do Skype for Business Online para Teams módulo do PowerShell é fácil e simples. As etapas a seguir explicam como fazer isso.

1. Instale o módulo Teams do PowerShell mais recente. Para ver as etapas, [consulte Install Microsoft Teams Powershell](teams-powershell-install.md).
2. Desinstale Skype conector para Empresas Online. Para fazer isso, no Painel de Controle, vá para Programas e **Recursos,** selecione **Skype for Business Online, Windows PowerShell Módulo** e selecione **Desinstalar**.
3. Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de

    `SkypeOnlineConnector` ou `LyncOnlineConnector` `MicrosoftTeams` para .

    Por exemplo, altere `Import-Module -Name SkypeOnlineConnector` para `Import-Module -Name MicrosoftTeams` .

4. Ao usar Teams Módulo 2.0 do PowerShell ou posterior, atualize seus scripts que se referem `New-CsOnlineSession` a `Connect-MicrosoftTeams` . `Import-PsSession`não é mais necessário estabelecer uma sessão do PowerShell remoto Skype for Business Online, como é feito implícito ao usar `Connect-MicrosoftTeams` .

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>Suporte Online

Economize tempo iniciando sua solicitação de serviço online. Ajudaremos você a encontrar uma solução ou a conectá-lo ao suporte técnico.
1.  Vá para o centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) . Se você receber uma mensagem que diga que não tem permissão para acessar esta página ou executar essa ação, então você não é um administrador. Who tem permissões de administrador na minha empresa?
2.  Selecione a **opção Precisa de ajuda?** button.
3.  Na Necessidade **de ajuda?** painel, diga-nos com o que você precisa de ajuda e pressione Enter.
4.  Se os resultados não ajudarem, selecione **Contatar suporte**.
5.  Insira uma descrição do seu problema, confirme seu número de contato e endereço de email, selecione seu método de contato preferencial e selecione **Contact me**. O tempo de espera esperado é indicado no Need help? painel.

## <a name="related-topics"></a>Tópicos relacionados

[Instalar Microsoft Teams Powershell](teams-powershell-install.md)

[Gerenciar Teams com Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de versão do PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams de cmdlet](/powershell/teams/?view=teams-ps)

[Skype for Business de cmdlet](/powershell/skype/intro?view=skype-ps)
