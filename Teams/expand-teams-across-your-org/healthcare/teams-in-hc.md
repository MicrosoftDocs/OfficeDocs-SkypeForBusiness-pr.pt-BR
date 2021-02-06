---
title: Comece a usar o Microsoft Teams para organizações de assistência médica
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Saiba mais sobre os recursos de assistência médica, como o Microsoft Teams telehealth, a integração do EHR, a integração do sistema do Frontline Worker e o aplicativo pacientes.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125764"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Comece a usar o Microsoft Teams para organizações de assistência médica

O Microsoft Teams oferece vários recursos de telemedicina úteis para hospitais e outras organizações de assistência médica. Os recursos do teams estão em desenvolvimento para ajudar hospitais com:

- Integração de visitas virtuais e do EHR (Electronic Healthcare Record)
- Pacotes de política de equipe
- Mensagens seguras
- Modelos de equipe
- Coordenação e colaboração de cuidados

Esta funcionalidade faz parte da Microsoft Cloud para assistência médica. Saiba mais sobre como usar esta solução, que reúne recursos do Azure, do Dynamics 365 e do Microsoft 365 no [Microsoft Cloud para assistência médica](https://docs.microsoft.com/industry/healthcare).

Assista ao vídeo a seguir para saber mais sobre como usar o conjunto de assistência médica para aprimorar a colaboração da equipe de saúde no Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> O conteúdo desta seção pressupõe que você já implantou o Microsoft Teams em sua organização. Se você ainda não distribuiu o Microsoft Teams, comece lendo [como implantar o Microsoft Teams](../../How-to-roll-out-teams.md).

Os cenários a seguir estão disponíveis para as organizações de assistência médica:

| Cenário | Descrição | Requisitos |
| -------- | -------- | -------- |
| [Visitas virtuais à integração do EHR (Electronic Healthcare Record)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e realize visitas virtuais com pacientes. Esse cenário conecta o Microsoft Teams e a plataforma testamento para dar suporte a visitas virtuais. | Assinatura ativa para o Microsoft Cloud para assistência médica ou assinatura para a oferta autônoma do Microsoft Teams EHR Connector. <br> Os usuários devem ter uma licença do Microsoft 365 ou do Office 365 apropriada que inclua reuniões do Microsoft Teams *. <br> As organizações devem ter a versão testamento de novembro de 2018 ou posterior. <br>[Detalhes dos requisitos do EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuais com o Microsoft bookings e o aplicativo bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e realize visitas virtuais com pacientes. Esse cenário depende dos Microsoft bookings para dar suporte a visitas virtuais. | O Microsoft bookings deve estar ativado para a organização. <br> Todos os usuários do aplicativo reservas e todas as equipes participantes de reuniões devem ter uma licença compatível com o agendamento de reunião do teams *. <br>[Detalhes dos requisitos de reservas](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacotes de política de equipe](#teams-policy-packages)| Garantir que trabalhadores clínicos, operadores de informações e dispositivos da sala de pacientes tenham o acesso adequado à funcionalidade do teams.| Os usuários devem ter uma licença adequada *. |
| [Mensagens seguras](#secure-messaging) | Tenha uma atenção mais rápida para mensagens urgentes e tenha certeza de que a mensagem foi recebida e lida. | Os usuários devem ter uma licença adequada *.  |
| [Modelos de equipe](#teams-templates-for-healthcare-organizations) | Crie equipes que incluam um modelo predefinido de configurações, canais e aplicativos pré-instalados para comunicação e colaboração dentro de um hospital, Pod ou departamento, ou entre vários, pods e departamentos em um hospital. | Os usuários devem ter uma licença adequada *.  |
| [Coordenação e colaboração de cuidados](#care-coordination-and-collaboration) | Clínicos e funcionários podem colaborar internamente em agendas, documentos, tarefas e assim por diante.| Os usuários devem ter uma licença adequada *. |

* Office 365 a3, a5, E3 e e5, bem como o Microsoft 365 Business Standard, a3, a5, E3 e E5 são suportados. Para obter mais informações sobre o licenciamento geral do Teams, consulte [gerenciar o acesso do usuário ao Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Integração de visitas virtuais e do EHR (Electronic Healthcare Record)

Use a plataforma completa de reuniões no Microsoft Teams para agendar, gerenciar e conduzir visitas virtuais com pacientes.

- Se sua organização já usa registros de integridade eletrônicos ou o EHR, você pode integrar o Microsoft Teams para obter uma experiência mais perfeita. O conector do Microsoft Teams Electronic Health Record (EHR) facilita para os clínicos iniciarem uma visita ou consultoria do paciente virtual com outro provedor no Teams diretamente do sistema EHR. Para saber mais, consulte [visitas virtuais com o Teams-integração ao EHR](ehr-admin.md).
- Se você não estiver usando um EHR compatível, poderá usar o Microsoft bookings e o aplicativo bookings no Teams. Para saber mais, consulte [o aplicativo de livros e visitas virtuais no Microsoft Teams](../../bookings-app-admin.md).

![Visitas virtuais com o Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacotes de política de equipe

Aplicar pacotes de política de equipe para definir quais funções diferentes podem fazer no Teams. Por exemplo, especifique políticas para:

- Funcionários clínicos, como os trabalhadores registrados, a cobrar de los, médicos e trabalhadores sociais, para que eles possam ter acesso total a chats, chamadas, gerenciamento de turnos e reuniões.
- Os operadores de informações em sua organização de assistência médica, como pessoal de ti, equipe de informática, equipe de finanças e órgãos de conformidade podem ter acesso total a chats, chamadas e reuniões.
- Salas de pacientes para controlar as configurações dos dispositivos da sala de pacientes.

Para saber mais, consulte [pacotes de política de equipe para assistência médica](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Mensagens seguras

As mensagens seguras dão suporte à colaboração em equipes de saúde, incluindo vários novos recursos:

- Um remetente de mensagem pode definir uma prioridade especial para a mensagem, para que o destinatário seja repetidamente notificado até que ele leia a mensagem.
- Um remetente de mensagem pode solicitar uma confirmação de leitura para que elas sejam notificadas quando uma mensagem enviada por ele for lida pelo destinatário da mensagem.

Juntos, esses recursos permitem uma atenção mais rápida para mensagens urgentes e confiança de que a mensagem foi recebida e lida. Novas equipes de integridade que usam esses recursos podem ser criadas em uma base por paciente. Esses recursos são baseados em políticas e podem ser atribuídos a indivíduos ou a equipes inteiras.

Para saber mais, confira [introdução ao Secure Messaging Policies for Healthcare organizações](messaging-policies-hc.md).

Também relacionados a mensagens seguras é a capacidade de ter outros locatários agrupados por organizações de assistência médica, permitindo comunicações mais ricas entre os locatários. (Consulte [gerenciar o acesso externo (Federação) no Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Modelos de equipe para organizações de assistência médica

Novos modelos para a criação de equipes foram desenvolvidos para serem aplicados a uma configuração do hospital e mais esperadas em breve. Isso facilita a criação de equipes que os funcionários da área de saúde usam para coordenar o cuidado com pacientes em vários departamentos ou em diante. Para saber mais, confira [introdução aos modelos de equipe para organizações de assistência médica](healthcare-templates.md). As equipes podem ser iniciadas para departamentos internos, como cardiologia ou para portabilidade, e mais modelos estão em desenvolvimento.

## <a name="care-coordination-and-collaboration"></a>Coordenação e colaboração de cuidados

Reúna sua equipe de saúde para coordenar o cuidado e colaborar com o Microsoft Teams.

![Assistência médica: colaborar com sua equipe de saúde no Microsoft Teams](../../media/teams-healthcare-collaborate-in-teams.png)

O Microsoft Teams permite que médicos, clínicos, reprópriass e outros funcionários colaborem com eficiência com recursos de colaboração incluídos no Microsoft Teams, como:

- Configurar equipes e canais para suas equipes de saúde e operadores de informações. Use canais com guias como uma maneira de estruturar seu trabalho, com ajuda adicional das guias às quais elas podem fixar fontes de informações.
- Converse, poste mensagens e comunique-se. Sua equipe pode ter conversas persistentes sobre diferentes pacientes que precisam de atenção.
- Ligar e reunir-se com os membros da equipe de saúde. Configurar reuniões individuais ou usar reuniões de canal para gerenciar reuniões diárias, tanto com o poder do Teams, vídeo, compartilhamento de tela, gravação e recursos de transcrição.
- Armazene e compartilhe arquivos e documentos. Sua equipe de saúde faz parte de uma única equipe virtualizada que funciona e colabora em documentos do Office.

Além disso, sua equipe pode usar aplicativos no Teams para:

- Compartilhar listas e controlar informações com o aplicativo listas
- Controlar e monitorar tarefas com o aplicativo tarefas
- Simplificar as aprovações com o aplicativo aprovações
- Criar, gerenciar e compartilhar cronogramas com o aplicativo turnos

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartilhar listas e controlar informações com o aplicativo listas

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.

O aplicativo listas no Teams ajuda as equipes a acompanhar informações e organizar o trabalho. O aplicativo é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. As listas podem ser criadas do zero, de modelos predefinidos ou importando dados para o Excel.

as equipes de integridade podem usar o modelo de pacientes para começar. Elas podem criar listas para acompanhar as necessidades e o status dos pacientes. Os dados existentes do paciente em planilhas do Excel podem ser trazidos para criar uma lista no Teams. Essas listas podem ser usadas para cenários como rodadas e monitoramento de pacientes para coordenar o cuidado.

Por exemplo, um enfermeira de cobrança cria uma lista de pacientes em uma equipe que inclui todos os membros da equipe de saúde. Durante os XX, a equipe de saúde acessa as equipes em seus dispositivos móveis e atualiza as informações dos pacientes na lista, que todos os membros da equipe podem ver para permanecer em sincronização. Em sessões de arredondamento em que a equipe de saúde coleta para discutir e avaliar as principais métricas de desempenho da saúde para garantir que um paciente esteja no caminho de ponto de partida correto para a descarga, ele pode compartilhar essas informações usando o Microsoft Teams em uma tela grande de exibição. os membros da equipe de saúde que não estão no local podem ingressar remotamente.

Aqui está um exemplo de lista que foi configurada para o arredondamento de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de tela da lista de exemplos para o arredondamento de pacientes":::

Para saber mais, consulte [gerenciar o aplicativo listas para sua organização no Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Controlar e monitorar tarefas com o aplicativo tarefas

Use [tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) no Microsoft Teams para acompanhar itens em toda a sua equipe de saúde. Sua equipe de saúde pode criar, atribuir e agendar tarefas, categorizar tarefas e atualizar o status a qualquer momento, de qualquer dispositivo que esteja executando o Microsoft Teams.

Para saber mais, consulte [gerenciar o aplicativo tarefas para sua organização no Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar as aprovações com o aplicativo aprovações

Use [aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas as solicitações e processos com sua equipe. Crie, gerencie e compartilhe aprovações diretamente do seu hub para trabalho em equipe. Inicie um fluxo de aprovação do mesmo lugar em que você envia um chat, em uma conversa de canal ou a partir do aplicativo aprovações. Basta selecionar um tipo de aprovação, adicionar detalhes, anexar arquivos e escolher aprovadores. Depois de enviados, os aprovadores são notificados e podem revisar e agir na solicitação.

Você pode permitir o aplicativo aprovações para sua organização e adicioná-lo às suas equipes. Para saber mais sobre como gerenciar aplicativos, consulte [gerenciar seus aplicativos no centro de administração do Microsoft Teams](../../manage-apps.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Criar, gerenciar e compartilhar cronogramas com o aplicativo turnos e a integração com o trabalhador do Frontline

O Microsoft Teams integra-se ao aplicativo turnos e ao Frontline Worker, que pode ser usado para coordenar os recursos de pessoal de mudança e muito mais. Por exemplo, em turnos, os gerentes de enfermeira podem configurar e coordenar os cronogramas de seus funcionários, e às permutações podem verificar agendas e trocar de turno. O Microsoft Teams inclui uma política interna de configuração de aplicativo de trabalho do Frontline que você pode atribuir a trabalhadores do Frontline em sua organização. Por padrão, a política inclui os aplicativos atividade, turnos, chat e chamadas. Essa política controla o comportamento desses aplicativos, por exemplo, fixar o aplicativo turnos na barra de aplicativos para que a equipe possa acessá-lo rapidamente.

Para saber mais, consulte [gerenciar o aplicativo turnos para sua organização no Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ajude seus funcionários clínicos e de informações a se familiarizar com o Microsoft Teams

Há muitos recursos disponíveis para ajudar todos os usuários em sua organização a se sentirem confortável em usar o Microsoft Teams:

- Acesse o [centro de adoção do teams](https://adoption.microsoft.com/microsoft-teams/) para obter conselhos sobre como implantar equipes se você está apenas começando a jornada da sua organização com equipes ou expandindo o Teams em mais áreas da sua organização.
- Considere configurar os [caminhos de aprendizagem](https://adoption.microsoft.com/microsoft-365-learning-pathways/) personalizados para que seus usuários cubram apenas as tarefas que eles precisam fazer.
- Obtenha ajuda e treinamento para seus usuários sobre como executar tarefas básicas no Microsoft Teams no [site de suporte do teams](https://support.microsoft.com/teams), incluindo [vídeos de treinamento rápido](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Este site também tem ajuda e treinamento para os aplicativos do Teams, incluindo [listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [reservas](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)e [turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).
