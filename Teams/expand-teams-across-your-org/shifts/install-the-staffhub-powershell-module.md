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
description: Saiba como instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub e mover suas equipes do StaffHub para o Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 52b4e0c41520468bc1e05734644d1beb05fed5be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905723"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

> [!IMPORTANT]
> A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).  

Use as etapas neste artigo para instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub. Você precisará disso para [mover suas equipes do StaffHub para o Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

1. Baixe o [módulo StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub).
2. Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.
    > [!NOTE]
    > Para obter a versão mais recente do Windows PowerShell, consulte [instalando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).
3. Execute o seguinte:

    ```PowerShell
    $ENV:PSModulePath
    ```
4. Verifique o caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem em seu computador antes de ir para a próxima etapa. Se estiverem faltando pastas, crie-as.
5. Execute o seguinte para permitir a instalação do módulo StaffHub PowerShell:

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. Execute o seguinte, em &lt;que&gt; Path é o caminho na saída da etapa 3. Por exemplo, o caminho pode se parecer como C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Certifique-se de executar cada comando separadamente.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Saia do Windows PowerShell.
8. Abra o Windows PowerShell 3,0 ou posterior como um administrador global e, em seguida, execute o seguinte:

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar-se ao módulo do Microsoft StaffHub PowerShell

1. Execute o seguinte:

    ```PowerShell
    Connect-StaffHub
    ```

2. Quando for solicitado, faça logon como um administrador global.

## <a name="related-topics"></a>Tópicos relacionados

- [Referência do Microsoft StaffHub PowerShell](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Mova as suas equipes do Microsoft StaffHub para o Shifts no Teams](move-staffhub-teams-to-shifts-in-teams.md)
