---
title: Definir configurações de rede – roteamento baseado em localização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para Location-Based roteamento direto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999326"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurar definições de rede para o Roteamento baseado na localização

Este artigo descreve como definir as configurações de rede para Location-Based Roteamento. Se você ainda não fez isso, leia Plano de [](location-based-routing-plan.md) Location-Based roteamento para roteamento direto para examinar outras etapas que você precisará executar antes de definir as configurações de rede.

Depois de implantar o Roteamento Direto em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.

## <a name="define-network-regions"></a>Definir regiões de rede

Uma região de rede contém uma coleção de sites de rede e interconecta várias partes de uma rede em várias áreas geográficas. Para obter etapas sobre como configurar regiões de rede, acesse [Gerenciar sua topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definir sites de rede

Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus. Você deve associar cada site de rede em sua topologia a uma região de rede. Para obter etapas sobre como configurar sites de rede, consulte [Gerenciar sua topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Uma prática recomendada para Location-Based roteamento é criar um site separado para cada local que tenha conectividade PSTN (Rede Telefônica Pública Comunada) exclusiva. Você pode criar um site habilitado para roteamento Location-Based ou um site que não está habilitado para Location-Based Roteamento. Por exemplo, talvez você queira criar um site que não está habilitado para o Roteamento do Location-Based para permitir que os usuários habilitados para roteamento do Location-Based façam chamadas PSTN quando eles migram para esse site.

## <a name="define-network-subnets"></a>Definir sub-redes de rede

Cada sub-rede deve ser associada a um site de rede específico. Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede. Para obter etapas sobre como configurar sub-redes de rede, consulte  [Gerenciar sua topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Para Location-Based roteamento, as sub-redes IP no local em que os pontos de extremidade do Teams podem se conectar à rede devem ser definidas e associadas a uma rede definida para impor o bypass de chamada tarifada. Essa associação de sub-redes permite que Location-Based roteamento localize os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida. Há suporte para sub-redes IPv6 e IPv4. Ao determinar se um ponto de extremidade do Teams está localizado em um site, Location-Based roteamento primeiro verifica se há um endereço IPv6 correspondente. Se um endereço IPv6 não estiver presente, Location-Based roteamento verificará se há um endereço IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir endereços IP confiáveis (sub-redes externas)

Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Para obter etapas sobre como configurar endereços IP confiáveis, consulte [Gerenciar sua topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Se o endereço IP externo do usuário corresponder a um endereço IP que está na lista de endereços IP confiáveis, o roteamento do Location-Based verifica para determinar a sub-rede interna em que o ponto de extremidade do usuário está localizado. Se o endereço IP externo do usuário não corresponder a nenhum endereço IP definido na lista de endereços IP confiáveis, o ponto de extremidade será classificado como em um local desconhecido e todas as chamadas PSTN de ou para um usuário habilitado para o roteamento do Location-Based serão bloqueadas.

## <a name="next-steps"></a>Próximas etapas

Vá para [Habilitar Location-Based roteamento direto](location-based-routing-enable.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
