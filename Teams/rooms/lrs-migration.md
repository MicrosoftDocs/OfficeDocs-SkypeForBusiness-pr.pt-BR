---
title: Migrar dispositivos do sistema de sala do Lync para salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos do sistema de sala do Lync para usar o software de salas do Microsoft Teams.
ms.openlocfilehash: 2a324e426368722cf261554b09298f098644d5ba
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268730"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos do Lync Room System (LRS) para salas do Microsoft Teams

Os dispositivos do sistema de salas do Lync (LRS) com o software Skype V1 (versão 1 do Skype v1) chegaram [ao fim do suporte em 9 de outubro de 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018). Isso significa que o software Sistemas de Salas Skype v1 não recebe mais atualizações ou correções de produtos. Os clientes que usam os dispositivos do Sistema de Salas do Lync, usando o software Sistema de Salas do Skype v1, são aconselhados a atualizar os dispositivos nas Salas do Microsoft Teams.

O software de salas Microsoft Teams funciona com o Microsoft Teams, além do Skype for Business Server e serviços online para reuniões e chamadas em todos os dispositivos compatíveis com as salas do Microsoft Teams.

Seus dispositivos existentes **podem** continuar a funcionar após o término do suporte do software sistema de sala do Skype v1. No entanto, se este software chegar a um bug de software que precisa da Microsoft para lançar uma correção, ele não será compatível. O SRS v1 usa TLS 1.0/1,1, que será preterido pela Microsoft no futuro. Você pode saber mais sobre como se [preparar para a substituição de TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). 

## <a name="which-devices-are-affected"></a>Quais dispositivos são afetados?

Veja a seguir a lista dos dispositivos afetados por essa alteração:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de sala inteligente](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opções de atualização

Há várias opções para atualizar sistemas de sala do Lync para a próxima geração de salas do Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de troca de hardware Crestron

O Crestron fornecerá uma atualização para o [sistema CRESTRON Sr](https://www.crestron.com/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes do sistema de salas não Crestron do Lync (por exemplo, para usuários inteligentes ou Polycom). Veja os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, -->[mensagem de email](mailto:lrsupgrade@crestron.com) Suporte LRS Crestron.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Atualização do RL2 Crestron para salas do Microsoft Teams

Os clientes Crestron RL2 (também chamados de Crestron RL200) podem adquirir um kit de atualização para atualizar os RL2 atuais para o RL3 usando um por um custo mínimo por dispositivo. Veja os detalhes deste programa [aqui](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Atualização dos sistemas da sala inteligente

Para clientes do SMART LRS, além do programa de troca de hardware do Crestron, o SMART também está trabalhando para fornecer uma solução para fazer a atualização para salas do Microsoft Teams. Esta atualização será fornecida pela SMART Technologies Inc. para o cliente em suporte a produtos. Para saber mais [sobre isso,](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)acesse isso.


## <a name="what-should-you-do"></a>O que você deve fazer?

Recomendamos que você planeje atualizar os dispositivos do sistema de sala do Lync para salas do Microsoft Teams antes da substituição do TLS 1.0/1.1 usando as opções de atualização mencionadas acima. Além disso, você também pode considerar a substituição de dispositivos existentes por novos dispositivos certificados para salas do Microsoft Teams. Consulte [dispositivos da sala](https://aka.ms/roomdevices) para obter detalhes e também dê uma olhada nos [requisitos de salas do Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> O software de salas Microsoft Teams dá suporte ao protocolo TLS 1,2 a partir de 14 de dezembro de 2018 com a versão de aplicativo 4.0.64.0. Para clientes locais, a habilitação da comunicação com o TLS 1,2 para salas do Microsoft Teams requer o Skype for Business Server 2015 atualização cumulativa 9 (CU9) ou a atualização cumulativa 1 do Skype for Business Server 2019 (CU1). A alteração não deve afetar os clientes do Skype for Business Online, pois as alterações do cliente são compatíveis com versões anteriores e posteriores.
