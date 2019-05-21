---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'O Microsoft Lync Server 2013 permite configurar endereços IPv4 e IPv6 para cada interface do servidor de borda e do pool de borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293970"
---
# <a name="add-edge-server-ip-options"></a>Adicionar Opções de IP de Servidor de Borda
 
O Microsoft Lync Server 2013 permite configurar endereços IPv4 e IPv6 para cada interface do servidor de borda e do pool de borda. Para fazer isso, faça o seguinte:
  
- **Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas
    
- **Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas
    
- **Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas
    
- **Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas
    
Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos. Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.
  
Suporte a NAT. Não há suporte para a conversão de endereços de rede (NAT) quando você está usando o balanceamento de carga de hardware, portanto, não selecione a opção NAT se você estiver implantando um pool do servidor de borda com balanceamento de carga de hardware.
  

