---
title: Expansor de configurações de registrador para o Lync Server para 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Você pode edita as configurações de resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: 88a2d75ff6f0225328a0f27743e0129950a5ca91
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expansor de configurações de registrador para o Lync Server para 2010
 
Você pode edita as configurações de **resiliência** e configure as seguintes propriedades:
  
- Selecione o **pool registrador de backup associado** na lista.
    
    Como opção, marque a caixa de seleção **failover automático e failback para voz** .
    
    Configure o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**. Por padrão, os intervalos são 120 para detecção de falha de voz e 240 segundos para failback de voz.
    
    > [!CAUTION]
    > O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funciona conforme o esperado. Definir o intervalo para baixo (ou seja, menos de 120 segundos) ou o failover e failback definir muito parecido podem resultar na real failover e failback não funcionando conforme o esperado. 
  
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  

