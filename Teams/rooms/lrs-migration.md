---
title: Migrar dispositivos do Sistema de Salas do Lync para Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos do Sistema de Salas do Lync para usar o software Salas do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662616"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos do Lync Room System (LRS) para salas do Microsoft Teams

Os dispositivos Lync Room System (LRS) com o software Skype Room System versão 1 (SRS v1) chegaram ao fim do suporte em 9 de outubro de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Isso significa que o software Sistemas de Salas Skype v1 não recebe mais atualizações ou correções de produtos. Os clientes que usam os dispositivos do Sistema de Salas do Lync, usando o software Sistema de Salas do Skype v1, são aconselhados a atualizar os dispositivos nas Salas do Microsoft Teams.

O software Salas do Microsoft Teams funciona com o Microsoft Teams, além dos serviços Do Skype for Business Server e Online para reuniões e chamadas em todos os dispositivos com suporte nas Salas do Microsoft Teams.

Seus dispositivos **existentes podem** continuar a funcionar após o fim do suporte ao software Skype Room System v1. No entanto, se esse software atingir um bug de software que precisa que a Microsoft libere uma correção, ele não terá suporte. O SRS v1 usa tLS 1.0/ 1.1, que será preterido pela Microsoft no futuro. Você pode saber mais sobre como se preparar para a [depreciação do TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Quais dispositivos são afetados?

Aqui está a lista dos dispositivos afetados por essa alteração:

- RL daÇanúm
- [RL2 DaL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas smart room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opções de atualização

Há várias opções para atualizar o Lync Room Systems para a próxima geração de Salas do Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de trade-in de hardware DaÇanron

A Seniorron fornecerá uma atualização para o sistema [Sr. DaÇanureron ou](https://www.crestron.com/products/featured-solutions/crestron-sr) equivalente para todos os clientes do Sistema de Sala Não-Autorron Lync (por exemplo, Smart ou Polycom LRS). Veja os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Suporte a LRS da LRS DaÇanron.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Atualização da RL2 para Salas do Microsoft Teams

Os clientes existentes da Crestron RL2 (também conhecido como RL200 DaL200) podem adquirir um kit de atualização para atualizar RL2 para RL3 atual usando um custo mínimo por dispositivo. Veja os detalhes deste programa [aqui.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Atualização do smart room systems

Para clientes smart LRS, além do programa de troca de hardware DaLron, o SMART também está trabalhando no fornecimento de uma solução para atualizar para salas do Microsoft Teams. Esta atualização será fornecida pela SMART Technologies Inc. para o cliente sob suporte do produto. Veja mais sobre isso [aqui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>O que você deve fazer?

Recomendamos que você planeje atualizar os dispositivos do Sistema de Salas do Lync para salas do Microsoft Teams antes da depreciação do TLS 1.0/1.1 usando as opções de atualização mencionadas acima. Além disso, você também pode considerar substituir dispositivos existentes por novos dispositivos certificados para Salas do Microsoft Teams. Consulte [os dispositivos de](https://aka.ms/roomdevices) sala para obter detalhes e também dê uma olhada nos requisitos de Salas do Microsoft [Teams.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> O software Microsoft Teams Rooms oferece suporte ao protocolo TLS 1.2 a partir de 14 de dezembro de 2018 com a versão do aplicativo 4.0.64.0. Para clientes locais, a habilitação da comunicação por meio do TLS 1.2 para Salas do Microsoft Teams requer a Atualização Cumulativa 9 (CU9) do Skype for Business Server 2015 ou a Atualização Cumulativa 1 (CU1) do Skype for Business Server 2019. A alteração não deve afetar os clientes do Skype for Business Online, uma vez que as alterações do cliente estão em conformidade com o encaminhamento e com compatibilidade com compatibilidade.
