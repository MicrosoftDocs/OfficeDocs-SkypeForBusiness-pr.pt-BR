---
title: Suporte a vários troncos Skype for Business Server
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
description: Skype for Business Server funcionalidade suporta várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool do Servidor de Mediação e um gateway PSTN (rede telefônica pública comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
ms.openlocfilehash: 09ad94a15bbd7faa735f41fba81ade919d7a84da
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395183"
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
