---
title: Adicionar IP de NAT de servidor de borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT). O endereço IP deverá ser roteável publicamente. Isso é necessário porque você selecionou o endereço IP externo desse pool é convertido em + pela opção de NAT na página Selecionar recursos deste assistente de borda.
ms.openlocfilehash: be14b49a0d5ccac83dbee483d45aef91f1182621
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003114"
---
# <a name="add-edge-server-nat-ip"></a>Adicionar IP de NAT de servidor de borda
 
O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT). O endereço IP deverá ser roteável publicamente. Isso é necessário porque você selecionou a opção **o endereço IP externo deste pool de borda é convertido por NAT** na página **Selecionar recursos** deste assistente.
  
> [!NOTE]
> Conversão de endereço de rede (NAT) permite que os clientes ou servidores em uma rede privada (por exemplo, 192.168.0.0 intervalo) para se comunicar com sistemas em redes remotas através de redes públicas de Internet. NAT funciona usando um único endereço IP público em uma interface externa e endereços IP internos como associar o um endereço IP público. Mapeamento de NAT mapeia um endereço interno para o endereço IP público externo. O sistema remoto vê apenas o endereço público da fonte. O sistema remoto responde à fonte e a fonte refere-se para o mapa NAT para determinar qual endereço IP interno, que a resposta deve ser retornada ao. 
  
É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como adicionar servidores de borda a uma topologia existente, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de implantação de servidor de borda.
  

