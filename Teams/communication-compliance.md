---
title: Conformidade de comunicação com o Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre conformidade de comunicação, parte do conjunto de soluções de risco do Insider, da perspectiva do Microsoft Teams (isso faz parte da funcionalidade de conformidade de comunicação do M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597126"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformidade de comunicação com o Microsoft Teams

Conformidade com comunicações é uma solução de risco para Insider no Microsoft 365 que ajuda a minimizar os riscos de comunicação ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização.

Para o Microsoft Teams, a conformidade de comunicação ajuda a identificar os [seguintes tipos](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) de conteúdo inadequado em canais de equipe ou em 1:1 e chats em grupo:

- Linguagem ofensiva, obscena e importuna
- Imagens adultas, Racy e Gory
- Compartilhamento de informações confidenciais

>[!IMPORTANT]
>Os canais particulares do Microsoft Teams não são compatíveis com a conformidade com comunicações. As comunicações de chat enviadas por usuários convidados para o Teams Users não são monitoradas por conteúdo impróprio.

Para obter mais informações sobre conformidade de comunicação e como configurar políticas para sua organização, consulte [conformidade com comunicações no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Como usar a conformidade de comunicação no Microsoft Teams

A conformidade de comunicação e o Microsoft Teams são totalmente integrados e podem ajudar a minimizar os riscos de comunicação em sua organização. Depois de configurar suas primeiras políticas de conformidade de comunicação, você pode gerenciar ativamente mensagens inadequadas do Microsoft Teams e conteúdo automaticamente sinalizado em alertas.

### <a name="getting-started"></a>Introdução

Começar a usar a conformidade de comunicação no Microsoft Teams começa com o [planejamento](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) e a criação de políticas predefinidas ou personalizadas para identificar atividades inadequadas do usuário em canais de equipe ou no 1:1 e grupos. Lembre-se de que você precisará [Configurar](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) algumas permissões e pré-requisitos básicos como parte do processo de configuração.

Os administradores do teams podem configurar políticas de conformidade de comunicação nos seguintes níveis:

- **Nível do usuário**: as políticas nesse nível se aplicam a um usuário individual do teams ou podem ser aplicadas a todos os usuários do teams na sua organização. Essas políticas abrangem mensagens que esses usuários podem enviar no 1:1 ou em chats em grupo. As comunicações por chat para os usuários são automaticamente monitoradas em todas as equipes da Microsoft, onde os usuários são membros.
- **Nível**de equipe: as políticas nesse nível se aplicam a um canal do Microsoft Team. Essas políticas abrangem as mensagens enviadas somente no canal de equipe.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agir em mensagens inadequadas no Microsoft Teams

Depois de configurar suas políticas e ter recebido alertas de conformidade de comunicação para mensagens do Microsoft Teams, é hora de os revisores de conformidade em sua organização executarem ações nessas mensagens. Os revisores podem ajudar a proteger sua organização revisando alertas de conformidade de comunicação e removendo mensagens sinalizadas do modo de exibição no Microsoft Teams.

![Remover uma mensagem no Microsoft Teams](./media/communication-compliance-remove-teams-message.png)

As mensagens e o conteúdo removidos são substituídos por notificações para visualizadores explicando que a mensagem ou o conteúdo foi removido e qual política se aplica à remoção. O remetente da mensagem ou do conteúdo removido também é notificado sobre o status de remoção e fornecido com o conteúdo da mensagem original para contexto relacionado à sua remoção. O remetente também pode exibir a condição específica da política que se aplica à remoção da mensagem.

Exemplo de dica de política vista pelo remetente:

![Dica de política para remetente](./media/communication-compliance-warning-1.png)

Exemplo de notificação de condição da política vista pelo remetente:

![Informações de condição da política para o remetente](./media/communication-compliance-warning-2.png)

Exemplo de dica de política vista pelo destinatário:

![Dica de política para destinatário](./media/communication-compliance-warning-3.png)