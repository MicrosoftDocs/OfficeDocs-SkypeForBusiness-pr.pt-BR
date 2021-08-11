---
title: Mover usuários para a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Mover usuários antes de desmantelar um ambiente Skype for Business local.
ms.openlocfilehash: 44092460fa1db0664fe95b12cc99f3488544dc0ad049d75d56074e6bf0873c60
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292359"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Mover usuários necessários antes de desmantelar seu ambiente local

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo descreve como mover os usuários necessários para a nuvem da Microsoft antes de desativá-lo Skype for Business ambiente local. Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:

- **Etapa 1. Mova todos os usuários necessários do local para o online.** (Este artigo)

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- Etapa 3. [Migrar pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md). Esteja ciente de que quaisquer pontos de extremidade de aplicativo híbrido existentes não serão descobertos entre o momento em que você executar a Etapa 2 acima até concluir esta etapa. Você deve planejar fazer as etapas 2 e 3 na mesma janela de manutenção.

- Etapa 4. [Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos os usuários necessários do local para a nuvem

Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem. Você move os usuários usando as ferramentas de administração locais. Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)

Embora seja possível que os usuários com contas Skype for Business Server locais usem Teams, esses usuários não têm a funcionalidade completa do Teams. Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando Skype for Business (online ou local). Esses usuários também não podem receber chamadas PSTN em seu Teams cliente. Portanto, você deve mover esses usuários para online. Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para Teams.

Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela Skype for Business Server PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md). Para contas de usuário que não são mais necessárias, execute o seguinte Skype for Business Server cmdlet do PowerShell:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Executar Disable-CsUser removerá todos os Skype for Business para todos os usuários que atenderem aos critérios de filtro. Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.


Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Confira também

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md)

- [Remover a implantação local do Skype for Business](decommission-remove-on-prem.md)




