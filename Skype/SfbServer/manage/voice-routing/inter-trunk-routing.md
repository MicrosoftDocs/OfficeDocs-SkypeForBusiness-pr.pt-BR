---
title: Roteamento entre troncos no Skype for Business Server
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
description: 'O Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814121"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento entre troncos no Skype for Business Server

O Skype for Business Server fornece gerenciamento básico de sessão por meio do suporte ao roteamento entre confianças. Esse recurso permite que o Skype for Business Server forneça funcionalidades de controle de chamada para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas IP-PBX para que as chamadas possam ser feitas e recebidas entre telefones PBX de diferentes sistemas IP-PBX. 


A figura a seguir ilustra o Skype for Business Server fornecendo interconectividade entre um gateway PSTN e um IP-PBX.

![Interconexão entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

A próxima figura ilustra a conexão do Skype for Business Server com dois sistemas IP-PBX.

![Skype for Business Server conectando dois sistemas IP-PGX](../../media/two-ip-pbx-systems.jpg)

