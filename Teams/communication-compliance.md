---
title: Conformidade de comunicação com o Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Aprender sobre a conformidade de comunicação, parte do conjunto de soluções de risco interno, da perspectiva do Microsoft Teams (isso faz parte da funcionalidade de conformidade de comunicação do M365).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b96108f3bf548475cd19822967ba4e484fb26703
ms.sourcegitcommit: b383b309dbdf9caac7ad7e4a94df8d89016dc485
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66551198"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformidade de comunicação com o Microsoft Teams

Conformidade de Comunicações do Microsoft Purview é uma solução de risco interno no Microsoft 365 que ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização.

Para o Microsoft Teams, a conformidade de comunicação [](/microsoft-365/compliance/communication-compliance-feature-reference) ajuda a identificar os seguintes tipos de conteúdo inadequado em canais do Teams, canais privados do Teams ou em chats em grupo e 1:1:

- Linguagem ofensiva, profano e assediada
- Imagens adultas, geladas e gory
- Compartilhamento de informações confidenciais

Para obter mais informações sobre conformidade de comunicação e como configurar políticas para sua organização, [consulte Saiba mais sobre a conformidade de comunicação](/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Como usar a conformidade de comunicação no Microsoft Teams

A conformidade de comunicação e o Microsoft Teams estão totalmente integrados e podem ajudar a minimizar os riscos de comunicação em sua organização. Depois de configurar suas primeiras políticas de conformidade de comunicação, você poderá gerenciar ativamente mensagens e conteúdo inadequados do Microsoft Teams que são automaticamente sinalizados em alertas.

### <a name="getting-started"></a>Introdução

A introdução à conformidade de comunicação no Microsoft Teams começa com [](/microsoft-365/compliance/communication-compliance-plan) o planejamento e a criação de políticas predefinidas ou personalizadas para identificar atividades inadequadas do usuário em canais do Teams ou em grupos e 1:1. Tenha em mente que você precisará configurar [algumas](/microsoft-365/compliance/communication-compliance-configure) permissões e pré-requisitos básicos como parte do processo de configuração.

Os administradores do Teams podem configurar políticas de conformidade de comunicação nos seguintes níveis:

- **Nível de** usuário: as políticas nesse nível se aplicam a um usuário individual do Teams ou podem ser aplicadas a todos os usuários do Teams em sua organização. Essas políticas abrangem mensagens que esses usuários podem enviar em chats em grupo ou 1:1. As comunicações de chat para os usuários são monitoradas automaticamente em todos os Microsoft Teams em que os usuários são membros.
- **Nível do Teams**: as políticas nesse nível se aplicam a um canal do Microsoft Teams, incluindo um canal privado. Essas políticas abrangem apenas as mensagens enviadas no canal do Teams.

### <a name="report-a-concern-in-microsoft-teams"></a>Relatar uma preocupação no Microsoft Teams

>[!NOTE]
>A disponibilidade de mensagens relatadas pelo usuário para organizações [](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) licenciadas e usando a conformidade de comunicação e o Microsoft Teams começou em maio de 2022. Esse recurso estará disponível até 31 de agosto de 2022 para todas as organizações licenciadas e usando a conformidade de comunicação até julho de 2022. Para organizações que começam a usar a conformidade de comunicação após julho de 2022, a disponibilidade da política de mensagens relatadas pelo usuário pode levar até 30 dias a partir da data de seu licenciamento e do primeiro uso da conformidade de comunicação.

A *opção Relatar uma preocupação* para mensagens de chat pessoais e de grupo do Teams é habilitada por padrão e pode ser controlada por meio de políticas de mensagens do Teams no centro [de administração do Teams](/microsoftteams/manage-teams-in-modern-portal). Isso permite que os usuários em sua organização enviem mensagens de chat internas inadequadas para revisão por revisores de conformidade de comunicação para a política. Para obter mais informações sobre mensagens relatadas pelo usuário na conformidade de comunicação, consulte [Políticas de conformidade de comunicação](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Menu Relatar uma preocupação.](./media/communication-compliance-report-a-concern-full-menu.png)

Depois de enviar a mensagem para revisão, o usuário recebe uma confirmação do envio no Microsoft Teams. Outros participantes no chat não veem essa notificação.

![Relate uma confirmação de preocupação.](./media/communication-compliance-report-a-concern.png)

Os usuários em sua organização obtêm automaticamente a política global, a menos que você crie e atribua uma política personalizada. Edite as configurações na política global ou crie e atribua uma ou mais políticas personalizadas para ativar ou desativar esse recurso. Para obter mais informações, consulte [Gerenciar políticas de mensagens no Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agir em mensagens inadequadas no Microsoft Teams

Depois de configurar suas políticas e receber alertas de conformidade de comunicação para mensagens do Microsoft Teams, é hora de os revisores de conformidade em sua organização agirem sobre essas mensagens. Isso também incluirá mensagens relatadas pelo usuário, se habilitadas para sua organização. Os revisores podem ajudar a proteger sua organização examinando alertas de conformidade de comunicação e removendo mensagens sinalizadas da exibição no Microsoft Teams.

![Remova uma mensagem no Teams.](./media/communication-compliance-remove-teams-message.png)

As mensagens e o conteúdo removidos são substituídos por notificações para visualizadores, explicando que a mensagem ou o conteúdo foi removido e qual política é aplicável à remoção. O remetente da mensagem ou do conteúdo removido também é notificado sobre o status de remoção e fornecido com o conteúdo original da mensagem para contexto relacionado à sua remoção. O remetente também pode exibir a condição de política específica que se aplica à remoção da mensagem.

Exemplo de dica de política vista pelo remetente:

![Dica de política para o remetente.](./media/communication-compliance-warning-1.png)

Exemplo de notificação de política vista pelo remetente:

![Informações de condição de política para o remetente.](./media/communication-compliance-warning-2.png)

Exemplo de dica de política vista pelo destinatário:

![Dica de política para o destinatário.](./media/communication-compliance-warning-3.png)