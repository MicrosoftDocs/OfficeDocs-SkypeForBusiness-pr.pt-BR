---
title: Adicionar IP NAT de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: O endereço IP público é o endereço IP usado pela NAT (conversão de endereços de rede). O endereço IP deve ser roteável publicamente. Isso é necessário porque você selecionou o endereço IP externo desse pool de bordas é convertido pela opção NAT na página Selecionar recursos deste assistente.
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698396"
---
# <a name="add-edge-server-nat-ip"></a>Adicionar IP NAT de Servidor de Borda

O endereço IP público é o endereço IP usado pela NAT (conversão de endereços de rede). O endereço IP deve ser roteável publicamente. Isso é necessário porque você selecionou **o endereço IP externo desse pool de bordas é convertido pela opção NAT** na página **selecionar recursos** deste assistente.

> [!NOTE]
> A NAT (conversão de endereços de rede) permite que clientes ou servidores em uma rede privada (por exemplo, o intervalo 192.168.0.0) se comuniquem com sistemas em redes remotas por meio das redes públicas da Internet. O NAT funciona usando um único endereço IP público em uma interface externa e associando endereços IP internos a um endereço IP público. O mapeamento NAT mapeia um endereço interno para o endereço IP público externo. O sistema remoto vê apenas o endereço público da fonte. O sistema remoto responde à fonte, e a origem se refere ao mapa NAT para determinar a qual endereço IP interno a resposta deve ser retornada.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como incluir Servidores de Borda na topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de Implantação do Servidor de Borda.


