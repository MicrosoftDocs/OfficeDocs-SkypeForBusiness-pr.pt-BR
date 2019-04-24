---
title: Migrar dispositivos de sistema do Lync sala para salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos de sistema do Lync sala para usar o software de salas de equipes da Microsoft.
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219392"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrar dispositivos de sistema de sala do Lync (LRS) para salas de equipes da Microsoft

Dispositivos de sistema de sala do Lync (LRS) com o software do sistema de sala do Skype versão 1 (v1 SRS) atingiu o [fim do suporte em 9 de outubro de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Isso significa que o software do Skype sala sistemas v1 não são mais receberá quaisquer atualizações de produto ou correções mais. Clientes com dispositivos de sistema do Lync sala usando o software do sistema de sala Skype v1 recomenda-se para atualizar seus dispositivos para salas de equipes da Microsoft.

Dispositivos suportados de salas de equipes da Microsoft software funciona com o Microsoft Teams além do Skype para Business Server e Online services para reuniões e chamadas em todas as salas de equipes da Microsoft.

Seus dispositivos existentes **podem** continuar a funciona depois que o suporte a fim de software do sistema de sala Skype v1. No entanto, se esse software acessa um bug de software que precisa Microsoft para liberar uma correção, ela não será suportada. V1 SRS usa o protocolo TLS 1.0 / 1.1 que será preterido pela Microsoft no futuro. Você pode aprender mais sobre [Preparando para TLS 1.0/1.1 preterir](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Salas de equipes da Microsoft está adicionando suporte a TLS 1.2 e continuará inserido antigas 31 de outubro de 2018. Skype para negócios local os clientes não devem desabilitar TLS 1.0/1.1 até que as salas de equipes da Microsoft anuncia o suporte para TLS 1.2 independentemente diretrizes gerais sobre preterir TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Quais dispositivos são afetados?

Aqui está uma lista dos dispositivos que são afetados por essa alteração:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemas de sala inteligentes](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opções de atualização

Há várias opções para atualizar o Lync sistemas de sala para a próxima geração de salas de equipes da Microsoft.

### <a name="crestron-hardware-trade-in-program"></a>Programa de trade-in de hardware Crestron

Crestron fornecerá uma atualização para o [sistema Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes não-Crestron o sistema do Lync sala (por exemplo inteligente ou Polycom LRS). Ver os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Suporte de Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Atualização de Crestron RL2 para salas de equipes da Microsoft

Os clientes existentes do Crestron RL2 (também conhecido como Crestron RL200) podem adquirir um kit de atualização para atualizar RL2 atual para RL3 usando um para um custo mínimo por dispositivo. Ver os detalhes deste programa [aqui](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Atualização de sistemas de sala inteligente

Para clientes inteligentes LRS, além do programa de trade-in de hardware Crestron, inteligente também está trabalhando no fornecimento de uma solução para atualizar para o Microsoft equipes salas. Essa atualização será fornecida pelo Inc. de tecnologias inteligentes ao cliente em suporte ao produto. Consulte mais informações sobre esta [aqui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>O que você deve fazer?

Recomendamos que você planeja atualizar dispositivos de sistema do Lync sala salas de equipes da Microsoft antes de preterir TLS 1.0/1.1 usando as opções de atualização mencionadas acima. Além disso, você também pode considerar a substituição de dispositivos existentes com novos dispositivos certificados para salas de equipes da Microsoft. Consulte [dispositivos de sala](https://aka.ms/roomdevices) para obter detalhes e também dar uma olhada em [requisitos de salas de equipes da Microsoft](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Funcionalidade de toque e whiteboard ainda não é suportada em salas de equipes da Microsoft. Suporte de toque e quadro de comunicações está atualmente planejado para salas de equipes da Microsoft e 2019 será adicionado.

> [!NOTE]
> Software de salas de equipes da Microsoft suporta o protocolo TLS 1.2 a partir de 14 de dezembro de 2018 com a versão de aplicativo 4.0.64.0. Para clientes de local, permitindo a comunicação sobre TLS 1.2 para salas de equipes da Microsoft requer Skype para Business Server 2015 atualização cumulativa 9 (CU9) ou Skype para Business Server 2019 atualização cumulativa 1 (CU1). A alteração não deve afetar Skype para clientes corporativos Online conforme as alterações de cliente são frente e para trás compatível.
