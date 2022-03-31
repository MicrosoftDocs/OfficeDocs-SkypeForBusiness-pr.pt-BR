---
title: Visitas virtuais com Microsoft Teams e o Bookings app
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Saiba como agendar, gerenciar e conduzir Visitas Virtuais usando o aplicativo Bookings em Teams.
ms.openlocfilehash: 0db414765a649192d96122ac69764fa279a8dac5
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556532"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuais com o Microsoft Teams e o aplicativo Bookings

## <a name="overview"></a>Visão geral

O [Bookings no Microsoft Teams](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) oferece às organizações uma maneira simples de agendar e gerenciar compromissos virtuais para funcionários e participantes. Use-o para agendar compromissos como consultas de saúde, consultas financeiras, entrevistas, suporte ao cliente, conexões virtuais e consultas, horário de expediente educacional e muito mais.

O Bookings aplicativo facilita o gerenciamento de demandas complexas de agendamento de qualquer organização. Os agendadores podem gerenciar vários calendários de departamentos e de funcionários, assim como comunicações com os participantes internos e externos em uma única experiência.

Os compromissos virtuais são realizados Microsoft Teams reuniões, que oferecem recursos robustos de videoconferência. Por exemplo, um médico pode compartilhar a tela e revisar os resultados do teste com um paciente. Ou, um consultor bancário pode solicitar assinaturas eletrônicas em documentos, permitindo que eles fechem transações remotamente.

Cada compromisso virtual inclui um link Teams de reunião que é enviado aos participantes por email, onde eles podem ingressar facilmente em um navegador da Web ou Teams em qualquer dispositivo. Lembretes de email automatizados ajudam a reduzir os não-shows e melhorar o envolvimento do cliente e do cliente.

Com Bookings, você tem uma experiência adaptada ao seu setor. Aqui estão alguns exemplos de como você pode usá-lo em sua organização:

|Setor | Exemplos |
|---------|---------|
|Serviços financeiros    |  Visitas virtuais para vendas remotas e serviço<br/>Agende e gerencie compromissos para gerentes de relação bancária, consultores financeiros e ajustadores de declarações, apenas para nomear alguns, para atender seus clientes com maior eficiência e conveniência.  |
|Varejo   | Conexões virtuais e consultas <br/>Agende e gerencie compromissos para seus associados de vendas, especialistas em produtos e consultores de design para conduzir conexões virtuais e consultas com clientes.   |
|Assistência médica   |  Visitas virtuais para atendimento ao paciente <br/>Agende e gerencie compromissos para os membros da equipe de assistência médica se reunirem com os pacientes ou outros provedores de saúde para discutir os cuidados médicos.   |

Este artigo fornece uma visão geral de como agendar, gerenciar e conduzir Visitas Virtuais usando o aplicativo Bookings no Teams.

## <a name="before-you-get-started"></a>Antes de começar

Se você for um administrador, consulte [Manage the Bookings app in Teams](../bookings-app-admin.md) to learn about the prerequisites for using the Bookings app in Teams, how to control access to Bookings in your organization, and recommended policy and admin settings.

Lembre-se de que somente agendadores em sua organização precisam ter o aplicativo Bookings instalado em Teams. A equipe que conduz ou participa de compromissos virtuais não precisa do aplicativo. Eles ins juntam compromissos Teams ou Outlook calendário ou usando o link de reunião no email de confirmação de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar um novo calendário de reserva

### <a name="create-the-booking-calendar"></a>Criar o calendário de reserva

Em Teams, **vá para Bookings** >  **Introdução** e selecione **Novo calendário de reserva**. Preencha o formulário e certifique-se de escolher o tipo de negócios relevante para sua organização.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de tela da nova tela de calendário de reserva mostrando tipos de negócios":::

