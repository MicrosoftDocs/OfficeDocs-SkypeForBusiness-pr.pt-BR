---
title: Suporte a vários troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP. Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274909"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Suporte a vários troncos no Skype for Business Server

A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP. Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).

- Para atribuir ou remover um tronco no Skype for Business Server, primeiro você deve definir um tronco no construtor de topologias. Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação. Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange). 

Quando um tronco é definido, ele precisa ser associado à rota. Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias. Esse nome simples é usado como o nome do tronco no painel de controle do Skype for Business Server, em que os troncos podem ser associados às rotas. O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Skype for Business Server.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

O administrador deve selecionar um tronco padrão associado a um servidor de mediação. No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**. Especifique o gateway padrão do servidor de mediação. 

O diagrama a seguir ilustra os vários troncos que são definidos para cada servidor e gateway de mediação. 

![Várias atribuições de tronco](../../media/multiple-trunk-assignments.jpg)
