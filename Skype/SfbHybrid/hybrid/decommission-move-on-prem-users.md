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
description: Mova os usuários antes de desmantelar um ambiente local do Skype for Business.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656667"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Mover usuários necessários antes de desmantelar seu ambiente local

Este artigo descreve como mover os usuários necessários para a nuvem da Microsoft antes de desmantelar seu ambiente local do Skype for Business. Esta é a etapa 1 das etapas a seguir para desmantelar seu ambiente local:

- **Etapa 1. Mova todos os usuários necessários do local para o online.** (Este artigo)

- Etapa 2. [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- Etapa 3. [Mover pontos de extremidade de aplicativo híbrido de local para online](decommission-move-on-prem-endpoints.md).

- Etapa 4. [Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Mover todos os usuários necessários do local para a nuvem

Todos os usuários que você continuará a usar depois de concluir a migração devem primeiro ser movidos do local para a nuvem. Você move os usuários usando as ferramentas de administração locais. Para obter detalhes, [consulte Mover usuários entre o local e a nuvem.](move-users-between-on-premises-and-cloud.md)

Embora seja possível que os usuários com contas locais do Skype for Business Server usem o Teams, esses usuários não têm a funcionalidade completa do Teams. Esses usuários não podem interoperar ou federar com qualquer outro usuário que ainda esteja usando o Skype for Business (online ou local). Esses usuários também não podem receber chamadas PSTN em seu cliente do Teams. Portanto, você deve mover esses usuários para online. Esta etapa também garante que todos os contatos ou reuniões criados no Skype for Business Server sejam migrados para o Teams.

Para verificar se há outros usuários em sua implantação local, execute o cmdlet a seguir em uma janela do PowerShell do Skype for Business Server.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Se algum usuário for retornado, revise a saída para determinar se alguma conta deve ser movida para a nuvem e, para esses usuários, siga as etapas [aqui](move-users-between-on-premises-and-cloud.md). Para contas de usuário que não são mais necessárias, execute o seguinte cmdlet do PowerShell do Skype for Business Server:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Executar Disable-CsUser removerá todos os atributos do Skype for Business para todos os usuários que atenderem aos critérios de filtro. Antes de prosseguir, confirme se essas contas não são mais necessárias para avançar.


Agora você está pronto para [desabilitar sua configuração híbrida.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Confira também

- [Desativar o ambiente local do Skype for Business](decommission-on-prem-overview.md)

- [Desabilitar sua configuração híbrida](cloud-consolidation-disabling-hybrid.md)

- [Mover pontos de extremidade de aplicativo híbrido do local para o online](decommission-move-on-prem-endpoints.md)

- [Remover a implantação local do Skype for Business](decommission-remove-on-prem.md)




