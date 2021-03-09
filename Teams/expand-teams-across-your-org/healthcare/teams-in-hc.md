---
title: Começar com o Teams para organizações de saúde
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
description: Saiba mais sobre recursos de saúde, como teleaqueleto do Microsoft Teams, integração com OHR, integração com o sistema de trabalho frontline e o aplicativo Patients.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 1bf890c7ffb6fa13730870cb1f4eabecb5df7c85
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558380"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Começar com o Teams para organizações de saúde

O Microsoft Teams oferece vários recursos de telemedicina úteis para hospitais e outras organizações de Saúde. Os recursos do Teams estão em desenvolvimento para ajudar os hospitais com:

- Visitas virtuais e integração com o Registro Eletrônico de Saúde (EHR)
- Pacotes de política do Teams
- Mensagens seguras
- Modelos do Teams
- Coordenação e colaboração do cuidado

Essa funcionalidade faz parte do Microsoft Cloud for Healthcare. Saiba mais sobre como usar essa solução, que reúne recursos do Azure, do Dynamics 365 e do Microsoft 365 no [Microsoft Cloud for Healthcare.](https://docs.microsoft.com/industry/healthcare)

Assista ao vídeo a seguir para saber mais sobre como usar a coleção de cuidados de saúde para aprimorar a colaboração da equipe de saúde no Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> O conteúdo desta seção supõe que você já implantou o Teams em sua organização. Se você ainda não tiver lançado o Teams, comece lendo [Como lançar o Microsoft Teams](../../How-to-roll-out-teams.md).

Os seguintes cenários estão disponíveis para organizações de saúde:

| Cenário | Descrição | Requisitos |
| -------- | -------- | -------- |
| [Visitas virtuais com integração do Registro Eletrônico de Saúde (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e conduza visitas virtuais com os pacientes. Este cenário conecta o Microsoft Teams e a plataforma Épico para dar suporte a visitas virtuais. | Assinatura ativa do Microsoft Cloud for Healthcare ou assinatura da oferta autônoma do Microsoft Teams EHR Connector. <br> Os usuários devem ter uma licença apropriada do Microsoft 365 ou office 365 que inclua reuniões do Microsoft Teams*. <br> As organizações devem ter com a versão Épica de novembro de 2018 ou posterior. <br>[Detalhes para requisitos de EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuais com o Microsoft Bookings e o aplicativo Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agende, gerencie e conduza visitas virtuais com os pacientes. Esse cenário depende do Microsoft Bookings para dar suporte a visitas virtuais. | O Microsoft Bookings deve estar ligado para a organização. <br> Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões devem ter uma licença que dá suporte ao agendamento de Reuniões do Teams*. <br>[Detalhes dos requisitos do Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacotes de política do Teams](#teams-policy-packages)| Certifique-se de que os funcionários, funcionários da informação e dispositivos de sala de pacientes tenham o acesso apropriado à funcionalidade do Teams.| Os usuários devem ter uma licença apropriada*. |
| [Mensagens seguras](#secure-messaging) | Tenha mais atenção para mensagens urgentes e tenha confiança de que a mensagem foi recebida e lida. | Os usuários devem ter uma licença apropriada*.  |
| [Modelos do Teams](#teams-templates-for-healthcare-organizations) | Crie equipes que incluam um modelo predefinido de configurações, canais e aplicativos pré-instalados para comunicação e colaboração dentro de uma ala, pod ou departamento ou entre várias alas, pods e departamentos dentro de um hospital. | Os usuários devem ter uma licença apropriada*.  |
| [Coordenação e colaboração do cuidado](#care-coordination-and-collaboration) | Os médicos e funcionários podem colaborar internamente em cronogramas, documentos, tarefas e assim por diante.| Os usuários devem ter uma licença apropriada*. |

*O Office 365 A3, A5, E3 e E5, bem como o Microsoft 365 Business Standard, A3, A5, E3 e E5 são suportados. Para obter mais informações sobre o licenciamento geral do Teams, consulte [Manage user access to Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visitas virtuais e integração com o Registro Eletrônico de Saúde (EHR)

Use a plataforma de reuniões completa no Microsoft Teams para agendar, gerenciar e realizar visitas virtuais com os pacientes.

- Se sua organização já usa Registros Eletrônicos de Saúde ou EHR, você pode integrar o Microsoft Teams para uma experiência mais perfeita. O Conector do Registro Eletrônico de Saúde (EHR) do Microsoft Teams facilita o início de uma visita de paciente virtual ou consulta a outro provedor no Teams diretamente do sistema EHR. Para saber mais, confira [Visitas virtuais com o Teams - Integração ao EHR](ehr-admin.md).
- Se você não estiver usando um EHR com suporte, poderá usar o Microsoft Bookings e o aplicativo Bookings no Teams. Para saber mais, confira [Bookings app and virtual visits in Microsoft Teams](../../bookings-app-admin.md).

![Visitas virtuais com o Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacotes de política do Teams

Aplique pacotes de política do Teams para definir o que funções diferentes podem fazer no Teams. Por exemplo, especifique políticas para:

- Os funcionários médicos, como as enfermeiras registradas, os técnicos de carga, os médicos e os assistentes sociais, podem ter acesso total ao chat, chamada, gerenciamento de turnos e reuniões.
- Os funcionários de informações em sua organização de saúde, como funcionários de SERVIÇOS, equipe de informática, equipe de finanças e agentes de conformidade, podem ter acesso total a chat, chamada e reuniões.
- Salas de pacientes, para controlar as configurações de dispositivos de sala do paciente.

Para saber mais, confira [Pacotes de política do Teams para assistência médica.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Mensagens seguras

As mensagens seguras suportam a colaboração dentro de equipes de saúde, incluindo vários novos recursos:

- Um remetente de mensagem pode definir uma prioridade especial para sua mensagem, para que o destinatário seja notificado repetidamente até ler a mensagem.
- Um remetente de mensagem pode solicitar um recibo de leitura, para que eles sejam notificados quando uma mensagem enviada foi lida pelo destinatário da mensagem.

Juntos, esses recursos permitem uma atenção mais rápida a mensagens urgentes e a confiança de que a mensagem foi recebida e lida. Novas equipes de saúde usando esses recursos podem ser criadas por paciente. Esses recursos são baseados em política e podem ser atribuídos a indivíduos ou a todo o Teams.

Para saber mais, confira Começar com políticas de [Mensagens Seguras para organizações de saúde.](messaging-policies-hc.md)

Também relacionado a mensagens seguras é a capacidade de ter outros locatários federados por organizações de saúde, permitindo maior comunicação entre locatários. (Consulte [Gerenciar acesso externo (federação) no Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Modelos do Teams para organizações de saúde

Novos modelos para a criação do Teams foram desenvolvidos para aplicar a uma configuração de Hospital e mais são esperados em breve. Isso facilita a criação de equipes que os funcionários de Saúde usam para coordenar o atendimento aos pacientes em vários departamentos ou alas. Para saber mais, confira [Começar a usar modelos do Teams para organizações de saúde.](healthcare-templates.md) As equipes podem ser iniciadas para departamentos internos, como a cardiologia, ou para as alas de cuidado, e mais modelos estão em desenvolvimento.

## <a name="care-coordination-and-collaboration"></a>Coordenação e colaboração do cuidado

Reunir sua equipe de saúde para coordenar o cuidado e colaborar com o Microsoft Teams.

![Assistência médica: colaborar com sua equipe de saúde no Teams](../../media/teams-healthcare-collaborate-in-teams.png)

O Microsoft Teams permite que médicos, médicos, médicos, médicos e outras equipes colaborem de forma eficiente com recursos de colaboração incluídos no Microsoft Teams, como:

- Configurar equipes e canais para suas equipes de saúde e funcionários de informações. Use canais com guias como uma maneira de estruturar seu trabalho, com ajuda adicional de guias para as quais eles podem fixar fontes de informações.
- Chat, postagem de mensagens e comunicação. Sua equipe pode ter conversas persistentes sobre diferentes pacientes que precisam de atenção.
- Chame e se encontre com membros da equipe de saúde. Configurar reuniões individuais ou usar reuniões de canal para gerenciar reuniões diárias, com o poder dos recursos de áudio, vídeo, compartilhamento de tela, gravação e transcrição do Teams.
- Armazenar e compartilhar arquivos e documentos. Sua equipe de saúde faz parte de uma única equipe virtualizada que funciona e colabora em documentos do Office.

Além disso, sua equipe pode usar aplicativos no Teams para:

- Compartilhar listas e acompanhar informações com o aplicativo Listas
- Controlar e monitorar tarefas com o aplicativo Tarefas
- Simplificar aprovações com o aplicativo Aprovações
- Criar, gerenciar e compartilhar agendamentos com o aplicativo Shifts

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartilhar listas e acompanhar informações com o aplicativo Listas

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Patients foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que vão de reuniões de equipe interdisciplinar e de equipe interdisciplinar até o monitoramento geral de pacientes.

O aplicativo Listas no Teams ajuda as equipes a controlar informações e organizar o trabalho. O aplicativo é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. As listas podem ser criadas do zero, de modelos predefinidos ou importando dados para o Excel.

as equipes de saúde podem usar o modelo Patients para começar. Eles podem criar listas para acompanhar as necessidades e o status dos pacientes. Dados de pacientes existentes em planilhas do Excel podem ser trazidos para criar uma lista no Teams. Essas listas podem ser usadas para cenários como rodadas e monitoramento de pacientes para coordenar o cuidado.

Por exemplo, uma ama de cobrança cria uma lista de pacientes em uma equipe que inclui todos os membros da equipe de saúde. Durante as rodadas, a equipe de saúde acessa o Teams em seus dispositivos móveis e atualiza as informações do paciente na lista, que todos na equipe podem ver para permanecer em sincronia. Em sessões de arredondamento em que a equipe de saúde se reúne para discutir e avaliar as principais métricas de desempenho de saúde para garantir que um paciente está no caminho certo para a liberação, eles podem compartilhar essas informações usando o Teams em uma tela de exibição grande. os membros da equipe de saúde que não estão no site podem ingressar remotamente.

Aqui está uma lista de exemplos que foi configurada para arredondamento de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de tela da lista de exemplos para arredondamento de pacientes":::

Para saber mais, confira [Gerenciar o aplicativo Listas para sua organização no Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Controlar e monitorar tarefas com o aplicativo Tarefas

Use [Tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) no Teams para rastrear itens de tarefas para toda a sua equipe de saúde. Sua equipe de saúde pode criar, atribuir e agendar tarefas, categorizar tarefas e atualizar o status a qualquer momento, de qualquer dispositivo que executa o Teams.

Para saber mais, confira [Gerenciar o aplicativo Tarefas para sua organização no Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar aprovações com o aplicativo Aprovações

Use [Aprovações para](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) simplificar todas as suas solicitações e processos com sua equipe. Crie, gerencie e compartilhe aprovações diretamente do hub para trabalho em equipe. Inicie um fluxo de aprovação no mesmo local em que você envia um chat, em uma conversa de canal ou no próprio aplicativo Aprovações. Basta selecionar um tipo de aprovação, adicionar detalhes, anexar arquivos e escolher aprovadores. Depois de enviado, os aprovadores são notificados e podem revisar e agir na solicitação.

Você pode permitir o aplicativo Aprovações para sua organização e adicioná-lo às suas equipes. Para saber mais, confira [Disponibilidade do aplicativo Aprovações do Teams.](../../approval-admin.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Criar, gerenciar e compartilhar agendamentos com o aplicativo Shifts e a integração do Trabalho de Linha de Frente

O Microsoft Teams se integra ao aplicativo Shifts e ao Trabalho de Linha de Frente, que podem ser usados para coordenar os recursos de equipe de turno e muito mais. Por exemplo, em Turnos, os gerentes de enfermagem podem configurar e coordenar agendamentos para sua equipe, e os funcionários podem verificar os horários e os turnos de troca. O Teams inclui uma política interna de configuração de aplicativos de Trabalho de Linha de Frente que você pode atribuir aos Trabalhadores de Linha de Frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada. Essa política controla o comportamento desses aplicativos, por exemplo, fixar o aplicativo Shifts na barra de aplicativos para que a equipe possa acessá-lo rapidamente.

Para saber mais, consulte [Manage the Shifts app for your organization in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ajudar seus funcionários de informações e clínicas a começar a ir com o Teams

Há muitos recursos disponíveis para ajudar todos os usuários em sua organização a se sentir confortáveis com o uso do Teams:

- Visite o [Centro de](https://adoption.microsoft.com/microsoft-teams/) adoção do Teams para obter conselhos sobre a implantação do Teams se você estiver apenas iniciando a jornada da sua organização com o Teams ou expandindo o Teams para mais áreas da sua organização.
- Considere configurar caminhos [de aprendizado personalizados](https://adoption.microsoft.com/microsoft-365-learning-pathways/) para que seus usuários cubram apenas as tarefas que precisam fazer.
- Obter ajuda e treinamento para seus usuários sobre como executar tarefas básicas no Microsoft Teams no site de suporte do [Teams,](https://support.microsoft.com/teams)incluindo [vídeos de treinamento rápido.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Este site também tem ajuda e treinamento para os aplicativos do Teams, incluindo [Listas,](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) [Tarefas,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Aprovações,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Reservas](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)e [Turnos.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
