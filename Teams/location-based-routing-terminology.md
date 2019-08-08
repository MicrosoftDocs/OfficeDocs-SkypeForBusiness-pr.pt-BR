---
title: Terminologia do Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Aprenda terminologia e conceitos associados ao roteamento baseado em local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d35b42453ac0eb9d9ae4a3f4c71f4452943a3b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245090"
---
# <a name="location-based-routing-terminology"></a>Terminologia do Roteamento baseado na localização

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Veja a seguir alguns termos e conceitos que são usados em toda a documentação de roteamento baseado em local. É uma boa ideia estar familiarizado com estes termos e conceitos antes de ficar mais profundo na documentação.

|Termo  |Descrição  |
|---------|---------|
|Regiões de rede     | Uma região de rede contém uma coleção de locais de rede. Por exemplo, se a sua organização tiver muitos sites localizados na Índia, você pode optar por designar "Índia" como uma região de rede.        |
|Sites de rede    | Um site de rede representa um local onde a sua organização tem um local físico, como um escritório, um conjunto de prédios ou um campus. Os sites de rede são definidos como um conjunto de sub-redes IP. Uma prática recomendada para o roteamento baseado em localização é criar um site separado para cada local que tenha conectividade PSTN exclusiva.  Cada site de rede deve estar associado a uma região de rede. Você pode criar um site que está habilitado para roteamento baseado em localização ou um site que não está habilitado para roteamento baseado em local. Por exemplo, talvez você queira criar um site que não esteja habilitado para roteamento baseado em local para permitir que os usuários habilitados para roteamento baseado em localização façam chamadas PSTN quando estiverem em roaming para esse site. Observe que os sites de rede também podem ser usados para habilitar e configurar chamadas de emergência.        |
|Sub-redes de rede     |As sub-redes IP no local onde os pontos de extremidade da equipe podem se conectar à rede devem ser definidas e associadas a uma rede definida para impor a chamada em tarifas. Várias sub-redes podem estar associadas ao mesmo local de rede, mas vários sites podem não estar associados a uma mesma sub-rede. Essa associação de sub-redes habilita o roteamento baseado em localização para localizar os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida. As sub-redes IPv6 e IPv4 são aceitas. Ao determinar se um ponto de extremidade do teams está localizado em um site, o roteamento baseado em local verifica primeiro se há um endereço IPv6 correspondente. Se um endereço IPv6 não estiver presente, o roteamento baseado em local verificará se há um endereço IPv4. <br><br>
|Endereços IP externos confiáveis    |Os endereços IP externos confiáveis são os endereços IP externos da Internet da rede corporativa. Elas determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar se há uma correspondência de site específica. Se o IP externo do usuário for compatível com um endereço IP definido na lista de confiáveis, o roteamento baseado em local fará uma verificação para determinar a sub-rede interna na qual o ponto de extremidade do usuário está localizado. Se o endereço IP externo do usuário não corresponder a qualquer endereço IP definido na lista de confiáveis, o ponto de extremidade será classificado como sendo um local desconhecido e as chamadas PSTNs de ou para um usuário habilitado para roteamento baseado em localização serão bloqueadas.          |

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
