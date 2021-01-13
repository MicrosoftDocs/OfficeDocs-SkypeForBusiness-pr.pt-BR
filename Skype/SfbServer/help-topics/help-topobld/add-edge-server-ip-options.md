---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'O Microsoft Lync Server 2013 permite configurar endereços IPv4 e IPv6 para cada interface para o Servidor de Borda e o pool de Borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: d8bfed4d7318133d33d733953cfcf472aa0e88ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815201"
---
# <a name="add-edge-server-ip-options"></a>Adicionar Opções de IP de Servidor de Borda
 
O Microsoft Lync Server 2013 permite configurar endereços IPv4 e IPv6 para cada interface para o Servidor de Borda e o pool de Borda. Para fazer isso, faça o seguinte:
  
- **Habilitar IPv4 na interface** interna: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do Servidor de Borda ou do pool de Borda
    
- **Habilitar IPv6 na interface** interna: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do Servidor de Borda ou do pool de Borda
    
- **Habilitar IPv4 na interface** externa: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do Servidor de Borda ou do pool de Borda
    
- **Habilitar IPv6 na interface** externa: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do Servidor de Borda ou do pool de Borda
    
Você também pode configurar o Servidor de Borda ou pool de Borda para usar um endereço de conversão de endereço de rede para os endereços IP externos. Faça isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**.
  
Suporte a NAT. NAT (Conversão de endereço de rede) não é suportado quando você está usando balanceamento de carga de hardware. Portanto, não selecione a opção NAT se estiver implantando um pool de Servidor de Borda com balanceamento de carga de hardware.
  

