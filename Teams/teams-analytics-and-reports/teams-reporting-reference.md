---
title: Análise e relatórios do Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Neste artigo, você aprenderá sobre os relatórios Teams que estão disponíveis no Microsoft Teams de administração.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6a3cbf42c65d054befac8ad4e1f25d8be65f286
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853032"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatório para Microsoft Teams está disponível no Microsoft Teams de administração. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e chat e os tipos de dispositivos que eles usam para se conectar Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões de negócios e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve ser um administrador global no Microsoft 365 ou Office 365, leitor global no Microsoft 365 ou Office 365, administrador de serviços do Teams ou administrador Skype for Business. Para saber mais sobre Teams funções de administrador e quais relatórios cada função de administrador pode acessar, consulte Usar funções de administrador do [Teams para gerenciar](../using-admin-roles.md) Teams.

Vá para o Microsoft Teams de administração, no painel de navegação à esquerda, selecione **Relatórios do Analytics &** e, em Exibir **Relatórios, escolha** o relatório que você deseja executar.

> [!NOTE]
> Os relatórios no Microsoft Teams de administração são separados dos relatórios de atividade para Teams que fazem parte dos relatórios Microsoft 365 no Centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividade no Centro de administração do Microsoft 365, [Teams relatórios de atividade no Centro de administração do Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams de relatório

Aqui está uma lista dos relatórios Teams disponíveis no centro de administração do Microsoft Teams e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de Teams relatórios e adicionando recursos e funcionalidades. Ao longo do tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no Microsoft Teams de administração.

|Relatório  |O que é avaliado? |
|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados em uma equipe   |
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  | Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chamadas em que um usuário participou<br/> Número de reuniões organizadas pelo usuário <br/>Número de reuniões em que o usuário participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Data da última atividade de um usuário     |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |  Total de exibições<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Teams relatório de usuários bloqueados PSTN](pstn-blocked-users-report.md)   |  Nome de exibição<br>Telefone número<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Teams de pools de minutos PSTN](pstn-minute-pools-report.md) |  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Teams de uso de PSTN – Planos de Chamada](pstn-usage-report.md#calling-plans)|  Carimbo de data/hora<br>Nome de usuário<br>Telefone número<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>Do país ou da região<br>Carga<br>Moeda<br>Duração<br>Nacionais/Internacionais<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Teams de uso de PSTN – Roteamento Direto](pstn-usage-report.md#direct-routing)  |  Carimbo de data/hora<br>Nome de exibição<br>Endereço SIP<br>Telefone número <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final da Microsoft<br>Frase SIP final<br>ID de correlação  |
|[Teams de licença de proteção de informações](information-protection-license-report.md)  | <br>Se os usuários têm licenças válidas para enviar suas mensagens por push por meio de notificações de alteração</br><br>Número total de eventos de notificação de alteração disparados por um usuário<br><br>Quais aplicativos estão escutando eventos de notificação de alteração em toda a organização<br>|
|[Teams de uso de Visitas Virtuais](virtual-visits-usage-report.md)  | Número de compromissos virtuais<br>Número de Bookings compromissos<br>Número de Teams EHR (Registros eletrônicos de integridade) integrados<br>Duração média de um compromisso<br>Tempo médio de espera do lobby dos participantes<br>Hora de início<br>ID da Reunião<br>Tempo de espera do lobby<br>Duração<br>Status<br>Tipo de produto<br>Participantes<br>SMS enviado
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados na Teams do usuário e Teams relatório de uso do dispositivo anônimo, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e Microsoft Azure Active Directory ID em relatórios e suas exportações.

1. No Centro de administração do Microsoft 365, vá para o  \> Configurações **Org Configurações** e, na **guia Serviços,** escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, escolha **Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como Teams de administração.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentirá informações [Teams](user-activity-report.md) relatório de atividade do usuário [e Teams relatório de uso do](device-usage-report.md) dispositivo. Ele não afetará outros relatórios de uso disponíveis no Teams de administração.
> Essa configuração também se aplica Microsoft 365 relatórios de uso no Centro de administração do Microsoft 365, microsoft Graph e Power BI.
