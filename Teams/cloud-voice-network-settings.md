---
title: Configurações de rede para recursos de voz na nuvem
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba mais sobre as configurações de rede que você deve configurar para Location-Based roteamento direto e serviços de emergência aprimorados.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834331"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configurações de rede para recursos de voz na nuvem no Microsoft Teams

Saiba mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis. Esses termos e conceitos são usados [](location-based-routing-plan.md) em toda a nossa documentação de voz na nuvem para Roteamento Baseado em Localização para Roteamento Direto e [chamadas de emergência dinâmicas.](configure-dynamic-emergency-calling.md) Se você estiver implantando esses recursos de nuvem em sua organização, deverá definir as configurações de rede para uso com esses recursos no Microsoft Teams.

Este artigo apresenta uma visão geral das configurações de rede que são comuns Location-Based roteamento e chamadas de emergência dinâmicas. Dependendo do recurso de voz na nuvem e do recurso que você está implantando, configure algumas ou todas essas configurações. Para ver as etapas sobre como configurar essas configurações, consulte Gerenciar sua topologia de rede [para recursos de nuvem no Teams.](manage-your-network-topology.md)

> [!NOTE]
> Todos os requisitos específicos de recursos para configurações de rede são documentados nos tópicos de configuração para esse recurso.

## <a name="network-region"></a>Região da rede

Uma região de rede contém uma coleção de locais de rede. Ele interconecta várias partes de uma rede em várias áreas geográficas. Por exemplo, se sua organização tiver muitos sites localizados na Índia, você poderá optar por designar "Índia" como uma região de rede. Cada site de rede deve estar associado a uma região de rede.

As mesmas regiões de rede são compartilhadas Location-Based roteamento para Roteamento Direto e serviços de emergência aprimorados. Se você já criou regiões de rede para um recurso, não é preciso criar novas regiões de rede para o outro recurso.

## <a name="network-site"></a>Site de rede

Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus. Os sites de rede são definidos como um conjunto de sub-redes IP. Cada site de rede deve estar associado a uma região de rede.

Você também pode usar sites de rede para habilitar e configurar as chamada de emergência.

## <a name="network-subnet"></a>Sub-rede de rede

Cada sub-rede deve estar associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede de rede e no site de rede associado. Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede.

As informações da sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade está localizado quando uma nova sessão é iniciada. Quando a localização de cada parte em uma sessão é conhecida, o recurso de voz na nuvem pode aplicar essas informações para determinar como lidar com a configuração ou o roteamento de chamadas.

Para cada site de rede, trabalhe com seu administrador de rede para determinar quais sub-redes IP são atribuídas a cada site de rede. Por exemplo, o site de Nova York na região da América do Norte pode ter as seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, que normalmente trabalha em De bobby, viajar para o escritório de Nova York para treinamento, ligar o computador e se conectar à rede, o computador receberá um endereço IP em um dos quatro intervalos atribuídos a Nova York, por exemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Endereço IP confiável

Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa. Eles determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar se há uma combinação de site específica.

Se o endereço IP externo do usuário corresponde a um endereço IP que está na lista de endereços IP confiável, o recurso de voz na nuvem verifica para determinar a sub-rede interna onde o ponto de extremidade do usuário está localizado. Uma combinação pode ser feita em relação a endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede. (Se um endereço IP público tiver IPv4 e IPv6, você deverá adicionar ambos como endereços IP confiáveis.)

Se o endereço IP externo do usuário não corresponder a um endereço IP que está na lista de endereços IP confiável, o ponto de extremidade será classificado como sendo em um local desconhecido.
