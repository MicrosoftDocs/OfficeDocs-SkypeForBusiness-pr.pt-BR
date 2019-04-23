---
title: Editar configurações de usuários do Microsoft Teams em massa
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar as configurações de usuário do Microsoft Teams em massa no Centro de administração do Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988969"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Editar configurações de usuário do Microsoft Teams em massa

Como um administrador, você gerenciar configurações de usuário de equipes no Centro de administração do Microsoft Teams. Na página **usuários** , você pode exibir informações como a conta e detalhes de licenciamento e editar a política e outras configurações. Você pode editar as configurações para usuários individualmente ou para vários usuários ao mesmo tempo.

## <a name="edit-user-settings-in-bulk"></a>Editar configurações de usuário em massa

Use o Centro de administração do Microsoft Teams para editar as configurações para vários usuários ao mesmo tempo. É recomendável editando configurações para 20 usuários ao mesmo tempo. Para editar configurações de um grande número de usuários, use o PowerShell. Para obter mais informações, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, selecione **os usuários**.
2. Pesquise os usuários que você deseja editar ou filtrar a exibição para mostrar os usuários que deseja editar.
3. No **& #x 2713;** coluna (marca de seleção), selecione os usuários, seguindo um destes procedimentos:
    - Selecione usuários um por vez. Um **& #x 2713;** será exibido ao lado de cada usuário que você selecionar. Se você selecionar mais de 20 usuários, você não serão bloqueados, mas tenha em mente que mais usuários que você selecionar, a operação levará mais para ser concluída.

        ![Captura de tela da página usuários mostrando a seleção do usuário](media/bulk-edit-user-settings-select-users.png)

    - Clique no & #x 2713; (marca de seleção) na parte superior da tabela para selecionar todos os usuários (até um máximo de 20 usuários) e clique em **continuar Selecionar tudo** para concluir a seleção na caixa de diálogo **seleção limitar** .

        ![Captura de tela da página usuários, mostrando o limite de seleção](media/bulk-edit-user-settings-select-all-limit.png) <br> Um **& #x 2713;** será exibido ao lado dos usuários selecionados.

        ![Captura de tela da página usuários, mostrando 20 usuários selecionados](media/bulk-edit-user-settings-select-all.png)
4. Clique em **Editar configurações**, faça as alterações desejadas e clique em **Salvar**.

    ![Captura de tela do painel Editar configurações](media/bulk-edit-user-settings-edit-settings.png)
