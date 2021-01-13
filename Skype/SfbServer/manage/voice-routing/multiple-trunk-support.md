---
title: Suporte a vários troncos no Skype for Business Server
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
description: A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826221"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Suporte a vários troncos no Skype for Business Server

A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).

- Para atribuir ou remover um tronco no Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias. Um tronco consiste na seguinte associação: FQDN (nome de domínio totalmente qualificado) do Servidor de Mediação, a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.
- Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação. Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários interoperacionais pbx (central privada de computação). 

Quando um tronco é definido, ele deve ser associado a uma rota. Para associar um tronco a uma rota, defina um nome simples para o tronco no Construtor de Topologias. Esse nome simples é usado como o nome do tronco no Painel de Controle do Skype for Business Server, onde os troncos podem ser associados a rotas. O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento do Skype for Business Server.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação. No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades.** Especifique o gateway padrão para o Servidor de Mediação. 

O diagrama a seguir ilustra os vários troncos definidos para cada Servidor de Mediação e gateway. 

![Várias atribuições de tronco](../../media/multiple-trunk-assignments.jpg)
