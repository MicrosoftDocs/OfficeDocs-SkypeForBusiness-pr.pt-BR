---
title: Suporte a vários troncos Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server funcionalidade suporta várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool do Servidor de Mediação e um gateway PSTN (rede telefônica pública comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
ms.openlocfilehash: aee1cdebba9780eb0079200cf6b0e0c1a5789535
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833347"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Suporte a vários troncos Skype for Business Server

Skype for Business Server funcionalidade suporta várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool do Servidor de Mediação e um gateway PSTN (rede telefônica pública comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).

- Para atribuir ou remover um tronco Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias. Um tronco consiste na seguinte associação: FQDN (Nome de domínio totalmente qualificado do Servidor de Mediação), a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação. Isso fornece resiliência adicional à infraestrutura de Enterprise Voice, que é especialmente útil em cenários interoperacionais de PBX (private branch exchange). 

Quando um tronco é definido, ele deve estar associado a uma rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no Construtor de Topologias. Esse nome simples é usado como o nome do tronco no painel de controle Skype for Business Server, onde os troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento Skype for Business Server.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação. No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades**. Especifique o gateway padrão para o Servidor de Mediação. 

O diagrama a seguir ilustra os vários troncos que são definidos para cada Servidor de Mediação e gateway. 

![Várias atribuições de tronco.](../../media/multiple-trunk-assignments.jpg)