Se você for uma organização maior, considere criar mais de um calendário de reserva se quiser que os participantes recebam um email de reserva de um departamento específico, em vez de sua organização geral.
Para saber mais, consulte [Create a Bookings calendar](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Se essa não for sua primeira vez no aplicativo Bookings ou se você quiser trabalhar em um calendário de reserva existente, em Bookings, selecione a seta listada ao lado do nome da sua organização e escolha **Calendário** de reserva existente. A partir daqui, você pode pesquisar o que deseja.

### <a name="add-staff"></a>Adicionar equipe

No calendário de reserva, vá para **Mais opções** (...) > **Configurações** e selecione **Staff**. Adicione membros da equipe e atribua uma função a cada pessoa que você adicionar. Você pode adicionar até 100 membros da equipe a um calendário de reserva.

O Bookings se integra ao Outlook. Depois de adicionar funcionários, você poderá exibir a disponibilidade do calendário dessa pessoa e agendar reservas para elas. Para saber mais, confira [Adicionar equipe e exibir um Bookings calendário](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Criar tipos de compromisso

Crie tipos de compromisso específicos para representar os serviços oferecidos pela sua organização e adaptar a experiência de reserva. Os agendadores podem usar o tipo de compromisso para agendar uma visita.

No calendário de reserva, vá para **Mais opções** (...) > **Configurações**, selecione **Tipos** de compromisso e selecione **Adicionar tipo de compromisso**. Insira um nomepara&mdash; exemplo, Abertura de conta, renovação de receita, consulta de empréstimo,&mdash; preparação de imposto e quaisquer outras informações e configurações que você deseja.

As informações que você adicionar estão incluídas na confirmação de email enviada aos participantes sempre que esse tipo de compromisso é reservado. Você pode definir lembretes de email e outras opções, como se os participantes podem ingressar em um navegador [móvel](mobile-browser-join.md) sem precisar baixar Teams.

Se você for um administrador Bookings, poderá vincular até quatro formulários para que os participantes preencham cada vez que esse tipo de compromisso for reservado. Por exemplo, você pode exigir que os participantes concluam um formulário de registro antes de ingressarem em uma visita. Para vincular um formulário, escolha **Vincular um formulário**. Insira a URL do formulário e escolha **Link**. (Se essa for a primeira vez que você estiver vinculando um formulário, você será solicitado a criar um grupo Microsoft 365 para armazenar formulários. Escolha **Criar grupo** para criar o grupo. Você só precisa fazer isso uma vez para o calendário de reserva.)

Ao trabalhar com formulários, lembre-se de que:

- Para fazer alterações em um formulário que já esteja vinculado a um tipo de compromisso, selecione o formulário no tipo de compromisso ou no grupo Microsoft 365 em [https://forms.office.com](https://forms.office.com).
- O carregamento de arquivos em formulários que contêm uma pergunta de [carregamento](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) de arquivo é suportado quando todos os participantes são da mesma organização.

Quando um agendador usa o tipo de compromisso para agendar uma visita, ele pode optar por incluir o formulário, removê-lo ou adicionar quaisquer outros formulários vinculados ao tipo de compromisso. Os participantes devem preencher o formulário antes de ingressar na visita.

Para saber mais, confira [Criar um tipo de compromisso](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>Agendar uma visita

No calendário de reserva, selecione **Novo reserva**. Selecione um tipo de compromisso e preencha as informações relevantes.

Isso inclui informações de contato do participante, o membro da equipe que fornecerá o serviço, observações internas que somente a equipe pode ver, lembretes de email e se o participante pode ingressar em um navegador móvel. Se um formulário estiver vinculado ao tipo de compromisso, você poderá optar por incluí-lo, removê-lo ou adicionar quaisquer outros formulários vinculados.

A confirmação de email enviada ao participante inclui o link de reunião e um anexo para que eles possam adicionar o compromisso virtual ao calendário. A equipe também recebe uma confirmação de email e um convite de reunião. Se um formulário foi incluído no compromisso, os Bookings e agendadores poderão ver se o formulário foi concluído pelo participante antes da visita e podem exibir a resposta do participante.

Para saber mais, confira [Agendar uma reserva no Teams Bookings app](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-a-visit"></a>Conduzir uma visita

Em seu Teams ou Outlook calendário, vá para a reserva e selecione **Ingressar** ou o link Teams reunião. Verifique suas configurações de áudio e vídeo e selecione **Ingressar agora**. Para saber mais, consulte [Conduct a Bookings appointment](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>Monitorar visitas e obter atualizações de status em tempo real

A [exibição de](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) fila no Bookings fornece à sua equipe um painel para monitorar todos os compromissos virtuais do dia, com atualizações em tempo real. Para ver a fila, vá para a guia **Fila** no Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Captura de tela do exibição de fila no aplicativo Bookings no Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Na fila, os agendadores podem adicionar uma nova reserva, exibir detalhes relevantes do compromisso e ver os status do compromisso ao longo do dia. Quando um paciente entra na sala de espera, o status muda e o tempo de espera é exibido e rastreado. O modo de exibição é atualizado automaticamente com atualizações codificadas por cores para que as alterações possam ser facilmente identificadas.

A equipe pode até mesmo ingressar e gerenciar compromissos diretamente da fila.

> [!NOTE]
> Atualmente, o aplicativo Bookings dá suporte à adição de até 100 funcionários por calendário de reserva. Se você usou Graph APIs para configurar e adicionar funcionários a um calendário de reserva, esse limite pode não ser imposto. Nesse cenário, a guia **Fila** não poderá renderizar conteúdo para calendários com mais de 100 funcionários. Para uma experiência ideal, recomendamos que você adicione não mais de 100 funcionários a um calendário de reserva. Estamos trabalhando para resolver essa limitação em versões futuras.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Recursos adicionais com o Bookings web

O Bookings web oferece recursos adicionais. Por exemplo, você pode publicar uma página de reserva online de autoatend pois as pessoas podem agendar compromissos com sua equipe. Para acessar o Bookings web, acesse **Mais** opções (...) > **abrir Bookings web**.

Para saber mais, confira [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-visits-usage"></a>Obter informações sobre o uso de Visitas Virtuais

O [relatório de uso de](../teams-analytics-and-reports/virtual-visits-usage-report.md) Visitas Virtuais no centro de administração Microsoft Teams oferece aos administradores uma visão geral Teams atividade de Visitas Virtuais em sua organização. O relatório mostra análises detalhadas para compromissos virtuais, incluindo Bookings visitas.

Você pode exibir as principais métricas, como tempo de espera do lobby e duração da visita. Use essas informações para obter informações sobre tendências de uso para ajudá-lo a otimizar as Visitas Virtuais para oferecer melhores resultados comerciais.

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar a experiência de junção para Teams virtuais em navegadores móveis](mobile-browser-join.md)

- [Teams relatório de uso de Visitas Virtuais](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Introdução com Teams para organizações de saúde](healthcare/teams-in-hc.md)

- [Bookings app na documentação Teams ajuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
