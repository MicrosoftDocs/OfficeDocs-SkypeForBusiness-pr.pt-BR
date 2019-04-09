---
title: Instale o módulo StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como instalar e conectar ao módulo do Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555125"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Instale o módulo do Microsoft StaffHub PowerShell

> [!IMPORTANT]
> A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada. Estamos compilando recursos StaffHub em Teams da Microsoft. Hoje, equipes inclui o aplicativo desloca para o gerenciamento de agenda e recursos adicionais serão distribuir ao longo do tempo. StaffHub irá parar de funcionar para todos os usuários em 1 de outubro de 2019. Qualquer pessoa que tenta abrir StaffHub será mostrada uma mensagem direcionando-os para baixar as equipes. Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).  

Use as etapas neste artigo para instalar e conectar ao módulo do Microsoft StaffHub PowerShell. Você precisará isso para gerenciar StaffHub usando o PowerShell e mover suas equipes StaffHub a Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Instale o módulo do Microsoft StaffHub PowerShell

1. Baixe o [módulo de StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Abra o Windows PowerShell 3.0 ou posterior como administrador. Para fazer isso, clique em **Iniciar**, digite o **Windows PowerShell**, com o botão direito **Do Windows PowerShell**e, em seguida, selecione **Executar como administrador**.
3. Execute o seguinte:

    ```
    $ENV:PSModulePath
    ```

4. O caminho da pasta na saída e certifique-se de que todas as pastas no caminho existem no seu computador antes de ir para a próxima etapa. Se não existirem pastas, criá-los.
5. Execute o seguinte, onde &lt;caminho&gt; é o caminho na saída da etapa 2. Por exemplo, o caminho pode parecer com C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Conectar ao módulo do Microsoft StaffHub PowerShell

1. Execute o seguinte:

    ```
    Connect-StaffHub
    ```

2. Quando solicitado, faça login como um administrador de global.

## <a name="related-topics"></a>Tópicos relacionados

- [Referência do Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Mova as suas equipes do Microsoft StaffHub para Turnos no Teams](move-staffhub-teams-to-shifts-in-teams.md)
