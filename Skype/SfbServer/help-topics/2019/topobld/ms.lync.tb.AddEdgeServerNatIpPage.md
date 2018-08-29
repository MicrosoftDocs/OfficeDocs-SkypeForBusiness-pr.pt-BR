---
title: Adicionar IP de NAT de servidor de borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT). O endereço IP deverá ser roteável publicamente. Isso é necessário porque você selecionou o endereço IP externo desse pool é convertido em + pela opção de NAT na página Selecionar recursos deste assistente de borda.
ms.openlocfilehash: 94146cf7d6b8f77a79ae5c7f4cacbf3fb03677dc
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23254169"
---
# <a name="add-edge-server-nat-ip"></a>Adicionar IP de NAT de servidor de borda

O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT). O endereço IP deverá ser roteável publicamente. Isso é necessário porque você selecionou a opção **o endereço IP externo deste pool de borda é convertido por NAT** na página **Selecionar recursos** deste assistente.

> [!NOTE]
> Conversão de endereço de rede (NAT) permite que os clientes ou servidores em uma rede privada (por exemplo, 192.168.0.0 intervalo) para se comunicar com sistemas em redes remotas através de redes públicas de Internet. NAT funciona usando um único endereço IP público em uma interface externa e endereços IP internos como associar o um endereço IP público. Mapeamento de NAT mapeia um endereço interno para o endereço IP público externo. O sistema remoto vê apenas o endereço público da fonte. O sistema remoto responde à fonte e a fonte refere-se para o mapa NAT para determinar qual endereço IP interno, que a resposta deve ser retornada ao.

É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar servidores de borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de implantação de servidor de borda.


