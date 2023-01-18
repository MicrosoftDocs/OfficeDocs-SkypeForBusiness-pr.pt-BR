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
- m365initiative-meetings
description: Neste artigo, você aprenderá sobre os relatórios do Teams que estão disponíveis no centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e93a34f19ecf53e05a51fe36983a9f46f741e67e
ms.sourcegitcommit: 40cba40b1babdb3fbfc1a416b7eeb0118f8353df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2023
ms.locfileid: "69820316"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatório para o Microsoft Teams está disponível no centro de administração do Microsoft Teams. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando o Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e chat e os tipos de dispositivos que eles usam para se conectar ao Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões de negócios e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve receber uma das seguintes funções:

- Administrador global.
- Administrador do Teams ou Skype for Business.
- Leitor global (somente agregação no nível do locatário e sem dados por usuário ou equipe).

Para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar, consulte [Usar funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

Vá para o centro de administração do Microsoft Teams, na navegação à esquerda, selecione **Análise & relatórios** e, em **Exibir Relatórios**, escolha o relatório que você deseja executar.

> [!NOTE]
> Os relatórios no centro de administração do Microsoft Teams são separados dos relatórios de atividades do Teams que fazem parte dos relatórios do Microsoft 365 no Centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividades no Centro de administração do Microsoft 365, consulte [Relatórios do Microsoft 365 no centro de administração](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Referência de relatório do Teams

Aqui está uma lista dos relatórios do Teams disponíveis no centro de administração do Microsoft Teams em diferentes ambientes e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de relatório do Teams e adicionando recursos e funcionalidades. Com o tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no centro de administração do Microsoft Teams.

|Relatório  |Público |GCC |GCCH |Dod |O que é avaliado? |
|---------|---------|---------|---------|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |Sim|Sim|Sim|Sim|  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados ativos em uma equipe  <br/>Usuários externos ativos (em canais compartilhados)<br/>Detalhes específicos do canal compartilhado em uma equipe (novo)|
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  |Sim|Sim|Sim|Sim|Usuários internos e externos ativos (em canais compartilhados)<br/> Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chama um usuário participante<br/> Número de reuniões organizadas pelo usuário <br/>Número de reuniões em que o usuário participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Última data de atividade de um usuário  <br>Interações de canal compartilhado de um usuário (novo)</br>   |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |Sim|Sim|Sim|Sim|  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso do aplicativo teams (novo)](app-usage-report.md)   |Sim|Sim|Não|Não|  Total de usuários ativos do aplicativo<br/>Total de equipes ativas usando o aplicativo<br/>Total de aplicativos instalados (novo)<br/>Total de aplicativos inativos <br/>Uso total do aplicativo 1P vs 3P vs LoB (novo)     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |Sim|Sim|Não|Não|  Exibições totais<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Relatório de usuários bloqueados do Teams PSTN](pstn-blocked-users-report.md)   |Sim|Sim|Não|Não|  Nome da exibição<br>Número de telefone<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Relatório de pools de minutos PSTN do Teams](pstn-minute-pools-report.md) |Sim|Sim|Não|Não|  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Relatório de uso PSTN do Teams – Chamando Planos](pstn-usage-report.md#calling-plans)|Sim|Sim|Não|Não|  Carimbo de hora<br>Nome de usuário<br>Número de telefone<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>De país ou região<br>Carga<br>Moeda<br>Duração<br>Doméstico/Internacional<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Relatório de uso PSTN do Teams – Roteamento Direto](pstn-usage-report.md#direct-routing)  |Sim|Sim|Não|Não|  Carimbo de hora<br>Nome da exibição<br>Endereço SIP<br>Número de telefone <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcodificado final da Microsoft<br>Frase FINAL SIP<br>ID de correlação  |
|[Relatório de licença de proteção de informações do Teams](information-protection-license-report.md)  |Sim|Sim|Não|Não| <br>Se os usuários têm licenças válidas para enviar suas mensagens por meio de notificações de alteração</br><br>Número total de eventos de notificação de alteração disparados por um usuário<br><br>Quais aplicativos estão ouvindo eventos de notificação de alterações em toda a organização<br>|
|[Relatório de uso do Teams Compromissos virtuais](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|Sim|Sim|Não|Não| Número de compromissos virtuais<br>Número de compromissos de Reservas<br>Número de compromissos integrados do Teams Electronic Health Records (EHR)<br>Duração média de um compromisso<br>Tempo médio de espera do lobby dos participantes<br>Hora de início<br>ID da reunião<br>Tempo de espera do lobby<br>Duração<br>Status<br>Tipo de produto<br>Participantes<br>Departamento<br>SMS enviado<br>Se o compromisso usou uma funcionalidade de Compromissos virtuais avançada|
|[Relatório de atividades do Teams Advanced Compromissos virtuais](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sim|Sim|Não|Não|Número de usuários usando recursos avançados de Compromissos virtuais<br>Número de usuários que usam notificações de texto SMS<br>Número de usuários que usam chat de lobby (em breve)<br>Número de usuários que realizam compromissos sob demanda|
|[Relatório Compromissos virtuais do conector do Teams EHR](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Sim|Sim|Não|Não| Hora de início<br>Duração<br>Primário (nome do organizador da reunião)<br>Email da primária (email do organizador da reunião)<br>Departamento<br>Atendentes<br>Tempo de espera do lobby<br>Se o compromisso está dentro do limite de alocação|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar as informações identificáveis em relatórios de uso anônimas, você precisa ser um Administrador global. O Administrador global pode ocultar informações identificáveis (usando hashes MD5), como nome de exibição, nome do grupo, email e ID do AAD no relatório e sua exportação.

1. Em Centro de administração do Microsoft 365, acesse as **Configurações** \> **de Organização** e, na guia **Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e, em seguida **, escolha Exibir nomes de usuário, grupo e site ocultos em todos os relatórios**. Essa configuração é aplicada tanto aos relatórios de uso no Centro de administração do Microsoft 365 quanto ao centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilitar essa configuração desidentifirá informações de usuário, grupo e nome do site no [relatório de atividade do usuário do Teams](user-activity-report.md), [no relatório de uso do dispositivo do Teams](device-usage-report.md) e [no relatório de uso do Teams](teams-usage-report.md). A partir de 1º de setembro de 2021, essa configuração está habilitada por padrão para todos como parte de nosso compromisso contínuo de ajudar a proteger informações importantes e permitir que as empresas apoiem suas leis de privacidade local. 
>
>Essa configuração também se aplica aos relatórios de uso do Microsoft 365 em Centro de administração do Microsoft 365, Microsoft Graph e Power BI.
