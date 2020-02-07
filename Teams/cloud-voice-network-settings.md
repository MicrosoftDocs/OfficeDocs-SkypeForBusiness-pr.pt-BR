---
title: Configurações de rede para recursos de voz na nuvem no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba mais sobre as configurações de rede que devem ser configuradas para roteamento baseado em local para roteamento direto e serviços de emergência avançados.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c24444e9beb38aa1d0888e415d9dca3a46e249a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824949"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Configurações de rede para recursos de voz na nuvem no Microsoft Teams

Saiba mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis. Estes termos e conceitos são usados em toda a documentação de voz em nuvem para [roteamento baseado em local para roteamento direto](location-based-routing-plan.md) e [chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md). Se você estiver implantando esses recursos de nuvem em sua organização, deverá definir as configurações de rede para usar com esses recursos no Microsoft Teams.

Este artigo fornece uma visão geral das configurações de rede comuns a roteamento baseado em local e chamadas de emergência dinâmicas. Dependendo do recurso de voz em nuvem e do recurso que você está implantando, você define algumas ou todas essas configurações. Para ver as etapas sobre como definir essas configurações, consulte [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).

> [!NOTE]
> Qualquer requisito específico de recurso para configurações de rede está documentado nos tópicos de configuração para esse recurso.

## <a name="network-region"></a>Região de rede

Uma região de rede contém uma coleção de locais de rede. Ele interconecta várias partes de uma rede em várias áreas geográficas. Por exemplo, se a sua organização tiver muitos sites localizados na Índia, você pode optar por designar "Índia" como uma região de rede. Cada site de rede deve estar associado a uma região de rede.

As mesmas regiões de rede são compartilhadas por roteamento baseado em local para roteamento direto e serviços de emergência avançados. Se já tiver criado regiões de rede para um único recurso, você não precisará criar novas regiões de rede para o outro recurso.

## <a name="network-site"></a>Site de rede

Um site de rede representa um local onde a sua organização tem um local físico, como um escritório, um conjunto de prédios ou um campus. Os sites de rede são definidos como um conjunto de sub-redes IP. Cada site de rede deve estar associado a uma região de rede.

Você também pode usar sites de rede para habilitar e configurar chamadas de emergência.

## <a name="network-subnet"></a>Sub-rede da rede

Cada sub-rede deve estar associada a um site de rede específico. A localização de um cliente é determinada com base na sub-rede da rede e no site de rede associado. Você pode associar várias sub-redes com o mesmo site de rede, mas não pode associar vários sites com a mesma sub-rede.

As informações de sub-rede são usadas para determinar o site de rede no qual um ponto de extremidade se localiza quando uma nova sessão é iniciada. Quando o local de cada participante de uma sessão é conhecido, o recurso de voz em nuvem pode aplicar essas informações para determinar como lidar com a configuração ou o roteamento de chamadas.

Para cada site de rede, trabalhe com seu administrador de rede para determinar quais sub-redes IP são atribuídas a cada site de rede. Por exemplo, o site de Nova York na região da América do Norte pode receber as seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Se Bob, que normalmente funciona no Detroit, vai para o novo escritório de Nova York para treinamento, ativa o computador e se conecta à rede, o computador receberá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo, 172.29.80.103.

## <a name="trusted-ip-address"></a>Endereço IP confiável

Endereços IP confiáveis são endereços IP externos da Internet da rede corporativa. Elas determinam se o ponto de extremidade do usuário está dentro da rede corporativa antes de verificar se há uma correspondência de site específica.

Se o endereço IP externo do usuário corresponder a um endereço IP que está na lista de endereços IP confiáveis, o recurso de voz na nuvem verifica para determinar a sub-rede interna na qual o ponto de extremidade do usuário está localizado. Uma coincidência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede. (Se um endereço IP público tem IPv4 e IPv6, você deve adicionar ambos como endereços IP confiáveis.)

Se o endereço IP externo do usuário não coincidir com um endereço IP que está na lista de endereços IP confiáveis, o ponto de extremidade será classificado como sendo de um local desconhecido.
