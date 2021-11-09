---
title: Expansor de Configurações SBA do Registrador
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
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Edite as configurações para Resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: 8ea7267d5074783823622609e6a2330d09b0ed46
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837713"
---
# <a name="registrar-sba-settings-expander"></a>Expansor de Configurações SBA do Registrador

Edite as configurações para **Resiliência** e configure as seguintes propriedades:

- Selecione **Pool associado de Serviço de usuário Registradores de backup** na lista.

    Como opção, marque a caixa de seleção **Failover e failback automático para Voice**.

    Configure o **Intervalo de detecção de falha do Voice (seg.)** e o **Intervalo de failback do Voice (seg.)**. Por padrão, os intervalos são de 120 segundos para detecção de falha do Voice e 240 segundos para failback do Voice.

    > [!CAUTION]
    > O número de segundos definido para os intervalos de failover e failback deve ser testado com cuidado a fim de assegurar que a resiliência funcione conforme o esperado. Configurar o intervalo de forma muito baixa (ou seja, menos de 120 segundos) ou o failover e failback definidos de forma muito próxima pode resultar no não funcionamento real e conforme o esperado do failover e do failback.

  **OK** aceita e confirma as alterações na caixa de diálogo.

  **Cancelar** descarta as alterações e fecha a caixa de diálogo.

  **Ajuda** exibe essa tela de ajuda.

## <a name="see-also"></a>Confira também

[Planejamento para Enterprise Voice Resiliência](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)