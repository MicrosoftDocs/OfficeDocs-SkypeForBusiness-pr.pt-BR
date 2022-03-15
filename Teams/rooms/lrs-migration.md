---
title: Migrar dispositivos do Sistema de Sala do Lync para Salas do Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos do Sistema de Sala do Lync para usar o software Salas do Microsoft Teams software.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aae146767f66327e5678956a14dfe72d957a8164
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503508"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos LRS (Sistema de Sala do Lync) para Salas do Microsoft Teams

Os dispositivos do Sistema de Sala do Lync (LRS) com Skype software do Sistema de Sala Versão 1 (SRS v1) chegaram ao fim do suporte em 9 de outubro de [2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018). Isso significa que o software Sistemas de Salas Skype v1 não recebe mais atualizações ou correções de produtos. Os clientes que usam os dispositivos do Sistema de Salas do Lync, usando o software Sistema de Salas do Skype v1, são aconselhados a atualizar os dispositivos nas Salas do Microsoft Teams.

Salas do Microsoft Teams software funciona com Microsoft Teams além de serviços online e Skype for Business Server para reuniões e chamada em todos os Salas do Microsoft Teams com suporte.

Seus dispositivos existentes **podem** continuar a funcionar após o final do Skype de software do Sistema de Sala v1. No entanto, se esse software atingir um bug de software que precisa da Microsoft para liberar uma correção, ele não terá suporte. O SRS v1 usa o TLS 1.0/ 1.1 que será preterido pela Microsoft no futuro. Você pode saber mais sobre [como se preparar para o adiamento do TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). 

## <a name="which-devices-are-affected"></a>Quais dispositivos são afetados?

Aqui está a lista dos dispositivos afetados por essa alteração:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas SMART Room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opções de atualização

Há várias opções para atualizar o Lync Room Systems para a próxima geração de Salas do Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programa de troca de hardware crestron

A Crestron fornecerá uma atualização para o sistema [SR crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes do Sistema de Sala não Crestron Lync (por exemplo, Smart ou Polycom LRS). Consulte detalhes deste programa [aqui ou](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[Email](mailto:lrsupgrade@crestron.com) Suporte a LRS crestron.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Atualização do Crestron RL2 para Salas do Microsoft Teams

Os clientes existentes crestron RL2 (também chamados de Crestron RL200) podem adquirir um kit de atualização para atualizar o RL2 atual para RL3 usando um por um custo mínimo por dispositivo. Confira detalhes deste [programa aqui](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Atualização de sistemas smart room

Para clientes LRS INTELIGENTES, além do programa de troca de hardware crestron, o SMART também está trabalhando no fornecimento de uma solução para atualizar para Salas do Microsoft Teams. Essa atualização será fornecida pela SMART Technologies Inc. para o cliente sob suporte ao produto. Confira mais sobre isso [aqui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>O que você deve fazer?

Recomendamos que você planeje atualizar os dispositivos do Lync Room System para Salas do Microsoft Teams antes da deprecação do TLS 1.0/1.1 usando opções de atualização mencionadas acima. Além disso, você também pode considerar a substituição de dispositivos existentes por novos dispositivos certificados para Salas do Microsoft Teams. Consulte [Dispositivos de sala](https://aka.ms/roomdevices) para obter detalhes e também confira os requisitos [Salas do Microsoft Teams sala](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> Salas do Microsoft Teams software suporta o protocolo TLS 1.2 a partir de 14 de dezembro de 2018 com o aplicativo versão 4.0.64.0. Para clientes locais, a habilitação da comunicação por meio do TLS 1.2 para o Salas do Microsoft Teams Skype for Business Server requer a Atualização Cumulativa 9 (CU9) 2015 2015 ou a Atualização Cumulativa 1 do Skype for Business Server 2019 2019 (CU1). A alteração não deve afetar os clientes Skype for Business Online, pois as alterações do cliente são compatíveis com encaminhamento e compatibilidade com compatibilidade.