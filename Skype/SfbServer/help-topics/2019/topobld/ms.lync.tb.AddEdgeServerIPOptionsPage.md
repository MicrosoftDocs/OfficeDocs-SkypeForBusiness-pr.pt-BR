---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype para Business Server permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: 727a946c6e9992b9391e7bf77238fdb61910c830
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898582"
---
# <a name="add-edge-server-ip-options"></a>Adicionar Opções de IP de Servidor de Borda
 
Skype para Business Server permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda. Para fazer isso, faça o seguinte:
  
- **Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface interna do pool de borda
    
- **Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface interna do pool de borda
    
- **Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface externa do pool de borda
    
- **Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface externa do pool de borda
    
Você também pode configurar o servidor de borda ou pool de borda para usar um endereço de conversão de endereço de rede para os endereços IP externos. Você pode fazer isso marcando a caixa de seleção, **o endereço IP externo deste pool de borda é convertido por NAT**.
  
Suporte NAT. Conversão de endereço de rede (NAT) não é suportado quando você estiver usando hardware balanceamento de carga, portanto, não marque a opção NAT se você estiver implantando um pool do servidor de borda com balanceamento de carga de hardware.
  

