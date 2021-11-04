---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface para o pool de Borda e Servidor de Borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: ec350921c0a3778b6474d555f0ca0950a2b1518d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772891"
---
# <a name="add-edge-server-ip-options"></a>Adicionar Opções de IP de Servidor de Borda
 
Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface para o pool de Borda e Servidor de Borda. Para fazer isso, faça o seguinte:
  
- **Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do Servidor de Borda ou do Pool de Borda
    
- **Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do Servidor de Borda ou do Pool de Borda
    
- **Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do Servidor de Borda ou do Pool de Borda
    
- **Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do Servidor de Borda ou do pool de Borda
    
Você também pode configurar o Pool de Borda ou Servidor de Borda para usar um endereço de rede para os endereços IP externos. Faça isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**.
  
Suporte a NAT. NAT (Conversão de endereço de rede) não é suportado quando você está usando balanceamento de carga de hardware. Portanto, não selecione a opção NAT se estiver implantando um pool de Servidor de Borda com balanceamento de carga de hardware.
  

