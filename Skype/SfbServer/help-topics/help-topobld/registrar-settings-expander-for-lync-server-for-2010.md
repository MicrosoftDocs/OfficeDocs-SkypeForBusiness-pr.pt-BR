---
title: Expansor de Configurações de Registrador para o Lync Server for 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Edite as configurações para resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: adc3d3f0be42d542583cf269a7acf83d98df8dd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819333"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expansor de Configurações de Registrador para o Lync Server for 2010
 
Edite as configurações para **resiliência** e configure as seguintes propriedades:
  
- Selecione o **pool de registradores de backup associado** na lista.
    
    Opcionalmente, marque a caixa de seleção **failover automático e failback para voz** .
    
    Configurar o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**. Por padrão, os intervalos são de 120 segundos para a detecção de falha de voz e 240 segundos para failback de voz.
    
    > [!CAUTION]
    > O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funcione conforme o esperado. Definir o intervalo como baixo (ou seja, menos de 120 segundos) ou o failover e o failback definidos com mais detalhes podem resultar no failover real e o failback não funcionando como esperado. 
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

