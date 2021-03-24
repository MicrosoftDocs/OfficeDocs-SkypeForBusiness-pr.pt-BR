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
description: Aprenda sobre recursos de saúde como a telessaúde do Microsoft Teams, a integração EHR, a integração do sistema de trabalhador na linha de frente e o aplicativo Pacientes.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 00dbf546166dbc1fd40d633516ac77ffaff3774c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092679"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Começar com o Teams para organizações de saúde

O Microsoft Teams oferece vários recursos de telemedicina úteis para hospitais e outras organizações de saúde. Os recursos do Teams estão em desenvolvimento para ajudar hospitais em:

- Integração das visitas virtuais e do Registro Eletrônico de Saúde (EHR)
- Pacotes de políticas do Teams
- Mensagens seguras
- Modelos do Teams
- Coordenação e colaboração do cuidado

Esta funcionalidade faz parte do Microsoft Cloud for Healthcare. Saiba mais sobre como usar esta solução, que une os recursos do Azure, Dynamics 365 e Microsoft 365 no [Microsoft Cloud for Healthcare](/industry/healthcare).

Assista ao vídeo a seguir para saber mais sobre como usar a coleção de saúde para melhorar a colaboração em equipe de saúde no Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> O conteúdo nesta seção presume que você já implantou o Teams em sua organização. Se você ainda não implantou o Teams, comece lendo [Como implantar o Microsoft Teams](../../deploy-overview.md).

Os cenários a seguir estão disponíveis para organizações de saúde:

