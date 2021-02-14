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
description: Saiba como usar os controles do PowerShell para gerenciar o Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852152"
---
# <a name="microsoft-teams-powershell-overview"></a>Visão geral do Microsoft Teams PowerShell

O Microsoft Teams PowerShell é um conjunto de cmdlets para gerenciar o Teams diretamente da linha de comando do PowerShell. Escrito no .NET Standard, o PowerShell do Teams funciona no PowerShell 5.1 no Windows, PowerShell 6.x e superior em todas as plataformas, incluindo o Shell de Nuvem do Azure.

Antes de começar a usar o PowerShell, você precisará [instalá-lo.](teams-powershell-install.md) 

> [!WARNING]
> Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell. Recomendamos usar o PowerShell 5.1 até que os problemas sejam resolvidos.

## <a name="releases"></a>Libera


O Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.

- **Disponibilidade Geral (GA)**: cmdlets prontos para produção, atualizados mensalmente.

- **Visualização Pública:** acesso antecipado aos recursos. Pode ser atualizado com mais frequência do que GA.

Para obter informações detalhadas sobre adições de recursos e melhorias para ambas as versões, leia as notas de versão [do PowerShell do Teams.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gerenciar equipes com o PowerShell

Você usará módulos do Teams PowerShell para gerenciar completamente o Teams:

- [Módulo do Microsoft Teams PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)o módulo do Teams PowerShell contém cmdlets para gerenciar equipes, chats e canais.

> [!NOTE]
> A versão [pública mais recente do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.

- [Skype for Business PowerShell Connector:](https://www.microsoft.com/download/details.aspx?id=39366)o conector do PowerShell do Skype for Business agora faz parte do módulo do PowerShell do Teams.

Para ver um guia completo sobre como gerenciar o Teams usando esses módulos, consulte [Gerenciar Equipes com o Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Tópicos relacionados

[Instalando o PowerShell do Teams](teams-powershell-install.md)

[Gerenciando equipes com o Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de versão do PowerShell do Teams](teams-powershell-release-notes.md)

[Referência de cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência de cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md)
