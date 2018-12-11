---
title: Roteamento intertronco no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222811"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento intertronco no Skype para Business Server

Skype para Business Server fornece gerenciamento de sessão básica por meio do suporte de roteamento entre troncos. Essa capacidade permite Skype para Business Server fornecer funcionalidades de controle de chamada aos sistemas de telefonia de downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, Skype para Business Server pode interconexão dois ou mais sistemas IP-PBX para que as chamadas podem ser colocadas e recebidas em telefones PBX dos diferentes sistemas IP-PBX. 


A figura a seguir ilustra o Skype para Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.

![Interconectividade entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

A próxima figura ilustra o Skype para Business Server conectando dois sistemas IP-PBX.

![Skype para Business Server conectando dois sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

