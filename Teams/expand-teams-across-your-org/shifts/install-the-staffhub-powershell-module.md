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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142029"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

> [!IMPORTANT]
> A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).  

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
- [Mova as suas equipes do Microsoft StaffHub para Turnos no Teams](move-staffhub-teams-to-shifts-in-teams.md)
