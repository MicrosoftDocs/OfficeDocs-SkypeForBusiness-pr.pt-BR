---
title: 'Editar configurações em massa dos usuários do Microsoft Teams '
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como gerenciar as configurações de usuário do Microsoft Teams em massa no centro de administração do Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9585266ff2af124a1b9985c4cf18d842bc45af5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236776"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Editar as configurações de usuário do Microsoft Teams em massa

Como administrador, você gerencia as configurações de usuário do teams no centro de administração do Microsoft Teams. Na página **usuários** , você pode exibir informações como a conta e os detalhes de licenciamento e editar a política e outras configurações. Você pode editar as configurações de usuários individualmente ou para vários usuários ao mesmo tempo.

## <a name="edit-user-settings-in-bulk"></a>Editar configurações de usuário em massa

Use o centro de administração do Microsoft Teams para editar as configurações de vários usuários de uma vez. Recomendamos a edição de configurações para 20 usuários de cada vez. Para editar as configurações de um grande número de usuários, use o PowerShell. Para obter mais informações, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**.
2. Procure os usuários que você deseja editar ou filtrar o modo de exibição para mostrar os usuários que você deseja editar.
3. Na coluna **&#x2713;** (marca de seleção), selecione usuários seguindo um destes procedimentos:
    - Selecione um usuário de cada vez. Um **&#x2713;** é exibido ao lado de cada usuário que você selecionar. Se você selecionar mais de 20 usuários, não será possível bloquea-los, mas lembre-se de que quanto mais usuários você selecionar, mais demorado será a conclusão da operação.

        ![Captura de tela da página usuários mostrando seleção do usuário](media/bulk-edit-user-settings-select-users.png)

    - Clique na &#x2713; (marca de seleção) na parte superior da tabela para selecionar todos os usuários (até um máximo de 20 usuários) e, em seguida, na caixa de diálogo **limite de seleção** , clique em **continuar selecionar tudo** para concluir a seleção.

        ![Captura de tela da página usuários, mostrando o limite de seleção](media/bulk-edit-user-settings-select-all-limit.png) <br> Um **&#x2713;** é exibido ao lado dos usuários selecionados.

        ![Captura de tela da página usuários, mostrando 20 usuários selecionados](media/bulk-edit-user-settings-select-all.png)
4. Clique em **Editar configurações**, faça as alterações desejadas e clique em **salvar**.

    ![Captura de tela do painel Editar configurações](media/bulk-edit-user-settings-edit-settings.png)
