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
ms.openlocfilehash: b773b2d214bd105b8ca94850c0ddbc6e8c23757a
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556352"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatório para Microsoft Teams está disponível no centro de administração Microsoft Teams local. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e de chat e os tipos de dispositivos que eles usam para se conectar a Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões comerciais e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve ser um administrador global no Microsoft 365 ou Office 365, leitor global no Microsoft 365 ou Office 365, administrador de serviço Teams ou administrador Skype for Business. Para saber mais sobre Teams de administrador e quais relatórios cada função de administrador pode acessar, consulte [Use Teams funções](../using-admin-roles.md) de administrador para gerenciar Teams.

Vá para o Microsoft Teams de administração, na navegação à esquerda, selecione **Relatórios** de análise & e, em **Exibir** Relatórios, escolha o relatório que deseja executar.

> [!NOTE]
> Os relatórios no centro de administração Microsoft Teams são separados dos relatórios de atividades para Teams que fazem parte dos relatórios Microsoft 365 no Centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividades no Centro de administração do Microsoft 365, [consulte Teams relatórios de atividade no Centro de administração do Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams de relatórios

Aqui está uma lista dos relatórios de Teams disponíveis no centro de administração Microsoft Teams e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de relatório Teams e adicionando recursos e funcionalidades. Com o tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no Microsoft Teams de administração.

|Relatório  |O que é avaliado? |
|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados em uma equipe   |
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  | Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chama um usuário participado<br/> Número de reuniões organizadas pelo usuário <br/>Número de reuniões que o usuário participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Data da última atividade de um usuário     |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |  Total de exibições<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Teams relatório de usuários bloqueados PSTN](pstn-blocked-users-report.md)   |  Nome para exibição<br>Telefone número<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Teams pools de minutos PSTN](pstn-minute-pools-report.md) |  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Teams de uso PSTN - Planos de Chamada](pstn-usage-report.md#calling-plans)|  Carimbo de data/hora<br>Nome de usuário<br>Telefone número<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>Do país ou região<br>Charge<br>Moeda<br>Duração<br>Doméstico/Internacional<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Teams de uso PSTN - Roteamento Direto](pstn-usage-report.md#direct-routing)  |  Carimbo de data/hora<br>Nome para exibição<br>Endereço SIP<br>Telefone número <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcodigo final da Microsoft<br>Frase SIP final<br>ID de correlação  |
|[Teams relatório de licença de proteção de informações](information-protection-license-report.md)  | <br>Se os usuários têm licenças válidas para enviar suas mensagens por meio de notificações de alteração</br><br>Número total de eventos de notificação de alteração disparados por um usuário<br><br>Quais aplicativos estão escutando eventos de notificação de alterações em toda a organização<br>|
|[Teams relatório de uso de Visitas Virtuais](virtual-visits-usage-report.md)  | Número de visitas virtuais<br>Número de Bookings visitas<br>Número de Teams EHR (Registros Eletrônicos de Saúde) integrados<br>Duração média de uma visita<br>Tempo médio de espera do lobby dos participantes<br>Hora de início<br>ID da Reunião<br>Tempo de espera do lobby<br>Duração<br>Status<br>Tipo de produto<br>Participantes<br>SMS enviado
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados na Teams do usuário e Teams relatório de uso do dispositivo anônimo, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e Microsoft Azure Active Directory ID em relatórios e suas exportações.

1. Em Centro de administração do Microsoft 365, vá **para a Configurações** \> **Org Configurações** e, em **Serviços**, escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir nomes de usuário, grupo e site ocultos **em todos os relatórios**. Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como Teams centro de administração.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> Habilenciar essa configuração desidentificá-Teams relatório de atividade do usuário [e Teams](device-usage-report.md) relatório de uso do dispositivo.[](user-activity-report.md) Ele não afetará outros relatórios de uso disponíveis Teams centro de administração.
> Essa configuração também se aplica Microsoft 365 relatórios de uso em Centro de administração do Microsoft 365, microsoft Graph e Power BI.
