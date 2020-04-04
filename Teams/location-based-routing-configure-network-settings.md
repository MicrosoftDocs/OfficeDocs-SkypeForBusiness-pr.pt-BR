---
title: Definir configurações de rede-roteamento baseado em local
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado em local para roteamento direto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141274"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurar definições de rede para o Roteamento baseado na localização

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Se ainda não tiver feito isso, leia [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará tomar antes de definir as configurações de rede para roteamento baseado em local.

Este artigo descreve como definir as configurações de rede para roteamento baseado em local. Depois de implantar o roteamento direto do sistema telefônico em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.

## <a name="define-network-regions"></a>Definir regiões de rede

Uma região de rede contém um conjunto de sites de rede e interconecta várias partes de uma rede em várias áreas geográficas. Para ver as etapas sobre como configurar regiões de rede, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Definir sites de rede

Um site de rede representa um local onde a sua organização tem um local físico, como um escritório, um conjunto de prédios ou um campus. Você deve associar cada site de rede na sua topologia a uma região de rede. Para ver as etapas sobre como configurar sites de rede, consulte [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Uma prática recomendada para o roteamento baseado em localização é criar um site separado para cada local que tenha conectividade PSTN exclusiva. Você pode criar um site que está habilitado para roteamento baseado em localização ou um site que não está habilitado para roteamento baseado em local. Por exemplo, talvez você queira criar um site que não esteja habilitado para roteamento baseado em local para permitir que os usuários habilitados para roteamento baseado em localização façam chamadas PSTN quando estiverem em roaming para esse site.

## <a name="define-network-subnets"></a>Definir sub-redes de rede

Cada sub-rede deve estar associada a um site de rede específico. Você pode associar várias sub-redes com o mesmo site de rede, mas não pode associar vários sites com a mesma sub-rede. Para ver as etapas sobre como configurar sub-redes de rede, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Para roteamento baseado em local, as sub-redes IP no local onde os pontos de extremidade da equipe podem se conectar à rede devem ser definidas e associadas a uma rede definida para aplicar a chamada em tarifas. Essa associação de sub-redes habilita o roteamento baseado em localização para localizar os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida. As sub-redes IPv6 e IPv4 são aceitas. Ao determinar se um ponto de extremidade do teams está localizado em um site, o roteamento baseado em local verifica primeiro se há um endereço IPv6 correspondente. Se um endereço IPv6 não estiver presente, o roteamento baseado em local verificará se há um endereço IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Definir endereços IP confiáveis (sub-redes externas)

Os endereços IP confiáveis são endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa. Para ver as etapas sobre como configurar endereços IP confiáveis, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

Se o endereço IP externo do usuário corresponder a um endereço IP que está na lista de endereços IP confiáveis, o roteamento baseado em local fará uma verificação para determinar a sub-rede interna na qual o ponto de extremidade do usuário está localizado. Se o endereço IP externo do usuário não corresponder a qualquer endereço IP definido na lista de endereços IP confiáveis, o ponto de extremidade será classificado como sendo de um local desconhecido e as chamadas PSTNs de ou para um usuário habilitado para roteamento baseado em local serão bloqueadas.

## <a name="next-steps"></a>Próximas etapas

Vá para [habilitar o roteamento baseado em local para roteamento direto](location-based-routing-enable.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
