---
title: Migrar dispositivos de sistema do Lync sala ao sistema de sala Skype versão 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos de sistema do Lync sala para usar o software do sistema de sala Skype v2.
ms.openlocfilehash: 9436c5a843f21b9913c0dbcbed6e62df8ef62ce2
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729404"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Migrar dispositivos de sistema de sala do Lync (LRS) para o sistema de sala Skype v2 
Dispositivos de sistema de sala do Lync (LRS) com o software do sistema de sala do Skype versão 1 (v1 SRS) atingiu o [fim do suporte em 9 de outubro de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Isso significa que o software do Skype sala sistemas v1 não são mais receberá quaisquer atualizações de produto ou correções mais. Clientes com dispositivos de sistema do Lync sala usando o software do sistema de sala Skype v1 recomenda-se para atualizar seus dispositivos para o sistema de sala Skype v2 (versão 2 SRS).

Software Skype sala sistema versão 2 (v2 SRS) funciona com Microsoft Teams além do Skype para Business Server e Online services para reuniões e chamadas em todos os dispositivos do SRS v2 suportados.

Seus dispositivos existentes **podem** continuar a funciona depois que o suporte a fim de software do sistema de sala Skype v1. No entanto, se esse software acessa um bug de software que precisa Microsoft para liberar uma correção, ela não será suportada. V1 SRS usa o protocolo TLS 1.0 / 1.1 que será preterido pela Microsoft no futuro. Você pode aprender mais sobre [Preparando para TLS 1.0/1.1 preterir](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Skype sala sistema V2 está adicionando suporte a TLS 1.2 e continuará inserido antigas 31 de outubro de 2018. Skype para negócios nos clientes do local não deve desabilitar o TLS 1.0/1.1 que suportem a annouces Skype sala sistema V2 para TLS 1.2 independentemente diretrizes gerais sobre preterir TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Quais dispositivos são afetados?
Aqui está uma lista dos dispositivos que são afetados por essa alteração:
- [Sistemas de sala inteligentes](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>Opções de atualização
Há várias opções para atualizar o Lync sistemas de sala para a próxima geração de sistemas de sala Skype (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Programa de trade-in de hardware Crestron
Crestron fornecerá uma atualização para o [sistema Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes do sistema de sala do Lync não-Crestron. Ver os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [email](mailto:lrsupgrade@crestron.com) suporte Crestron LRS.  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a>Atualização de Crestron RL2 para V2 SRS
Os clientes existentes do Crestron RL2 (também conhecido como Crestron RL200) podem adquirir um kit de atualização para atualizar RL2 atual para RL3 usando um para um custo mínimo por dispositivo. Ver os detalhes deste programa [aqui](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT). 


### <a name="smart-room-systems-upgrade"></a>Atualização de sistemas de sala inteligente 
Para clientes inteligentes LRS, além de Crestron programa de trade-in de hardware, o Microsoft e inteligente também estão trabalhando em fornecendo uma solução para atualizar para o sistema de sala Skype v2. Essa atualização será fornecida pelo Inc de tecnologias inteligentes. Consulte mais informações sobre esta [aqui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).

  
Para usar essa opção, no entanto, os clientes devem additionaly compre um adaptador de [Compartilhamento de tela Logitech](https://www.logitech.com/en-us/product/screen-share) . Microsoft fornecerá instruções sobre como usar este adaptador com o software do sistema de sala Skype v2. 


Procure instruções de atualização nesta página em breve. 
  
### <a name="summary-of-upgrade-options"></a>Resumo das opções de atualização
Esta tabela lista de resumo de todas as opções disponíveis para os dispositivos LRS existentes:

## <a name="what-should-you-do"></a>O que você deve fazer?
Recomendamos que você planeja atualizar dispositivos de sistema do Lync sala para sistemas de sala Skype v2 antes de preterir TLS 1.0/1.1 usando as opções de atualização mencionadas acima. Além disso, você também pode considerar a substituição de dispositivos existentes com novos dispositivos certificados para o SRS v2. Consulte [dispositivos de sala](https://aka.ms/roomdevices) para obter detalhes e também dar uma olhada em [sistemas de sala Skype v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Funcionalidade de toque e whiteboard ainda não é suportada no sistema de sala Skype v2. Suporte de toque e quadro de comunicações está no registro acumulado para o sistema de sala Skype v2 e será adicionado em CY2019 de S1.

> [!NOTE]
> Software de Skype sala sistema V2 suporta o protocolo TLS 1.2 desde 14 de dezembro de 2018 com a versão de aplicativo 4.0.64.0. Nos clientes do local, permitindo communciation sobre TLS 1.2 para Skype sala sistema V2 requer Skype para Business Server 2015 Cummulative Update 9 (CU9) ou Skype para divisões Server 2019 Cummulative Update 1 (CU1). A alteração deve ser independente para Skype para clientes corporativos Online como as alterações do cliente para a frente e para trás compatível. 
