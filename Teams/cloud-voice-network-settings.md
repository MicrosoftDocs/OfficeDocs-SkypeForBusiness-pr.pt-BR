---
title: Configurações de rede para recursos de voz na nuvem
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba mais sobre as configurações de rede que você deve configurar para roteamento Location-Based roteamento direto e serviços de emergência aprimorados.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2165ea1e4e9732f0e840b4f0949b230f5243121d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769939"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configurações de rede para recursos de voz na nuvem Microsoft Teams

Saiba mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis. Esses termos e conceitos são usados [](location-based-routing-plan.md) em toda a documentação de voz na nuvem para Roteamento Baseado em Localização para Roteamento Direto e [chamada de emergência dinâmica.](configure-dynamic-emergency-calling.md) Se você estiver implantando esses recursos de nuvem em sua organização, deverá configurar as configurações de rede para uso com esses recursos Microsoft Teams.

Este artigo fornece uma visão geral das configurações de rede comuns Location-Based roteamento e chamadas de emergência dinâmicas. Dependendo do recurso de voz na nuvem e da funcionalidade que você está implantando, configure algumas ou todas essas configurações. Para ver as etapas sobre como configurar essas configurações, consulte [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).

> [!NOTE]
> Todos os requisitos específicos de recursos para configurações de rede são documentados nos tópicos de configuração desse recurso.

## <a name="network-region"></a>Região de rede

Uma região de rede contém uma coleção de locais de rede. Ele interconecta várias partes de uma rede em várias áreas geográficas. Por exemplo, se sua organização tiver muitos sites localizados na Índia, você poderá optar por designar "Índia" como uma região de rede. Cada site de rede deve estar associado a uma região de rede.

As mesmas regiões de rede são compartilhadas Location-Based roteamento para roteamento direto e serviços de emergência aprimorados. Se você já criou regiões de rede para um recurso, não é preciso criar novas regiões de rede para o outro recurso.

## <a name="network-site"></a>Site de rede

Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus. Os sites de rede são definidos como uma coleção de sub-redes IP. Cada site de rede deve estar associado a uma região de rede.

Você também pode usar sites de rede para habilitar e configurar a chamada de emergência.

## <a name="network-subnet"></a>Sub-rede de rede

Cada sub-rede deve ser associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede de rede e no site de rede associado. Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede.

As informações de sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade está localizado quando uma nova sessão é iniciada. Quando o local de cada parte em uma sessão é conhecido, o recurso de voz na nuvem pode aplicar essas informações para determinar como manipular a configuração ou o roteamento de chamadas.

Para cada site de rede, trabalhe com o administrador de rede para determinar quais sub-redes IP são atribuídas a cada site de rede. Por exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento, liga seu computador e se conecta à rede, seu computador receberá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Endereço IP confiável

Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa. Eles determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar se há uma combinação de site específica.

Se o endereço IP externo do usuário corresponde a um endereço IP que está na lista de endereços IP confiáveis, o recurso de voz na nuvem verifica para determinar a sub-rede interna onde o ponto de extremidade do usuário está localizado. Uma combinação pode ser feita em relação a endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede. (Se um endereço IP público tiver IPv4 e IPv6, você deverá adicionar os dois como endereços IP confiáveis.)

Se o endereço IP externo do usuário não corresponder a um endereço IP que está na lista de endereços IP confiáveis, o ponto de extremidade será classificado como em um local desconhecido.

> [!Important]
> As buscas de configuração de rede não são suportadas com implantações de serviço proxy na nuvem que modificam os endereços IP de origem de Teams clientes.
