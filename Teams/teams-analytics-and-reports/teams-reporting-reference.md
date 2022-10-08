---
title: Análise e relatórios do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: b08e62a7ddee8298ff38846d8d254d10d3d6f681
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033829"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatórios para o Microsoft Teams está disponível no centro de administração do Microsoft Teams. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando o Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e chat e os tipos de dispositivos que eles usam para se conectar ao Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões de negócios e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve ser um administrador global no Microsoft 365 ou Office 365, leitor global no Microsoft 365 ou Office 365, administrador de serviços do Teams ou Skype for Business administrador. Para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar, consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

Vá para o centro de administração do Microsoft Teams, no painel de navegação à esquerda, selecione **Relatórios do Analytics &** e, em Exibir **Relatórios, escolha** o relatório que você deseja executar.

> [!NOTE]
> Os relatórios no centro de administração do Microsoft Teams são separados dos relatórios de atividades do Teams que fazem parte dos relatórios do Microsoft 365 no Centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividades no Centro de administração do Microsoft 365, consulte [Relatórios do Microsoft 365 no centro de administração](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Referência de relatórios do Teams

Aqui está uma lista dos relatórios do Teams disponíveis no Centro de administração do Microsoft Teams em diferentes ambientes e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de relatório do Teams e adicionando recursos e funcionalidades. Ao longo do tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no centro de administração do Microsoft Teams.

|Relatório  |Público |Gcc |GCCH |Dod |O que é avaliado? |
|---------|---------|---------|---------|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |Sim|Sim|Sim|Sim|  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados ativos em uma equipe  <br/>Usuários externos ativos (em canais compartilhados)<br/>Detalhes específicos do canal compartilhado dentro de uma equipe (novo)|
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  |Sim|Sim|Sim|Sim|Usuários ativos internos e externos (em canais compartilhados)<br/> Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chamadas em que um usuário participou<br/> Número de reuniões organizadas pelo usuário <br/>Número de reuniões em que o usuário participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Data da última atividade de um usuário  <br>Interações de canal compartilhado de um usuário (novo)</br>   |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |Sim|Sim|Sim|Sim|  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso de aplicativos do Teams (novo)](app-usage-report.md)   |Sim|Sim|Não|Não|  Total de usuários ativos do aplicativo<br/>Total de equipes ativas usando o aplicativo<br/>Total de aplicativos instalados (novo)<br/>Total de aplicativos inativos <br/>Total de uso de aplicativos 1P vs 3P versus LoB (novo)     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |Sim|Sim|Não|Não|  Total de exibições<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Relatório de usuários bloqueados do PSTN do Teams](pstn-blocked-users-report.md)   |Sim|Sim|Não|Não|  Nome de exibição<br>Número de telefone<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Relatório de pools de minutos PSTN do Teams](pstn-minute-pools-report.md) |Sim|Sim|Não|Não|  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Relatório de uso de PSTN do Teams – Planos de Chamadas](pstn-usage-report.md#calling-plans)|Sim|Sim|Não|Não|  Carimbo de data/hora<br>Nome de usuário<br>Número de telefone<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>Do país ou da região<br>Carga<br>Moeda<br>Duração<br>Nacionais/Internacionais<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Relatório de uso de PSTN do Teams – Roteamento Direto](pstn-usage-report.md#direct-routing)  |Sim|Sim|Não|Não|  Carimbo de data/hora<br>Nome de exibição<br>Endereço SIP<br>Número de telefone <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcódigo final da Microsoft<br>Frase SIP final<br>ID de correlação  |
|[Relatório de licença de proteção de informações do Teams](information-protection-license-report.md)  |Sim|Sim|Não|Não| <br>Se os usuários têm licenças válidas para enviar suas mensagens por push por meio de notificações de alteração</br><br>Número total de eventos de notificação de alteração disparados por um usuário<br><br>Quais aplicativos estão escutando eventos de notificação de alteração em toda a organização<br>|
|[Relatório de uso de Visitas Virtuais do Teams](/microsoft-365/frontline/virtual-visits-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)  |Sim|Sim|Não|Não| Número de compromissos virtuais<br>Número de compromissos do Bookings<br>Número de compromissos integrados ao EHR (Registros eletrônicos de integridade) do Teams<br>Duração média de um compromisso<br>Tempo médio de espera do lobby dos participantes<br>Hora de início<br>ID da Reunião<br>Tempo de espera do lobby<br>Duração<br>Status<br>Tipo de produto<br>Participantes<br>SMS enviado
|[Relatório do conector EHR Compromissos virtuais Teams](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sim|Sim|Não|Não| Hora de início<br>Duração<br>Principal (nome do organizador da reunião)<br>Email principal (email do organizador da reunião)<br>Departamento<br>Atendentes<br>Tempo de espera do lobby<br>Se o compromisso está dentro do limite de alocação|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados no relatório de atividades do usuário do Teams anônimos, você precisa ser um administrador global. O administrador global pode ocultar informações identificáveis (usando hashes MD5), como nome de exibição, nome do grupo, email e ID do AAD no relatório e sua exportação.

1. No Centro de administração do Microsoft 365, vá para **As Configurações** \> da **Organização e,** na **guia Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida, escolha **Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentirá as informações de nome de usuário, grupo e site no relatório de atividades do usuário do [Teams](user-activity-report.md), relatório de uso de dispositivos do [Teams](device-usage-report.md) e relatório [de uso do Teams](teams-usage-report.md). A partir de 1º de setembro de 2021, essa configuração é habilitada por padrão para todos como parte do nosso compromisso contínuo de ajudar a proteger informações importantes e permitir que as empresas deem suporte às leis de privacidade locais. 
>
>Essa configuração também se aplica aos relatórios de uso do Microsoft 365 Centro de administração do Microsoft 365, Microsoft Graph e Power BI.
