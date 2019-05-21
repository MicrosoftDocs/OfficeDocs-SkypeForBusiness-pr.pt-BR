---
title: Expansor de Configurações de Registrador para o Lync Server for 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Edite as configurações para resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: 5ed1311e73ea035b7672ba75bab337c9212e8816
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282235"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a>Expansor de Configurações de Registrador para o Lync Server for 2010
 
Edite as configurações para **resiliência** e configure as seguintes propriedades:
  
- Selecione o pool de registradores de **backup associado** na lista.
    
    Opcionalmente, marque a caixa de seleção **failover automático e failback para voz** .
    
    Configurar o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**. Por padrão, os intervalos são de 120 segundos para a detecção de falha de voz e 240 segundos para failback de voz.
    
    > [!CAUTION]
    > O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funcione conforme o esperado. Definir o intervalo como baixo (ou seja, menos de 120 segundos) ou o failover e o failback definidos com mais detalhes podem resultar no failover real e o failback não funcionando como esperado. 
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

