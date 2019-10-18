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
description: Saiba como instalar e se conectar à versão de pré-lançamento do módulo do PowerShell do Microsoft StaffHub.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569205"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

> [!IMPORTANT]
> A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).  

Use as etapas neste artigo para instalar e se conectar à versão de pré-lançamento do módulo Microsoft StaffHub PowerShell. Você precisará disso para [mover suas equipes do StaffHub para o Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Instalar a versão de pré-lançamento do módulo do PowerShell Microsoft StaffHub

1. Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.
    > [!NOTE]
    > Para obter a versão mais recente do Windows PowerShell, consulte [instalando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Execute o seguinte para instalar a versão de pré-lançamento do módulo StaffHub PowerShell:

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Você pode ver a mensagem de aviso:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Digite `Y`e clique em `Enter`.
 
4. Saia do Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar-se ao módulo do Microsoft StaffHub PowerShell

1. Execute o seguinte:

    ```
    Connect-StaffHub
    ```

2. Quando for solicitado, faça logon como um administrador global.

## <a name="related-topics"></a>Tópicos relacionados

- [Referência do Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mova as suas equipes do Microsoft StaffHub para o Shifts no Teams](move-staffhub-teams-to-shifts-in-teams.md)
