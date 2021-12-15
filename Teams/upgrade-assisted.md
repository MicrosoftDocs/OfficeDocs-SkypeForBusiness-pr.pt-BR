---
title: Atualizações assistidas | Skype Business Online para Teams Atualização
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Visão geral das atualizações assistidas do Skype for Business Online para Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44ca04f9fce23876c7ee782ef5cc5078da7e67c4
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513462"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações assistidas do Skype for Business Online para Microsoft Teams

A Microsoft oferece atualizações assistidas para Teams ajudar as organizações a fazer uma transição bem-sucedida do Skype for Business Online à medida que o serviço se retira em 31 de julho de 2021. Se sua organização está atualizando de um *Skype for Business Online* ou *Skype for Business Online* com híbrido (usuários no Skype for Business **Online** e Skype for Business Server ) ambiente, atualizações assistidas reduzem o número de tarefas técnicas que você precisa fazer e permitem maior foco na preparação organizacional, no reconhecimento do usuário e Teams treinamento.

Recomendamos que você revise nossas [diretrizes de atualização antes](https://aka.ms/SkypeToTeams) da atualização. Nossas diretrizes de atualização incluem atividades recomendadas e recursos úteis para concluir uma atualização do Skype for Business Online para Teams. Essa orientação se aplica a qualquer organização que planeja uma atualização para Teams, quer gerencie todos os aspectos da atualização ou use o processo assistido.

> [!NOTE]
> Se você estiver agendado para uma atualização assistida para Teams, você pode executar sua própria atualização do Skype for Business Online antes da data de atualização agendada. Para obter mais informações sobre como atualizar manualmente para Teams, consulte nossas [diretrizes de atualização.](https://aka.ms/SkypeToTeams)
>
> As atualizações assistidas não estão disponíveis para implantações locais de Skype for Business Server.

## <a name="notifications-for-scheduled-customers"></a>Notificações para clientes agendados

Skype for Business online agendados para atualizações assistidas para Teams receberão uma série de notificações de atualização. Essas notificações começarão 30 dias antes da data de atualização agendada. Essas notificações serão entregues como Plan *for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.

As notificações de atualização incluirão a data agendada da atualização assistida e vinculam-se aos recursos de atualização e treinamento para ajudar a impulsionar a adoção e o uso de Teams.

## <a name="the-assisted-upgrade-experience"></a>A experiência de atualização assistida

As atualizações assistidas começarão em agosto de 2021 com datas específicas do locatário compartilhadas nas notificações de agendamento mencionadas acima.

Sua experiência de atualização assistida será ligeiramente diferente, dependendo se você tem um Skype for Business somente online ou um Skype for Business Online com ambiente híbrido:

- **Skype for Business somente online O** processo de atualização assistida aplicará a `TeamsUpgradeOverridePolicy` política à sua organização. Quando essa política for aplicada, todos os usuários Skype for Business Online serão colocados no modo Somente Teams.
- **Skype for Business Online com ambientes** híbridos híbridos podem ter usuários que se enquadram em uma das seguintes categorias:

  - Usuários locais em casa no Skype for Business Server
  - Skype for Business online que estão no modo Somente Teams
  - Skype for Business usuários online que **não estão** no Teams modo Somente

  Se você tiver uma mistura de usuários em cada uma das categorias listadas acima, o processo de atualização assistida só alterna o Skype for Business Online para o modo Somente Teams se eles ainda não estão nesse modo. Os usuários locais Skype for Business não serão afetados pelo processo de atualização assistida.

> [!NOTE]
> Não se preocupe se a atualização assistida estiver agendada para uma data após 31 de julho de 2021. Sua organização poderá usar o Skype for Business Online até que sua atualização seja concluída.

A duração da atualização varia de acordo com o volume de usuários e as características da implantação. Na maioria dos casos, os usuários dentro de um locatário serão atualizados dentro de 24 horas após o início da atualização. Durante esse tempo, os usuários finais ainda terão acesso à funcionalidade Skype for Business Online. Depois que a atualização for concluída e os usuários sairem do Skype for Business Online, eles começarão a usar o Teams para mensagens, reuniões e chamada.

## <a name="the-post-upgrade-experience"></a>A experiência pós-atualização

Quando a atualização assistida é concluída, o Modo de **Coexistência** para usuários atualizados é definido como somente Teams. Recomendamos que você revise [Teams considerações de modo Somente](teams-only-mode-considerations.md) antes da atualização. A tabela a seguir fornece uma visão geral de alto nível da experiência Teams usuário somente.

:::row:::
    :::column span="1":::
        **Chat e Chamada**
    :::column-end:::
    :::column span="3":::
        - Todas as chamadas e chats são iniciados e recebidos Teams
        - Os usuários podem se comunicar (chat/chamada) com qualquer Skype for Business usuário
        - As organizações podem permitir que Teams usuários se comuniquem com usuários do serviço Skype consumidor gerenciando [permissões de](manage-external-access.md) acesso externo
        - Teams usuários que tentam entrar no Skype for Business Online são redirecionados para Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Reuniões**
    :::column-end:::
    :::column span="3":::
        - Os usuários agendam todas as novas reuniões Teams (plug-in substituído)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Dados Migrados**
    :::column-end:::
    :::column span="3":::
        - Contatos existentes do Skype for Business Online, incluindo federados (mas sem listas de distribuição)
        - Os contatos são migrados quando os usuários fazem logoff Teams pela primeira vez.
            > [!IMPORTANT]
            >Os contatos devem ser migrados dentro de 90 dias após a conclusão da atualização.
        - As reuniões Skype for Business Online existentes são convertidas em Teams reuniões
            > [!IMPORTANT]
            > Os clientes com configurações Skype for Business Online precisam usar o Serviço de Migração de Reunião (MMS) para migrar reuniões existentes do Skype for Business Online para reuniões Teams reuniões. Recomendamos usar MMS antes da data de atualização assistida. Para obter mais informações sobre MMS, consulte [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
    :::column-end:::
:::row-end:::

Se você tiver uma implantação Skype for Business Server híbrida e atualizar para Teams, poderá mover os usuários entre Skype for Business Server e Teams após a conclusão da atualização.

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)
