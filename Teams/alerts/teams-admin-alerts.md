---
title: Monitoramento e alertas do Microsoft Teams
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
description: Saiba mais sobre os recursos de alertas e notificações do Teams disponíveis no Centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 452bcbebeffa3936b9d05270626e11923caf5cda
ms.sourcegitcommit: 72b6f7ab2a44dec395622bfe64119a48094960bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2022
ms.locfileid: "67283082"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Monitoramento e alertas do Microsoft Teams

Novos recursos de monitoramento e alerta do Microsoft Teams estão disponíveis no centro de administração do Teams. Use diferentes conjuntos de regras disponíveis na seção Notificações **& alertas** no centro de administração do Teams para monitorar as funcionalidades do Teams e receber alertas. Por exemplo, você pode monitorar ativamente a integridade de dispositivos do Teams, como Telefones IP, barras de colaboração e outros, se eles estiverem offline inesperadamente.  

Sua organização pode usar o monitoramento e os alertas do Teams para fazer os seguintes itens:

- Gerenciar automaticamente os recursos do Teams
- Seja alertado se eles mostrarem algo inesperado.
- Execute ações corretivas para colocar as coisas de volta no controle.

> [!NOTE]
> A funcionalidade de alerta no Centro de administração do Teams não está disponível em ambientes GCC/GCC-High.

## <a name="how-to-manage-monitoring-and-alerting"></a>Como gerenciar monitoramento e alertas

 Você deve ser um administrador global no Microsoft 365 ou um administrador de serviços do Teams para configurar regras de alerta. Consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md) para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar.

1. Entre no Centro de administração do Teams.
2. No painel de navegação esquerdo, selecione **Notificações & alertas**.
3. Escolha a regra que você deseja configurar em **Regras**.

## <a name="teams-monitoring-rules-reference"></a>Referência de regras de monitoramento do Teams

Continuamos adicionando e melhorando a experiência de monitoramento do Teams adicionando vários recursos de monitoramento e funcionalidades de configuração. Aqui está uma lista das regras de monitoramento do Teams atualmente disponíveis no centro de administração do Teams.


|Rule  |Capacidade de monitoramento|O que é monitorado? |
|---------|---------|---------|
|Envios de aplicativo  |Aplicativos do Teams | Monitore ativamente os aplicativos do Teams se eles forem enviados para aprovação.|
|[Regra de estado do dispositivo](device-health-status.md)  |Dispositivos do Teams | Monitore ativamente os dispositivos do Teams se eles estiverem offline.|
