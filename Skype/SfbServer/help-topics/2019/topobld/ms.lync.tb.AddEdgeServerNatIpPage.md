---
title: Adicioanr IP NAT de Servidor de Borda
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: O endereço IP público é o endereço IP utilizado pela NAT (conversão de endereços de rede). O endereço IP deve ser publicamente roteável, porque você selecionou a opção O endereço IP externo deste pool de Borda é convertido pela NAT na página Selecionar recursos deste assistente.
ms.openlocfilehash: 178b8af0fbb97a0fc3d7737a7e12381b9fdba1eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840353"
---
# <a name="add-edge-server-nat-ip"></a>Adicionar IP NAT de Servidor de Borda

O endereço IP público é o endereço IP utilizado pela NAT (conversão de endereços de rede). O endereço IP deve ser publicamente roteável, porque você selecionou a opção  **O endereço IP externo deste pool de Borda é convertido pela NAT** na página  **Selecionar recursos** deste assistente.

> [!NOTE]
> NAT (Conversão de Endereço de Rede) permite que clientes ou servidores em uma rede privada (por exemplo, na faixa 192.168.0.0) se comuniquem com sistemas em redes remotas via redes públicas de Internet. NAT funciona utilizando um único endereço IP público em uma interface externa e associando os endereços IP internos com o endereço IP público. O mapeamento NAT mapeia um endereço interno ao endereço IP público externo. O sistema remoto vê apenas o endereço público da fonte. O sistema remoto responde à fonte e a fonte consulta o mapa NAT para determinar para qual endereço IP interno a resposta deve ser retornada.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como incluir Servidores de Borda na topologia existente, consulte  [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology), na documentação de Implantação do Servidor de Borda.