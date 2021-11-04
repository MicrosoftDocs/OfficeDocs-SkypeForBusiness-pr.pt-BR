---
title: Configurar configurações de rede - Roteamento baseado em local
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento Location-Based roteamento direto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f3c487828ea3b19bcd3c99604aac473c53d9e46e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749047"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurar definições de rede para o Roteamento baseado na localização

Se você ainda não tiver feito isso, leia [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) para revisar outras etapas que você precisará seguir antes de definir as configurações de rede para Location-Based Routing.

Este artigo descreve como configurar configurações de rede para roteamento Location-Based roteamento. Depois de implantar Sistema de Telefonia Roteamento Direto em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.

## <a name="define-network-regions"></a>Definir regiões de rede

Uma região de rede contém um conjunto de sites de rede e interconecta várias partes de uma rede em várias áreas geográficas. Para saber mais sobre como configurar regiões de rede, vá para [Gerenciar sua topologia](manage-your-network-topology.md)de rede para recursos de nuvem em Teams .

## <a name="define-network-sites"></a>Definir sites de rede

Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus. Você deve associar cada site de rede em sua topologia a uma região de rede. Para saber mais sobre como configurar sites de rede, consulte [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).

Uma prática prática para Location-Based roteamento é criar um site separado para cada local que tenha conectividade PSTN exclusiva. Você pode criar um site habilitado para roteamento Location-Based ou um site que não está habilitado para roteamento Location-Based. Por exemplo, talvez você queira criar um site que não está habilitado para o roteamento Location-Based para permitir que os usuários habilitados para roteamento de Location-Based façam chamadas PSTN quando eles circulam para esse site.

## <a name="define-network-subnets"></a>Definir sub-redes de rede

Cada sub-rede deve ser associada a um site de rede específico. Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede. Para saber mais sobre como configurar sub-redes de rede, vá para Gerenciar sua [topologia](manage-your-network-topology.md)de rede para recursos de nuvem em Teams .

Para Location-Based roteamento, sub-redes IP no local onde os pontos de extremidade Teams podem se conectar à rede devem ser definidos e associados a uma rede definida para impor o desvio de tarifa. Essa associação de sub-redes permite que Location-Based Roteamento localize os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida. As sub-redes IPv6 e IPv4 são suportadas. Ao determinar se um ponto de extremidade Teams está localizado em um site, Location-Based routing primeiro verifica se há um endereço IPv6 correspondente. Se um endereço IPv6 não estiver presente, Location-Based Roteamento verifica se há um endereço IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir endereços IP confiáveis (sub-redes externas)

Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Para saber mais sobre como configurar endereços IP confiáveis, vá para [Gerenciar sua topologia](manage-your-network-topology.md)de rede para recursos de nuvem em Teams .

Se o endereço IP externo do usuário corresponde a um endereço IP que está na lista de endereços IP confiáveis, Location-Based Roteamento verifica para determinar a sub-rede interna onde o ponto de extremidade do usuário está localizado. Se o endereço IP externo do usuário não corresponder a nenhum endereço IP definido na lista de endereços IP confiáveis, o ponto de extremidade será classificado como em um local desconhecido e quaisquer chamadas PSTN para ou de um usuário habilitado para o roteamento de Location-Based serão bloqueadas.

## <a name="next-steps"></a>Próximas etapas

Vá para [Habilitar Location-Based roteamento direto para roteamento](location-based-routing-enable.md)direto.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem Teams](cloud-voice-network-settings.md)
