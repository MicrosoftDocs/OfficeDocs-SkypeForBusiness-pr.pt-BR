---
title: Expansor de configurações SBA do Registrador Avançado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
description: 'Edite as configurações para resiliência e configure as seguintes propriedades:'
ms.openlocfilehash: dc5f207653142374fce00cdc774bc3a88fcea1b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306465"
---
# <a name="registrar-sba-settings-expander"></a>Expansor de configurações SBA do Registrador Avançado

Edite as configurações para **resiliência** e configure as seguintes propriedades:

- Selecione o **serviço de usuário associado e o pool** de registradores de backup na lista.

    Opcionalmente, marque a caixa de seleção **failover automático e failback para voz** .

    Configurar o **intervalo de detecção de falha de voz (s)** e o **intervalo de failback de voz (s)**. Por padrão, os intervalos são de 120 segundos para a detecção de falha de voz e 240 segundos para failback de voz.

    > [!CAUTION]
    > O número de segundos que você define para os intervalos de failover e failback deve ser testado cuidadosamente para garantir que a resiliência funcione conforme o esperado. Definir o intervalo como baixo (ou seja, menos de 120 segundos) ou o failover e o failback definidos com mais detalhes podem resultar no failover real e o failback não funcionando como esperado.

  **OK** Aceita e confirma as alterações na caixa de diálogo.

  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.

  **Ajuda** Exibe essa tela de ajuda.

## <a name="see-also"></a>Confira também

[Planejando a resiliência do Enterprise Voice](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
