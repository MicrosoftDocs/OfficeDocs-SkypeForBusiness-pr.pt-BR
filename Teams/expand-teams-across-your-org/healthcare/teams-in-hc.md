---
title: Começar a trabalhar com o Teams para organizações de saúde
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
description: Saiba mais sobre os recursos de saúde, como a telehealth do Microsoft Teams, a integração com o EHR, a integração do sistema de trabalhadores de linha de frente e o aplicativo Pacientes.
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
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Começar a trabalhar com o Teams para organizações de saúde

O Microsoft Teams oferece vários recursos de telemedicina úteis para instituições de saúde e outras organizações de saúde. Os recursos do Teams estão em desenvolvimento para auxiliar os hospitalizados com:

- Visitas virtuais e integração com o Registro Eletrônico de Saúde (EHR)
- Pacotes de política do Teams
- Sistema de mensagens seguro
- Modelos do Teams
- Coordenação e colaboração do cuidado

Essa funcionalidade faz parte do Microsoft Cloud for Healthcare. Saiba mais sobre como usar essa solução, que reúne recursos do Azure, do Dynamics 365 e do Microsoft 365 no [Microsoft Cloud for Healthcare.](https://docs.microsoft.com/industry/healthcare)

Assista ao vídeo a seguir para saber mais sobre como usar a coleção de serviços de saúde para aprimorar a colaboração em equipe de saúde no Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> O conteúdo desta seção supõe que você já implantou o Teams em sua organização. Se você ainda não tiver lançado o Teams, comece lendo [Como lançar o Microsoft Teams.](../../How-to-roll-out-teams.md)

Os seguintes cenários estão disponíveis para organizações de saúde:

| Cenário | Descrição | Requisitos |
| -------- | -------- | -------- |
| [Visitas virtuais com integração com o Registro De Saúde Eletrônico (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e conduza visitas virtuais com pacientes. Esse cenário conecta o Microsoft Teams e a plataformaPico para dar suporte a visitas virtuais. | Assinatura ativa do Microsoft Cloud for Healthcare ou assinatura do Microsoft Teams EHR Connector oferta autônoma. <br> Os usuários devem ter uma licença apropriada do Microsoft 365 ou do Office 365 que inclua reuniões do Microsoft Teams*. <br> As organizações devem ter a versão Original de novembro de 2018 ou posterior. <br>[Detalhes dos requisitos de EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuais com o Microsoft Bookings e o aplicativo Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e conduza visitas virtuais com pacientes. Esse cenário depende do Microsoft Bookings para dar suporte a visitas virtuais. | O Microsoft Bookings deve ser ligado para a organização. <br> Todos os usuários do aplicativo Bookings e toda a equipe que participa das reuniões devem ter uma licença compatível com o agendamento de Reunião do Teams*. <br>[Detalhes dos requisitos do Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacotes de política do Teams](#teams-policy-packages)| Certifique-se de que os trabalhadores clínicos, os profissionais de informações e os dispositivos de sala de pacientes tenham o acesso apropriado à funcionalidade do Teams.| Os usuários devem ter uma licença apropriada*. |
| [Sistema de mensagens seguro](#secure-messaging) | Receba uma atenção mais rápida para mensagens urgentes e tenha certeza de que a mensagem foi recebida e lida. | Os usuários devem ter uma licença apropriada*.  |
| [Modelos do Teams](#teams-templates-for-healthcare-organizations) | Crie equipes que incluam um modelo predefinido de configurações, canais e aplicativos pré-instalados para comunicação e colaboração dentro de um departamento, um vagem ou um departamento ou entre vários locais, vagens e departamentos dentro de um hospital. | Os usuários devem ter uma licença apropriada*.  |
| [Coordenação e colaboração do cuidado](#care-coordination-and-collaboration) | Funcionários e funcionários podem colaborar internamente em cronogramas, documentos, tarefas e assim por diante.| Os usuários devem ter uma licença apropriada*. |

*O Office 365 A3, A5, E3 e E5, bem como o Microsoft 365 Business Standard, A3, A5, E3 e E5 são suportados. Para obter mais informações sobre licenciamento geral do Teams, consulte [Gerenciar o acesso do usuário ao Teams.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visitas virtuais e integração com o Registro Eletrônico de Saúde (EHR)

Use a plataforma completa de reuniões no Microsoft Teams para agendar, gerenciar e realizar visitas virtuais com pacientes.

- Se sua organização já usa registros de saúde eletrônica, ou EHR, você pode integrar o Microsoft Teams para uma experiência mais perfeita. O Microsoft Teams Electronic Health Record (EHR) Connector facilita a entrada de pacientes virtuais ou consulta com outro provedor no Teams diretamente do sistema EHR. Para saber mais, consulte [Visitas virtuais com o Teams – Integração com o EHR.](ehr-admin.md)
- Se você não estiver usando um EHR com suporte, poderá usar o Microsoft Bookings e o aplicativo Bookings no Teams. Para saber mais, confira o [aplicativo Bookings e as visitas virtuais no Microsoft Teams.](../../bookings-app-admin.md)

![Visitas virtuais com o Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacotes de política do Teams

Aplique pacotes de política do Teams para definir o que diferentes funções podem fazer no Teams. Por exemplo, especifique políticas para:

- Trabalhadores clínicos, como as médicas registradas, cobram médicos, médicos e assistentes sociais, para que eles possam ter acesso total a chats, chamada, gerenciamento de turnos e reuniões.
- Os profissionais de informações em sua organização de saúde, como funcionários de SERVIÇOS de SAÚDE, equipes de informações, funcionários financeiros e responsáveis pela conformidade, podem ter acesso total a chats, chamada e reuniões.
- Salas de pacientes para controlar as configurações de dispositivos de sala de pacientes.

Para saber mais, consulte pacotes [de política do Teams para serviços de saúde.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Sistema de mensagens seguro

As mensagens seguras são compatíveis com a colaboração dentro de equipes de saúde, incluindo vários novos recursos:

- Um remetente de mensagem pode definir uma prioridade especial para a mensagem, para que o destinatário seja notificado repetidamente até que ele leia a mensagem.
- Um remetente de mensagem pode solicitar uma confirmação de leitura, para que ele seja notificado quando uma mensagem enviada foi lida pelo destinatário da mensagem.

Juntos, esses recursos permitem uma atenção mais rápida para mensagens urgentes e a confiança de que a mensagem foi recebida e lida. Novas equipes de saúde que usam esses recursos podem ser criadas de acordo com cada paciente. Esses recursos são baseados em política e podem ser atribuídos a indivíduos ou equipes inteiras.

Para saber mais, consulte Começar a trabalhar com políticas de Sistema de Mensagens [Seguras para organizações de saúde.](messaging-policies-hc.md)

Também relacionada a mensagens seguras é a capacidade de ter outros locatários federados por organizações de saúde, permitindo uma comunicação inter locatário mais rica. (Consulte [Gerenciar acesso externo (federação) no Microsoft Teams.](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Modelos do Teams para organizações de saúde

Novos modelos para a criação do Teams foram desenvolvidos para aplicar a uma configuração do Hospital e muito mais são esperados em breve. Isso facilita a criação de equipes que os profissionais de saúde usam para coordenar o atendimento a pacientes em vários departamentos ou distritos. Para saber mais, consulte [Começar a usar modelos do Teams para organizações de saúde.](healthcare-templates.md) As equipes podem ser iniciadas para departamentos internos, como carey ou para cuidador, e mais modelos estão em desenvolvimento.

## <a name="care-coordination-and-collaboration"></a>Coordenação e colaboração do cuidado

Reunir sua equipe de saúde para coordenar o cuidado e colaborar com o Microsoft Teams.

![Saúde: Colaborar com sua equipe de saúde no Teams](../../media/teams-healthcare-collaborate-in-teams.png)

O Microsoft Teams permite que médicos, médicos, médicos, médicos e outras equipes colaborem com eficiência com recursos de colaboração incluídos no Microsoft Teams, como:

- Configurar equipes e canais para suas equipes de saúde e profissionais da informação. Use canais com guias como uma maneira de estruturar seu trabalho, com a ajuda adicional de guias para as quais eles podem fixar fontes de informações.
- Converse, poste mensagens e comunique-se. Sua equipe pode ter conversas persistentes sobre diferentes pacientes que precisam de atenção.
- Ligue e se encontre com membros da equipe de saúde. Configurar reuniões individuais ou usar reuniões de canal para gerenciar reuniões diárias, com o poder dos recursos de áudio, vídeo, compartilhamento de tela, gravação e transcrição do Teams.
- Armazene e compartilhe arquivos e documentos. Sua equipe de saúde faz parte de uma única equipe virtualizada que trabalha e colabora em documentos do Office.

Além disso, sua equipe pode usar aplicativos no Teams para:

- Compartilhar listas e controlar informações com o aplicativo Listas
- Controlar e monitorar tarefas com o aplicativo Tarefas
- Simplificar aprovações com o aplicativo Aprovações
- Criar, gerenciar e compartilhar agendas com o aplicativo Shifts

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartilhar listas e controlar informações com o aplicativo Listas

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de meleções até o monitoramento geral dos pacientes.

O aplicativo Listas no Teams ajuda as equipes a acompanhar informações e organizar o trabalho. O aplicativo é pré-instalado para todos os usuários do Teams e está disponível como uma guia em todas as equipes e canais. Listas podem ser criadas do zero, de modelos predefinidos ou importando dados para o Excel.

as equipes de saúde podem usar o modelo Pacientes para começar. Eles podem criar listas para acompanhar as necessidades e o status dos pacientes. Dados de pacientes existentes em planilhas do Excel podem ser trazidos para criar uma lista no Teams. Essas listas podem ser usadas para cenários como rounds e monitoramento de pacientes para coordenar o atendimento.

Por exemplo, uma enfermeira responsável cria uma lista de pacientes em uma equipe que inclui todos os membros da equipe de saúde. Durante as voltas, a equipe de saúde acessa o Teams em seus dispositivos móveis e atualiza as informações dos pacientes na lista, que todos na equipe podem ver para permanecerem em sincronia. Em sessões de arredondamento em que a equipe de saúde se reúne para discutir e avaliar as principais métricas de desempenho de saúde para garantir que um paciente está no caminho certo para a liberação, eles podem compartilhar essas informações usando o Teams em uma tela de exibição grande. os membros da equipe de saúde que não estão no local podem ingressar remotamente.

Aqui está uma lista de exemplos que foi configurada para arredondamento de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de tela da lista de exemplos para arredondamento de pacientes":::

Para saber mais, consulte [Gerenciar o aplicativo Listas da sua organização no Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Controlar e monitorar tarefas com o aplicativo Tarefas

Use [Tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) no Teams para acompanhar itens para toda a sua equipe de saúde. Sua equipe de saúde pode criar, atribuir e agendar tarefas, categorizar tarefas e atualizar o status a qualquer momento, em qualquer dispositivo que executa o Teams.

Para saber mais, consulte [Gerenciar o aplicativo Tarefas da sua organização no Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar aprovações com o aplicativo Aprovações

Use [Aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas as suas solicitações e processos com sua equipe. Crie, gerencie e compartilhe aprovações diretamente do seu hub para trabalhar em equipe. Inicie um fluxo de aprovação no mesmo local em que você envia um chat, em uma conversa de canal ou no próprio aplicativo Aprovações. Basta selecionar um tipo de aprovação, adicionar detalhes, anexar arquivos e escolher aprovadores. Após o envio, os aprovadores são notificados e podem revisar e agir na solicitação.

Você pode permitir o aplicativo Aprovações para sua organização e adicioná-lo às suas equipes. Para saber mais sobre como gerenciar aplicativos, consulte [Gerenciar seus aplicativos no Centro de administração do Microsoft Teams.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Criar, gerenciar e compartilhar agendas com o aplicativo Shifts e a integração com o Frontline Worker

O Microsoft Teams integra-se ao aplicativo Shifts e ao Trabalhador da Linha de Frente, que podem ser usados para coordenar os recursos de equipe de turno e muito mais. Por exemplo, no Turnos, os gerentes de enfermeira podem configurar e coordenar agendas para seus funcionários, e as médicas podem verificar agendas e trocar de turno. O Teams inclui uma política de configuração de aplicativo Frontline Worker interna que você pode atribuir aos Trabalhadores de Linha de Frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada. Essa política controla o comportamento desses aplicativos, por exemplo, fixando o aplicativo Shifts na barra de aplicativos para que a equipe possa acessá-lo rapidamente.

Para saber mais, confira [Gerenciar o aplicativo Shifts para sua organização no Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ajude seus funcionários de saúde e informações a começar a fazer isso com o Teams

Há muitos recursos disponíveis para ajudar todos os usuários de sua organização a se sentir à vontade com o uso do Teams:

- Visite o [Centro de adoção](https://adoption.microsoft.com/microsoft-teams/) do Teams para obter conselhos sobre como lançar o Teams se você estiver apenas iniciando a jornada da sua organização com o Teams ou expandindo o Teams para mais áreas da sua organização.
- Considere configurar caminhos [de aprendizagem personalizados](https://adoption.microsoft.com/microsoft-365-learning-pathways/) para que os usuários cubram apenas as tarefas que precisam fazer.
- Obter ajuda e treinamento para os usuários sobre como realizar tarefas básicas no Microsoft Teams no site de suporte do [Teams,](https://support.microsoft.com/teams)incluindo [vídeos de treinamento rápido.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Este site também tem ajuda e treinamento para os aplicativos do Teams, incluindo [Listas,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Tarefas,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Aprovações,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Reservas](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)e [Turnos.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
