---
title: Terminologia do Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Saiba a terminologia e conceitos associados ao roteamento baseado no local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34ec6558873da0db3537f6c5ae82b6624a3af369
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462392"
---
# <a name="location-based-routing-terminology"></a>Terminologia do Roteamento baseado na localização

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Aqui estão alguns termos e conceitos que são usados em toda a documentação de roteamento baseados em local. É uma boa ideia estar familiarizado com esses termos e conceitos antes de fazer mais aprofundado para a documentação.

|Termo  |Descrição  |
|---------|---------|
|Regiões de rede     | Uma região de rede contém uma coleção de locais de rede. Por exemplo, se sua organização tiver muitos sites localizados na Índia, você pode escolher designar "Índia" como uma região de rede.        |
|Sites de rede    | Um site de rede representa um local onde a sua organização tem um local físico, como um escritório, um conjunto de prédios ou um campus. Sites de rede são definidos como uma coleção de subredes IP. Uma prática recomendada para roteamento baseado em local é criar um site separado para cada local que tenha conectividade PSTN exclusiva.  Cada site de rede deve ser associado uma região de rede. Você pode criar um site que está habilitado para roteamento baseado no local ou um site que não está habilitado para roteamento baseado no local. Por exemplo, convém criar um site que não está habilitado para roteamento baseado no local permitir que os usuários habilitados para roteamento baseado no local fazer chamadas PSTN quando estiverem em roaming nesse site. Observe que os sites de rede também podem ser usadas para habilitar e configurar as chamadas de emergência.        |
|Subredes     |Subredes IP no local onde os pontos de extremidade de equipes podem se conectar à rede devem ser definidas e associados a uma rede definida para impor o bypass de Chamada Tarifada. Várias sub-redes podem ser associados ao mesmo site de rede, mas os múltiplos sites não podem ser associados uma mesma sub-rede. Essa associação de sub-redes permite o roteamento baseado no local localizar os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ter permissão. Há suporte para sub-redes IPv4 e IPv6. Ao determinar se um ponto de extremidade de equipes está localizado em um site, roteamento baseado em local primeiro verifica um endereço IPv6 correspondente. Se um endereço IPv6 não estiver presente, o roteamento baseado em local procura um endereço IPv4. <br><br>Suporte a IPv6 estiver em andamento e estará disponível por gerais disponibilidade (GA) de roteamento baseados em local.          |
|Confiáveis endereços IP externos    |Os endereços IP externos confiáveis são Internet endereços IP externos da rede corporativa. Elas determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar uma correspondência de sites específico. Se IP externo do usuário corresponder a um endereço IP que é definido na lista de confiáveis, roteamento baseado em local verifica para determinar a sub-rede interna, onde o ponto de extremidade do usuário está localizado. Se o endereço IP externo do usuário não corresponder a qualquer endereço IP que é definido na lista de confiáveis, o ponto de extremidade é classificado como sendo em um local desconhecido e todas as chamadas PSTN de ou para um usuário habilitado para roteamento baseado no local são bloqueadas.          |

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