| Cenário | Descrição | Requisitos |
| -------- | -------- | -------- |
| [Integração das visitas virtuais e do Registro Eletrônico de Saúde (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agendar, gerenciar e conduzir visitas virtuais com pacientes. Este cenário conecta o Microsoft Teams e a plataforma Epic para dar suporte às visitas virtuais. | Uma assinatura ativa do Microsoft Cloud for Healthcare ou uma assinatura da oferta autônoma do Conector EHR do Microsoft Teams. <br> Os usuários devem ter uma licença apropriada do Microsoft 365 ou do Office 365 que inclua reuniões* do Microsoft Teams. <br> As organizações devem ter a versão do Epic de novembro de 2018 ou posterior. <br>[Detalhes dos requisitos EHR](ehr-admin.md#before-you-begin) |
| [Visitas virtuais com o Microsoft Bookings e o aplicativo Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Agendar, gerenciar e conduzir visitas virtuais com pacientes. Este cenário depende do Microsoft Bookings para dar suporte às visitas virtuais. | O Microsoft Bookings deve ser ativado para a organização. <br> Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões devem ter uma licença com suporte para o agendamento* de Reunião no Teams. <br>[Detalhes dos requisitos do Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Pacotes de políticas do Teams](#teams-policy-packages)| Garanta que os funcionários da saúde, operadores de informações e dispositivos da sala do paciente tenham acesso apropriado à funcionalidade do Teams.| Os usuários devem ter uma licença apropriada*. |
| [Mensagens seguras](#secure-messaging) | Obtenha atenção às mensagens urgentes com mais rapidez e tenha a certeza de que a mensagem foi recebida e lida. | Os usuários devem ter uma licença apropriada*.  |
| [Modelos do Teams](#teams-templates-for-healthcare-organizations) | Crie equipes que incluam um modelo predefinido de configurações, canais e aplicativos instalados previamente para se comunicar e colaborar com uma ala, câmara ou departamento ou entre várias alas, câmaras e departamentos em um hospital. | Os usuários devem ter uma licença apropriada*.  |
| [Coordenação e colaboração do cuidado](#care-coordination-and-collaboration) | Os médicos e funcionários podem colaborar internamente em agendas, documentos, tarefas e muito mais.| Os usuários devem ter uma licença apropriada*. |

*O Office 365 A3, A5, E3 e E5, assim como o Microsoft 365 Business Standard, A3, A5, E3 e E5 têm suporte. Para obter mais informações sobre licenciamento geral do Teams, consulte [Gerenciar o acesso do usuário ao Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Integração das visitas virtuais e do Registro Eletrônico de Saúde (EHR)

Use a plataforma completa de reuniões no Microsoft Teams para agendar, gerenciar e conduzir visitas virtuais com pacientes.

- Se sua organização já utiliza os Registros Eletrônicos de Saúde, ou EHR, você pode integrar o Microsoft Teams para ter uma experiência mais uniforme. O Conector do Registro Eletrônico de Saúde (EHR) do Microsoft Teams facilita para os médicos a inicialização de uma visita virtual ou consulta com outro provedor no Teams diretamente do sistema EHR. Para saber mais, consulte [Visitas virtuais com o Teams - Integração com EHR](ehr-admin.md).
- Se você não estiver usando um EHR com suporte, poderá usar o Microsoft Bookings e o aplicativo Bookings no Teams. Para saber mais, confira [Aplicativo Bookings e visitas virtuais no Microsoft Teams](../../bookings-app-admin.md).

![Visitas virtuais com o Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Pacotes de políticas do Teams

Aplicar os pacotes de políticas do Teams para definir o que diferentes funções podem fazer no Teams. Por exemplo, especifique as políticas para:

- Funcionários da saúde, como enfermeiros registrados, enfermeiros chefe, médicos e assistentes sociais, para que eles tenham acesso total ao chat, chamadas, gerenciamento de turnos e reuniões.
- Os operadores de informações na sua organização de saúde, como equipe de TI, de informática, equipe financeira e responsáveis pela conformidade podem ter acesso total ao chat, chamadas e reuniões.
- Sala dos pacientes, para controlar as configurações dos dispositivos da sala do paciente.

Para saber mais, confira [Pacotes de políticas do Teams para a saúde](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Mensagens seguras

As mensagens seguras dão suporte a colaboração em equipes de saúde, incluindo vários recursos novos:

- Um remetente pode definir uma prioridade especial para sua mensagem para que o destinatário seja notificado repetidamente até que leia a mensagem.
- Um remetente pode solicitar uma confirmação de leitura para que seja notificado quando a mensagem que ele enviou for lida pelo destinatário da mensagem.

Juntos, esses recursos permitem uma atenção mais rápida a mensagens urgentes e certeza de que a mensagem foi recebida e lida. Novas equipes de saúde que usam esses recursos podem ser criadas para cada paciente que precisar. Esses recursos são baseados na política e podem ser atribuídos a indivíduos ou equipes inteiras.

Para saber mais, confira [Introdução às políticas de Mensagens Seguras para Organizações de Saúde](messaging-policies-hc.md).

Além disso, a capacidade de ter outros locatários federados por organizações de saúde está relacionada às mensagens seguras, permitindo uma comunicação mais avançada entre locatários. (Confira [ Gerenciar o acesso externo (federação) no Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Modelos do Teams para organizações de saúde

Desenvolvemos novos modelos para criar equipes para aplicar a um cenário hospitalar e mais serão apresentados em breve. Isso facilita a criação de equipes que os funcionários da saúde usarão para coordenar o cuidado de pacientes em vários departamentos ou alas. Para saber mais, confira [Introdução aos modelos do Teams para Organizações de Saúde](./healthcare-templates-admin-console.md). O Teams pode ser iniciado para departamentos internos, como cardiologia ou para alas de cuidado, e mais modelos estão em desenvolvimento.

## <a name="care-coordination-and-collaboration"></a>Coordenação e colaboração do cuidado

Reúna sua equipe de saúde para coordenar o cuidado o colaborar com o Microsoft Teams.

![Saúde: colabore com sua equipe de saúde no Teams](../../media/teams-healthcare-collaborate-in-teams.png)

O Microsoft Teams permite que os médicos, clínicos, enfermeiros e outros funcionários colaborem de forma eficiente com recursos de colaboração incluídos no Microsoft Teams, como:

- Configurar equipes e canais para suas equipes de saúde e operadores de informações. Utilizar os canais com guias como uma forma de estruturar o trabalho, com ajuda adicional de guias em que eles podem fixar fontes de informações.
- Conversar, postar mensagens e se comunicar. Sua equipe pode ter conversas persistentes sobre pacientes diferentes que precisam de atenção.
- Chamar e se reunir com membros da equipe de saúde. Organizar reuniões individuais ou usar reuniões de canal para gerenciar reuniões diárias, com o poder dos recursos de áudio, vídeo, compartilhamento de tela, gravação e transcrição do Teams.
- Armazenar e compartilhar arquivos e documentos. Sua equipe de saúde faz parte de uma única equipe virtualizada que trabalha e colabora em documentos do Office.

Além disso, sua equipe pode usar aplicativos no Teams para:

- Compartilhar listas e acompanhar informações com o aplicativo Listas
- Acompanhar e monitorar tarefas com o aplicativo Tarefas
- Simplificar as aprovações com o aplicativo Aprovações
- Criar, gerenciar e compartilhar agendas com o aplicativo Turnos

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Compartilhar listas e acompanhar informações com o aplicativo Listas

> [!NOTE]
> Em 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com o Listas, as equipes de cuidado na sua organização de saúde podem criar listas de pacientes para cenários de rondas e reuniões de equipe interdisciplinar e monitoramento geral de pacientes.

O aplicativo Listas no Microsoft Teams ajuda os usuários da sua organização a controlar informações, organizar o trabalho e gerenciar fluxos de trabalho. O aplicativo é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. As listas podem ser criadas do zero, de modelos predefinidos ou importando dados do Excel.

As equipes de saúde podem usar o modelo Patients para começar. Elas podem criar listas para acompanhar as necessidades e o status dos pacientes. Os dados existentes de pacientes em planilhas do Excel podem ser trazidos para criar uma lista no Teams. Essas listas podem ser usadas para cenários como rondas e monitoramento de pacientes para coordenar o cuidado.

Por exemplo, um enfermeiro chefe cria uma lista de pacientes em uma equipe que inclui todos os membros da equipe de saúde. Durante as rondas, a equipe de saúde acessa o Teams em seus dispositivos móveis e atualiza as informações do paciente na lista, o que todos na equipe podem visualizar para se manterem em sincronia. Nas sessões de ronda em que a equipe de saúde se reúne para discutir e avaliar as principais métricas de desempenho de saúde para garantir que um paciente esteja na direção certa para receber alta, ela pode compartilhar estas informações usando o Teams em uma tela de exibição grande. os membros de equipe de saúde que não estão no local podem ingressar remotamente.

Esta é uma lista de exemplo que foi organizada para rondas de pacientes.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Captura de tela da lista de exemplo para rondas de pacientes":::

Para saber mais, confira [Gerenciar o aplicativo Listas para sua organização no Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Acompanhar e monitorar tarefas com o aplicativo Tarefas

Utilize o [Tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) no Teams para acompanhar os itens pendentes para toda a sua equipe de saúde. Sua equipe de saúde pode criar, atribuir e agendar tarefas, categorizá-las e atualizar o status a qualquer momento, de qualquer dispositivo executando o Teams.

Para saber mais, confira [Gerenciar o aplicativo Tasks para sua organização no Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplificar as aprovações com o aplicativo Aprovações

Utilizar [Aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) para simplificar todas as suas solicitações e processos com sua equipe. Criar, gerenciar e compartilhar aprovações diretamente do seu hub para trabalho em equipe. Iniciar um fluxo de aprovação do mesmo local que você enviar um chat, em uma conversa de canal ou do próprio aplicativo Aprovações. Basta selecionar um tipo de aprovação, adicionar detalhes, anexar arquivos e escolher aprovadores. Depois que for enviado, os aprovadores são notificados e podem analisar e atuar na solicitação.

Você pode permitir o aplicativo Aprovações na sua organização e adicioná-lo às suas equipes. Para saber mais, confira [Disponibilidade do aplicativo Aprovações do Teams](../../approval-admin.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Criar, gerenciar e compartilhar agendas com a integração do aplicativo Turnos e do Trabalhador na Linha de Frente

O Microsoft Teams é integrado com o aplicativo Turnos e Trabalhador na Linha de Frente, que pode ser usado para coordenar os recursos de pessoal de turnos e muito mais. Por exemplo, no Turnos, os gerentes de enfermagem podem definir e coordenar agendas para a equipe e os enfermeiros podem verificar agendas e alternar turnos. O Teams inclui uma política interna de configuração de aplicativo de Trabalhador na Linha de Frente que você pode atribuir aos trabalhadores na linha de frente em sua organização. Por padrão, a política inclui os aplicativos Atividade, Turnos, Chat e Chamada. Esta política controla o comportamento desses aplicativos, por exemplo, fixando o aplicativo Turnos à barra de aplicativos para que a equipe possa acessá-lo rapidamente.

Para saber mais, confira [Gerenciar o aplicativo Turnos para sua organização no Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Ajudar os funcionários de saúde e operadores de informações a começar a usar o Teams.

Existem muitos recursos disponíveis para ajudar todos os usuários em sua organização a se familiarizarem com o Teams:

- Visite o [centro de adoção do Teams](https://adoption.microsoft.com/microsoft-teams/) para obter conselhos sobre como implantar o Teams se você acabou de iniciar a jornada da sua organização com o Teams, ou para expandir o Teams para mais áreas da sua organização.
- Considere definir [caminhos de aprendizado](https://adoption.microsoft.com/microsoft-365-learning-pathways/) para seus usuários para abordar somente as tarefas que eles precisam fazer.
- Obtenha ajuda e treinamento para seus usuários saberem como realizar tarefas básicas no Microsoft Teams no [site de suporte do Teams](https://support.microsoft.com/teams), incluindo [vídeos de treinamento rápidos](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Este site também possui ajuda e treinamento para os aplicativos do Teams, incluindo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Tarefas](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Aprovações](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) e [Turnos](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).