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
description: Neste artigo, você aprenderá sobre os relatórios do Teams que estão disponíveis no centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0891b9267039d8c07d437cb8e67eb2b982a0016
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883544"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatórios para o Microsoft Teams está disponível no centro de administração do Microsoft Teams. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando o Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e chat e os tipos de dispositivos que eles usam para se conectar ao Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões de negócios e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve ser um administrador global no Microsoft 365 ou Office 365, leitor global no Microsoft 365 ou Office 365, administrador de serviços do Teams ou administrador do Skype for Business. Para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar, consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

Vá para o centro de administração do Microsoft Teams, no painel de navegação à esquerda, selecione **Relatórios do Analytics &** e, em Exibir **Relatórios, escolha** o relatório que você deseja executar.

> [!NOTE]
> Os relatórios no centro de administração do Microsoft Teams são separados dos relatórios de atividades do Teams que fazem parte dos relatórios do Microsoft 365 no Centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividades no Centro de administração do Microsoft 365, consulte relatórios de atividades do Teams no Centro de administração [do Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Referência de relatórios do Teams

Aqui está uma lista dos relatórios do Teams disponíveis no Centro de administração do Microsoft Teams e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de relatório do Teams e adicionando recursos e funcionalidades. Ao longo do tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no centro de administração do Microsoft Teams.

|Relatório  |O que é avaliado? |
|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados em uma equipe   |
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  | Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chamadas em que um usuário participou<br/> Número de reuniões organizadas pelo usuário <br/>Número de reuniões em que o usuário participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Data da última atividade de um usuário     |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |  Total de exibições<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Relatório de usuários bloqueados do PSTN do Teams](pstn-blocked-users-report.md)   |  Nome de exibição<br>Número de telefone<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Relatório de pools de minutos PSTN do Teams](pstn-minute-pools-report.md) |  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Relatório de uso de PSTN do Teams – Planos de Chamadas](pstn-usage-report.md#calling-plans)|  Carimbo de data/hora<br>Nome de usuário<br>Número de telefone<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>Do país ou da região<br>Carga<br>Moeda<br>Duração<br>Nacionais/Internacionais<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Relatório de uso de PSTN do Teams – Roteamento Direto](pstn-usage-report.md#direct-routing)  |  Carimbo de data/hora<br>Nome de exibição<br>Endereço SIP<br>Número de telefone <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final da Microsoft<br>Frase SIP final<br>ID de correlação  |
|[Relatório de licença de proteção de informações do Teams](information-protection-license-report.md)  | <br>Se os usuários têm licenças válidas para enviar suas mensagens por push por meio de notificações de alteração</br><br>Número total de eventos de notificação de alteração disparados por um usuário<br><br>Quais aplicativos estão escutando eventos de notificação de alteração em toda a organização<br>|
|[Relatório de uso de Visitas Virtuais do Teams](virtual-visits-usage-report.md)  | Número de compromissos virtuais<br>Número de compromissos do Bookings<br>Número de compromissos integrados ao EHR (Registros eletrônicos de integridade) do Teams<br>Duração média de um compromisso<br>Tempo médio de espera do lobby dos participantes<br>Hora de início<br>ID da Reunião<br>Tempo de espera do lobby<br>Duração<br>Status<br>Tipo de produto<br>Participantes<br>SMS enviado
|[Relatório de Compromissos Virtuais do conector EHR do Teams](../expand-teams-across-your-org/healthcare/ehr-admin-reports.md) | Hora de início<br>Duração<br>Principal (nome do organizador da reunião)<br>Email principal (email do organizador da reunião)<br>Departamento<br>Atendentes<br>Tempo de espera do lobby<br>Se o compromisso está dentro do limite de alocação
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados na atividade do usuário do Teams e no relatório de uso de dispositivos do Teams anônimos, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e ID do Microsoft Azure Active Directory em relatórios e suas exportações.

1. No Centro de administração do Microsoft 365, vá  \> para As Configurações da Organização **e, na** guia Serviços, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, escolha **Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentirá as informações no relatório [de atividades do usuário do Teams](user-activity-report.md) e nos relatórios [de uso de dispositivos do Teams](device-usage-report.md) . Ele não afetará outros relatórios de uso disponíveis no Centro de administração do Teams.
> Essa configuração também se aplica aos relatórios de uso do Microsoft 365 no Centro de administração do Microsoft 365, no Microsoft Graph e no Power BI.
