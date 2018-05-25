---
title: Expansor de configurações SBA do registrador
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Você pode edita as configurações de resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: cdc367d1f010749e72ea2144e757d673bd41ba4a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="registrar-sba-settings-expander"></a>Expansor de configurações SBA do registrador
 
Você pode edita as configurações de **resiliência** e configure as seguintes propriedades:
  
- Selecione o **serviço de usuário associados e o pool de registradores de backup** na lista.
    
    Como opção, marque a caixa de seleção **failover automático e failback para voz** .
    
    Configure o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**. Por padrão, os intervalos são 120 para detecção de falha de voz e 240 segundos para failback de voz.
    
    > [!CAUTION]
    > O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funciona conforme o esperado. Definir o intervalo para baixo (ou seja, menos de 120 segundos) ou o failover e failback definir muito parecido podem resultar na real failover e failback não funcionando conforme o esperado. 
  
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejamento para o Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

