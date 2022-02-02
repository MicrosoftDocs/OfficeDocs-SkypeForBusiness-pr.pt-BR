---
title: Visitas virtuais com o Microsoft Teams e o aplicativo Bookings
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
description: Saiba como usar o aplicativo Bookings em Teams agendar, gerenciar e conduzir visitas virtuais.
ms.openlocfilehash: ae74a4195bc8aa0deeca81221e70fe28890938ec
ms.sourcegitcommit: fd4d7557997c537c094e79ada21c569acde65aa6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "62312344"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuais com o Microsoft Teams e o aplicativo Bookings

## <a name="overview"></a>Visão Geral

O [aplicativo Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) no Microsoft Teams oferece às organizações uma maneira simples de agendar e gerenciar compromissos virtuais para funcionários e participantes. Use-o para agendar compromissos virtuais, como consultas de saúde, consultas financeiras, entrevistas, suporte ao cliente, conexões virtuais e consultas, horário de expediente educacional e muito mais.

O aplicativo Bookings facilita o gerenciamento de demandas complexas de agendamento de qualquer organização. Os agendadores podem gerenciar vários calendários de departamentos e de funcionários, assim como comunicações com os participantes internos e externos em uma única experiência.

As visitas virtuais são realizadas Microsoft Teams reuniões, que oferecem recursos robustos de videoconferência. Por exemplo, um médico pode compartilhar a tela e revisar os resultados do teste com um paciente. Ou, um consultor bancário pode solicitar assinaturas eletrônicas em documentos, permitindo que eles fechem transações remotamente.

Cada compromisso virtual inclui um link Teams de reunião que é enviado aos participantes no email onde eles podem ingressar facilmente em um navegador da Web ou em Teams em qualquer dispositivo. Lembretes de email automatizados ajudam a reduzir os não-shows e melhorar o envolvimento do cliente e do cliente.

Com o Bookings, você tem uma experiência adaptada ao seu setor. Aqui estão alguns exemplos de como você pode usá-lo em sua organização:

|Setor | Exemplos |
|---------|---------|
|Serviços financeiros    |  Visitas virtuais para vendas remotas e serviço<br/>Agende e gerencie compromissos virtuais para gerentes de relações bancárias, consultores financeiros e ajustadores de declarações, apenas para nomear alguns, para atender seus clientes com maior eficiência e conveniência.  |
|Assistência médica   |  Visitas virtuais para atendimento ao paciente <br/>Agende e gerencie visitas virtuais para que os membros da equipe de assistência médica se reunirem com os pacientes ou outros provedores de saúde para discutir os cuidados médicos.   |
|Varejo   | Conexões virtuais e consultas <br/>Agende e gerencie compromissos para seus associados de vendas, especialistas em produtos e consultores de design para conduzir conexões virtuais e consultas com clientes.   |

Este artigo fornece uma visão geral de como usar o aplicativo Bookings Teams agendar, gerenciar e conduzir visitas virtuais.

## <a name="before-you-get-started"></a>Antes de começar

Se você for um administrador, consulte Gerenciar o aplicativo [Bookings no Teams](../bookings-app-admin.md) para saber mais sobre os pré-requisitos para usar o aplicativo Bookings no Teams, como controlar o acesso ao Bookings em sua organização e as configurações de política e administrador recomendadas.

Lembre-se de que apenas agendadores em sua organização precisam ter o aplicativo Bookings instalado Teams. A equipe que conduz ou participa de compromissos virtuais não precisa do aplicativo. Eles ins juntam compromissos de seu calendário Teams ou Outlook ou usando o link de reunião em seu email de confirmação de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar um novo calendário de reserva

### <a name="create-the-booking-calendar"></a>Criar o calendário de reserva

Em Teams, vá para **BookingsGet** >  **started** e selecione **Novo calendário de reserva**. Preencha o formulário e certifique-se de escolher o tipo de negócios relevante para sua organização.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de tela da nova tela de calendário de reserva mostrando tipos de negócios":::

