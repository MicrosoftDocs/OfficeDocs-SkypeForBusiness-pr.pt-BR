---
title: Instalar a versão de pré-lançamento do módulo do teams PowerShell
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Siga estas etapas para instalar a versão de pré-lançamento do módulo do teams PowerShell da Galeria de teste do PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321764"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Instalar a versão de pré-lançamento do módulo do teams PowerShell

Este artigo descreve como instalar a versão de pré-lançamento mais recente do módulo do teams PowerShell da [Galeria de teste do PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Você precisará da versão de pré-lançamento do módulo do teams PowerShell nos cenários em que cmdlets para gerenciar um recurso do Teams não são compatíveis com a versão geralmente disponível do módulo e estão disponíveis apenas na versão de pré-lançamento.

Use estas etapas para instalar a versão de pré-lançamento mais recente do módulo do teams PowerShell a partir da Galeria de teste do PowerShell.

> [!NOTE]
> Não instale o módulo Teams PowerShell da Galeria de teste do PowerShell lado a lado com uma versão do módulo da [Galeria pública do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Siga estas etapas para desinstalar primeiro o módulo do teams PowerShell da galeria do PowerShell público e instalar a versão mais recente do módulo da Galeria de teste do PowerShell.

1. Feche todas as sessões existentes do PowerShell.
2. Inicie uma nova instância do módulo do Windows PowerShell.
3. Execute o seguinte para desinstalar o módulo do teams PowerShell da galeria do PowerShell público:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Feche todas as sessões existentes do PowerShell.
5. Inicie o módulo do Windows PowerShell novamente e, em seguida, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Execute o seguinte para instalar o módulo do PowerShell mais recente do teams a partir da Galeria de teste do PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Atualize para a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell

Se você já tiver instalado o módulo do teams PowerShell da Galeria de teste do PowerShell, use as etapas a seguir para atualizar para a versão mais recente.

1. Feche todas as sessões existentes do PowerShell.
2. Inicie uma nova instância do módulo do Windows PowerShell.
3. Execute o seguinte para atualizar a versão atualmente instalada do módulo do teams PowerShell a partir da Galeria de teste do PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
