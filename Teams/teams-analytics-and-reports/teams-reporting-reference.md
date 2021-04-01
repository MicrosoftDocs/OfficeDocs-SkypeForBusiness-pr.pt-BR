---
title: Análise e relatórios do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Neste artigo, você aprenderá sobre os relatórios do Teams que estão disponíveis no centro de administração do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d195c90dc7e959146546dde1a75fedf0764c24a
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478341"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Análise e relatórios do Microsoft Teams

Uma nova experiência de análise e relatórios para o Microsoft Teams está disponível no centro de administração do Microsoft Teams. Você pode executar relatórios diferentes para obter informações sobre como os usuários em sua organização estão usando o Teams. Por exemplo, você pode ver quantos usuários se comunicam por meio de mensagens de canal e de chat e os tipos de dispositivos que eles usam para se conectar ao Teams. Sua organização pode usar as informações dos relatórios para entender melhor os padrões de uso, ajudar a tomar decisões comerciais e informar os esforços de treinamento e comunicação.

## <a name="how-to-access-the-reports"></a>Como acessar os relatórios

Para acessar os relatórios, você deve ser um administrador global no Microsoft 365 ou Office 365, administrador de serviço do Teams ou administrador do Skype for Business. Para saber mais sobre as funções de administrador do Teams e quais relatórios cada função de administrador pode acessar, consulte [Use Teams administrator roles to manage Teams](../using-admin-roles.md).

Vá para o Centro de administração do Microsoft Teams, na navegação à esquerda, selecione **Análise & relatórios** e, em Relatório, escolha o relatório que deseja executar. 

> [!NOTE]
> Os relatórios no centro de administração do Microsoft Teams são separados dos relatórios de atividades do Teams que fazem parte dos relatórios do Microsoft 365 no centro de administração do Microsoft 365. Para obter mais informações sobre os relatórios de atividades no Centro de administração do Microsoft 365, consulte Relatórios de atividades do Teams no Centro de administração [do Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Referência de relatórios do Teams

Aqui está uma lista dos relatórios do Teams disponíveis no Centro de administração do Microsoft Teams e uma visão geral de algumas das informações disponíveis em cada relatório.

Estamos melhorando continuamente a experiência de relatório do Teams e adicionando recursos e funcionalidades. Com o tempo, criaremos recursos adicionais nos relatórios e adicionaremos novos relatórios no centro de administração do Microsoft Teams.

|Relatório  |O que é avaliado? |
|---------|---------|
|[Relatório de uso do Teams](teams-usage-report.md)  |  Usuários ativos<br/>Usuários ativos em equipes e canais<br/>Canais ativos<br/>Mensagens<br/>Configuração de privacidade das equipes<br/>Convidados em uma equipe   |
|[Relatório de atividades do usuário do Teams](user-activity-report.md)  | Mensagens que um usuário postou em um chat de equipe<br/>Mensagens que um usuário postou em um chat privado<br/>  1:1 chama um usuário participado<br/> Número de usuários de reunião organizados <br/>número de usuário de reunião que participou<br/>Tempo de compartilhamento de áudio, vídeo e tela de reuniões<br/>   Data da última atividade de um usuário     |
|[Relatório de uso de dispositivos do Teams](device-usage-report.md)   |  Usuários do Windows<br/>Usuários do Mac<br/>Usuários do iOS<br/>Usuários de telefone Android     |
|[Relatório de uso de evento ao vivo do Teams](teams-live-event-usage-report.md)   |  Total de exibições<br>Hora de início<br>Status do evento<br>Organizador<br>Apresentador<br>Produtor<br>Configuração de gravação<br>Tipo de produção    |
|[Relatório de usuários bloqueados do PSTN do Teams](pstn-blocked-users-report.md)   |  Nome para exibição<br>Número de telefone<br>Motivo<br>Tipo de ação<br>Data e hora da ação   |
|[Relatório de pools de minutos PSTN do Teams](pstn-minute-pools-report.md) |  País ou região<br>Funcionalidade (licença) <br>Total de minutos<br>Minutos usados<br>Minutos disponíveis|
|[Relatório de uso PSTN do Teams - Planos de Chamada](pstn-usage-report.md#calling-plans)|  Carimbo de data/hora<br>Nome de usuário<br>Número de telefone<br>Tipo de chamada <br>Chamado para<br>Para país ou região <br>Chamado de <br>Do país ou região<br>Charge<br>Moeda<br>Duração<br>Doméstico/Internacional<br>ID da chamada<br>Tipo de número<br>País ou região<br>ID de conferência<br>Funcionalidade (licença)|
|[Relatório de uso PSTN do Teams - Roteamento Direto](pstn-usage-report.md#direct-routing)  |  Carimbo de data/hora<br>Nome para exibição<br>Endereço SIP<br>Número de telefone <br>Tipo de chamada<br>Chamado para<br>Hora de início<br>Hora do convite<br>Tempo de falha<br>Hora de término<br>Duração<br>Tipo de número<br>Bypass de mídia<br>SBC FQDN<br>Região do Azure<br>Tipo de evento<br>Código SIP final<br>Subcodigo final da Microsoft<br>Frase SIP final<br>ID de correlação  |

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Tornar os dados específicos do usuário anônimos

Para tornar os dados na atividade do usuário do Teams e no relatório de uso de dispositivos do Teams anônimo, você precisa ser um administrador global. Isso ocultará informações identificáveis, como nome de exibição, email e ID do AAD em relatórios e suas exportações.

1. No Centro de administração do Microsoft 365, acesse a guia **Configurações** da Organização de Configurações e, em \>  **Serviços,** escolha **Relatórios**.
    
2. Selecione **Relatórios** e escolha Exibir **identificadores anônimos.** Essa configuração é aplicada aos relatórios de uso no Centro de administração do Microsoft 365, bem como ao Centro de administração do Teams.
  
3. Selecione **Salvar alterações**.

> [!NOTE]
> A habilitação dessa configuração desidentificá informações no relatório de atividades do [usuário do Teams](user-activity-report.md) e nos relatórios de relatório de uso do dispositivo do [Teams.](device-usage-report.md) Ele não afetará outros relatórios de uso disponíveis no Centro de administração do Teams.
