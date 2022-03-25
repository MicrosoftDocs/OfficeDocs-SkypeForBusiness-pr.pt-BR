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
ms.openlocfilehash: 8becd4a83bb544747fa59a823bae37461c3642c3
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783890"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Atualizações assistidas do Skype for Business Online para Microsoft Teams

A Microsoft Skype for Business online em 31 de julho de 2021.  A Microsoft está fornecendo um processo de atualização assistido para ajudar as organizações a mover os usuários restantes Skype for Business Online para Teams Somente.  As atualizações assistidas da Microsoft reduzem o número de tarefas técnicas e simplificam a transição para um mundo sem Skype for Business Online se sua organização está:
 - Uma organização online pura que precisa atualizar do *Skype for Business Online* para se tornar pura Teams Somente ou
 - Uma organização híbrida com usuários no *Skype for Business Online*  e em um ambiente de Skype for Business Server local, que precisa atualizar apenas os usuários do Skype for Business *Online* para Teams Somente.

Recomendamos que você revise nossas [diretrizes de atualização antes](https://aka.ms/SkypeToTeams) da atualização. Nossas diretrizes de atualização incluem atividades recomendadas e recursos úteis para concluir uma atualização do Skype for Business Online para Teams. Essa orientação se aplica a qualquer organização que planeja uma atualização para Teams, quer gerencie todos os aspectos da atualização ou use o processo assistido.

## <a name="the-assisted-upgrade-experience"></a>A experiência de atualização assistida
Os clientes do Skype for Business Online agendados para atualizações assistidas para o Teams receberão várias formas de *notificações: Planejar* postagens de alteração no Centro de Mensagens do Microsoft 365, atualizar notificações de painel no centro de administração do Teams e sinalizadores no aplicativo para usuários finais. A notificação de atualização no Centro de Mensagens e no centro de administração do Teams inclui a data agendada da atualização assistida, bem como um link para atualizar recursos e treinamento para ajudar a impulsionar a adoção e o uso de Teams.

A experiência de atualização assistida difere ligeiramente, dependendo se sua organização tem algum usuário em um ambiente Skype for Business Server local:
- **Organizações online puras** Para *organizações* sem qualquer Skype local para usuários do Busineess Server, `TeamsUpgradeOverridePolicy` o processo de atualização assistida aplica a política à sua organização. Quando essa política for aplicada, todos os usuários do Skype for Business Online serão colocados Teams modo Somente.
- **Organizações Híbridas com** usuários Skype for Business locais Isso inclui organizações com todos os usuários que estão no Skype for Business Server, independentemente de o Híbrido ter sido configurado. Essas organizações podem ter usuários que se enquadram em uma das seguintes categorias:

  - Usuários locais que estão em casa Skype for Business Server (que podem ou não usar Teams, mas não são Teams usuários somente)
  - Teams usuários que residiram no Skype for Business Online
  - Somente usuários Teams que estão em casa no Skype for Business Online

O processo de atualização assistida afetará apenas a última categoria de usuários: Somente usuários não Teams no Skype for Business Online serão atualizados para o modo Somente Teams. Usuários locais Skype for Business e usuários existentes do TeamsOnly não serão afetados pelo processo de atualização assistida.

> [!NOTE]
> Sua organização pode continuar a usar o Skype for Business Online até que sua atualização seja concluída. Se você estiver agendado para uma atualização assistida para Teams, você pode executar sua própria atualização do Skype for Business Online antes da data de atualização agendada. Para obter mais informações sobre como atualizar manualmente para Teams, consulte nossas [diretrizes de atualização](https://aka.ms/SkypeToTeams).

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
        - As organizações podem Teams que os usuários se comuniquem com os usuários do serviço Skype consumidor gerenciando [permissões de acesso externo](manage-external-access.md)
        - Teams usuários que tentam entrar no Skype for Business Online são redirecionados para Teams
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
        - Contatos existentes do Skype for Business Online incluindo federados (mas sem listas de distribuição)
        - Os contatos são migrados quando os usuários fazem logoff Teams pela primeira vez.
            > [!IMPORTANT]
            >Os contatos devem ser migrados dentro de 90 dias após a conclusão da atualização.
        - As reuniões Skype for Business Online existentes são convertidas em Teams reuniões
            > [!IMPORTANT]
            > Os clientes com configurações Skype for Business Online precisam usar o Serviço de Migração de Reunião (MMS) para migrar reuniões do Skype for Business Online existentes para reuniões Teams reuniões. Recomendamos usar MMS antes da data de atualização assistida. Para obter mais informações sobre MMS, consulte [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
    :::column-end:::
:::row-end:::

Se você tiver uma implantação Skype for Business Server híbrida e atualizar para Teams, poderá mover usuários entre Skype for Business Server e Teams após a conclusão da atualização.

## <a name="related-content"></a>Conteúdo relacionado

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Desativação do Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Considerações sobre o modo Teams Only (Apenas Teams)](teams-only-mode-considerations.md)
