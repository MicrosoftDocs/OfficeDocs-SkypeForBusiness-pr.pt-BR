---
title: Configurações de rede para recursos de voz na nuvem
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba mais sobre as configurações de rede que você deve definir para roteamento Location-Based roteamento direto e serviços de emergência aprimorados.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49709c2c3cc8816b404c88970c6ec916470f200e
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790146"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configurações de rede para recursos de voz na nuvem no Microsoft Teams

Saiba mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis. Esses termos e conceitos são usados em toda a nossa documentação de voz na nuvem para roteamento baseado em localização para roteamento [direto e](location-based-routing-plan.md) [chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md). Se você estiver implantando esses recursos de nuvem em sua organização, deverá definir as configurações de rede para uso com esses recursos no Microsoft Teams.

Este artigo fornece uma visão geral das configurações de rede que são comuns Location-Based roteamento e chamadas de emergência dinâmicas. Dependendo do recurso de voz na nuvem e da funcionalidade que você está implantando, defina algumas ou todas essas configurações. Para obter etapas sobre como definir essas configurações, consulte [Gerenciar sua topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

> [!NOTE]
> Todos os requisitos específicos de recursos para configurações de rede são documentados nos tópicos de configuração para esse recurso.

## <a name="network-region"></a>Região de rede

Uma região de rede contém uma coleção de locais de rede. Ele interconecta várias partes de uma rede em várias áreas geográficas. Por exemplo, se sua organização tiver muitos sites localizados na Índia, você poderá optar por designar "Índia" como uma região de rede. Cada site de rede deve ser associado a uma região de rede.

As mesmas regiões de rede são compartilhadas por Location-Based roteamento direto e serviços de emergência aprimorados. Se você já criou regiões de rede para um recurso, não precisa criar novas regiões de rede para o outro recurso.

## <a name="network-site"></a>Site de rede

Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus. Os sites de rede são definidos como uma coleção de sub-redes IP. Cada site de rede deve ser associado a uma região de rede.

Você também pode usar sites de rede para habilitar e configurar chamadas de emergência.

## <a name="network-subnet"></a>Sub-rede de rede

Cada sub-rede deve ser associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede de rede e no site de rede associado. Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede.

As informações de sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade está localizado quando uma nova sessão é iniciada. Quando o local de cada parte em uma sessão é conhecido, o recurso de voz na nuvem pode aplicar essas informações para determinar como lidar com a configuração ou o roteamento de chamadas.

Para cada site de rede, trabalhe com o administrador de rede para determinar quais sub-redes IP são atribuídas a cada site de rede. Por exemplo, o site de Nova York na região América do Norte pode receber as seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, que normalmente trabalha em Detroit, viajar para o escritório de Nova York para treinamento, ligar seu computador e se conectar à rede, seu computador receberá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Endereço IP confiável

Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa. Eles determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar se há uma correspondência de site específica.

Se o endereço IP externo do usuário corresponder a um endereço IP que está na lista de endereços IP confiáveis, o recurso de voz de nuvem verificará para determinar a sub-rede interna em que o ponto de extremidade do usuário está localizado. Uma correspondência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede. (Se um endereço IP público tiver IPv4 e IPv6, você deverá adicionar ambos como endereços IP confiáveis.)

Se o endereço IP externo do usuário não corresponder a um endereço IP que está na lista de endereços IP confiáveis, o ponto de extremidade será classificado como em um local desconhecido.

> [!Important]
> Não há suporte para pesquisas de configuração de rede com implantações de serviço de proxy de nuvem que modificam os endereços IP de origem de clientes do Teams.
