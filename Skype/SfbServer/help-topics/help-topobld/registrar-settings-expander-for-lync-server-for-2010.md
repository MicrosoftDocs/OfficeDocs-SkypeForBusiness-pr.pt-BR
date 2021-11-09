---
title: Expansor de Configurações de Registrador para o Lync Server for 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Edite as configurações para Resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: fbdd6f63ac46aa6ca2c00b75466d192be939f642
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830945"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expansor de Configurações de Registrador para o Lync Server for 2010
 
Edite as configurações para **Resiliência** e configure as seguintes propriedades:
  
- Selecione **Pool associado de Registradores de backup** na lista.
    
    Como opção, marque a caixa de seleção **Failover e failback automático para Voice**.
    
    Configure o **Intervalo de detecção de falha do Voice (seg.)** e o **Intervalo de failback do Voice (seg.)**. Por padrão, os intervalos são de 120 segundos para detecção de falha do Voice e 240 segundos para failback do Voice.
    
    > [!CAUTION]
    > O número de segundos definido para os intervalos de failover e failback deve ser testado com cuidado a fim de assegurar que a resiliência funcione conforme o esperado. Configurar o intervalo de forma muito baixa (ou seja, menos de 120 segundos) ou o failover e failback definidos de forma muito próxima pode resultar no não funcionamento real e conforme o esperado do failover e do failback. 
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

