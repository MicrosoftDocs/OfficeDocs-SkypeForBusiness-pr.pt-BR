---
title: Desativar o ambiente local do Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como desmantelar seu ambiente local Skype for Business ambiente.
ms.openlocfilehash: 53ed840c89ab02eff87607f0bdffebcef94fd4e2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583385"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Desativar o ambiente local do Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Se sua organização usa Teams com uma implantação local do Skype for Business Server, você pode migrar esses ambientes totalmente para a nuvem e, em seguida, retirar sua implantação local do Skype for Business Server. 

> [!NOTE]
> Antes de desmantelar seu ambiente [](configure-hybrid-connectivity.md) local, você deve configurar a conectividade híbrida entre sua implantação local e Microsoft 365. Depois de configurar a conectividade híbrida, você pode migrar usuários para a nuvem, ao migrar suas reuniões do local e migrar quaisquer contatos do Skype for Business Server para o Teams. Configurar a conectividade híbrida é uma etapa necessária para migrar os usuários do local para a nuvem e garantir a funcionalidade Teams completa.

Para concluir sua movimentação do local para a nuvem e desativá-lo Skype for Business Server ambiente local, você deve concluir as seguintes etapas na seguinte ordem:

- **Etapa 1.** [Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).

- **Etapa 2.** [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- **Etapa 3.** [Mover pontos de extremidade de aplicativo híbrido de local para online](decommission-move-on-prem-endpoints.md).

- **Etapa 4.** [Remova sua implantação local Skype for Business .](decommission-remove-on-prem.md)

