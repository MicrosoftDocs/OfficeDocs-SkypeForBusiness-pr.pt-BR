---
title: Suporte a troncos múltiplos no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para a funcionalidade do Business Server suporta vários associações entre gateways e servidores de mediação. Essas associações são feitas por meio da definição de um tronco, que é uma associação de lógica entre um pool do servidor de mediação e um gateway PSTN (rede) telefônica pública comutada, controlador de borda de sessão (SBC) ou IP-PBX. Use o construtor de topologia para associar os gateways com servidores de mediação (ou seja, troncos).
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214630"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Suporte a troncos múltiplos no Skype para Business Server

Skype para a funcionalidade do Business Server suporta vários associações entre gateways e servidores de mediação. Essas associações são feitas por meio da definição de um tronco, que é uma associação de lógica entre um pool do servidor de mediação e um gateway PSTN (rede) telefônica pública comutada, controlador de borda de sessão (SBC) ou IP-PBX. Use o construtor de topologia para associar os gateways com servidores de mediação (ou seja, troncos).

- Para atribuir ou remover um tronco no Skype para Business Server, você deve definir um tronco no construtor de topologia. Consiste em um tronco a associação a seguir: servidor de mediação totalmente qualificado (FQDN) do nome de domínio, a porta de escuta do servidor de mediação, o gateway FQDN e a porta de escuta do gateway.
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso oferece resiliência adicional a infraestrutura do Enterprise Voice, o que é especialmente útil em cenários interoperational do privada de comutação telefônica (PBX). 

Quando um tronco é definido, ele precisa ser associado à rota. Para associar um tronco a uma rota, você pode definir um nome simples para o tronco no construtor de topologia. Esse nome simple é usado como o nome do tronco no Skype para painel de controle do Business Server, onde troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome de gateway a partir do Skype do Shell de gerenciamento do servidor de negócios.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No Topology Builder, com o botão direito do servidor de mediação associado e clique em **Propriedades**. Especifique o gateway padrão para o servidor de mediação. 

O diagrama a seguir ilustra os vários troncos que são definidos para cada servidor de mediação e o gateway. 

![Várias atribuições de tronco](../../media/multiple-trunk-assignments.jpg)
