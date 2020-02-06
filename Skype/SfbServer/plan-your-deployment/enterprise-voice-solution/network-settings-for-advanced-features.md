---
title: Configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Aprender sobre regiões de rede, sites de rede e sub-redes IP. Todas elas devem ser configuradas para implantar o plano de bypass de mídia no Skype for Business, planejar o controle de admissão de chamadas no Skype for Business Server) ou planejar serviços de emergência no Skype for Business Server no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 25987630ae2082ca8805d87a988760296637d3f7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802591"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Configurações de rede para os recursos avançados de voz empresarial no Skype for Business Server

Aprender sobre regiões de rede, sites de rede e sub-redes IP. Todas elas devem ser configuradas para implantar o [plano de bypass de mídia no Skype for Business](media-bypass.md), [planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md)ou [planejar serviços de emergência no Skype for Business](emergency-services.md) Server no Skype for Business Server Enterprise Voice.

O Skype for Business Server tem três recursos avançados do Enterprise Voice: [planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md), [planejar serviços de emergência no Skype for Business Server](emergency-services.md)e [planejar o bypass de mídia no Skype for Business](media-bypass.md). Esses recursos compartilham determinados requisitos de configuração para regiões de rede, sites de rede e Associação de cada sub-rede na topologia do servidor do Skype for Business com um site de rede.

Este tópico fornece uma visão geral dos requisitos de configuração que são comuns a todos esses três recursos avançados do Enterprise Voice.

## <a name="network-regions"></a>Regiões de Rede

Uma região de rede é um hub de rede ou backbone de rede usada somente na configuração do serviço de controle de admissão de chamadas (CAC),  E9-1-1 e bypass de mídia.

> [!NOTE]
> As regiões de rede não são iguais às regiões de conferência discada do Skype for Business Server, que são necessárias para associar números de acesso de conferência discada com um ou mais planos de discagem do Skype for Business Server. Para obter detalhes sobre as regiões de conferência de discagem, consulte [Planning for Dial-In Conferencing](https://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx).

O CAC requer que todas as regiões de rede tenham um site central do Skype for Business Server associado, que gerencia o tráfego de mídia dentro da região (isto é, toma decisões com base em políticas que você configurou, em relação a se ou não um áudio em tempo real ou é possível estabelecer uma sessão de vídeo. Os sites centrais do Skype for Business Server não representam locais geográficos, mas em vez de grupos lógicos de servidores que são configurados como um pool ou um conjunto de pools.

Para configurar uma região de rede, você pode usar a guia **regiões** na seção **configuração de rede** do painel de controle do Skype for Business Server, ou executar os cmdlets shell do Shell de gerenciamento do Skype for Business Server **New-CsNetworkRegion** ou **set-CsNetworkRegion** . Para obter instruções, consulte [implantar regiões de rede, sites e sub-redes no Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Skype for Business Server.

As mesmas definições de região de rede são compartilhadas por todos os três recursos avançados do Enterprise Voice. Se você já criou áreas de rede para um recurso, não será necessário criar novas regiões de rede para outros recursos. No entanto, pode ser necessário modificar uma definição de região de rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você criou áreas de rede para E9-1-1 (que não requer um site central associado) e posteriormente implantou o serviço de controle de admissão de chamadas, é necessário modificar cada uma das definições de região de rede para especificar um site central.

Para associar um site central do Skype for Business Server a uma região de rede, você especifica o nome do site central, seja usando a seção **configuração de rede** do painel de controle do Skype for Business Server, ou executando os cmdlets **New-CsNetworkRegion** ou **set-CsNetworkRegion** . Para obter instruções, consulte [implantar regiões de rede, sites e sub-redes no Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Skype for Business Server.

## <a name="network-sites"></a>Sites de rede

Um site de rede representa uma localização geográfica, como um escritório principal, filiais ou regionais. Cada site de rede deve ser associado a uma região específica de rede.

> [!NOTE]
> Os sites de rede são usados somente pelos recursos avançados de voz da empresa. Eles não são iguais aos dos sites de filiais que você configura na topologia do Skype for Business Server.

Para configurar um site de rede e associá-lo a uma região de rede, você pode usar a seção **configuração de rede** do painel de controle do Skype for Business Server ou executar cmdlets **New-CsNetworkSite** ou **set-CsNetworkSite** do Shell de gerenciamento do Skype for Business Server. Para obter detalhes, consulte [criar ou modificar um site de rede](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Skype for Business Server.

## <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.

No exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, seu computador terá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo 172.29.80.103.

> [!CAUTION]
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um cliente Skype for Business leva seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comparar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamadas, mas não o bypass de mídia, o controle de admissão de chamadas funcionará corretamente mesmo se você configurar sub-redes virtuais.) Por exemplo, se um cliente Skype for Business entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, ele solicitará o ID de bypass associado ao subnet 172.29.81.0. Se a subrede for definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira sub-redes exatamente como é fornecido pelos clientes do Skype for Business (que são provisionados com sub-redes durante a configuração de rede, seja estaticamente ou pelo protocolo DHCP (protocolo de configuração de host dinâmico).)

## <a name="associating-subnets-with-network-sites"></a>Associando Subredes aos Locais de Rede

Cada subrede na rede corporativa deve ser associado um site de rede (ou seja, cada sub-rede deve ser associada a uma localização geográfica). Essa associação de sub-redes habilita os recursos avançados de voz empresarial para localizar os pontos de extremidade geograficamente. Por exemplo, localizar os pontos de extremidade permite que o CAC regule o fluxo de áudio e dados de vídeo em tempo real indo e voltando do local de rede.

Para associar sub-redes a sites de rede, você pode usar a seção **configuração de rede** do painel de controle do Skype for Business Server, ou pode usar o Shell de gerenciamento do Skype for Business Server. Para obter instruções, confira [associar uma sub-rede a um site de rede](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) na documentação de implantação ou consulte a documentação do Shell de gerenciamento do Skype for Business Server.

## <a name="see-also"></a>Confira também

[Planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md)

[Planejar serviços de emergência no Skype for Business Server](emergency-services.md)

[Planejar a bypass de mídia no Skype for Business](media-bypass.md)

