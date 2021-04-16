---
title: Visão geral do Microsoft Teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a usar os controles do PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768350"
---
# <a name="microsoft-teams-powershell-overview"></a>Visão geral do Microsoft Teams PowerShell

O Microsoft Teams PowerShell é um conjunto de cmdlets para gerenciar o Teams diretamente da linha de comando do PowerShell. Escrito no .NET Standard, o PowerShell do Teams funciona no PowerShell 5.1 no Windows, PowerShell 6.x e superior em todas as plataformas, incluindo o Azure Cloud Shell.

Antes de começar a usar o PowerShell, você precisará [instalá-lo](teams-powershell-install.md). 

> [!WARNING]
> Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell. Recomendamos usar o PowerShell 5.1 até que os problemas sejam resolvidos.

## <a name="releases"></a>Versões


O Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.

- **Disponibilidade Geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.

- **Visualização Pública**: Acesso antecipado aos recursos. Pode ser atualizado com mais frequência do que GA.

Para obter informações detalhadas sobre adições de recursos e melhorias para ambas as versões, leia as notas de versão [do Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gerenciar o Teams com o PowerShell

Você usará módulos do Teams PowerShell para gerenciar totalmente o Teams:

- [Módulo do PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): o módulo do Teams PowerShell contém cmdlets para gerenciar equipes, chat e canais.

> [!NOTE]
> A [versão pública do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) versão 2.0 ou superior inclui todos os cmdlets do Conector do Skype for Business Online, fornecendo um único módulo para o gerenciamento do Teams PowerShell.

- [Conector do PowerShell do Skype for Business](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): O conector do PowerShell do Skype for Business agora faz parte do módulo do Teams PowerShell.

Para ver um guia completo sobre como gerenciar o Teams usando esses módulos, consulte [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Tópicos relacionados

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Gerenciando o Teams com o Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md)