Se você for uma organização maior, considere criar mais de um calendário de reserva se quiser que os participantes recebam um email de reserva de um departamento específico, em vez de sua organização geral.
Para saber mais, confira [Criar um calendário do Bookings](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Se essa não for sua primeira vez no aplicativo Bookings ou se você quiser trabalhar em um calendário de reserva existente, no Bookings, selecione a seta listada ao lado do nome da sua organização e escolha **Calendário** de reserva existente. A partir daqui, você pode pesquisar o que deseja.

### <a name="add-staff"></a>Adicionar equipe

No calendário de reserva, acesse **Mais opções** (...) > **Configurações** e selecione **Staff**. Adicione membros da equipe e atribua uma função a cada pessoa que você adicionar. Você pode adicionar até 100 membros da equipe a um calendário de reserva.

O aplicativo Bookings se integra ao Outlook. Depois de adicionar funcionários, você poderá exibir a disponibilidade do calendário dessa pessoa e agendar reservas para elas. Para saber mais, confira [Adicionar equipe e exibir um calendário do Bookings](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Criar tipos de compromisso

Crie tipos de compromisso específicos para representar os serviços oferecidos pela sua organização e adaptar a experiência de reserva.

No calendário de reserva, vá para **Mais opções** (...) > **Tipos** de compromisso e selecione **Novo tipo de compromisso**. Insira um nomepara&mdash; exemplo, Abertura de conta, renovação de receita, consulta de empréstimo,&mdash; preparação de imposto e quaisquer outras informações e configurações que você deseja.

As informações e links que você adiciona estão incluídos na confirmação de email enviada aos participantes sempre que esse tipo de compromisso é reservado. Você pode até definir lembretes de email e outras opções, como se os participantes podem [](mobile-browser-join.md) ingressar em um navegador móvel sem precisar baixar Teams. Para saber mais, confira [Criar um tipo de compromisso](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-virtual-visit"></a>Agendar uma visita virtual

No calendário de reserva, selecione **Novo reserva**. Selecione um tipo de compromisso e preencha as informações relevantes.

Isso inclui informações de contato do participante, o membro da equipe que fornecerá o serviço, observações internas que somente a equipe pode ver, lembretes de email e se o participante pode ingressar em um navegador móvel. Para saber mais, confira [Agendar uma reserva no aplicativo Teams Bookings](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

A confirmação de email enviada ao participante inclui o link de reunião e um anexo para que eles possam adicionar o compromisso virtual ao calendário. A equipe também recebe uma confirmação de email e um convite de reunião.

## <a name="conduct-a-virtual-visit"></a>Conduzir uma visita virtual

Em seu Teams ou Outlook calendário, vá para a reserva e selecione **Ingressar** ou o link Teams reunião. Verifique suas configurações de áudio e vídeo e selecione **Ingressar agora**. Para saber mais, confira [Conduzir um compromisso do Bookings](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-virtual-visits-and-get-real-time-status-updates"></a>Monitorar visitas virtuais e obter atualizações de status em tempo real

A [exibição de](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) fila no Bookings fornece à sua equipe um painel para monitorar todos os compromissos virtuais do dia, com atualizações em tempo real. Para ver a fila, vá para a guia **Fila** no Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Captura de tela do exibição de fila no aplicativo Bookings em Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Na fila, os agendadores podem adicionar uma nova reserva, exibir detalhes relevantes do compromisso e ver os status do compromisso ao longo do dia. Quando um paciente entra na sala de espera, o status muda e o tempo de espera é exibido e rastreado. O modo de exibição é atualizado automaticamente com atualizações codificadas por cores para que as alterações possam ser facilmente identificadas.

A equipe pode até mesmo ingressar e gerenciar compromissos diretamente da fila.

> [!NOTE]
> Atualmente, o aplicativo Bookings dá suporte à adição de até 100 funcionários por calendário de reserva. Se você usou Graph APIs para configurar e adicionar funcionários a um calendário de reserva, esse limite pode não ser imposto. Nesse cenário, a guia **Fila** não poderá renderizar conteúdo para calendários com mais de 100 funcionários. Para uma experiência ideal, recomendamos que você adicione não mais de 100 funcionários a um calendário de reserva. Estamos trabalhando para resolver essa limitação em versões futuras.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Recursos adicionais com o aplicativo Web do Bookings

O aplicativo Web do Bookings oferece recursos adicionais. Por exemplo, você pode publicar uma página de reserva online de autoatend pois as pessoas podem agendar compromissos com sua equipe. Para acessar o aplicativo Web do Bookings, acesse **Mais opções** (...) > **aplicativo Web abrir Reservas**.

Para saber mais, confira [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar a experiência de junção para Teams virtuais em navegadores móveis](mobile-browser-join.md)

- [Começar a Teams para organizações de saúde](healthcare/teams-in-hc.md)

- [Aplicativo bookings na documentação Teams ajuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
