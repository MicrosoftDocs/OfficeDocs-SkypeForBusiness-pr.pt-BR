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
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852152"
---
# <a name="microsoft-teams-powershell-overview"></a>Visão geral do Microsoft Teams PowerShell

O Microsoft Teams PowerShell é um conjunto de cmdlets para o gerenciamento de equipes diretamente da linha de comando do PowerShell. Escrito em .NET Standard, o PowerShell do teams funciona no PowerShell 5,1 no Windows, PowerShell 6. x e superior em todas as plataformas, incluindo o Shell de nuvem do Azure.

Antes de começar a usar o PowerShell, você precisará [instalá-lo](teams-powershell-install.md). 

> [!WARNING]
> Há problemas conhecidos com o PowerShell 7 e o Teams PowerShell. Recomendamos usar o PowerShell 5,1 até que os problemas sejam resolvidos.

## <a name="releases"></a>Imprensa


O Microsoft Teams PowerShell está disponível na [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) em dois tipos de versão.

- **Disponibilidade geral (GA)** : cmdlets prontos para produção, atualizados mensalmente.

- **Visualização pública** : acesso antecipado aos recursos. Pode ser atualizado com mais frequência do que o GA.

Para obter informações detalhadas sobre adições de recursos e melhorias para ambos os lançamentos, leia as [notas de versão do teams PowerShell](teams-powershell-release-notes.md).


## <a name="manage-teams-with-powershell"></a>Gerenciar equipes com o PowerShell

Você usará os módulos do teams PowerShell para gerenciar totalmente as equipes:

- [Módulo do PowerShell do Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/): o módulo do PowerShell do teams contém cmdlets para gerenciar equipes, chats e canais.

> [!NOTE]
> A versão mais recente do [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada ao conector do Skype for Business Online, fornecendo um único módulo para gerenciamento do teams PowerShell.

- [Conector do PowerShell do Skype for Business](https://www.microsoft.com/download/details.aspx?id=39366): o conector do PowerShell do Skype for Business agora faz parte do módulo do teams PowerShell.

Para obter um guia completo sobre o gerenciamento de equipes usando esses módulos, consulte [gerenciar equipes com o PowerShell do teams](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Tópicos relacionados

[Instalando o Microsoft Teams PowerShell](teams-powershell-install.md)

[Gerenciando equipes com o PowerShell do teams](teams-powershell-managing-teams.md)

[Notas de versão do teams PowerShell](teams-powershell-release-notes.md)

[Referência do cmdlet do Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referência do cmdlet do Skype for Business](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar as funções de administrador do Microsoft Teams para gerenciar o Microsoft Teams](using-admin-roles.md)
