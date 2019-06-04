---
title: Instalar o módulo PowerShell do StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681877"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

> [!IMPORTANT]
> A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado. Estamos criando recursos de StaffHub no Microsoft Teams. Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo. O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019. Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams. Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).  

Use as etapas neste artigo para instalar e se conectar ao módulo do PowerShell do Microsoft StaffHub. Você precisará disso para gerenciar o StaffHub usando o PowerShell e para mover suas equipes do StaffHub para o Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instalar o módulo PowerShell do Microsoft PowerHub

1. Baixe o [módulo StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Abra o Windows PowerShell 3,0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e selecione **Executar como administrador**.
3. Execute o seguinte:

    ```
    $ENV:PSModulePath
    ```
    

4. Verifique o caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem em seu computador antes de ir para a próxima etapa. Se estiverem faltando pastas, crie-as.
5. Execute o seguinte para permitir a instalação do módulo StaffHub do PowerShell:

```
Set-ExecutionPolicy RemoteSigned
```

6. Execute o seguinte, em &lt;que&gt; Path é o caminho na saída da etapa 2. Por exemplo, o caminho pode se parecer como C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar-se ao módulo do Microsoft StaffHub PowerShell

1. Execute o seguinte:

    ```
    Connect-StaffHub
    ```

2. Quando for solicitado, faça logon como um administrador global.

## <a name="related-topics"></a>Tópicos relacionados

- [Referência do Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mova as suas equipes do Microsoft StaffHub para Turnos no Teams](move-staffhub-teams-to-shifts-in-teams.md)
