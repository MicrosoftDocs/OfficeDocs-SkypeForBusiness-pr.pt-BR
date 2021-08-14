---
title: Roteamento entre troncos em Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. '
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351491"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento entre troncos em Skype for Business Server

Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. Essa funcionalidade permite que Skype for Business Server funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas IP-PBX. 


A figura a seguir ilustra Skype for Business Server a interconectividade entre um gateway PSTN e um IP-PBX.

![Interconectividade entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

A próxima figura ilustra Skype for Business Server conectar dois sistemas IP-PBX.

![Skype for Business Server conectar dois sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

