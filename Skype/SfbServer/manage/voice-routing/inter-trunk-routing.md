---
title: 'Skype for Business Server: roteamento entre troncos'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. '
ms.openlocfilehash: dd63f5f03c46e03f313f9cac42a2432499c216b6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390993"
---
# <a name="skype-for-business-server-inter-trunk-routing"></a>Skype for Business Server: roteamento entre troncos

Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. Essa funcionalidade permite que Skype for Business Server funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas IP-PBX. 


A figura a seguir ilustra Skype for Business Server a interconectividade entre um gateway PSTN e um IP-PBX.

![Interconectividade entre um gateway PSTN e um IP-PBX.](../../media/pstn-gateway-ip-pbx.jpg)

A próxima figura ilustra Skype for Business Server conectar dois sistemas IP-PBX.

![Skype for Business Server conectar dois sistemas IP-PGX.](../../media/two-ip-pbx-systems.jpg)

