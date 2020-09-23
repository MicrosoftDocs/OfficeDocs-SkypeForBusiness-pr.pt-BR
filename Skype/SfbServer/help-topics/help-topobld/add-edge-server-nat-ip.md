---
title: Adicioanr IP NAT de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: O endereço IP público é o endereço IP usado pela NAT (conversão de endereço de rede). O endereço IP deve ser publicamente roteável. Isso é necessário porque você selecionou o endereço IP externo deste pool de borda é convertido pela opção NAT na página Selecionar recursos deste assistente.
ms.openlocfilehash: 12749d3bcaec2478481fc1a4bc5597fb9693c5c4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216542"
---
# <a name="add-edge-server-nat-ip"></a>Adicioanr IP NAT de Servidor de Borda

O endereço IP público é o endereço IP utilizado pela NAT (conversão de endereços de rede). O endereço IP deve ser publicamente roteável, porque você selecionou a opção  **O endereço IP externo deste pool de Borda é convertido pela NAT ** na página  **Selecionar recursos ** deste assistente.

> [!NOTE]
> NAT (Conversão de Endereço de Rede) permite que clientes ou servidores em uma rede privada (por exemplo, na faixa 192.168.0.0) se comuniquem com sistemas em redes remotas via redes públicas de Internet. NAT funciona utilizando um único endereço IP público em uma interface externa e associando os endereços IP internos com o endereço IP público. O mapeamento NAT mapeia um endereço interno ao endereço IP público externo. O sistema remoto vê apenas o endereço público da fonte. O sistema remoto responde à fonte e a fonte consulta o mapa NAT para determinar para qual endereço IP interno a resposta deve ser retornada.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar Servidores de Borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação Implantação do Servidor de Borda.


