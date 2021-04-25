---
title: Atualizações assistidas | Atualização do Skype Business Online para o Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Visão geral das atualizações assistidas do Skype for Business Online para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995189"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações assistidas do Skype for Business Online para o Microsoft Teams

A Microsoft oferece atualizações assistidas para o Teams para ajudar as organizações a fazer uma transição bem-sucedida do Skype for Business Online à medida que o serviço se retira em 31 de julho de 2021. As atualizações assistidas reduzem o número de tarefas técnicas que você precisa fazer e permitem maior foco na preparação organizacional, no reconhecimento do usuário e no treinamento do Teams.

Recomendamos que você revise nossas [diretrizes de atualização antes](https://aka.ms/SkypeToTeams) da atualização. Nossas diretrizes de atualização incluem atividades recomendadas e recursos úteis para concluir uma atualização do Skype for Business Online para o Teams. Essa orientação se aplica a qualquer organização que planeja uma atualização para o Teams, quer gerencie todos os aspectos da atualização ou use o processo assistido.

> [!NOTE]
> Se você estiver agendado para uma atualização assistida para o Teams, poderá executar sua própria atualização do Skype for Business Online antes da data de atualização agendada. Para obter mais informações sobre como atualizar manualmente para o Teams, consulte nossas [diretrizes de atualização.](https://aka.ms/SkypeToTeams)
>
> A atualização assistida não está disponível para implantações locais do Skype for Business Server.

## <a name="notifications-for-scheduled-customers"></a>Notificações para clientes agendados

Os clientes do Skype for Business Online agendados para atualizações assistidas para o Teams receberão uma série de notificações de atualização. Essas notificações começarão 90 dias antes da data de atualização agendada. Essas notificações serão entregues como Planos de Alterações postagens no Centro de Mensagens do Microsoft 365, notificações de painel de atualização no centro de administração do Teams e sinalizadores no aplicativo para usuários finais. 

As notificações de atualização incluirão a data agendada da atualização assistida e vinculam-se aos recursos de atualização e treinamento para ajudar a impulsionar a adoção e o uso do Teams.

## <a name="the-assisted-upgrade-experience"></a>A experiência de atualização assistida

As atualizações assistidas começarão em agosto de 2021 com datas específicas do locatário compartilhadas nas notificações de agendamento mencionadas acima.

A duração da atualização varia de acordo com o volume de usuários e as características da implantação. No entanto, na maioria dos casos, os usuários dentro de um locatário serão atualizados dentro de 24 horas após o início da atualização. Durante esse tempo, os usuários finais ainda terão acesso à funcionalidade do Skype for Business Online. Depois que a atualização for concluída e os usuários sairem do Skype for Business Online, eles começarão a usar o Teams para mensagens, reuniões e chamadas.

## <a name="the-post-upgrade-experience"></a>A experiência pós-atualização

Quando a atualização assistida é concluída, o Modo de **Coexistência** para usuários atualizados é definido como Somente equipe e só pode ser alterado para um modo de coexistência diferente pela Microsoft. Recomendamos que você revise as [considerações do](teams-only-mode-considerations.md) modo Somente do Teams antes da atualização. A tabela a seguir fornece uma visão geral de alto nível da experiência do usuário Somente do Teams.

:::row:::
    :::column span="1":::
        **Chat e Chamada**
    :::column-end:::
    :::column span="3":::
        - Todas as chamadas e chats são iniciados e recebidos no Teams
        - Os usuários podem se comunicar (chat/chamada) com qualquer usuário do Skype for Business
        - As organizações podem permitir que os usuários do Teams se comuniquem com usuários do serviço de consumidor skype gerenciando [permissões de acesso externo](manage-external-access.md)
        - Os usuários do Teams que tentarem entrar no Skype for Business Online serão redirecionados para o Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Reuniões**
    :::column-end:::
    :::column span="3":::
        - Os usuários agendam todas as novas reuniões no Teams (plug-in substituído)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **Dados Migrados**
    :::column-end:::
    :::column span="3":::
        - Contatos existentes do Skype for Business Online, incluindo federados (mas sem listas de distribuição
        - Reuniões existentes do Skype for Business Online são convertidas em reuniões do Teams
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)
