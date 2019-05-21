---
title: Roteamento inter-trunk no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274965"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>Roteamento inter-trunk no Skype for Business Server

O Skype for Business Server oferece gerenciamento de sessão básico por meio do suporte a roteamento de intertronco. Esse recurso permite que o Skype for Business Server forneça funcionalidades de controle de chamadas para sistemas de telefonia downstream. O roteamento entre troncos pode interconectar um IP-PBX a um gateway de rede de telefone pública comutada (PSTN) de forma que as chamadas de um telefone de central privada de comutação telefônica (PBX) possam ser encaminhadas para o PSTN, e as chamas PSTN de entrada possam ser encaminhadas para um telefone PBX. Da mesma forma, o Skype for Business Server pode interconectar dois ou mais sistemas de PBX IP para que chamadas possam ser feitas e recebidas entre telefones PBX dos diferentes sistemas de IP-PBX. 


A figura a seguir ilustra o Skype for Business Server que oferece interconectividade entre um gateway PSTN e um IP-PBX.

![Interconectividade entre um gateway PSTN e um IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

A próxima figura ilustra o Skype for Business Server conectando dois sistemas de PBX IP.

![Skype for Business Server conectando dois sistemas de PGX de IP](../../media/two-ip-pbx-systems.jpg)

