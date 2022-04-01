---
title: Turnos do Teams
description: Receba as diretrizes de administrador que você precisa configurar e gerenciar Turnos, a ferramenta de gerenciamento de agendamento, Teams.
ms.topic: conceptual
author: LanaChin
ms.author: v-lanachin
audience: admin
manager: samanro
f1.keywords:
- NOCSH
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 59e62ad1278c2703402a1186d198ae3ad877be63
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592767"
---
# <a name="shifts-for-teams"></a>Turnos do Teams

Turnos, a ferramenta de gerenciamento de agendamento Teams, mantém sua força de trabalho de linha de frente conectada e sincronizada. Ele foi criado primeiro para o gerenciamento de agendamento e comunicações rápidas e eficazes. Com Shifts, gerentes de linha de frente e funcionários podem gerenciar perfeitamente os agendamentos e manter contato.

Os gerentes podem criar, atualizar e gerenciar agendamentos de turno para suas equipes. Eles podem atribuir turnos, adicionar turnos abertos e aprovar solicitações de agendamento de funcionários. Os funcionários podem exibir seus próprios horários e suas equipes, definir sua disponibilidade, solicitar trocar ou oferecer um turno, solicitar folga e entrar e sair.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE42FjP]

Use os recursos a seguir para ajudá-lo a configurar e gerenciar Turnos em sua organização.

## <a name="set-up-and-manage-shifts"></a>Configurar e gerenciar Turnos

|&nbsp;  |&nbsp; |
|---------|---------|
|<img src="/office/media/icons/calendar-teams.png" alt="Calendar symbol.">   |**[Gerenciar Turnos](shifts/manage-the-shifts-app-for-your-organization-in-teams.md)** Saiba como gerenciar turnos para sua organização.         |
|<img src="/office/media/icons/users-people.png" alt="Users/people symbol.">   |**[Gerenciar proprietários de agendamento para gerenciamento de turnos](shifts/schedule-owner-for-shift-management.md)** Esse recurso permite que você eleve as permissões de um membro da equipe para um proprietário de agendamento sem tornar o funcionário um proprietário da equipe.         |
|<img src="/office/media/icons/help.png" alt="Help symbol.">     | **[Desloca perguntas frequentes sobre dados](shifts/shifts-data-faq.md)** Saiba onde os dados shifts são armazenados e outros tópicos relacionados aos dados shifts, incluindo retenção, recuperação e criptografia.        |

## <a name="shifts-connectors"></a>Conectores de turnos

Se você estiver usando um sistema WFM (gerenciamento de força de trabalho) de terceiros para agendamento, poderá integrar-se diretamente com Shifts por meio de conectores de Turnos gerenciados e por meio de APIs de turnos Graph e SDK com conectores shifts de código aberto. Depois de configurar uma conexão, seus funcionários de linha de frente podem exibir e gerenciar seus agendamentos em seu sistema WFM de dentro de Shifts.

|&nbsp;  |&nbsp;  |
|---------|---------|
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Visão geral dos conectores de turnos](shifts/shifts-connectors.md)** Obter uma visão geral dos conectores shifts e como eles funcionam. Saiba mais sobre os conectores gerenciados e de código aberto disponíveis e os sistemas WFM com suporte.   |
|<img src="/office/media/icons/connector-teams.png" alt="Connector symbol.">     | **[Conectores de Turnos Gerenciados](shifts/shifts-connectors.md#managed-shifts-connectors)** Os conectores de Turnos Gerenciados, desenvolvidos em colaboração com nossos parceiros, são hospedados e gerenciados por nós ou por nossos parceiros. Para saber mais, consulte [Microsoft Teams conector shifts para Blue Yonder](shifts/shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) e [Reflexis Shifts connector for Microsoft Teams](shifts/shifts-connectors.md#reflexis-shifts-connector-for-microsoft-teams).    |
|   | **[Use o assistente de conector de turnos para conectar Shifts ao Gerenciamento de Força de Trabalho de Zona Azul](shifts/shifts-connector-wizard.md)** O assistente do conector shifts no Centro de administração do Microsoft 365 ajuda você a configurar rapidamente uma conexão com seu sistema WFM. Atualmente, o assistente dá suporte ao conector Teams Shifts para Blue Yonder para integrar Shifts com o Gerenciamento de Força de Trabalho de Blue Yonder.
|  | **[Usar o PowerShell para conectar Turnos ao Gerenciamento de Força de Trabalho do Blue Yonder](shifts/shifts-connector-blue-yonder-powershell-setup.md)** Saiba como usar o PowerShell para configurar uma conexão com o Gerenciamento de Força de Trabalho do Blue Yonder por meio do conector Teams turnos para Blue Yonder.         |
|   | **[Use o PowerShell para gerenciar sua conexão shifts com o Gerenciamento de Força de Trabalho de Blue Yonder](shifts/shifts-connector-powershell-manage.md)** Obter orientações sobre como usar o PowerShell gerenciar sua conexão Shifts com o Gerenciamento de Força de Trabalho da Blue Yonder depois de defini-la por meio do assistente do conector de turnos ou do PowerShell.
|<img src="/office/media/icons/api.png" alt="Three gears - API.">    | **[Conectores de Shifts de código aberto](/microsoftteams/platform/samples/shifts-wfm-connectors)** Saiba como usar conectores de código aberto [orientados](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors) pela comunidade para integrar seu sistema WFM Kronos ou JDA por meio de APIs e SDK de turnos Graph.    |

## <a name="shifts-extensions"></a>Extensões de turnos

|&nbsp;|&nbsp;|
| ------------- | ------------- |
| <img src="/office/media/icons/api.png" alt="Three gears - API."> | **[Shift Graph APIs](/graph/api/resources/shift)** Shifts Graph APIs permitem integrar dados shifts com sistemas WFM (gerenciamento de força de trabalho externo). Você terá a flexibilidade de criar experiências personalizadas de Shifts no back-end, ao mesmo tempo que oferece aos usuários uma experiência de front-end rica em Teams.             |
|<img src="/office/media/icons/process-flow-teams.png" alt="Process/flow chart symbol."> | **[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate permite que você pegue informações de Shifts e crie fluxos de trabalho personalizados com outros aplicativos e execute operações em escala. Automatizar processos-chave com pouco ou nenhum código. Os gatilhos e modelos suportam vários cenários, como a habilitação de aprovações automáticas para solicitações de turno quando a aprovação de um gerente não é necessária. |

## <a name="featured-training"></a>Treinamento em destaque

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| <img src="/office/media/icons/get-started-teams.png" alt="Get started symbol.">  |  [Vídeo: O que é Shifts?](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |<img src="/office/media/icons/clock-teams.png" alt="Clock symbol."> |  [Vídeo: Criar uma agenda de turnos](https://support.microsoft.com/office/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |<img src="/office/media/icons/blocks-teams.png" alt="Blocks symbol.">|  [Vídeo: Gerenciar uma agenda de turnos](https://support.microsoft.com/office/manage-and-view-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
