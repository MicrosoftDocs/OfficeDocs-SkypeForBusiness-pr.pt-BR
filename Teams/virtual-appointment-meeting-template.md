---
title: Modelo de reunião de compromisso virtual no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: Saiba como gerenciar o modelo de reunião de compromisso virtual para usuários do Teams em sua organização.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0d93bb05a6456499ab1c0c16070149d8cdfd949
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767622"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Modelo de reunião de compromisso virtual no Microsoft Teams

![Ícone](media/info.png) de informações **Alguns recursos descritos neste artigo exigem [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versão prévia)**.

## <a name="overview"></a>Visão geral

O modelo de compromisso virtual é um modelo de reunião padrão no Microsoft Teams que seus usuários podem usar para agendar compromissos virtuais com clientes, clientes e outras pessoas fora de sua organização. Por exemplo, use-o para agendar e realizar entrevistas, sessões de mentoria, consultas financeiras, experiências de compras virtuais e muito mais.

O modelo permite especificar valores para configurações de reunião que os organizadores da reunião normalmente controlam. Ele oferece flexibilidade para aplicar configurações padrão e impor configurações. Você pode optar por bloquear as configurações para que os organizadores da reunião não possam alterá-las quando usarem o modelo.

Com esse modelo, você pode habilitar uma experiência consistente em toda a sua organização para compromissos virtuais agendados no Teams e ajudar a impor requisitos de conformidade.

Este artigo fornece uma visão geral de como exibir e gerenciar o modelo de reunião de compromisso virtual no centro de administração do Teams.

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>Exibir ou alterar configurações de modelo de reunião de compromisso virtual

1. Na navegação à esquerda do centro de administração do Teams, acesse **Modelos de Reunião** de **Reuniões** > .
1. Escolha **Compromisso virtual** e selecione **Editar**.
1. Para fazer alterações, selecione uma opção e configure as configurações desejadas. Para cada opção, você pode definir as seguintes configurações:
    - **Valor padrão**: o valor aplicado ao compromisso virtual quando o modelo é usado.
    - **Visibilidade**: escolha **Ocultar** ou **Mostrar** para especificar se a opção está visível para os organizadores da reunião nas opções de reunião do Teams.
    - **Status de bloqueio**: para impedir que os organizadores da reunião alterem o valor definido, escolha **Bloquear**. Para permitir que os organizadores da reunião alterem o valor definido, escolha **Desbloquear**.
1. Examine suas alterações e escolha **Salvar**.

## <a name="manage-the-virtual-appointment-meeting-template"></a>Gerenciar o modelo de reunião de compromisso virtual

Você usa políticas de modelo de reunião no centro de administração do Teams para controlar quais modelos de reunião estão disponíveis para os usuários em sua organização. Por padrão, a política Global permite que os usuários vejam e usem todos os modelos de reunião, incluindo o modelo de compromisso virtual e todos os modelos personalizados que você criou.

Se você quiser disponibilizar o modelo de compromisso virtual para usuários ou grupos específicos de usuários em sua organização, você poderá criar uma política de modelo de reunião personalizada e atribuí-la a esses usuários ou grupos.

Para saber mais, confira [Gerenciar modelos de reunião no Teams](manage-meeting-templates.md).

## <a name="user-experience"></a>Experiência de usuário

Quando os usuários da sua organização usam o modelo de reunião para agendar um compromisso virtual, as pessoas fora da sua organização (convidados externos) recebem um convite de reunião personalizado que inclui um **compromisso de junção como um botão convidado** e outros detalhes de compromisso. Eles podem usar esse botão para ingressar facilmente em qualquer dispositivo sem precisar baixar e instalar o Teams.

Tenha em mente que algumas opções de reunião do Teams podem não se aplicar a convidados externos ou a qualquer pessoa que ingresse usando o **botão Ingressar como convidado** . Há suporte para as seguintes opções de reunião para ingressar no convidado:

- **Quem pode ignorar o lobby**: a configuração **Todos** permite que convidados externos ignorem o lobby.
- **Escolher co-organizadores**
- **Gravar automaticamente**
- **Permitir chat de reunião**: defina como **Desabilitado** se você quiser impedir o chat da reunião antes, durante e depois da reunião.

Pessoas dentro de sua organização recebem um convite de reunião e o compromisso aparece em seu calendário do Teams e do Outlook, em que eles podem ingressar facilmente como em qualquer outra reunião do Teams. Todas as opções de reunião do Teams se aplicam aos participantes que ingressarem usando o link de reunião do Teams no convite da reunião ou no calendário do Teams ou do Outlook.

Para saber mais sobre como usar o modelo de reunião de compromisso virtual e a experiência do usuário, consulte [Usar um modelo de reunião do Teams para criar um Compromisso Virtual](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral dos modelos de reunião personalizados no Teams](custom-meeting-templates-overview.md)
