---
title: Microsoft Monitoramento e Alertas do Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Saiba mais sobre os recursos de alertas e notificações do Teams disponíveis no centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 18279954a9bd71932422bd60519977288ae30ca6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438249"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Microsoft monitoramento e alertas do Teams

Novos recursos de monitoramento e alerta para Microsoft Teams estão disponíveis no centro de administração do Teams. Use diferentes conjuntos de regras disponíveis na seção **Notificações & alertas** no centro de administração do Teams para monitorar os recursos do Teams e receber alertas. Por exemplo, você pode monitorar ativamente a integridade de dispositivos teams, como telefones IP, Salas do Teams no Android e outros se eles inesperadamente ficarem offline.  

Sua organização pode usar o monitoramento e o alerta do Teams para fazer os seguintes itens:

- Gerenciar automaticamente os recursos do Teams
- Fique atento se eles mostrarem algo inesperado.
- Tome ações corretivas para colocar as coisas de volta nos trilhos.

> [!NOTE]
> A funcionalidade de alerta no centro de administração do Teams não está disponível em ambientes GCC/GCC-High.

## <a name="how-to-manage-monitoring-and-alerting"></a>Como gerenciar o monitoramento e o alerta

 Você deve ser um administrador global no Microsoft 365 ou um administrador de serviço do Teams para configurar regras de alerta. Consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md) para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar.

1. Entre no Centro de administração do Teams.
2. Na navegação à esquerda, selecione **Notificações & alertas**.
3. Escolha a regra que você deseja configurar em **Regras**.

## <a name="teams-monitoring-rules-reference"></a>Referência de regras de monitoramento do Teams

Continuamos adicionando e melhorando a experiência de monitoramento do Teams adicionando vários recursos de monitoramento e funcionalidades de configuração. Aqui está uma lista das regras de monitoramento do Teams atualmente disponíveis no centro de administração do Teams.


|Rule  |Capacidade de monitoramento|O que é monitorado? |
|---------|---------|---------|
|Envios de aplicativo  |Aplicativos do Teams | Monitore ativamente os aplicativos do Teams se eles forem enviados para aprovação.|
|[Regra de estado do dispositivo](device-health-status.md)  |Dispositivos teams | Monitore ativamente os dispositivos do Teams se eles ficarem offline.|
