---
title: Instalar o módulo PowerShell do StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464660"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

> [!IMPORTANT]
> A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).  

Use as etapas neste artigo para instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub. Você precisará disso para gerenciar o StaffHub usando o PowerShell e para mover suas equipes do StaffHub para o Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

1. Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.
    > [!NOTE]
    > Para obter a versão mais recente do Windows PowerShell, consulte Instalando o [Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Execute o seguinte para instalar a versão estável atual do módulo StaffHub PowerShell:

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    Você só poderá executar esse comando se precisar instalar a versão mais recente, que pode ter mais instabilidade do que a versão estável atual:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Se você receber um erro durante a instalação da versão mais recente com mais instabilidades, poderá executar:`Install-Module PowershellGet -Force`

3. Você pode ver a mensagem de aviso:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Digite `Y` e clique `Enter`em.
 
4. Saia do Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar-se ao módulo do Microsoft StaffHub PowerShell

1. Execute o seguinte:

    ```
    Connect-StaffHub
    ```

2. Quando for solicitado, faça logon como um administrador global.

## <a name="related-topics"></a>Tópicos relacionados

- [Referência do Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mova as suas equipes do Microsoft StaffHub para Turnos no Teams](move-staffhub-teams-to-shifts-in-teams.md)
