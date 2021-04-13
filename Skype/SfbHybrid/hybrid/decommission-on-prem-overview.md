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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções sobre como desmantelar seu ambiente local do Skype for Business.
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656677"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Desativar o ambiente local do Skype for Business

Se sua organização usa o Teams ou o Skype for Business Online com uma implantação local do Skype for Business Server, você pode migrar esses ambientes totalmente para a nuvem e, em seguida, retirar sua implantação local do Skype for Business Server. 

> [!NOTE]
> Antes de desmantelar seu ambiente [](configure-hybrid-connectivity.md) local, você deve configurar a conectividade híbrida entre sua implantação local e o Microsoft 365. Depois de configurar a conectividade híbrida, você pode migrar usuários para a nuvem, ao migrar suas reuniões do local e migrar quaisquer contatos do Skype for Business Server para o Teams. Configurar a conectividade híbrida é uma etapa necessária para migrar os usuários do local para a nuvem e garantir a funcionalidade completa do Teams.

Para concluir sua movimentação do local para a nuvem e desmantelar seu ambiente local do Skype for Business Server, você deve concluir as seguintes etapas na seguinte ordem:

- **Etapa 1.** [Mova todos os usuários necessários do local para o online](decommission-move-on-prem-users.md).

- **Etapa 2.** [Desabilite sua configuração híbrida](cloud-consolidation-disabling-hybrid.md).

- **Etapa 3.** [Mover pontos de extremidade de aplicativo híbrido de local para online](decommission-move-on-prem-endpoints.md).

- **Etapa 4.** [Remova sua implantação local do Skype for Business.](decommission-remove-on-prem.md)

